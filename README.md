[@SplitWithBot](https://t.me/splitwithbot)
==========================================

<img align="right" src="http://is5.mzstatic.com/image/thumb/Purple122/v4/e5/f7/6f/e5f76f46-c4e3-f43a-f7b6-a78877f63a9b/source/175x175bb.png">
Telegram bot for splitting receipts between participants in your chats

https://t.me/splitwithbot

## Deployment
TBD..

## How we store information in redis
| hash key                                                   | hash value                                      |
|------------------------------------------------------------|-------------------------------------------------|
| `user_<user_id>`                                           | dictionary with fields `un`, `fn`, `ln`         |
| `chat_<chat_id>_message_<message_id>_owner`                | owner id                                        |
| `chat_<chat_id>_message_<message_id>_status`               | check status `open`, `wait_payments`, `closed`  |
| `chat_<chat_id>_message_<message_id>_items`                | set with `item_id` of items                     |
| `chat_<chat_id>_message_<message_id>_done>`                | set with `user_id` of users who clicked `done`  |
| `chat_<chat_id>_message_<message_id>_paid`                 | set with `user_id` of users who clicked `paid`  |
|`chat_<chat_id>_message_<message_id>_item_<item_id>`        | dictionary with fields `name`, `price`          |
| `chat_<chat_id>_message_<message_id>_item_<item_id>_users` | set with `user_id` of users who clicked on item |
