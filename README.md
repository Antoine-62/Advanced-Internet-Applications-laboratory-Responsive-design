# Advanced-Internet-Applications-laboratory-Responsive-design

For my beloved teacher :

Description : The aim of the exercice was to create a responsive website without use css framework. 

## Requirement

For install sass on my computer : npm install -g sass
For automatic compilation : sass --watch style.scss:style.css

## Utility of Scss (or sass) 

In my opinion, Sass is very usefull because you can define variables. When you want to change the parameters, you only need to 
change the value of the variable, and no look for all parameters to change in the css file (generally, there are a lot of code line in the css 
file, so it takes a lot of time...)

## Font Size

To define the default font size at 16px, you just need to define it in the tag body
```
body {
    font-size: $default-font;
}
```
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

Firstly, we define 3 screen width for differnts devices : -600px or less for mobile
														  -between 601px and 1023 for tablet
														  -1024px or more for destock

For responsive, we will use @media :
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

In the code above
