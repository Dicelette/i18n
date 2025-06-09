---
title: Sending message
---
This bot detects dice notation and sends the result using three methods:

1. **Direct Notation**:
   - Example: `1d20`
   - The "command" message will be deleted, and the result will be sent in the same channel (and in the log).
   ![Direct](/assets/rolls/direct.gif)

2. **Indirect Notation**:
   - Example: `my message content [1d20]`
   - The message will be retained, and only the content within the brackets will be rolled. You will receive a response with the result, and the log will be sent in the thread, including a link to the original message.
   ![Indirect](/assets/rolls/indirect.gif)

3. **Semi-Direct Notation**:
   - Example: `1d20 My message`
   - The initially found die will be rolled, and the rest of the message will be sent in the log, considered as a comment.
   ![Semi-direct](/assets/rolls/semi-direct.gif)


It is also possible to use slash-commands to throw dice, like `/roll` ([see here for more information](../usage/index.md#dice-rolling))  
