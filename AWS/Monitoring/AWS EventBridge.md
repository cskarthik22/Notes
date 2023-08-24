# AWS EventBridge

#### Keypoints
- EventBridge is a region-scoped, managed event bus service that grants you the ability to evaluate those events and send those events to specific targets. It also gives you the ability to replay events. So the event bus, rather than being entirely transient, gives you the ability to persist those events for a short period of time. And when you create rules to evaluate those events, if there's a failure that goes beyond a specific threshold, you can forward those failed events to a dead-letter queue that is hosted in the SQS service.
- This allows you to capture events from various sources shown in below diagram and trigger workflows, notifications, or other actions based on those events.

  <img width="688" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/9f2ff30c-7b75-4f1d-9d0b-e90a24b24940">
- Event Bus Filtered Events
  <img width="980" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/a14fc767-b507-46ba-8770-a7eef65f1f40">
- Event Bus Scheduled Events
  <img width="700" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/d5fe4820-5498-49bb-93ce-2362ce6b576b">





  
