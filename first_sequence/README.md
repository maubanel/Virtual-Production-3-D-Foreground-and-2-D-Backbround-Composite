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

***

11. Go to the **Materials** folder and press **Add/Import | Material**.

![add new material](../images/addMaterial.jpg)

***

12. Rename this material to `M_Composite`.  Double click to open the **Material Editor**.  Right mouse click in the empty graph and type `TextureSampleParameter2D`.  Select this node.

![add new material parameter 2d](../images/addTexture2D.jpg)

***

13.  Rename this node to `Background`.

![rename node to background](../images/renameToBackground.jpg)

***

14. Connect the **RGB** pin from **Background** to the **Emmisive Color** pin in **M_Composite**.  This is an emissive texture as there is no scene that this element lives in and there is no light.  So this is a self lit texture otherwise it would appear black.

![connect emissive color pin](../images/connectToEmissionColor.jpg)

15. Now the material we just created will have no effect untile we press the **Apply** button:

![apply material](../images/applyMaterial.jpg)

16. Now we can  select **PatioComp** in the World Outliner and add the new material to the **Transform/Compositing Passes** material slot. 

![assign material to transform](../images/addMaterialToComposure.jpg)

***

17. Now this original camera shot the footage at 24 frames per second.  Our sequence default is 30.  Correct this now:

![change framerate to 24fps](../images/twentyFourFPS.jpg)

***

18.  Now we still have not told **Sequencer** that the movie we imported ties to the **Media Texture**. Right click on the sequence **Media** track and select **Edit Section**.  Now make sure the **Media Source** has `Scene0010` added to it and link the **Media Texture** to `Scene0010MediaTexture`.

![attach texture to media in sequence](../images/linkMediaTexture.jpg)

***

19. Now we can see that the media texture is no longer black and we can see the clip behind it:

![media texture now working](../images/mediaTextureLinked.jpg)

***

20.  Add a **Composite** folder to the **World Outliner** then drag the **BackgroundPlate** and **PatioComp** into this folder.

![add composite folder and add objects](../images/addCompositeFolder.jpg)

***

21. Now the sequence has 488 frames in it. So click on the bottom left and set the length to `0488` and the length displayed to the user as `0644`. Unreal right now does not expand the clip to fit the length.  So click the begining and end to expand it to fit between **0** and **488**.  Now select **PatioComp** in World Outliner and press the **Play** button.  You now see that the movie that was shot play!

![create new third person game project](../images/adjustClip.jpg)

***

--- [Next Chapter - Add CG Character To Composite](../cg_character/README.md) ------ [name the new project](../README.md)