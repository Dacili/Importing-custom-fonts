# Importing custom fonts in app
How to import custom font in your app?

### 1. Get font files
Firstly, you need to download the font files from somewhere (for example: https://fontsgeek.com/fonts/Basic-Sans-SF-Regular).  
Font **formats/extensions** are usually some of these:  ```OTF, TTF, WOFF, SVG, and EOF.```  
I will use **Basic Sans** font with **otf** extension. You can find them in files. 

### 2. Import them in app
Usually, you should put them in the ```assets -> fonts``` folder.  
![image](https://github.com/Dacili/Importing-custom-fonts/assets/37112852/4fc600f6-fd31-4957-8ce9-c5c35c40052b)


### 3. Create typography file
There is a common way of font-weight name mappings (https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight):  
![image](https://github.com/Dacili/Importing-custom-fonts/assets/37112852/c4df4270-5074-472b-a118-db6a7a268169)
We need to **map font files names, with font-weight values** when setting up CSS.   
On the image we have shown some of matches. If we're missing file for some weight, just ignore that one, and proceed with other font files.  
![image](https://github.com/Dacili/Importing-custom-fonts/assets/37112852/e715f426-fd99-4629-a0ab-aaf40a0c1617)

Example for **Basic-Sans-Bold.otf file** :
``` 
@font-face {
  font-family: 'Basic Sans';
  src: url('/assets/fonts/Basic-Sans-Bold.otf') format('opentype');
  font-weight: 700;
  font-style: normal;
  font-display: swap;
}
```
For italic, make sure that ``` font-style: italic;``` 
``` 
@font-face {
  font-family: 'Basic Sans';
  src: url('/assets/fonts/Basic-Sans-Bold-Italic.otf') format('opentype');
  font-weight: 700;
  font-style: italic;
  font-display: swap;
}
```
Repeat this for every font file that you have. If you have only one font file, then awesome, less work!

### 4. Import in the main styles.scss

```@import 'styles/typography.scss';```  
![image](https://github.com/Dacili/Importing-custom-fonts/assets/37112852/7e2507c6-073b-4bc9-8e87-690c1340cbd8)  
And that's it! You should be able now to add CSS in your app such as:
```
.dacili-class {
font-family: 'Basic-Sans';
}
``` 
 
