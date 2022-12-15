#برمجه @JJJ22J 

#غير مسموح بالبيع اخلي مسؤليتي ع اي شخص يبيعه

#من الصفر برمجتي 

#تابع لقناة @SeroBots

<?php

ob_start();

$token = "5085228961:AAEf3tUV72YG8mheqBahR07AYJIior1yZ3Y"; 

define("API_KEY",$token);

echo file_get_contents("https://api.telegram.org/bot" . API_KEY . "/setwebhook?url=" . $_SERVER['SERVER_NAME'] . "" . $_SERVER['SCRIPT_NAME']);

function bot($method,$datas=[]){

    $url = "https://api.telegram.org/bot".API_KEY."/".$method;

$ch = curl_init();

    curl_setopt($ch,CURLOPT_URL,$url);

    curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);

    curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);

    $res = curl_exec($ch);

    if(curl_error($ch)){

        var_dump(curl_error($ch));

    }else{

        return json_decode($res);

    }

}

 

 

$update = json_decode(file_get_contents('php://input'));

$message= $update->message;

$text = $message->text;

$chat_id= $message->chat->id;

$name = $message->from->first_name;

$user = $message->from->username;

$message_id = $update->message->message_id;

$from_id = $update->message->from->id;

$a = strtolower($text);

$message = $update->message;

$chat_id = $message->chat->id;

$text = $message->text;

$chat_id2 = $update->callback_query->message->chat->id;

$message_id = $update->callback_query->message->message_id;

$data = $update->callback_query->data;

$from_id = $message->from->id;

if(isset($update->callback_query)){

$up = $update->callback_query;

$chat_id = $up->message->chat->id;

$from_id = $up->from->id;

$user = $up->from->username;

$name = $up->from->first_name;

$message_id = $up->message->message_id;

$data = $up->data;

}

$MyLan = file_get_contents("language$chat_id.txt");

$UserB = bot('getme',['bot'])->result->username;

$Botu ="@$UserB";

if($MyLan == "ar" or $MyLan == null){

$textstart = " 👋┇أهلاً بك عزيزي،

مع $Botu يمكنك تحميل من عدة مواقع بصيغ متعددة والاستماع اليها في أي وقت،

المواقع المدعومة: ( يوتيوب، انستكرام، فيسبوك، تويتر، تيك توك، سناب جات، ساوند كلاود، بينترست ، لايكي ، كواي).

";

$HowTo = "💠┇طرق التحميل من اليوتيوب:

🏷┇من خلال أرسال لي رابط الأغنية من اليوتيوب،

🖇┇أو أرسال لي أسم الأغنية للبحث عنها في اليوتيوب.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من الانستكرام:

🏷┇قم بأرسال لي رابط الفيديو أو الصورة في الانستكرام،

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من الفيسبوك:

🏷┇يمكنك تحميل مقاطع الفيديو العامة من موقع الفيسبوك،

🖇┇عن طريق أرسال رابط الفيديو فقط.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من بينترست:

🏷┇يمكنك تحميل مقاطع الفيديو العامة من موقع بينترست،

🖇┇عن طريق أرسال رابط الفيديو فقط.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من لايكي:

🏷┇يمكنك تحميل مقاطع الفيديو العامة من موقع لايكي،

🖇┇عن طريق أرسال رابط الفيديو فقط.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من التويتر:

🏷┇يمكنك تحميل مقاطع الفيديو العامة من موقع تويتر،

🖇┇عن طريق أرسال رابط الفيديو فقط.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من التيك توك:

🏷┇يمكنك تحميل مقاطع الفيديو العامة من موقع التيك توك،

🖇┇عن طريق أرسال رابط الفيديو فقط.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇طرق التحميل من ساوند كلاود:

🏷┇يمكنك تحميل الأغاني العامة من موقع ساوند كلاود،

🖇┇عن طريق أرسال رابط الأغنية فقط.

";

$buttonback = "🔙┇رجوع .";

$changge ="🇮🇶 ┇أختر لغة البوت أولاً.";

$search = "🔎 ┇ يتم البحث عن ";

$ResultSe ="🔎┇نتائج بحث اليوتيوب ل";

$Kefia ="❕ ┇ كيفية استخدام البوت.";

$BotLann ="🇮🇶 ┇ تغير لغة البوت.";

$Uploading ="🚀┇يتم الرفع علي خوادم تلكرام...";

$Loadongg ="♻️┇- انتظر جار التحميل...";

$FictionsVideo = ["📽┇مقطع فيديو","🔈┇ملف صوتي","🎙┇بصمه"];

$ntaij ="♻┇يتم الحصول علي النتائج";

$Keifa ="اختر نوع التحميل ";

}else{

$textstart = "👋┇Welcome Dear,

With $Botu you can download from multiple sites in multiple formats and listen to them at any time,

Supported sites: ( Youtube, Instagram, Facebook, Twitter, Tiktok, Snapchat, Soundcloud , pinterest ,Likee ,kwai).

";

$HowTo = "💠┇Download methods from Youtube:

🏷┇By sending me the song link from Youtube,

🖇┇Or send me the name of the song to search for on Youtube.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from Instagram:

🏷┇Send me the video or image link on Instagram,

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from Facebook:

🏷┇You can download public videos from Facebook,

🖇┇By sending the video link only.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from pinterest:

🏷┇You can download public videos from pinterest,

🖇┇By sending the video link only.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from Twitter:

🏷┇You can download public videos from Twitter,

🖇┇By sending the video link only.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from Tiktok:

🏷┇You can download public videos from Tiktok,

🖇┇By sending the video link only.

┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉ ┉

💠┇Download methods from Soundcloud:

🏷┇You can download public songs from Soundcloud,

🖇┇By sending the song link only.

";

$buttonback = "🔙┇Back.";

$changge ="🇺🇸 ┇ Choose the bot language first.";

$search = "🔎 ┇ Searching For ";

$ResultSe ="🔎┇Youtube search results for ";

$Kefia ="❕ ┇How To Use Bot.";

$BotLann ="🇺🇸 ┇Change The Bot Language.";

$Uploading ="🚀┇Uploading to Telegram servers...";

$Loadongg ="♻️┇Loading Download...";

$FictionsVideo = ["📽┇Video","🔈┇Audio","🎙┇Voice"];

$ntaij ="♻ ┇ The results are obtained";

$Keifa ="Choose ";

}

