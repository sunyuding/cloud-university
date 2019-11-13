# Amazon Simple Queue Service (SQS)
[Amazon SQS]() is a fast, reliable, scalable, and fully managed message queuing service.

Q. You are working with your application development team and have created an Amazon Simple Queue Service (Amazon SQS) standard queue. Your developers are complaining that messages are being processed more than once. What can you do to limit or stop this behavior?
- Deploy a **First-In, First-Out (FIFO) queue** and have the developers point their application to it.

Q. How can you grant a different AWS account permission to send messages to your Amazon SQS queuue?
- "Create an IAM User for the other account and add an IAM policy that grants access to the queue." is incorrect. Cross-account access need to create a role.
- Create an Amazon SQS policy that grants the other account access. 

[Amazon SQS Dead-Letter Queues](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html)

Q. You notice that all messages in an Amazon SQS queue are being redirected to the **Dead Letter Queue** even though they have been correctlly processed by your application. What could be causing this?
- The application is not deleting the message after processing it

Question: Hundreds of buses are sending real-time coordinates to your Amazon SQS FIFO queue. The queue has thousands of messages, but after retrieving 10 messages, no more message can be retrieved. What could be the cause?
1. SQS FIFO queues have a maximum of 10 in-flight messages'
2. Each bus should use its own [MessageGroupId](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/using-messagegroupid-property.html)
3. The Dead Letter Queue is full
4. Long Polling should be used

Answer: 2.

