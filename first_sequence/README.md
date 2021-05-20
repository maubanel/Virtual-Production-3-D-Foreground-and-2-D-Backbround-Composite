## First Level Sequence

1.  Normally we would use a **Media Player** actor to play the video.  Since we are not using a game engine to play a cut scene we will be just using it to play back a scene.  In UE4 it is called **Sequencer**.  This allows us to play back a clip without the media player object.  Go to the **Scenes | Scene0010** folder and click on the **Add/Import | Animation | Level Sequence** element. 

![add a level sequence](../images/levelSequence.jpg)

***

2. Rename the file to `Scene0010Sequence`.

![rename sequence](../images/scene10Sequence.jpg)

***

3. Press the **+ Track |  Media Track** to the sequence you just created.

![add media track to sequence](../images/addMediaTrack.jpg)

***

4.  Press the **+ Media** and add the **Scene0010** image media source to the track.

![add scene 10 to track](../images/addScene10ToTrack.jpg)

***

5. Now we cannot play back the image media source directly.  We have to put it through a **Media Texture**.   Go to the **Scenes | Scene0010** folder and click on the **Add/Import | Media | Media Texture** element. 

![add media texture](../images/addMediaTexture.jpg)

***

6. Rename the media texture to: `Scene0010MediaTexture`.

![rename media texture](../images/renameMediaTexture.jpg)

***

7. Select the **BackgroundPlate** in the World Outliner.  Drag the newly created media texture to the **Inputs | Media Source**.  Notice when you drag it on top of it the area has a green dashed outline.  This means that it will accept this actor to point the texture to this compositing level.

![add media source](../images/addMediaTextureToBackgroundPlate.jpg)

***

8. If you click on **BackgroundPlate** in the World Outliner, you will see a window pop up, but it is black.  We still haven't pointed our clip to this compositing layer.  We also have not told the compositor how to display the image.

![blank background plate](../images/emptyBackground.jpg)

***

9. Go to the world outliner and lets set up the composite so it can display our newly created background.  Select **PatioComp** the press the **+** button in **Transform/Compositing Passes**.

![add compositing pass](../images/addTransformPass.jpg)

***

10. Now all compositing happens through a material.  Lets create one but first add a **Materials** folder to the project.

![add materials folder](../images/addMaterialsFolder.jpg)