
What I am trying to do here is create something were I can share my pictures with family that I got to spend time with on vacation before this class started. 
I documented the trip for my aunt and my dad as it was the first time my aunt got to travel west. Any trip with my dad is an adventure as he takes his time to seak out things he has never seen and visit old fav's. 


My goal is to make a photo carousel with cards for each location and/or trip that you can click into and view the slide show. I will start with just this one trip but the photos are shot in raw and various methods so that will be another task in its self ..wish me luck!


I have looked at so many ways to do the carousel slide show and I have tried a few. I am trying to find a method that fits the needs of the assignments. 
In my search I found that react has had a React Slick carousel component buile in. I set up a new folder again and were going to give it a shot.


----------------------
I found the installation tag for npm here

https://react-slick.neostack.com/docs/get-started/

to start changing function app.js to a class. 
class App extends Component and changing the import to 
import React, {component}...dena dont forget the ,
add your render line

now says logo is not defined...i forgot to remove logo from the div so do that. 

add h tag to see if im working,..yaa it says hello!!

next...in terminal
npm install react-slick --save

then
npm install slick-carousel --save
wow it seams like it worked..ok cool

found out that that is nolonger supported when i dug deeper. 
trying something else

-------------------------

npm install react-simply-carousel --save

seamed to install..now to try it


ok...trying something

So I found that that is nolinger maintained and I am going to try to build it with things I have learned but really im unsure of all i need to make it work. I will try to puzzle a few ideas to gether and see what I can find. When it works I will celebrate somehow as I have spent days looking in to so much my mind has melted. I may of bit off more then I can chew. 
 
 im going to just try to build the component for this now 
 and see if i can make it work of something

 i know i need to import and link it to my app.js and put the Carousel object in the divs i cleaned the logo out of. 
 i need arrow icons 
 i found this tag...i think i can use this  import src from 'image/avif'

 avif

 https://blog.logrocket.com/how-to-format-quality-images-using-avif-squoosh-and-go-avif/

 ok ill list out the set up that I seen used in class and name them as meaniful to keep it as clear as possible. 

 doing 
 npm install react-icons for my icons used on my photo slide
 not sure if this will work but i found the suggeston to try it
 I found a github for 
 react-icons.github.io/react/icons/icons?name=fa
 there is a lot of icons here ...love it
 Fa is for Font Awsome

 im going to import everything. the past carousel i couldnt get to work and maybe my pics were the issue 
 i have renamed my pics to pic's and im going to import them like the other stuff and see what happends. 

 using rfce to let vs set up my react fuctional component...
. 

 adding props into the ()
of this function. 

Mitchell Grafton..

function Carousel() 
the images need to be passed into the ({ source 1, 2 and 3}) and also tell the parent componenent that we just changed the image so the call back will need to be put in props as well. call back will print console.log update

--------------dena----------------
so is this passing it backworks then? confused here as i didnt think it could communicate backworks
oh but its not waterfall
find the info on this to learn the vocab!!!

----------------------------------

set up the props with default values 
inside ({}) 
prop = default value. 
source 1 will be pic1 ect
for the call back we are going to consol.log out whatever the source is

inside the return { } but before the return we will set state
the set of state will hold the order that the images are in and keep track as the carousel moves.
Im changing my sources to src so they are different when i do the const. I was trying to keep it clear. 
so set up the array of sources, setSources and useState here to pass in the sourses form the porps
set state [setSources] array

setting up div's
the outer div will be className of carousel
(make sure its className not class for react!)
inner div 2 will be for container
inside container i need the direction button so div's for those called form  FaAngle 
so set up in order...icon, images, icon
the images will need the map targeting the index of the array 
under that add the images
the images will need a key for the index. each image will have a different key. 
images pulled from the source...src={src}..
the images will have an id. pic = index 
after getting the order of operations set up add the right icon in the next div

i had a syntax error...a couple inverted letters and i use {} where i should of used ()


lifecycle of a react components


https://files.slack.com/files-pri/T9KJM7QJX-F01M3QL7L6L/react-components-lifecyle-diagrams.jpg

it kep giving me this error...for like hours. i changed some things. tryed turning src back to sources becouse in the code the setSorces look weard

