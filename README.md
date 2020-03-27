# Advanced Internet Applications / laboratory / Responsive design

For my beloved teacher :

Description : The aim of the exercice was to create a responsive website without using css framework. 

## Requirements

For install sass on the computer : npm install -g sass  
For automatic compilation : sass --watch style.scss:style.css

## Utility of Scss (or sass) 

In my opinion, Sass is very usefull because you can define variables. When you want to change the parameters, you only need to change the value of the variable, and no look for all parameters to change in the css file (generally, there are a lot of code lines in the css file, so it takes a lot of time...).  
Sass proposes others functionalities, in this code I used a lot the operators, and the nesting. I also used inheritance, and did some manips with the mixins (I did the nav bar with it).

## Font Size

To define the default font size at 16px, you just need to define it in the tag body :
```
$default-font: 16px;//default font size
```
```
body {
    font-size: $default-font;
}
```
You can notify, we use the property of Sass to use a variable for the default font size.  
If we want our title 100% larger than our default font size, we just need to add 100%, so the size of our title will be 200% (the reference is default font size previously defined)
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

Firstly, we set to 0 the margin of all the elements containing the sections, actually "body", "container" and "sections". Because distances between sections (both horizontal  and  vertical)  as  well  as  the  distances  between  the  sections  and  the  edges  of  the browser should be identical.

```
body, #container, #sections{
    margin: 0px;  //For distance between sections and edge of navigator, we define the margin as 0
}
```
Because we will position sections as absolute in some cases (for destock and tablet devices), we need to have a reference element defined as relative. This element will be "container" because he contains all others elements :
```
#container { 
    position: relative;//Because it contains some sections and footer which have absolute position
    min-height: 100%;
 }
```
We set to 3% (it's a random value) the distance between section :

```
$distanceBetweenSection: 3%;//distance between each sections(and the edge of the navigator)
```
Secondly, we define 3 screen width for differnts devices : 
* 600px or less for mobile  
* between 601px and 1023 for tablet
* 1024px or more for destock

```
$mobile-width-limit: 600px;//maximum width for mobile device
$desktop-width-limit: 1024px;//minimum width for destock device
```

For responsive, we will use @media. The following code is to define screens for tablets :
```
/*Tablet*/
@media only screen and (min-width: $mobile-width-limit + 1) and (max-width: $desktop-width-limit - 1) {
    #sections { 
        padding-bottom: $heightFooterTab;    /* we need to keep the place for footer, because when the height of the window narrowed, the position will changed  */
    }
    #first
    {
        width:$widthSectionMobile;
        margin: $distanceBetweenSection;
    }
    #second
    {
        position: absolute;
        left: 0;
        width:$widthSectionTablet;
        margin: 0% $distanceBetweenSection $distanceBetweenSection $distanceBetweenSection;       
    }
    #third
    {
        position: absolute;
        left: $widthSectionTablet + 2*$distanceBetweenSection;    
        width:$widthSectionTablet;
        margin: 0% $distanceBetweenSection $distanceBetweenSection 0%;

    } 
}

```

In the code above, when we have a screen width for tablet, the section "first" will take all width of the sreen, and we let 6% for the margin (In the code, it's 3% because 3% for margin right + 3% for margin left). Under the section "first", we need to share the screen width for 2 sections : "second" and "third". Because before we defined a distance of 3% between "first" and the edges of the browser, we need to define the distance between sections as 3%. So the width of the articles will be 45.5%, and we set margin-top to 0% for the 2 sections, to keep the distance between the 2 sections and "first" equal to 3%.  
For the position, we define it as "absolute", and we position the section with the property "left".  
  
  
For Mobile and Destock resolution, it's the same principle.  

## Footer

To have the footer "stuck" in the bottom of the page, we define its position as "absolute", and then we position it with the property "bottom" equal to 0. 
```
footer {
   
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: #efefef;
    text-align: center;
  }
```
With this code, our footer's "stuck" to the bottom of the webpage when  the  content  of  the  document  does  not  fill  the full height of  the  website. However, if you play to decrease the height of the browser window (you can try we the 3 differents width devices), we have a problem : the position of the footer will change and could overlap with the sections. Indeed, because we define footer position with the property bottom set to 0, when the height of browser window decreases, the footer position will change in relation with the height of the window, but the size of the others sections doesn't change! That's why the footer will overslap others elements of the webpage.  
To resolve this problem, we need to define a padding-bottom to the container which contains the sections, here "sections".  

This padding-bottom should be big enough to contains the footer and the content of the last section before the footer.
We define differents sizes for differents devices
```
$heightFooterTab:24em;//place for footer for tablet
$heightFooterMob:7em;//place for the footer for Mobile
$heightFooterDes:24em;//place for the footer for Destock
```
And then, in @media, we include the following code, with the good variable for each devices.
```
 #sections { 
        padding-bottom: $heightFooterTab;    /* we need to keep the place for footer, because when the height of the window narrowed, the position will changed  */
    }
 ```
## Conclusion

In this exercice, I discovered a new technology, Sass, that I implemented by using some of its properties and functionnalities. I also improved my knowledge of css. For the first time of my life, I created a responsive website without using bootstrap.   
I thank my teacher, sir Piernik, for this exercice and new skills acquired.
