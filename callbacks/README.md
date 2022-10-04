# Urls Callbacks
### Get Message delivery status is available by Callback URL
In your entry point url (already defined in Ardary dashboard : Parameters > API ) you can receperate status like this 
***php example
``` php
<?php
$status_message =json_decode($_GET[« status »]); 
?>
```
$status_message is an object like this:
{
  "user":"SENDER_LOGIN",

   "phone_number":"RECIPIENT",

   "status":"received",      // values : "sent" or "received"

   "date_status":"2019-08-09T12:50:54.211Z",

   "id_sms_api":"YOUR_ID_SMS"      // or the one we provide you if empty when sending

 }
### GET INCOMING MESSAGE
Incoming message is available by Callback URL:
***php example
$message =json_decode($_GET[« message »]);
$message is an object like this:
{

    "title":"incoming sms",

    "from":"+1XXXXXXXXXX",    // phone number (international format)

    "message":"Hello world !",

    "date":"2020-01-21 10:01:38"

}
### GET CLICKED LINK
Clicked link tracking is available by Callback URL:
***php example
$click =json_decode($_GET[« click »]);
$click is an object like this:
{  

    "title":"clicked link",

    "phonenumber":"+1XXXXXXXXXX",    // phone number (international format)

    "link":"https:\/\/www.my-link.com\/",

    "date":"2019-07-08 15:07:03",

    "id_sms_api":"YOUR_ID_SMS"      // or the one we provide you if empty when sending

 }
 ### GET CALL LOGS
 Incoming, outgoing and missed calls is available by Callback URL:
 ***php example
 $call =json_decode($_GET[« call »]);
$call is an object like this:
{  

    "TITLE":"INCOMING CALL", // or "OUTGOING CALL" or "MISSED"

    "PHONE_NUMBER":"+1XXXXXXXXXX",

    "CALL_TIME":"2019-07-05",

    "DURATION": "15:11:04"

 }
