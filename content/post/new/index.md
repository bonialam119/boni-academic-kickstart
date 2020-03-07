---
title: 'Real or Not? NLP with Disaster Tweets'
# subtitle: ''

authors:
- admin


# - Academic
categories:
# - Demo
date: "2020-01-01T10:00:00Z" 
# "2020-01-01T10:00:00Z"
lastmod: "`r format(Sys.time(), '%d %B %Y')`"
# "2020-01-01T10:00:00Z"
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# image:
#  placement: 2
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
#  focal_point: ""
#  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
Twitter has become an important communication channel in times of emergency. The ubiquitousness of smartphones enables people to announce an emergency they’re observing in real-time. Because of this, more agencies are interested in programatically monitoring Twitter (i.e. disaster relief organizations and news agencies). So in this blog we tried create a model to filter the disaster tweet among the thousands of tweets in real life.

## Software used for the study
- We used kaggle notebook as software tool for this study https://www.kaggle.com/kernels

## Data Collected
For the purpose of our study, we collected data from kaggle "Real or Not? NLP with Disaster Tweets" competition from the following link.https://www.kaggle.com/c/nlp-getting-started/data

## Tools used in NoteBook
For our study we imported different tools in Python. We imported numpy, pandas, tensorflow, standard scaler and others as shown below.{{< figure src="https://github.com/bonialam119/boni-academic-kickstart/blob/master/content/post/new/1.PNG" >}}

