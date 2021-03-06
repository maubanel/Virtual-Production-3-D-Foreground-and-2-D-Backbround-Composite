[Previous](../lens_distortion/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Add Master Sequence](../master/README.md)

## Shot 0020

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

![add two image media source actors](../images/scene2Plates.jpg)
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

8.  Right click on **Media Track** and select **Edit Section** and assign the **Media | Media Texture** and assign it **BackgroundMediaTexture**.  

![add media texture to edit section](../images/assignSc2MediaTextureToTrack.jpg)

***

9.  Now you can click on the **Backbground** composure layer in the world outliner then scrub to see that the plate is showing up with a reverse view from the previous camera.  It should look like:

![reverse view on background plate](../images/sc2BackgroundPlate.jpg)

***

10. If we subtract the first frame from the last frame we find out that the sequence is 277 frames long.

![scene two is 277 frames long](../images/lengthOfSc2.jpg)

***

11. Now make the track long enough to see at least 277 frames and fill the media track to be **EXACTLY** `277` frames long.

![make media track precisely 277 frames long](../images/haveMediaTrackFillCut.jpg)

***

12.  Make sure the green beginning of the cut is at `0` and the end  of the cut (red line) is at `277`.

![set scene 2 cut length](../images/setBeginingAndEndSc2Cut.jpg)

***

13. Now we need to get the tracked camera path into the scene.  Got to **World Outliner** and drag and rop the **CineCamera** link to the sequence.  Right mouse click on the **Camera Component** and the **Transform** and delete them.

![drag and drop cine cam into scene 2 level sequence](../images/dragCineCamClearOldJunk.jpg)

***

14.  Make sure what is left is names **CineCamera**.  If it is not, then the animation of the camera will not import. Right click and select **Import**. Again this camera data was tracked in software like **Nuke** to derive a camera path from the 2-D plate.

![import new cam data scene 2](../images/importCeneCamDataSc2.jpg)

***

15. Now go to the student drive and in the **Scene2** folder you will find a file called **tracked_camera_0020.fbx**.

![import tracked cam 2](../images/importtTrackedCam2.jpg)

***

16.  Now `deselect` the **Match by Name Onlye** and **Create Camera** selections and press the **Import** button.

![import camera movement](../images/scene2CanImport.jpg)

***

17.  Now you should see a camera path in the game and notice it doesn't start at `0` on the level sequence.

![see camera path](../images/camPath.jpg)

***

18.  Now you need to left click and drag select all the keys under the camera on the **Transform** layer.  Let go and select the far left key and drag to the left to get to position 0.

![drag key to 0](../images/dragKeyTo0.jpg)

***

19.  Now we need the mannequin to animate in this scene as well.  Drag the **SK_Mannequin_Female** from the World Outliner into the **Level Sequence** as another track.

![add mannequin to track](../images/dragPlayerInTimeline.jpg)

***

20.  Press the **+ Animation** button and select the only animation we have **mocap_patio_walk**.

![add mannequin animation to track](../images/importAnim.jpg)

***

21. Now we are starting this at `0` but will be cutting roughly into frame 150 after the first cut.  So lets slip back the animation clip by a bit and we will fine tune it after.

![slip mannequin animation backwards](../images/slipTrackBack.jpg)

***

22.  Now access the **PatioComp** and scroll to the end and you should see the player on top of the background.

![scene 2 player on background composite](../images/compManBackSc2.jpg)

***

23.  Lets add lens distortion to scene 2.  Go back to **Sequencer** and add a second media track by pressing **+ Track** and selecting a **Media Track**.

![add distortion media track to scene 2](../images/sc2SecondMediaTrack.jpg)

***

24.  Now press on **+ Media** to link this media track to **Scene0020Distortion**.

![add media to scene 2 distortion media](../images/linkSc2MediaTrackDistortion.jpg)

***

25.  Expand this distortoin media layer to take up the entire cut.

![exapand distortion clip to take entire cut](../images/expandClipToTakeWholeCut.jpg)

***

26. Right click on **Media Track** and select **Edit Section** and assign the **Media | Media Texture** and assign it **DistortionMediaTexture**.  

![assign distortion media texture to track](../images/assignMediaTextureToDistortionSc2.jpg)

***

27.  Now go on **Scene0010Sequence** and **Scene0020Sequence** and make sure the **Camera Component** has a **Focal Length**, **Aperature** and **Manual Focus Length**. If either sequence does not add them by pressing **Component +** and adding the three components. I have also included scene 10 settings to confirm they are still the same.

![make sure camera component vaules are correct scene 2](../images/addCameraComponents.jpg)

![make sure camera component vaules are correct scene 1](../images/addCameraComponents2.jpg)

***

28.  So the settings for scene 20 are: **Current Aperature** is `9.0`, **Current Focal Length** is `45.4` and **Manual Focus Distance** is `213.36`.

![add camera components to sequence 1 and 2](../images/scene20Settings.jpg)

***

 29.  Now click on **PatioComp** and scroll and you should have shot 2 fully composited as designed.

 ![scene 2 finished](../images/sc2FinalClip.jpg)


***

[Previous](../lens_distortion/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Add Master Sequence](../master/README.md)