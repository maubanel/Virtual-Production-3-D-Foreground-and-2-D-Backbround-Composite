[Previous](../mannequin_anim/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Add Shadow](../shadow/README.md)

## Adjust Lighting and Adding Geometry

1.  Now lets look at the lighting in our scene.  First, we need to adjust our **Directional Light** which in UE4 represents the **Sun**.  This light's location is irrelevant as its light rays extend to infinity.  What we want to do is match the direction of the sun in the scene that was shot.  We can look at the shadow in the scene as well as the texture used in the **Skylight** as a hint.  Enter the **Transform | Rotation** to be `-179.9, -73.99, -154.91` for **X, Y & Z**. Now our character is moving and we are not baking our lights so lets make the **Directional Light** `Movable`.

![adjust sunlight](../images/adjustSunToMatchScene.jpg)

***

2. Now that we have the sun in the correct position we need to figure out how we will project the shadow.  We will need to make a flat white ground and just seledt the shadow portion to add it to the background.  We need this ground static mesh to be at the same level of the ground in the filmed scene.  Lets make a material to start. Go to the **Materials** folder and press the **Add/Import** button and add a new material.  Call it `M_White`.

![add m_white material](../images/mWhiteMat.jpg)

***

3.  Open up the new material and add a **Vector 3** node.  Change it to `1, 1, 1` for a full white node.

![add vector 3 make white](../images/addWhiteV3.jpg)

***

4.  Now attach the output of the **Vector 3** node to the **Base Color** input in the material.  Now press the **Apply** button.  That is it for our ground plane to pick up a shadow with no added color.

![connect v3 to base color node in m_white](../images/attachToBaseColor.jpg)

***

5.  We could assign this new material to the Ground by going through the **World Outliner** and selecting it through the menu.  But it is quicker to grab the material and drop it on the ground to do this in one step:

![assign ground material](../images/assignMWhiteToGround.jpg)

***

6.  Lets do a bit more housecleaning.  The level/map that UE4 has given us is **Main**.  It is in the root of the **Content Folder**.  Lets add a folder called **Maps** and move **Main** to it.

![move main map to new folder](../images/moveMaps.jpg)

***

7.  Now go the **Edit | Project Settings | Maps & Modes** and change the **Editor Startup Map** and **Game Default Map** to `Main`. This will boot the level up into your working map every time you have to run the software or reboot.

![add main map to project settings](../images/mapsAndModes.jpg)

***

8.  Now our main map is set to the default to load with and our ground is now white.

![see white ground](../images/whiteGround.jpg)

***

9.  Now the ground is not large enough as it stands to cast a shadow from the begining of the animation to the end.  I played around with the scaling and found the **Ground Transform Scale** to be best at `2.5, 1, 2`.

![rescale ground](../images/rescaleGround.jpg)

***

10. So now any frame in the animation should have a very strong shadow.

![harsh player shadow](../images/castHarshShadow.jpg)

***

11. Now the lighting is harsh because the direcitional light is lighting at its angle and there is no light *bouncing* and reflecting back to the mannequin.  This would require ray tracing and a lot more processing power.  So we need to use the **Skylight**.  We will be using image based lighting which is a 360 HDR photo of the scene that was shot at the time of the shoot.  That way we can project light just like the scene did in the camera on the day of the shoot.  Create a **Content | Texutres** folder and **Import** the **PatioSceneHDR.HDR** texture.

![add hdr texture](../images/addPatioHDRTexture.jpg)

***

12.  Open the texture.  Notice that it is a rectalinear projection.  If you want to create this you would need to either have a 360 camera or shot with a still camera at alll angles to capture a 360 scene.  

![look at hdr texture](../images/hdrTexture.jpg)

***

13.  Now go to **Place Actors | Lights | Sky Light** and drag it into the scene. 


![add skylight to level](../images/addSkylight.jpg)

***

14.  Normally in the game we would have a blue sky with clouds and a sun.  We would use this virtual sky to drive the skylight for ambient lighting.  In this case our sky is pure white and we don't want to blast the player with light.  So we are using a cube map instead (technically this is a spherical map). Now in the **Source Type** of the Sky Light select `SLS Specified Cubemap`.  Then below select the `PatioSceneHDR` texture we just looked at. Now look how the player is being lit with image taken from the scene of the shoot.

![add cube map to skylight](../images/addCubeMap.jpg)

***

15.  Lets make two adjustements.  Change the **Cubemap Resolution** to `256` and the **Sky Distance Threshold** to `50`. 

![adjust resolution and threshold](../images/adjustSkyLight.jpg)

***

