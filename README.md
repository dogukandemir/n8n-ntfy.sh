# n8n-nodes-ntfy.sh

This is an n8n community node. It lets you use [ntfy.sh](https://ntfy.sh) in your n8n workflows.

[Installation](#installation)  
[Operations](#operations)  
[Compatibility](#compatibility)  
[Roadmap](#roadmap)  <!-- delete if not using this section -->  
[Resources](#resources)  

## Installation

Follow the [installation guide](https://docs.n8n.io/integrations/community-nodes/installation/) in the n8n community nodes documentation.

## Operations

Only a single operation is supported right now to send a notification.

### Supported Fields

- **Topic**: The ntfy.sh topic to send the notification to (required)
- **Message**: The notification message content (required)
- **Title**: Optional notification title
- **Priority**: Message priority (1-5, where 1=min, 3=default, 5=urgent)
- **Click URL**: URL to open when notification is clicked
- **Tags**: Comma-separated tags (can include emoji short codes)
- **Delay**: Schedule delivery for later (supports multiple formats):
  - Duration: `30m`, `2h`, `1 day`, `3 days`
  - Unix timestamp: `1639194738`
  - Natural language: `10am`, `8:30pm`, `tomorrow, 3pm`, `Tuesday, 7am`
  - Min delay: 10 seconds, Max delay: 3 days (Max delay can be configured with the message-delay-limit option)

### Additional Fields

- **Alternate ntfy.sh Server URL**: Use a custom ntfy.sh server
- **Authentication Token**: Bearer token for protected topics

![alt ntfy sample operation](https://github.com/raghavanand98/n8n-ntfy.sh/blob/master/sample.png?raw=true)

## Compatibility

Tested against 0.212.0.

## Roadmap

The broad roadmap is to support all parameters in the [ntfy API](https://docs.ntfy.sh/publish/#publish-as-json). Roughly the order of this will likely be:

- [X] Click
- [X] Delay (scheduled delivery)
- [ ] Actions
- [X] Custom ntfy.sh server support
- [ ] All other params
- [ ] Better validation of correctness and error messages
- [ ] QoL improvements: allow selecting from a list of emojis
- [ ] Improve the security model for the topic name since it's effectively a secret.
- [ ] Add documentation for local development
- [ ] Add tests
