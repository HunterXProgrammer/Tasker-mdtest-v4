# Description
This Section is recommended for advanced Tasker users.

It contains a detailed list of variables that is populated when a WhatsApp message of the corresponding TYPE is received

Based on these variables, you can setup your own Tasks that would analyze the contents of the received messages and send back automated replies.

# List Of Tasker Variables
These variables are populated whenever a WhatApp message of the corresponding type is received.

**Note:-** You need to run **"Mdtest - Start (V4)"** from the **"Receive Messages"** Project in `%mode` = `1` for the variables to be populated in the Task **"This Task Runs When Message Received (V4)"**.

#### Generally Available For All Message Types:-

`%type` = The type of message received. Can be one of -> message, extended_message, button_response_message, list_response_message or poll_response_message.

`%port` = Think of it as a unique identifier that is used for distinction when you use multiple numbers.

`%sender_name` = Name of the sender. Only set if the sender is saved in contacts.

`%sender_pushname` = Push Name of the sender.

`%sender_number` = Phone Number of the sender. Country code followed by the number. Eg:- If country code is "91", then -> 919876543210

`%sender_jid` = The JID of the sender. Country code followed by the number and "@s.whatsapp.net" at the end. Eg:- If country code is "91", then -> 919876543210@s.whatsapp.net

`%receiver_number` = Phone Number of the receiver. Country code followed by the number. Eg:- If country code is "91", then -> 919876543210

`%receiver_jid` = The JID of the receiver. Country code followed by the number and "@s.whatsapp.net" at the end. Eg:- If country code is "91", then -> 919876543210@s.whatsapp.net

`%is_from_myself` = If message was sent by yourself. Value is `1` if true, `0` if false.

`%is_group` = If message was sent in group. Value is `1` if true, `0` if false.

`%group_name` = Name of the Group. Only set if message was sent to group.

`%group_number` = Number of the Group. Only set if message was sent to group. Eg:- 919876543210-1234567890

`%group_jid` = The JID of the group. Only set if message was sent to group. Eg:- 919876543210-1234567890@g.us

`%time_stamp` = Time stamp of the message. Its of the format -> 2023-04-21 01:22:04 +0000 UTC

`%message_id` = Message ID of the received message. Used in advanced Task like Message Revoke, etc, to identify which message to revoke.

#### Variables specific to Text/Extended Messages:-

`%message` = The text message.

#### Variables specific to Button Response Messages:-

`%button_title` = Title of the Button Message.

`%button_body` = Body of the Button Message.

`%button_footer` = Footer of the Button Message.

`%button_selected_button` = Text of the selected Button.

`%origin_message_id` = The message id from which the Button Response Message originates from.  
(**Note:-** It is seperate from `%message_id`)

#### Variables specific to List Response Messages:-

`%list_title` = Title of the List Message.

`%list_body` = Body of the List Message.

`%list_footer` = Footer of the List Message.

`%list_header` = Header of the List Message.

`%list_button_text` = Text of the button of the List Message.

`%list_selected_title` = The text of the selected Title

`%list_selected_description` = The text of the  selected Description

`%origin_message_id` = The message id from which the List Response Message originates from.  
(**Note:-** It is seperate from `%message_id`)

#### Variables specific to Poll Response Messages:-

`%poll_question` = The Poll Question. Only set if the Poll Response Message was received when Mdtest was running. It will be written as old/outdated otherwise.

`%poll_selected_options()` = The array that contains the list of selected options. Only set if the Poll Response Message was received when Mdtest was running.
