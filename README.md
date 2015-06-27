# PHP-telegram-bot-API
Unofficial PHP Class for Telegram-API

Example ussage:

require('telegram-bot-api.php');

$token = 'YOUR BOT TOKEN';
$bot = new telegram_bot($token);


For setting webhook (you only need to run this command once)
$bot->set_webhook('http:/....'); //Your url
For unset:
$bot->set_webhook();


Readding from webhook:
$message =  $bot->read_post_message(); //Returns a message object

Readding from message inbox:
$list_message = $bot->get_updates(); //Return an array of message objects

Create custom keyboard:
$keyboard = new ReplyKeyboardMarkup(TRUE, TRUE);
$options[0][0]="a";
$options[1][0]="b";
$options[2][0]="c";
$options[3][0]="d";
$keyboard->add_option($options);
$bot->send_message($user_id, $text_message, null, json_encode($keyboard));


List of methods:
send_action(string:usser_id, string:action_name)
send_message(string:usser_id, string:message, optional_string:id_message, optional_json:customkeyboard)
send_location(string:usser_id, string:latitude, string:longitude, optional_string:id_message, optional_json:customkeyboard)
send_sticker(string:usser_id, string/file:sticker_image, optional_string:id_message, optional_json:customkeyboard)
send_video(string:usser_id, string/file:video, optional_string:id_message, optional_json:customkeyboard)
send_photo(string:usser_id, string/file:photo, optional_string:photo_caption, optional_string:id_message, optional_json:customkeyboard)
send_audio(string:usser_id, string/file:audio, optional_string:id_message, optional_json:customkeyboard)
send_document(string:usser_id, string/file:document, optional_string:id_message, optional_json:customkeyboard)
forward_message(string:from_usser_id,string:usser_id,string:message_id)


Some message structure:
Text:
stdClass Object
(
    [update_id] =>
    [message] => stdClass Object
        (
            [message_id] =>
            [from] => stdClass Object
                (
                    [id] =>
                    [first_name] =>
                    [last_name] =>
                )

            [chat] => stdClass Object
                (
                    [id] =>
                    [first_name] =>
                    [last_name] =>
                )

            [date] =>
            [text] =>
        )

)

Location:
stdClass Object
(
    [update_id] =>
    [message] =>
        (
            [message_id] =>
            [from] => stdClass Object
                (
                    [id] =>
                    [first_name] =>
                    [last_name] =>
                )

            [chat] => stdClass Object
                (
                    [id] =>
                    [first_name] =>
                    [last_name] =>
                )

            [date] =>
            [location] => stdClass Object
                (
                    [longitude] =>
                    [latitude] =>
                )

        )

)


Sticker:
stdClass Object
(
    [update_id] => 
    [message] => stdClass Object
        (
            [message_id] => 
            [from] => stdClass Object
                (
                    [id] => 
                    [first_name] => 
                    [last_name] => 
                )

            [chat] => stdClass Object
                (
                    [id] => 
                    [first_name] => 
                    [last_name] => 
                )

            [date] => 
            [sticker] => stdClass Object
                (
                    [width] => 
                    [height] => 
                    [thumb] => stdClass Object
                        (
                            [file_id] => 
                            [file_size] => 
                            [width] => 
                            [height] => 
                        )

                    [file_id] =>
                    [file_size] =>
                )

        )

)

Audio:
stdClass Object
(
    [update_id] =>
    [message] => stdClass Object
        (
            [message_id] =>
            [from] => stdClass Object
                (
                    [id] =>
                    [first_name] =>
                    [last_name] =>
                )

            [chat] => stdClass Object
                (
                    [id] => 
                    [first_name] => 
                    [last_name] => 
                )

            [date] => 
            [audio] => stdClass Object
                (
                    [duration] => 
                    [mime_type] => 
                    [file_id] => 
                    [file_size] => 
                )

        )

)
