---
description: >-
  Hook up widget events to stream automations. Change scenes when a panic is
  triggered, send a chat message when dispatch information updates, and more!
icon: diagram-sankey
---

# Stream Automations

Stream Automations connect live Sonoran CAD and Radio activity to actions in [Streamer.bot](https://streamer.bot/). A panic can switch an OBS scene, a radio transmission can play an animation, or a dispatch update can send a chat message without creating a separate integration.

{% hint style="info" %}
Stream Automations require the [Pro version of Sonoran Studio](pricing.md), the Sonoran Studio desktop app, and Streamer.bot running on the same computer.
{% endhint %}

## How it works

1. The Studio desktop app receives the same realtime CAD and Radio events used by your stream widgets.
2. Studio converts a supported event into a Stream Automation event.
3. If that event has a mapped Streamer.bot action, Studio invokes the action through Streamer.bot's local WebSocket server.
4. Studio includes the event name and any available unit, call, channel, location, priority, or panic data as action arguments.

An event mapped to **Do nothing** does not invoke Streamer.bot. Automations run locally, so both desktop applications must remain open.

## Set up Streamer.bot

### 1. Create an action

In Streamer.bot, create the action you want Studio to run. Add sub-actions such as changing an OBS scene, playing audio, showing a source, or sending a chat message. Make sure the action is enabled.

### 2. Start the WebSocket server

In Streamer.bot, open **Servers/Clients → WebSocket Server** and start the server. The defaults are:

| Setting | Default |
| --- | --- |
| Address | `127.0.0.1` |
| Port | `8080` |
| Endpoint | `/` |
| Authentication | Off |

Enable **Auto Start** if the server should start with Streamer.bot. If authentication is enabled and enforced, enter the same password in Sonoran Studio. See Streamer.bot's [WebSocket server configuration](https://docs.streamer.bot/api/websocket/guide/configuration) for more detail.

### 3. Connect Sonoran Studio

1. Open the Sonoran Studio desktop app and select **Bot**.
2. Enter the WebSocket **Port** and **Endpoint**. Enter the password only if Streamer.bot requires one.
3. Select **Save & connect**.
4. Confirm that Studio reports **Connected** and loads your enabled Streamer.bot actions.

Studio only connects to Streamer.bot on the local computer. The password and event mappings are stored locally.

### 4. Map and test events

Choose a Streamer.bot action beside each Sonoran event. Select **Test** to invoke that mapping immediately. A test supplies `sonoranEvent`, `test`, `occurredAt`, and the title `Sonoran Studio test`; live event-specific data appears only when the corresponding event actually occurs.

## Supported events

| Sonoran event | When it runs | Event value |
| --- | --- | --- |
| Radio starts | A radio transmission begins | `radio.started` |
| Radio ends | The active radio transmission finishes | `radio.ended` |
| Unit status | Your CAD unit receives a status update | `unit.status` |
| Call attached | You attach to a different CAD call | `call.attached` |
| Call changed | The active call updates, or you detach from it | `call.changed` |
| Call note | A dispatch notification is identified as a call note | `call.note` |
| Dispatch update | Any other CAD dispatch notification arrives | `dispatch.notification` |
| Panic starts | A panic visible to your Studio overlay activates | `panic.started` |
| Panic ends | That visible panic clears | `panic.ended` |

Channel-only changes do not currently invoke a separate automation event. Call updates use **Call changed**, and call-note notifications use **Call note**.

## Action arguments

Every live action receives these arguments:

| Argument | Description |
| --- | --- |
| `sonoranEvent` | The mapped event value shown above |
| `sonoranSourceEvent` | The original Studio event, such as `cad.panic.changed` |
| `eventId` | Unique ID for this realtime event |
| `occurredAt` | ISO timestamp recorded by Studio |

Studio also includes the following values when they are available for the event or current overlay state:

`communityId`, `serverId`, `unit`, `displayName`, `unitNumber`, `department`, `status`, `location`, `postal`, `callsign`, `channel`, `priority`, `callId`, `title`, and `message`.

Panic actions additionally receive:

| Argument | Value |
| --- | --- |
| `panicActive` | `true` for `panic.started`; `false` for `panic.ended` |
| `panicScope` | `self` when the panic belongs to the signed-in account; otherwise `community` |

Call actions can receive `callAttached`: `true` when a call attaches and `false` when it detaches.

Streamer.bot exposes action arguments to sub-actions with `%variable%` syntax. For example, use `%unitNumber%`, `%status%`, or `%sonoranEvent%` in a compatible text field. Open **Actions & Queues → Action History** after a live event to inspect the values supplied to that run.

{% hint style="warning" %}
Optional arguments are omitted when Studio does not have a value. Design actions so missing unit, call, or location data does not cause the automation to fail.
{% endhint %}

## Troubleshooting

### Studio does not connect

* Confirm Streamer.bot is running and its WebSocket server is started.
* Verify the port and endpoint match. The defaults are `8080` and `/`.
* If authentication is enabled, re-enter the matching password in Studio.
* Keep the server address on `127.0.0.1`; Studio intentionally connects only to the local computer.

### An action is missing

Studio loads enabled actions reported by Streamer.bot. Enable the action, then select **Reload actions** in Studio.

### A mapped action does not run

* Confirm Studio shows **Connected** and the event is not set to **Do nothing**.
* Use **Test** beside the mapping. If the test succeeds, wait for the real Sonoran event to inspect its full arguments.
* Check **Actions & Queues → Action History** in Streamer.bot for the action result and supplied arguments.
* The desktop app must be signed into the same Sonoran account and community that is producing the CAD or Radio activity.

## Advanced integrations

Local tools can list or invoke Streamer.bot actions and mapped Sonoran events through the Studio desktop API. See [Developer Documentation](developer-documentation.md#streamerbot-actions).