16. What is the best way to see the reflection maps? How do we know if the lighting matches the film plate?  Lets build two materials to help us determine this.

***

17.  Createa a material called `M_GrayCard`.  A gray card is 18% gray.  So we only need to feed a **Constant** node (either right click and select **Constant** or press the **1** key and left click on the graph) and set it to `.18`.  This will send this value equally into the **R G B** channels. We remove all specular by setting it to `0` and setting the roughness to `1` so that it is reflecting minimal light to mimic the gray card that was shot in the **HDR** for the rectilinear projection.

![create gray card material](../images/mGrayCard.jpg)

***

18. Now create another material called `M_Mirror`.  We plug in `1` to the base color so it is white.  We put `0` in roughness so it reflects as much light as you can can.  We then set the metallic channel to `1` which makes the surface metallic which looks like a mirror.

![create gray card material](../images/mMirror.jpg)

***

19. So we add two **Spheres** into the game and set the **Transform | Scale** to `2.0, 2.0, 2.0` for **X Y Z**.  Call one `Gray Card Ball` and the other `Mirror Ball`. Place them in the **Lighting** folder in World Outliner and add the **M_Mirror** material to one sphere and **M_GrayCard** to the other.  We immediately notice one major problem,  The reflection only works for the top half of the sphere, the bottom half is black.

![create two spheres and place in level](../images/mirrorBallGrayCard.jpg)

***

20.  Normally a game has solid ground so we don't reflect the lower part of the sphere as we use the ground texture to reflect back up.  In our case the ground is in the HDR texture we included.  We need to select the **Sky Light** and click the arrow at the bottom of the **Light** tab in the **Details** panel and you will see an option **Lower Hemisphere's Solic Color** and you will turn uncheck it so it is `false`.

![adjust lower hemisphere](../images/turnOffLowerHemi.jpg)

***

21.  Now we can see the reflection will work for the entire mannequin and not just the top half.  We will also not be darkening the character by reflecting black into the bottom half.

![reflection is now 360 degrees](../images/fixedReflection.jpg)

***

22. Now we can look from inside of the platform looking out at the gray ball.  We can compare it to the gray ball shot in the texture used in the **Sky Light**.  We can adjust the **Intensity** of the **Light Source** (sun) to match the lighting of the gray card.


![adjust brightness of light](../images/adjustBrightnessOfSun.jpg)

***

23.  Now we want the sunlight and skylight to have a general architecture that resembles the scene shot.  So there is a walkway with a roof on it so duplicate the floor and raise it for the roof.  Use the video clip as reference for how high above the head (guess if you have to).

![duplicate floor for ceiling](../images/duplicateFloorForCeiling.jpg)

***

24. Now go back tot he **Sequence** and scrub until the player is at the edge of the shadow.  Now adjust the roof so that your roof line matches the one in the movie clip.

![adjust shadow line](../images/adjustRoofShadow.jpg)

***

25. Rename the roof to `Ceiling` and make sure it is in the **Patio Geo** folder (make one if you need to for all the level geometry).  Now duplicate the **Ceiling** and rotate it 90 degrees for the back wall. Rename it 1Back Wall`.

 ![duplicate floor for back wall](../images/backWall.jpg)

***

26. Now close off the end section.  Make sure no light is leaking between the wall pieces.

 ![close off end section](../images/closeOffEndSection.jpg)

***

27.  Now scrub the scene and make any adjustments you need to.

![scrub and adjust](../images/makeAdjustments.jpg)

***

28.  Now we want a material that has a bit more roughness to match an outdoor wall and make sure it is not pure white (nothing is pure white in the natural world - though it might show up that way on film). So go to the **Materials** ffolder and create a new material called `M_Basic`.

![new m_basic material](../images/mBasicMat.jpg)

***

29.  Add a **Vector3 and make it `.9, .9, .9` as a almost white color.

![add vector 3 and make whitish to m_basic material](../images/greyVector3.jpg)

***

30.  Connect the output of the **Vector 3** to the **Base Color** of the material.  Then add a **Scalar** node and set the value to `0.6407`. Plug this into roughness.  This will make the walls and ceiling absorb more light like the walls do in teh filmed scene.

![add roughness to m_basic material](../images/addRoughnessToMBasic.jpg)

***

31.  Now drag the material to all walls and ceilings (not the floor).

![apply m_basic material to walls](../images/applyMBasicToScene.jpg)

***


[Previous](../mannequin_anim/README.md)&nbsp;&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;&nbsp;[Home](../README.md)&nbsp;&nbsp;<------>&nbsp;&nbsp;&nbsp;[Next Chapter - Add Shadow](../shadow/README.md)