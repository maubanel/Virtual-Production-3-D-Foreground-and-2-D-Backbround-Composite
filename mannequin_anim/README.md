## Add Animation to Camera and Mannequin

1.  Now we need to animate the camera and the actor in the scene so it matches the camear path originally shot.  Make sure you have selected **Scene0010Sequence** and press **+ Track** and select a **Camera Cut Track**.

![add camera cut track](../images/addCameraCutTrack.jpg)

***

2.  Now we need to assign a camera to the cut track.  Press the **+ Camera** button and select the only camera we have in the scene **CineCamera**.
![add game camera to camera cut track](../images/addCameraToCuts.jpg)

***

3.  We need to delete all elements under the camera (???).  UE4 does not have the ability to derive a virutal camera position from a film plate.  You need to use software like ****Nuke** as well as numerous other options to get a camera FBX.  This has been done by Unreal for us so we can just import it (this does not come from the camera footage).  Right mouse click on **CineCamera** and select **Import**.


![press import button on camera in sequencer](../images/pressImportButtonForCamTrack.jpg)

***

4. Pick the file **tracked_cam.fbx**.

![select camera track fbx](../images/trackedCamFBX.jpg)

***

5.  Leave the defaults in the pop-up and select the **Import** button.

![leave default and press import](../images/leaveDefaultImport.jpg)


***

6.  Now make sure the **CineCamera** has a **Camera Component** and its transform has keyframes for **Location** and **Rotation**.
![make sure camera has translation and rotation data](../images/translationAndRotationCamTrack.jpg)

***

7.  Now when you hit play you will notice the camera move.  You should see the camera track appear and the camera moving around it.  Now this doesn't do us much good without animation.  Lets add the mannequin to the scene next.

![play to ensure camera track appears](../images/playCameraTrack.jpg)

***











--- [Next Chapter - Add CG Character To Composite II](../cg_character_ii/README.md) ------ [Back to Home Page](../README.md)