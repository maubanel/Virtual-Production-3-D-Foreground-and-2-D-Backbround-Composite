## Add Master & Second Sequence

1.  Create a new folder inside **Plates** called `Scene0020`.  Right click and select **Show in Explorer**.  We will be importing the new plates **WITHOUT** going through the import process.

![import new files into new scene0020 folder](../images/showInExplorerSc2.jpg)

***

2.  Drag the **footage** folder from the student folder to import the **EXR** files for the background plate and lens distortion.  Make sure you ignore the import message and press **DON'T IMPORT** when it pops up in the bottom right.

![copy footage folder from scene 2](../images/scopyScene2.jpg)
![do not import footage](../images/dontImort.jpg)
***



3. Now you should see the **plates** and **distortion** folder with no files showing up in Unreal (this is ok).

![empty scene two folders](../images/distortionPlateFolder.jpg)

***

4.  Lets add a **Scenes | Scene0020** folder and add two **Media | Image Media Source** actors.  Call one `Scene0020Source` and the other `Scene0020Distortion`.

![add two image media source actors(../images/scene2Plates.jpg)
*** 

5.  Double click on both media sources and point them to the first **EXR** in the Unreal folder.  It is very important you are **NOT** pointing them to files outside of your **Content** folder for this project.

![add scene 2 source](../images/linkScene2Source.jpg)
![add scene 2 distortion](../images/linkScene2Distortion.jpg)

***

6.  Add a new **Scenes | Scene 0020** a **Animation | Level Sequence** actor to the project. Call it `Scene0020Sequence`.

![add scene 2 level sequence](../images/addScene2Sequence.jpg)

***

7.  Open up the sequence and add a **+ Track** and select **Media Track**.

![add media track](../images/addMediaTrackSequence2.jpg)

***

8. Now click on **+ Media** and associate this with **Scene0020Source** image media.

![assign image media to new scene 2 source](../images/addScene2ToTrack.jpg)

***

9. We can have one media texture for source and for distortion but assign it to multiple **Media Tracks**.  Since we want to still use the same **M_Composite** material we will re-use those media textures.  Rename both and remove mention of scene 0010 and move them to the **Scenes** folder. Rename them to `BackgroundMediaTexutre` for the source and `DistortionMediaTexture` for the lens distortion.

![rename 2 media texture files and move them tou scenes](../images/moveRenameMediaTextures.jpg)

***

8.  Right click on **Media** and select  











***

--- [Next Chapter - Lighting and Scene Geometry](../shadow/README.md) ------ [Back to Home Page](../README.md)