## Optitrack plugin for Motion Builder
We need the Optitrack’s Plugin for Motion Builder in order to stream MoCap data to Motion Builder. Install the plugin following the on-screen steps and restart  Motion Builder if it is already running. After the MotionBuilder plugin has been installed, three OptiTrack devices will be added to the MotionBuilder _‘Assets Browser’_ under the _‘Device’_ section. Follow this [link](https://optitrack.com/public/documents/motion-builder-plugin-manual-v3.0.0.pdf) for a more detailed usage guide.

## Downloading a Rigged character
For the purpose of this blog, we will be making use of a rigged character, [Peggy Sue] (https://free3d.com/3d-model/peggy-sue-rigged-for-animation-45959.html). This model has bone mapping that matches with MoBu’s bone naming rules. We can use any character, but if the bone mapping of the model doesn’t follow MoBu naming, each bone has to be mapped manually. 
When you choose to download, peggy is downloaded as a .rar file. Extract from the .rar file and open ‘Peggy.fbx’ 
{{< figure src="/img/posts/mocap-separation/peggi-extract.png" title="Extracted files" >}}

## Streaming from MoCap
Load the pre-recorded mocap video from which individual mocaps are to be exported onto MoBu. To stream the recorded take into Motion Builder, open Motive and make sure that the **‘Data Streaming’** settings are as follows. 

{{< figure src="/img/posts/mocap-separation/motive-setting.png" title="Streaming settings in motive." >}}

Go to **‘Edit’** mode. Make sure that the video is in ‘Loop mode’ and play the video. “Loop’ mode can be found at the bottom of the screen beside the video timescale

{{< figure src="/img/posts/mocap-separation/motive-player.png" title="Motive player." >}}


## Recording in MoBu
Now, open Motion Builder. Download and install the Optitrack Plugin for Motive. Towards the bottom right of the screen from **‘Asset Browser’**, select **‘Devices’** .

{{< figure src="/img/posts/mocap-separation/mobu-device-selection.png" >}}

Drag **‘Optitrack Skeleton’** device in the Viewer or Navigator Hierarchy. This will add **‘I/O Optitrack Skeleton’** in the navigator. Click on _‘I/O devices’_ and select _‘I/O Optitrack Skeleton’_. Once the plugin interface is open, make sure that the ‘Multicast Interface’ in Motive ‘Data Streaming’ and ‘Local Address’ in MoBu (which is now **127.0.0.1**) match. 

{{< figure src="/img/posts/mocap-separation/optitrack-plugin-setting.png" >}}

We set the plugin to **Online** by checking the box. It will show green when Motive is streaming and MoBu Plugin is connected. Check both the **Live** as well as the **Recording** option. The live option enables us to see the streaming data in the MoBu viewer. The Recording option enables us to record the streaming data inside MoBu. From the Model Building drop down we click on **‘create’** to create skeletons of the entities in the streaming data called Characters in the hierarchy. This step creates both characters as well as skeleton objects.


{{< figure src="/img/posts/mocap-separation/mobu-skeletons.png" >}}


Go to Motive and drag the seekbar to the start. Back in MotionBuilder, recording the data being streamed by clicking on the record button right below the display. Select ‘overwrite’ when asked whether to overwrite current take. Then click play button to start recording.

{{< figure src="/img/posts/mocap-separation/mobu-recorder.png" >}}

Wait for the whole mocap video being streamed into MoBu to be recorded and click on the square stop button. It might take MoBu a few minutes to generate the new recording.

Now, disable the Live Option in the Skeleton Device Optitrack plugin as we now have the take inside MoBu. We can also disable the plugin at this point

## Putting Mocap Recording onto Model
Once the recording is done, go to the ‘File’ menu and click on ‘Merge’. In the subsequent window choose ‘peggy.fbx’ [The rigged character]. You will then be presented with ‘Merge Options’. Deselect the existing take, right click on ‘Element’ in the ‘Scene’ block and click on ‘Append All Elements’. 

{{< figure src="/img/posts/mocap-separation/peggi-import-1.png" >}}


Then right-click on ‘Element’ near ‘Settings’ block and click on ‘Merge All Settings’. Click on ‘merge’ to finish merging. 

{{< figure src="/img/posts/mocap-separation/peggi-import-2.png" >}}

Once the merging is complete, we are able to see Peggy on the Motion Builder viewer. In the characters hierarchy in the Navigator we are able to see Peggy’s ‘character’ Object.

{{< figure src="/img/posts/mocap-separation/peggi-tpose.png" >}}

Select the character of whose mocap data you want to apply to Peggy. The character name will be the name you have from Motive. In the character settings, select input type as stance and check the active button. This will set the skeleton in T-Pose. 
Then select Peggy’s character from the Character hierarchy and in the character settings select input type as character and select input source as the character whose mocap you want to apply. Make sure to check the ‘active’ box. Now, it looks like the Peggy character is superimposed on the skeleton and they are in sync.
Then click on the ‘plot character’ option inside the character settings. From the pop-up select ‘skeleton’

{{< figure src="/img/posts/mocap-separation/plot-char-settings.png" >}}

And then click on plot. After plotting the characters, the active box might become unchecked, so you might need to recheck the active box. The ‘plot character’ enables the plotting of the Motive character or control rig animation to the model’s (Peggy) skeleton.

Now to create an fbx for for single character mocap, delete all other mocap entities.

The next step is to again select ‘Rubel’ character or the character whose mocap we are applying and uncheck the ‘active’ box in the character settings. If the active box is checked,the character always remains in the T-pose. But for Peggy’s Character the ‘active’ box needs to be checked

Now, when we click on the play button, we find that the ‘Rubel’s mocap is applied to Peggy.

{{< figure src="/img/posts/mocap-separation/peggi-mapped.png" >}}

## Exporting Individual Mocap
To export the individual mocaps, select ‘save as’ from the file menu and save . An fbx file containing the mocap applied to the model(peggy) is created. The same procedure is to be followed to  create MoCap->Model animation and extract the individual mocaps. 

This video shows this whole process for Exporting the Motive Streaming to separate Characters.

<iframe width="560" height="315" src="https://www.youtube.com/embed/TQQAbnMasSI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

These fbx files can be imported into unity to create [user input controlled animations] (https://aishwarya.io/unity-control-an-animator).