if($text == "/start") {

bot('sendmessage',[

'chat_id'=>$chat_id,

'message_id'=>$message_id,

"text"=>"*

$textstart

*",

'parse_mode'=>"markdown",

'reply_markup'=>json_encode([

    'inline_keyboard'=>[

    [['text'=>"$Kefia",'callback_data'=>'HowTo']],

     [['text'=>"$BotLann",'callback_data'=>'ChangeLan']],

   ]])

]);return false;

}

if($data == "HowTo"){

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$message_id,

'text'=>"

*

$HowTo

*

",

'parse_mode'=>"markdown",'disable_web_page_preview'=>true,

'reply_to_message_id'=>$message_id,

'reply_markup'=>json_encode([

'inline_keyboard'=>[

[["text"=>"$buttonback", "callback_data"=>"backk"]],

]])

]);

}

if($data == "ChangeLan"){

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$message_id,

'text'=>"

*

$changge

*

",

'parse_mode'=>"markdown",'disable_web_page_preview'=>true,

'reply_to_message_id'=>$message_id,

'reply_markup'=>json_encode([

'inline_keyboard'=>[

[["text"=>"🇮🇶 ┇ العربية .", "callback_data"=>"chngetoar"]],

[["text"=>"🇺🇸 ┇ English .", "callback_data"=>"chngetoen"]],

[["text"=>"$buttonback", "callback_data"=>"backk"]],

]])

]);

}

if($data == "backk"){

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$message_id,

'text'=>"

*

$textstart

*",

'parse_mode'=>"markdown",

'reply_markup'=>json_encode([

    'inline_keyboard'=>[

    [['text'=>"$Kefia",'callback_data'=>'HowTo']],

     [['text'=>"$BotLann",'callback_data'=>'ChangeLan']],

   ]])

]);

}

if($data == "chngetoar"){

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$message_id,

'text'=>"

*

👋┇أهلاً بك عزيزي،

مع $Botu يمكنك تحميل من عدة مواقع بصيغ متعددة والاستماع اليها في أي وقت،

المواقع المدعومة: ( يوتيوب، انستكرام، فيسبوك، تويتر، تيك توك، سناب جات، ساوند كلاود، بينترست ، لايكي ، كواي).

*

",

'parse_mode'=>"markdown",'disable_web_page_preview'=>true,

'reply_to_message_id'=>$message_id,

'reply_markup'=>json_encode([

'inline_keyboard'=>[

[['text'=>'❕ ┇ كيفية استخدام البوت.','callback_data'=>'HowTo']],

     [['text'=>"🇮🇶 ┇ تغير لغة البوت.",'callback_data'=>'ChangeLan']],

]])

]);

file_put_contents("language$chat_id.txt","ar");

}

