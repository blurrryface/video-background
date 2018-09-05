# video-background

Lets go to our index.html file and set up our HTML layout for our video background. Lets add the following code:

<!DOCTYPE html>
<html>
    <head>
        
        <title>Video Background Tutorial</title>
        
    </head>
    <body>

        
        <div class="video-background">               <!-- set poster image -->
            <video id="video-element" preload="auto" poster="img/poster-bg.jpg" autoplay="true" loop="loop" muted="muted">
                <!-- add video here -->
                <source src="vid/video-1.mp4" type="video/mp4">
            </video>          
        </div>


        <div class="content">         
            <h1>Healine Background</h1>
            <p>supporting text at the bottom</p>
        </div>



    </body>
</html>

Let's go through the code here. We created 2 classes, video-background and content. 

video-background will work as our container to hold our video. We have also placed an id; video-element so we can add some CSS to our video.

Let's go through some of the properties of the video tag:
preload: set to "auto" to allow for our video to be loaded before playing.
poster: set image for background in case video fails to load. Good for mobile as video background aren't fully supported for mobile.
autoplay: set to true so video plays automatically.
loop: set to loop so video continues to play.
muted: set to muted so no audio is playing on video.

Set these options accordingly. You can also see all the options to choose from here (ADD LINK) to set the video how you like it.

In between the video tags we have our source tag. Add your video file here <source src="vid/video-1.mp4" type="video/mp4">. 

In our content file:

We will use the <h1> tag and <p> tags for our headlines.

If we run our project right now. We will see our video playing, and our headline below it to the left. We want our headline in the middle on top of the video. Our video is also not fitted on the entire screen, and we also want everything to be static with no scroll bars. Lets add some CSS.

----------------------------------------------------------------------------------------------------------------------------------------

Create a file called style.css and add it to our css folder. After that, let's also quickly connect our CSS file to our HTML file. Add this code beneath the <title> tag.

<head>
        
        <title>Video Background Tutorial</title>
        
        <!-- CSS STYLESHEET -->
        <link href="css/style.css" type="text/css" rel="stylesheet">
        
</head>

Open style.css and add this code:

* {
    margin: 0; /* we dont want any content of have margin or padding unless otherwise specified */
    padding: 0;
}

body {
    font-family: ; /* you can add your font here or at the .content class */
}

/* VIDEO BACKGROUND
************************/
.video-background {
    position: fixed;
    z-index: -1000; /* we want video background to be at the very bottom of everything else */
    width: 100%; /* set width and height to 100% to fill container */
    height: 100%;
    overflow: hidden; /* set no overflow to get rid of scroll bars */
    top: 0; /* top and left set to 0 to set origin of background */
    left: 0;
}

#video-element {
    position: absolute;
    top: 0; /* set origin of video */
    left: 0;
    min-height: 100%; /* set min height and width to make video fill video-background class */
    min-width: 100%;
}



/* HEADER CONTENT
************************/
.content {
    position: absolute;
    width: 100%; /* make content div fill the full width to make centering easier */
    text-align: center; /* center content */
    min-height: 100%;
    z-index: 1000; /* make sure content is on top of video */
    background-color: rgba(0,0,0,0.7); /* transparent background */
}

.content h1 {
    text-align: center;
    font-size: 65px;
    text-transform: uppercase;
    font-weight: 300;
    color: white; /* set your colour */
    padding-top: 18%; /* set padding from the top to center content */
    margin-bottom: 10px; /* allow room for <p> */
}

.content p {
    text-align: center;
    font-size: 20px;
    letter-spacing: 3px;
    color: #bbb;
}

That's all there is to it! Go ahead and play around with it to your liking. Use that content class to add more info such as buttons, social icons, etc. Maybe try and build a unique navigation?
