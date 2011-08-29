Synchtube Simple API
===========

The synchtube simple API allows you retrieve information about rooms and returns the result in a JSON format.

## Usage

The format of the REST URL is http://synchtube.com/api/{version}/{resource}. The current version of the API is 1.

## Resources
We currently only have one resource.

* <b>room/:ROOM_NAME</b> --- GET Request. Requires a room name and returns all the information about the room and its current state.

## Quick Start

The simple way to access a resource is with jQuery:

    $.getJSON("http://synchtube.com/api/1/room/{ROOM_NAME}?callback=?", function(response) {
        console.log(response);
    });

## Example

This is a complete example using the API to gather information about the room "mrchess".

###Request

    $.getJSON("http://synchtube.com/api/1/room/mrchess?callback=?", function(response) {
        console.log(response);
    });

###Response
JSON Response

    {
        "user": {
                "username":"mrchess",
                "avatar": {
                    "original":"http://synchtube.com/uploads/avatars/3/original_avatar.jpg",
                    "thumb":"http://synchtube.com/uploads/avatars/3/thumb_avatar.jpg"
                }
        },
        "description":"<p>\n\tWelcome to my hangout. I&#39;m typically here during the day while I code. Feel free to chill.</p>\n<br />\n<p>\n\tThis room is a portal to my other rooms.</p>\n<br />\n<p>\n\t<strong>chessclassical </strong>- classical piano music up to the late-romantic period [<a href=\"http://synchtube.com/r/chessclassical\">go now</a>]</p>",

        "moderators":["lucidrains","chessclassical"],
        "affiliates":["chessclassical"],
        "current_media":{
            "title":"VOCALOID MUSICAL Alice in Musicland ~English~Original Son",
            "image":"http://i.ytimg.com/vi/jHatMUTHSiY/default.jpg",
            "type":"Youtube",
            "type_icon":"http://synchtube.com/images/icons/favico/yt.ico"
        }
        "current_users": 0
    }

A complete code example of the above can be found in the <b>example.html</b> file.