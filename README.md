# UIFromJSON-iOS
Framework for constructing UI From JSON

This framework creates User Interface eleements from JSON data. This is similar to how a web browser renders a screen from HTML and CSS. Also similar to cross platform like flutter, or cordova. UIFromJSON is intended for rapid prototyping and/or occassions where the UI may need to be changed on the fly from either project included data or from a RESTful web serice end point. The same JSON specificaiton should be compatible with either iOS or Android versions.

The structure of JSON data is presented in a form similar to Bacus-Naur Form (BNF). UI ::= [ Elements ] should translate to "UI" : [ ... ] , that is an array of elements.

The current specification is:

<pre>
UI ::= [ Elements ]

Elements ::= Screen 

Screen ::= "Screen" ScreenAttributes [ UIElements ]

<ScreenAttributes> ::= | Background

ElementAtrributes ::= Background            

Background ::= Color | Image

Color ::= "Color" red green blue

Image ::= "Image" filespec | imageURL

UIElements ::= Label 
              | TextInput

Label ::= "Label" text

TextInput ::= "TextInput" 

Button ::= "Button"
</pre>

An example JSON:

<pre>
"UI" : [ 
        "Screen" : 
                   [
                       "Background" : 
                             "Color" r:0  g:0 b:0
                       "Label" : "username"
                       "TextInput" : "userName"
                       "Label" : "password"
                       "TextInput" : "password"
                       "BUtton" : "login"
                   ]
       ]
</pre>


This should at run time present a login screen in the form of a ViewController with UILabels, UITextFields on iOS or an Activity with TextView, EditText and Button on Android.



