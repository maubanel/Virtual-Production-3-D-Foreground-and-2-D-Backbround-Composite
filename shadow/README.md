## Add Shadow Matte

1.  Now lets look at the lighting in our scene.  First, we need to adjust our **Directional Light** which in UE4 represents the **Sun**.  This light's location is irrelevant as its light rays extend to infinity.  What we want to do is match the direction of the sun in the scene that was shot.  We can look at the shadow in the scene as well as the texture used in the **Skylight** as a hint.  Enter the **Transform | Rotation** to be `-179.9, -73.99, -154.91` for **X, Y & Z**. Now our character is moving and we are not baking our lights so lets make the **Directional Light** movable.

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










***

--- [Next Chapter - Add Shadow Matte](../cg_character_ii/README.md) ------ [Back to Home Page](../README.md)