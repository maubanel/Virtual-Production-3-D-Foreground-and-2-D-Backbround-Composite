## Add Master Sequence and Create First Edit

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

![change play to ](../images/newPieEditorWindow.jpg).jpg

***






***

--- [Next Chapter - Scene 0030](../shot_30/README.md) ------ [Back to Home Page](../README.md)