TypeError: sources.map is not a function
Carousel
src/components/Carousel/Carousel.js:21
  18 | return (
  19 |     <div className="Carousel">
  20 |         <div className="container">
> 21 |             <div>
     | ^  22 |                 <FaAngleLeft/>
  23 |             </div>
  24 |             {sources.map((src, index) =>
View compiled
▶ 21 stack frames were collapsed.



error was in line 16

const [sources, setSources] = useState (src1, src2, src3);

i had this. i put it in [] but it was unhappy so i tryed that and it was happier 
but it made outher sources weard. what i needed was ([src1, src2, src]); 
i knew it had to be an array but i just had it wrong. also i found that i was missing 
; and had a spelling on a src inverted

the index.js was causing problems from how it was set up so i gutted the render function 
and put a div in it for now

I SEE PICTURES!!!

they are in a colum and the buttons do not work. the page is layed out all wrong. ill add some css to see what happends

the hardest part about this code is the source src. i changed them around alot and confused myself. 

This is the first time i imported the photoes like that. i also renamed them this time. 
I tried using some of mine now but they are too big for tinypic and dont seam to want to work. I have more work to do there. It can take a bit to get the photos how i want them i hope i have time. 

CSS

to remove all the extra padding and spacing that come with the basic elements
using a *
* i seen this used before and i didnt know what it was. 

The * selector matches all elements in the DOM. You use the star selector without knowing it. When you use other selectors like class or element, they already imply the star selector. 
I had some issues in the past and wonder if this selector would fix some. 
I added this and i 'see' no changes but I understand the valuel

i need my pictures to go left to right so...the Carousel is what ill start with. also the buttons are tiney and need to be placed like i want them. 
im tageting the container of the carousel
displaying flex and setting to row worked really well. the pics are really big and have no spacing. 
my sixes turned out different but i didnt set the size of the accual photo so that makes some sense. i tryed to fux this with .Carousel img but it kinda didnt work like that. 
i want the middle img to be bigger and right now its the smallest. 

.Carousel #pic2...i did not know you can do this but in line 26 in Carousel.js we set the id to the index. 

i need to give some thougth to my pic sizes. its working but not like i want it to. 
im adding the 
Carousel.js becouse it took me a while to get it working and im about to mess with it to get the buttons to work.


import React, {useState} from 'react'
import './Carousel.css'
import pic1 from './images/pic1.jpg'
import pic2 from './images/pic2.jpg'
import pic3 from './images/pic3.jpg'
import {FaAngleLeft, FaAngleRight} from 'react-icons/fa'


function Carousel({ 
    src1 = pic1, 
    src2 = pic2, 
    src3 = pic3, 
    callback = (src) => {console.log(src)}
}) 
{
    const [sources, setSources] = useState ([src1, src2, src3]);

    return (
        <div className="Carousel">
            <div className="container">
                <div>
                    <FaAngleLeft/>
                </div>
                {sources.map((src, index) =>
                    <div>
                        <img id={'pic' + index} src= {src} alt="img"/>
                    </div>
                )}
                <div>
                    <FaAngleRight/>
                </div>
            </div>
            
        </div>
    )
}

export default Carousel


https://www.w3schools.com/react/react_css.asp
you can style in js I havent done it for a while. This is what i used to refresh. 

its getting late and I need a nap. ill watch the video alex put up about hooks being I been trying to look into them. 
everything is working ok at this time but things are not how I have them layed out in my wireframe to be. 

its acting up. i have the first pic half off the page and the middle pick dont want to adjust properly. 

under the state before the return
adding a function to get the buttons working 
make a const for each left and right and create an array to hold sorces after they move
set sourses to new order and 
above
populate new order
so const newIndex incrementing the index, checking to see if its greater then sources.length
if it is we will go back to the begining otherwise set to what ever that increment is. 
this will make it keep looping starting from the begining again and the same for the other way will be set so if -- the index and if its o go back to the end
ok i missed something its not working
so set the new order, the array of new index set to src

newOrder[newIndex] = src is exacually where is  should move it over 1

dont forget to add the onclick for the shift left and shift right to the button

ok so its acting up.Im trying to figure out how to fix it

https://reachlightspeed.com/blog/using-the-new-high-performance-avif-image-format-on-the-web-today/

yep still not working. 
i have reached out and im running out of time. i have tried several ways and using the avif was working for a second but now its not and i have done everything i can find
feeling really sad right now...lol


the callback us used in the function for moving left and right just to print the src ...the photo in the console log. i might take that out. 






















# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)