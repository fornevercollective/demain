![Tuesday js visual novels engine](https://repository-images.githubusercontent.com/233020914/1b3240ff-9db8-4163-92ba-f86e81d10967)

# Tuesday JS visual novel engine 
is a simple web-based, free and open-source visual novel editor that can be used in a web browser. It is written in JavaScript without using any third party libraries and thus does not require additional software installation. The engine uses standard HTML5 document elements such as div and img. This allows the use of any media format supported by browsers including vector graphics svg, gif animations and css styles.
There is a version of the editor available as a standalone application for Android devices and desktops. All versions are fully compatible with each other and have the same interface.



> Run in browser: https://fornevercollective.github.io/tuesday-js/translate/en_tuesday_visual.html

Download
-------------------------

Tutorials
-------------------------
> EN - [A quick tutorial to create a visual novel ](https://kirilllive.github.io/tuesday-js/doc_editor.html#quick_tutorial)

-------------------------


# Visualization
The visual editor allows you to create graphics or kinetic novels without any programming knowledge. If is necessary, it is possible to expand the basic functionality using JavaScript and css.

![Tuesday JS script structure](screenshots/script_structure.jpg)


# Scene editor
The scene editor can arrange all the elements in their places. It also shows how the scene will change on different screens. 
In the scene layout you can use standard HTML units in percentage pixels or centimeters to better adapt the scene to different screens.


![Tuesday JS scene editor](screenshots/scene_editor.jpg)


# Translate tool 
The built-in translation editing tool allows you to quickly add a new translation and edit all the texts in your project without leaving the editor. In addition, it displays the number of completed translations for each language.

![Tuesday JS preview](screenshots/translate_tool.jpg)


# Preview

Preview allows you to start a project from a certain point in the script with the selected localization.

![Tuesday JS preview](screenshots/preview.jpg)


# JSON
A story script has all the elements stored in a JSON structure. Almost any programming language can work with this format. This allows you to port your script to another engine or platform.
The editor has a built-in tool to work with JSON. This will allow you to edit the entire contents of the script or just the selected element.

![Tuesday JS json edit](screenshots/json_edit.jpg)


# ASCII art

The engine is adapted to use ASCII graphics. With its help, you can diversify the texts with images and patterns made up of text characters.

![Tuesday JS preview](screenshots/ascii_art.jpg)


# Localization
Tuesday JS provides ample opportunities for adapting stories into other languages.
You can set the localized translation for almost any element of your project including text and graphics.
The preview function allows you to run the project in the selected language.
All language texts can also be exported to a table csv file for editing or adding localizations in another editor.

![Tuesday JS localization](screenshots/localization.jpg)


# Creating a СhatBot
The project can be exported as a bot for the Telegram messenger. 
You can easily create an online assistant for your business to automate customer service and improve service levels.
Step-by-step guide to running a local server with Node.JS: https://kirilllive.github.io/tuesday-js/doc_editor.html#bot_telegram


![Tuesday JS localization](screenshots/telegram_bot.jpg)


# Warning for Android version

Minimum version of Android 5.1

If you have problems with files on Android 10 and higher, then you need to specify 'Allow access to manage all files' in the application settings in 'Permissions' section.

![Tuesday JS error access files on Android](tutorial_img/android_settings.png)


# Tutorial for RunTime

step 1
The engine file "tuesday.js" downloaded from https://kirilllive.github.io/tuesday-js/tuesday.js

step 2
Index.html file with id = 'tuesday' elements to display the novel
```html
<html>
    <head>
    </head>
    <!--After loading, the load_story function is launched, indicating a file or array with history-->
    <body onload="load_story('file','story.json')">
        <!--display area-->
        <div id='tuesday' style='width:100%; height:90vh;'></div>
        <!--path to the engine file, always at the end of the page-->
        <script type="text/javascript" src="tuesday.js"></script>
    </body>
</html>
```

step 3
Create a story file story.json
```json
{
    "parameters": {
        "text_panel": {
            "size": ["95%","25%"],
            "color": "#9cf",
            "indent_bottom": "32px",
            "size_text": "20px",
            "dialog_speed": 20
        },
        "name_panel": {
            "size": ["0","48px"],
            "position": ["0","0","-48px","0"],
            "size_text": "18px"
        },
        "launch_story": "main_menu",
        "languares": ["en"],
        "buttons": [
            {
                "name": "tue_back",
                "position": ["0","55%","0","8px"],
                "size": ["52px","52px"],
                "color": "#888",
                "size_text": "48px",
                "text":"<"
            },{
                "name": "tue_next",
                "position": ["55%","0","0","8px"],
                "size": ["52px","52px"],
                "color": "#888",
                "size_text": "48px",
                "text":">"
            }
        ]
    },
    "main_menu":[
        {
            "dialogs":[
                {
                    "choice":[
						{
                            "go_to": "story",
                            "position": ["50%","0","0","50%"],
                            "size": ["128px","48px"],
                            "color": "#888",
                            "color_text": "#fff",
                            "text": "Start"
                        }
                    ]
                }
            ]
        }
    ],
    "story": [
        {
            "dialogs":[
                {
                    "back_to": "main_menu",
                    "text":"1234567890",
                    "name":"numbers"
                },{
                    "go_to": "main_menu",
                    "text":"ABCDEFZHIKLMNOPQRSTVX",
                    "name":"letters"
                }
            ]
        }
    ]
}
```

Possible startup problems 

Index.html file with id = 'tuesday' elements to display the novel
```html
<html>
    <head>
    </head>
    <!--Change load_story value from ('file', 'story.json') to ('data', story) -->
    <body onload="load_story('data',story)">
    <div id='tuesday' style='width:100%; height:90vh;'></div>
        <!-- Add script tag before tuesday.js --> ;
        <script>
            let story = <!--insert content from story.json --> ;
        </script>
        <script type="text/javascript" src="tuesday.js"></script>
    </body>
</html>
```

