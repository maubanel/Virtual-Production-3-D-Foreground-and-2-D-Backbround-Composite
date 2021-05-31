[Previous](../shot_20/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Scene 0030](../shot_30/README.md)

## Add Master Sequence and Export First Edit

1.  Now we can include multiple sequences inside a master sequence.  So we can edit different sequences together.  Go to **Scenes** and add a **Animation | Level Sequence**.  Call it `MasterSequence`.  Press the **+ Track** and add a **Shot Track**.

![create master sequence](../images/createMasterTrack.jpg)

***

2.  Now put the scrub bar at **Frame** `0` and select **Scene0010** as the first cut.

![add first cut to master sequence](../images/addFirstCut.jpg)

***

3.  Now I will be cutting at around frame **150** away to shot 2.  I looked at the footage and this seems like a logical spot.  So I will trim the clip to 150 frames.

![add first cut to master sequence](../images/150FramesLong.jpg)

***

4.  Now we go to **Scene0010Sequence** and scroll to frame **150**.  We then click on the animation layer in the mannequin and see that in my case it is frame `392`. Remember the mocap animation is NOT captured at 24 frames per second so the scale will be different.

![first cut at frame 392 in walking anitnation](../images/firstCut392.jpg)

***

5.  Now go to **Scene0020Sequence** and slip the mannequin animation to start at the next frame which in my case is `395`.

![adjust frame in scene 2](../images/moveScene2To395.jpg)

***

6.  Now in the **MasterSequence** add another **+ Shot** and select **Scene0020Sequence**.

![edit scene 2](../images/scene20Edit.jpg)

***

7. If the edit doesn't look right make sure that shot 0010 and 0020 have the **Green** start is in the right spot and that the **Camera Cuts** layer lines up and doesn't start early or late.  You can also trim both **Media** tracks as well.

![line up cuts](../images/lineUpCut.jpg)

***

8. Now you need to scrub the edit.  Is the player continuous.  Look at the game editor and see if the mannequin jumps back or foreward and make adjustements.  I decided to tweak this as well as make the first shot a bit longer.

![tweak edits](../images/tweakEdits.jpg)

***

9. Now to export the video, it is the equivalent of hitting **Play** like when you play again in Unreal. Click on the **Arrow** next to the **Play** button.  Select **New Editor Window (PIE).

![chamnge playback of game](../images/newPieEditorWindow.jpg)

***

10.  Create a new folder called `Blueprints` and press **Add/Import** and select **Blueprint Class**.

![add blueprint](../images/addBPFolder.jpg)

***

11.  Select **Actor** blueprint.

![select actor blueprint](../images/actorBP.jpg)

***

12.  Call it `BP_Game`.

![name it BP_Game](../images/bp_game.jpg)

***

13. Open up **BP_Game** by double clicking on it.  Select the **Event Graph** tab and delete **Event Tick** and **Event Actor Begin Overlap** as we will not be using these.

![delete unused events](../images/deleteUnusedEvents.jpg)

***

14. Add a new **Variable** of type **Boolean** and call it `bAutoPlay`.  Make sure it is set to **Instance Editable**. This will allow us to turn this on and off in the editor.

![add autopla boolean](../images/addedBooleanforBP.jpg)

***

15.  Drag and drop **bAutoPlay** onto the empty graph.  Select **Get Auto Play**.

![get auto play](../images/dragAutoPlay.jpg)

***

16.  Now right click on the empty graph and add a **Branch** node.  Connect the exeuction pin from **Begin Play** to the execution pin from **Branch**. Then connect the output of **AutoPlay** into the **Condition** input pin on the **Branch** node.

![add branch node](../images/beginPlayBranch.jpg)

***

17.  Right click on graph and select the **Create Level Sequence Player** node.

![add level sequence player node](../images/createLevelPlayer.jpg)

***

18. Now connect the execution pin from **Branch True** (so this will only run if the boolean is set to true) to **Create Level Sequence Player** execution pin.  Press on **Level Sequence** and select `MasterSequence`.

![select master sequence](../images/selectMasterSequence.jpg)

***

19. Pull off of the **Return Value** pin and select **PlayLooping** node.

![select play looping node](../images/playLooping.jpg)

***

20.  Connect the execution pins and **Return Value** to **Target** pins in the node chart then press the **Compile** button.

connectPlayLooping

![select play looping node](../images/connectPlayLooping.jpg)

***

21.  Close the blueprint and go back to the editor.  Drag **BP_Game** into the game scene.

![drag master sequence into game scene](../images/dragBPIntoGame.jpg)

***

22. Now drag the **Master Sequence** clip into the level so that it appears in the **World Outliner**

![drag bp game into game scene](../images/.jpg)

***

22.  Play video

***

23. Now we need to export the video so we can use it.  You could export **EXR** and assemble it in Adobe Premier or Nuke which would be prefered.  You can also just export an **AVI** in the editor.  You need to export it inside the Unreal project (it puts it in the **Saved** folder) as it doesn't have access to write data outside.

![export movie](../images/defaultMovieExport.jpg)

***

23.  Play exported movie

***

[Previous](../shot_20/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Scene 0030](../shot_30/README.md)