if($data == "chngetoen"){

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$message_id,

'text'=>"

*

👋┇Welcome Dear,

With $Botu you can download from multiple sites in multiple formats and listen to them at any time,

Supported sites: ( Youtube, Instagram, Facebook, Twitter, Tiktok, Snapchat, Soundcloud , pinterest ,Likee ,kwai).

*

",

'parse_mode'=>"markdown",'disable_web_page_preview'=>true,

'reply_to_message_id'=>$message_id,

'reply_markup'=>json_encode([

'inline_keyboard'=>[

[['text'=>'❕ ┇How To Use Bot.','callback_data'=>'HowTo']],

     [['text'=>"🇺🇸 ┇Change The Bot Language.",'callback_data'=>'ChangeLan']],

]])

]);

file_put_contents("language$chat_id.txt","en");

}

$vidi = explode("##", $data); 

$txt = explode("|",$data);

if(!preg_match('(https://)',$text)){

	if(!preg_match('(/dl_)',$text)){		if(!$data){

			

$texttt=str_replace(' ','-',$text);

$item = json_decode(file_get_contents("https://ssmxzs.ml/Api/VBB8.php?search=".urlencode($text)))->results;      	

	  	 for($i=0;$i < 7;$i++){

		

$na=$item[$i]->title;

$idv=$item[$i]->url;

$timev=$item[$i]->time;

$views=$item[$i]->view;

$Sixe = $obj[videoInfo][downloadInfoList][6][partList][0][size];

$Video .= "* 🎬 $na*\n *🕦 $timev - 👁 $views* \n 🔗 [/dl_$idv]\n\n"."\n";

}

$s=bot('sendmessage',[

'chat_id'=>$chat_id,

'text'=>"$search *$text*...",

'message_id'=>$message_id, 

'disable_web_page_preview'=>true,

])->result->message_id;

bot('EditMessageText',[

'chat_id'=>$chat_id,

'message_id'=>$s,

'text'=>"

$ResultSe *$text*

$Video 

",

'parse_mode'=>"markdown",

    'disable_web_page_preview'=>true,

  ]);

}

}

}

if($update->inline_query){

$text_inline = $update->inline_query->query;

$iid=$update->inline_query->id;

$idchat = $update->inline_query->chat->id; 

$idms = $update->inline_query->message_id; 

$text_inline=str_replace(' ','-',$text_inline);

$result = json_decode(file_get_contents("https://ssmxzs.ml/Api/VBB8.php?search=".urlencode($text_inline)))->results;      	

 	$keyboard["inline_keyboard"]=[];

	  	 for($i=0;$i < count($result);$i++){

        $res[$i] = [

                'type'=>'article',

                'id'=>base64_encode(rand(5,555)), 'thumb_url'=>$result[$i]->image,

                'title'=>$result[$i]->title,

               'description' => "".$result[$i]->view." Views  - Time ".$result[$i]->time."", 'input_message_content'=>['parse_mode'=>'HTML','message_text'=>"https://www.youtube.com/watch?v=".$result[$i]->url],

          ];

    }

	  	$r = json_encode($res);

    bot('answerInlineQuery',[

 'inline_query_id'=>$update->inline_query->id,    

            'results' =>($r)

        ]);

}

if(preg_match('(https://)',$text) or preg_match('(http://)',$text)){

	$YutDl= json_decode(file_get_contents("https://ssmxzs.ml/Api/SSDL.php?url=" . urlencode($text)),true);

$YutDl1 = $YutDl["url"][0]["url"];

$mmusc=$YutDl["url"][1]["url"];

$metitle = $YutDl["meta"]["title"];

$mda = $YutDl["meta"]["duration"];

$Video = new CURLFile($YutDl1);

	$kls=bot('sendMessage',[      

'chat_id'=>$chat_id,   

'text'=>"*

$Loadongg

*

",

'parse_mode'=>"markdown",

])->result->message_id;

bot('sendaudio',[

'chat_id'=>$chat_id,

'audio'=>$mmusc,

'title'=>"m",

]);                

bot('sendvideo',[ 

'chat_id'=>$chat_id,

'message_id'=>$message_id,

'video'=>$Video,

'caption' =>" $Botu - $metitle, $mda",

     ]);

     

     bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$kls,

]);

}

 if(preg_match('(/dl_)',$text)){

 $text_get = str_replace(['/dl_'],'',$text);

 $IdVideo2 = str_replace('ovhj','-',$text_get);

 

 $n=bot('sendmessage',[

'chat_id'=>$chat_id,

'text'=>"$ntaij",

'message_id'=>$message_id, 

'disable_web_page_preview'=>true,

])->result->message_id;

bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$n,

]);

