# Advanced Internet Applications / laboratory / Responsive design

For my beloved teacher :

Description : The aim of the exercice was to create a responsive website without using css framework. 

## Requirement

For install sass on my computer : npm install -g sass  
For automatic compilation : sass --watch style.scss:style.css

## Utility of Scss (or sass) 

In my opinion, Sass is very usefull because you can define variables. When you want to change the parameters, you only need to 
change the value of the variable, and no look for all parameters to change in the css file (generally, there are a lot of code line in the css file, so it takes a lot of time...)

## Font Size

To define the default font size at 16px, you just need to define it in the tag body :
```
body {
    font-size: $default-font;
}
```
You can notify we use the property of Sass to use a variable for the default font size.  
If we want our title 100% larger than our default font size, we just need to add 100%, so the size of our title will be 200% (the reference is default font size defined previously)
```
 #titre {
     font-size: 200%;
 }
 ```
 We do the same for the section title (here we add 50%)
 ```
#titreS {
    font-size: 150%;
    margin-top: 0%;
    text-align: center;
    position: relative;
    left: 50.5%;
    padding: 2%;
    width:45.5%;
}
```
## Responsive && Blank between sections 

Firstly, we define 3 screen width for differnts devices : 
* 600px or less for mobile  
* between 601px and 1023 for tablet
* 1024px or more for destock

For responsive, we will use @media. The followiing code is to define the screen width tablet :
```
@media only screen and (min-width: $mobile-width-limit + 1) and (max-width: $desktop-width-limit - 1) {
    #first
    {
        width:94%;
        margin: 3%;
    }
    #second
    {
        position: absolute;
        left: 0;
        width:45.5%;
        margin: 0% 3% 3% 3%;   
    }
    #third
    {
        position: absolute;
        left: 51.5%;
        width:45.5%;
        margin: 0% 3% 3% 0%;
    }    
}
```

In the code above, when we have a screen width for tablet, the section "first" will take all width of the sreen, and we let 6% for the margin (In the code, it's 3% because 3% for margin right + 3% for margin left). Under the section "first", we need to share the screen width for 2 sections : "second" and "third". Because before we defined a distance of 3% between "first" and the edges of the browser, we need to define the distance between sections as 3%. So the width of the articles will be 45.5%, and we put margin-top = 0% for the 2 sections, to keep the distance between the 2 sections and "first" equal to 3%. For the position, we define it as "absolute", and we position the section with the property "left".  
For Mobile and Destock resolution, it's the same principle.  

## Footer

To have the footer "stick" in the bottom of the page, we define its position as "absolute", and then we position it with the property "bottom" equal to 0. 
```
footer {
   
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: #efefef;
    text-align: center;
  }
```

## Conclusion

In this exercice, I discovered Sass, and improved my knoledges in css. 
