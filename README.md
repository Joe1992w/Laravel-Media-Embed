# Laravel Media Embed

A simple wrapper for dereuromark/MediaEmbed to generate embed HTML for popular media hosting services.

##Installation
````bash
composer require joe1992w/laravel-media-embed:dev-master
````
OR
````json
"require": {
    "joe1992w/laravel-media-embed": "dev-master",
},
````
````bash
composer install
````

##Service Provider
````php
'providers' => [
    // Others...
    Joe1992w\LaravelMediaEmbed\Providers\LaravelMediaEmbedServiceProvider::class,
],
````

##Facade
````php
'aliases' => [
    // Others...
    'LaravelMediaEmbed' => Joe1992w\LaravelMediaEmbed\Facades\LaravelMediaEmbed::class,
],
````

##Usage

````php
//URL to be used for embed generation
$url = "https://www.youtube.com/watch?v=8eK-5ivYb3o";

//Optional array of website names, if present any websites not in the array will result in false being returned by the parser
$whitelist = ['YouTube', 'Vimeo'];

return LaravelMediaEmbed::parse($url, $whitelist);
// "<iframe src="https://www.youtube.com/embed/8eK-5ivYb3o?wmode=transparent" type="text/html" width="480" height="295" frameborder="0" allowfullscreen></iframe>"

return LaravelMediaEmbed::parse($url);
// "<iframe src="https://www.youtube.com/embed/8eK-5ivYb3o?wmode=transparent" type="text/html" width="480" height="295" frameborder="0" allowfullscreen></iframe>"

return LaravelMediaEmbed::parse($url, ['Vimeo']);
// false
````

##Supported Hosts

Please see [dereuromark/MediaEmbed](https://github.com/dereuromark/MediaEmbed)

##Supported Website Whitelist names
Name |
--- |
YouTube |
Facebook |
Dailymotion |
MetaCafe |
Vimeo |
123video |
5min Life Videopedia |
AdultSwim |
AniBoom |
AOL Video (Old) |
Aparat |
Archive.org |
Atom |
Blastro |
$2 |
BoFunk |
Break |
Brightcove.com |
CBS News |
Cellfish |
Clarin |
Clip.vn |
ClipFish (Old) |
ClipFish (Special) |
ClipFish (New) |
ClipJunkie |
ClipMoon |
ClipShack |
CNetTV |
CollegeHumor |
TheDailyShow |
ColbertNation |
Crackle |
CrunchyRoll |
Current |
Dailyhaha |
Dave.tv |
DotSub (w/o Captions) |
DoubleViking |
dropshots.com |
Dv.ouou |
Divshare |
EASportsWorld |
EbaumsWorld |
ESPN |
Fandome |
Flickr |
Foxhead |
FunnyOrDie |
FunMansion |
G4TV |
GameKyo |
GameSpot |
GameTrailers (Inc. User Movies) |
Gametube.org |
GameVideos.1up |
GarageTv |
Gloria |
GoEar |
Good.IS |
Glumbert |
GodTube |
GrindTv |
Guzer |
TheHub |
Howcast |
Hulu (Usa Only) |
Humour |
Video.i.ua |
IGN |
iJigg |
IMDB |
ImageShack |
IndyaRocks |
iReport |
Izlesene |
Jamendo |
Jokeroo |
JujuNation Video |
JujuNation Audio |
JustinTV |
Kewego |
Koreus |
Last.fm (Audio) |
Last.fm (Video) |
Libero |
LiveLeak |
LiveVideo |
MSNBC |
Video.mail.ru |
MadnessVideo |
Metatube |
MotionBox |
Mpora |
Mp3tube |
MtvU (Usa Only) |
MP3 Audio |
MyNet |
MyShows.cn/SeeHaha.com |
MySpaceTv |
MyVideo |
MyVi |
M Thai |
NewGrounds |
NhacCuaTui |
OnSmash |
Orb |
Photobucket |
PikNikTube |
Project Playlist |
Putfile |
Rambler |
RawVegas |
RuTube |
Screencast |
ScreenToaster |
SevenLoad |
ShareView |
Sharkle |
Smotri |
Snotr |
SouthPark Studios |
Space.tv.cctv.com |
Spike |
Songza |
Streetfire |
StupidVideos |
TagTélé |
Ted.com |
The Onion |
TinyPic |
Todays Big Thing |
TrailerAddict |
TrTube |
Trilulilu |
Tu.tv |
Tudou |
Tumblr (Music) |
Twitvid |
UOL VideoLog |
u-Tube |
Ustream |
VideoJug |
videos.sapo |
Vidiac |
Viddler |
Videa |
VidiLife |
VidMax |
Vidivodo |
VoiceThread |
WeGame |
Webshots (Slideshows) |
Wistia |
Yahoo Video HK |
Yahoo Video |
Yahoo Music Videos |
YouKu |
sina video |
XVideos |
Local Content |
