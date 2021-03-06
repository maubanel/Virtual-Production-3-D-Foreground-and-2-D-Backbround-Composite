[Previous](../master/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Home](../README.md)

## Third and Fourth Cut

1.  You should know enough about the process by now to complete the third and fourth cut.  You will import the third set of plates, create a new **Media Image Sequence** for the background and the lens distortion.  Add the animation into the scene and import the motions capture.  Drag the camera from the **World Outliner** and import the 3rd camera track to match the last camera. You will notice that the mannequin moves in front of the pillar and the chairs and should be behind them.

![import new files into new scene0020 folder](../images/scene03Overview.png)

***

2.  Now I forgot to adjust the aperature, focal length and focus distance.  We need to make sure that each scene has these three **Camera Components**.  If not press **Camera Component +** and add a `Current Aperture`, `Current Focal Length` and `Focus Settings | Manual Focus Settings | Manual Focus Distance`.

![add three camera components](../images/threeCameraComponents.jpg)

***

3.  The three scenes need the following settings.  The setting for Scene 1 and 4 are the same.

![scene 10 camera settings](../images/scene10CameraSettings.jpg)
![scene 20 camera settings](../images/scene20CameraSettings.jpg)
![scene 30 camera settings](../images/scene30CameraSettings.jpg)
***

4. You will need to import a **Matte** layer into the sequence and the composite for shot three.  Create a new **Media Image Sequeqnce** and call it **Shot0030Matte**.  Add another **Media Layer** to the **Shot0030Sequence**.  Create a new **Media | Media** texture.

![add thrid media texture](../images/thirdMediaTexture.jpg)

***

5. Now open up the **Component** tab and add a new **Media Layer** and call it `Matte`.

![add matte layer to comp](../images/matteMediaLayer.jpg)

***

6. Now we need to adjust our compositing material to add this matte.  Open up **M_Composite** and add a **Texture Sample Parameter 2D** node to the chart.  In the Unreal video they mentioned initially wanting two matte layers but ended up only using one.  So we can add the **B G** layer together.  We invert this layer to get the matted section to be black with a **One Minus** node.  We then feed it into the **Matte** pin of the **Over** node.

![create a matte set of nodes in m_composite](../images/mCompositeMatte.jpg)

***

7.  Don't forget to add the source and media texture to the **Matte** track in the **Sequencer**.

![assign source and matte to sequence](../images/mediaSourceAndMatte.jpg)

***

8.  You should get it so that the player appears behind the objects:

![matte workign in game](../images/matteWorks.jpg)

***

9.  For the final cut we do go back to the first view.  But we can't use the same sequence as the start time is wrong.  We need to duplicate it instead.

![duplicate scene 10](../images/duplicateScene10.jpg)

***

10.  Retrim the final shot so that the animation starts at the point you want it to for the final cut.

![duplicate scene 10](../images/moveStartTrack.jpg)

***
11.  Export the final movie.

![duplicate scene 10](../images/exportFinalMovie.jpg)

12. Now I went to export the final clip (even though it played back fine) and I had a matte showing up in other scenes without a matte layer.

![bad matte in wrong shot](../images/unwantedMatte.jpg)

***

13.  If you have the same problem lets assign a blank matte to the other three scenes. In **Scenes** ad a **Img Media Source** layer and copy over any of the matte layers into the **Plates** folder without importing them (like before).  The matte folder for scene 10 and 20 are the same so you only need one.  Then point the new image source to this one file.

![add empty matte data source](../images/emptyMatteSource.jpg)

***

14.  Now you can add a **Media** track to the first, second and fourth cut. Don't forget to assign the media texture to it.

![assign media matte texture to added media layers in three shots](../images/assignNewMatteLayer.jpg)

***

15.  Export the movie one final time.

![export movie again](../images/defaultMovieExport.jpg)

***

16.  So the movie should look something like this.


https://user-images.githubusercontent.com/5504953/120218419-53b31a80-c1ff-11eb-9377-3e96a42359a5.mp4

***

[Previous](../master/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Home](../README.md)
