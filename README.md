# Welcome to the model-viewer-add-annotations-onclick git repository readme
 Example on how to add annotations in model viewer on click


This is a explanation on how to add the functionality to add annotations to the model viewer on click. Like the example https://sietsenefs.github.io/model-viewer-add-annotations-on-click/index.html I made. <br> 
It can be useful if you want users to have an interactive experience with the 3d model and combined with php can even be used to let user give feedback trough annotations.

## Links
* html file: simple annotation added on double click https://sietsenefs.github.io/model-viewer-add-annotations-on-click/noText
* html file: annotation with text added on double click https://sietsenefs.github.io/model-viewer-add-annotations-on-click/noText
* css file for both: css file for simple and with text https://github.com/sietsenefs/model-viewer-add-annotations-on-click/blob/main/stylesheet.css
* assets: assets (example 3d model) https://github.com/sietsenefs/model-viewer-add-annotations-on-click/tree/main/assets


## Installing model viewer

First you will need to install the model viewer itself onto your website which is pretty easy and a simple guide can be found here https://codelabs.developers.google.com/codelabs/model-viewer/index.html?index=..%2F..index#0 and some more info can be found here https://modelviewer.dev/

## Adding interactive annotations

Although you can add annotations dynamically in model viewer like they do here https://modelviewer.dev/examples/annotations.html there is currently no straight forward way to add annotations while viewing the model viewer in the browser.
This is why I made this GitHub to make it easier to add this functionality yourself.

* First you will need to add `ondblclick="onClick()"` to your model viewer element here I used double click but I will also work with a normal onclick.
* Then add a function that gets the position and normal on the model from your cursor with the `positionAndNormalFromPoint(pixelX, pixelY)` method (see explanation what this does https://modelviewer.dev/) and add a new hotspot with that position and normal.
* Finnaly we just need to add a button that on click removes the last added hotspot
All this (and minor styling) should look something like this: simple annotation added on double click https://sietsenefs.github.io/model-viewer-add-annotations-on-click/noText

* To add text in the annotation we will add a text input
* then add to the add hotspot script that we can only add something if input is not empty or else alert with a message saying to fill input first
* We can then in the bottom of the add hotspot script say that we want to add a new div with the class annotation and put in in the last made hotspot. and put the text in it the same as the input field
* remove the input field text by replacing it with ""
* if we then add a selected class to it it will work but eventually we will get to many annotations and nothing can be clicked trough it so we will create a function that adds the class selected to the hotspot when clicked so we can only see one (this does not work completely because it doesnt work on the first click when a new hotspot is added, this has to be fixed in the future)

after doing that (and minor styling) it should now look like this: annotation with text added on double click https://sietsenefs.github.io/model-viewer-add-annotations-on-click/noText



