# Manage Your SCSS files !

Why to manage your SASS files ?
Because with CSS, you can't split your file, so you have 1 file with a lot of lines. So maintain  or add some features to this file is complex and not pleasant.

So to improve the management of your SCSS files, you can split them into several other small files that will be gathered in a main file, style.scss.
It is therefore easier to write and to manage your css file. You can find faster what you search.

# Structure

At the first approch, the structure seems to be complex but it is pretty simple and intuitive.

The "style" folder is the folder which contains every sub files of style.scss.

## Reset
In style.scss, you can find this line (line 6):
```
// Reset CSS
//@import 'style/reset/reset';
```
If you want a Reset CSS, you have just to uncomment this line.
This is the Reset [of Eric](https://meyerweb.com/eric/tools/css/reset/), but you can use the reset you want.

## Variables
This file contain all variables you will use in all of your files and you can add your mixins too. So it will be more pratical to create your SCSS files, with all variables in one place.

## Themes
Here, you'll just change the colors of your pages, no code for the layout, only color. You can have one or multiple themes. But if you add a files,  don't forget to add it to the style.scss file.

You can use mixin to avoid repeating your code and variables as arguments.
A mixin which is in the "variables" file:
```
@mixin theme ($color, $color-text, $color-background, $color-header-background, $color-hover) {
    color: $color-text;
    background-color: $color-background;
}
```
And to use the mixin in the "dark" file:
```
@include theme ( $color, $color-dark-text, $color-dark-background, $color-dark-header-background, $color-dark-hover)
```

## Base
In the html-body file, you will add the basics rules, ex:
```
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
}
```
and the "content" file contains mains rules of the arrangment of your layout global(like header, footer, aside...).

"Content responsive" is for the responsive rules:
```
@media screen and (max-width: 600px) {
}
```

And remenber, no color in these files.

## Layout
The design of your blocks like the header, the footer, the aside and other many thinks will be create in the folder "layout". You can add as many files as you want but but don't forget to add them to the style.scss file.

## Your files
Here is your files. For spécial design of a web page, or for a special items on your web page. Create a file but don't forget to add it to the style.scss file with:
```
// Style {your element} Responsive
@import 'style/yourfiles/nameOfYourFile';
```

# Create CSS file

Your SASS files is ready ? Want to have a CSS for your HTML files ?

To do this, you have to use the [SASS Compiler](https://sass-lang.com/install). Then execute this command in a nodejs command prompt (if you do not use nodejs, please refer you to the [documentation](https://sass-lang.com/install)):
sass style.scss:style.css -s compressed

And you CSS file is ready !

# Exemple

You can find a exemple of use [here](https://github.com/Barbapapazes/switch-theme).

# Thanks
Please, do not hesitate to suggest your ideas.