$YutDl= json_decode(file_get_contents("https://ssmxzs.ml/Api/SSDL.php?url=https://youtu.be/".$IdVideo2),true);

	$YutDl2 = $YutDl["url"][0]["url"];

	$metitle = $YutDl["meta"]["title"];

$mda = $YutDl["meta"]["duration"];

$Phho = "sendphoto";

$pog=bot($Phho,[

'chat_id'=>$chat_id,

'photo'=>"https://youtu.be/$IdVideo2",

'caption'=>"*🎬 [$metitle](https://youtu.be/$IdVideo2) \n 🕑 $mda*",

'parse_mode'=>"markdown",

    'disable_web_page_preview'=>true,

'reply_markup'=>json_encode([

    'inline_keyboard'=>[

    [['text'=>"$FictionsVideo[0]",'callback_data'=>'mo##'.$IdVideo2]],

     [['text'=>"$FictionsVideo[1]",'callback_data'=>'mo1##'.$IdVideo2],['text'=>"$FictionsVideo[2]",'callback_data'=>'mo2##'.$IdVideo2]],

   ] 

   ])

  ])->result->message_id;

file_put_contents("msgid.txt",$pog);

}

$msgid = file_get_contents("msgid.txt");

if($vidi[0] == "mo"){

	bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$msgid,

]);

$kls=bot('sendMessage',[      

'chat_id'=>$chat_id,   

'text'=>"

*

$Loadongg

*

",

'parse_mode'=>"markdown",

])->result->message_id;

sleep(1);

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$kls,

"text"=>"*$Uploading*",

'parse_mode'=>"markdown",

]);

	$YutDl= json_decode(file_get_contents("https://ssmxzs.ml/Api/SSDL.php?url=https://youtu.be/".$vidi[1]),true);

$YutDl1 = $YutDl["url"][0]["url"];

$metitle = $YutDl["meta"]["title"];

$sizee = $YutDl["url"][3]["filesize"];

$mda = $YutDl["meta"]["duration"];

$Video = new CURLFile($YutDl1);

file_put_contents("$vidi[1].mp4",file_get_contents($YutDl1));

	

bot('sendvideo',[ 

'chat_id'=>$chat_id,

'message_id'=>$message_id,

'video'=>new CURLFile("$vidi[1].mp4"),

'caption' =>" $Botu - $metitle, $mda",

     ]);

     

     bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$kls,

]);

unlink("$vidi[1].mp4");

}

if($vidi[0] == "mo1"){

	$YutDl= json_decode(file_get_contents("https://ssmxzs.ml/Api/SSDL.php?url=https://youtu.be/".$vidi[1]),true);

	$YutDl2 = $YutDl["url"][1]["url"];

	$metitle = $YutDl["meta"]["title"];

$mda = $YutDl["meta"]["duration"];

	$Music =new CURLFile($YutDl2);

	

	bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$msgid,

]);

$kls=bot('sendMessage',[      

'chat_id'=>$chat_id,   

'text'=>"

*

$Loadongg

*

",

'parse_mode'=>"markdown",

])->result->message_id;

sleep(1);

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$kls,

"text"=>"*$Uploading*",

'parse_mode'=>"markdown",

]);

bot('sendaudio',[

'chat_id'=>$chat_id,

'audio'=>$Music,

'performer'=>"$title",

'title'=>"$Botu - $metitle, $mda",

'thumb'=>$thumb,  

]);                

bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$kls,

]);

}

if($vidi[0] == "mo2"){

	$YutDl= json_decode(file_get_contents("https://ssmxzs.ml/Api/SSDL.php?url=https://youtu.be/".$vidi[1]),true);

	$YutDl2 = $YutDl["url"][1]["url"];

	$metitle = $YutDl["meta"]["title"];

$mda = $YutDl["meta"]["duration"];

	$Music =new CURLFile($YutDl2);

	

	bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$msgid,

]);

$kls=bot('sendMessage',[      

'chat_id'=>$chat_id,   

'text'=>"

*

$Loadongg

*

",

'parse_mode'=>"markdown",

])->result->message_id;

sleep(1);

bot('EditMessageText',[

'chat_id'=>$chat_id2,

'message_id'=>$kls,

"text"=>"*$Uploading*",

'parse_mode'=>"markdown",

]); 

bot('sendvoice',[         

'chat_id'=>$chat_id,           

'voice'=>$Music,  

'caption' =>"*

$Botu - $metitle, $mda

*

",

]);                

bot('deletemessage',[

'chat_id'=>$chat_id,

'message_id'=>$kls,

]);

}
