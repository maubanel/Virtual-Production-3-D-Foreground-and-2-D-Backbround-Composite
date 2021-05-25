## Add CG Character

1.  We will use the UE4 supplied mannequin to our game.  To do this we will have to migrate it from another project.  Press **File | Save All** and run the **Epic Launcher** again.  Create a new project and this time select the **Game Type**.  Then select **Third Person** template as this will contain the player mannequin.

![create new composite](../images/thirdPersonGameProject.jpg)

***

2. Now we can keep all the defaults and create this project which we will later delete. 

![addjust clip and play](../images/createTempProject.jpg)

***

3. Once this project builds and loads go to the **Content | Mannequin | Mesh** folder and see the new **SK_Mannequin_Female**.  This is the character we will migrate to our project.

![see female mannequin](../images/femalmanequin.jpg)

***

4. Now right click on **SK_Mannequin_Female** and select **Asset Actions | Migrate...**.

![migrate mannequin](../images/migrateMannequin.jpg)

***

5. UE4 is smart enough to know that this character has a mesh, a material, a skeleton and many other assets needed for it to run.  We will need all the attached components so we will just select **OK**.

![migrate all related files](../images/ue4SelectsAllNeedeFiles.jpg)

***

6. Now the windows finder appears.  The important thing to do in Migrating is regarding the folder you put it in.  It has to be in the new project you are migrating to in the **Content** folder.  Do not put it in a higher or lower folder in the hei

![select content folder](../images/selectContentFolder.jpg)

***

7. Now reopen our compositing project and notice that the mannequin succesfully imported with all the required assets to render the full mannequin.


![mannequin imported](../images/mannequinImported.jpg)

***

8. Add the mannequin to the level.  This is a skeletal mesh called **Content | Mannequin | Character | Mesh | SK_Mannequin_Female**.  Make sure to put it in Transform Location `0, 0, 0`, Rotation `0, 0, 0` and Scale `1, 1, 1`.

![mannequin imported](../images/addMannequinToLevel.jpg)

***

9. Now in an empty level Unreal adds a bunch of default items we will not need.  Control Select **Atmospheric Fog, Player Start, Sky Sphere, Skylight, SphereReflectoinCapture** and right mouse click and select **Edit | Delete** to remove these from the scene.

![remove unneeded level actors](../images/deletePeripheralObjects.jpg)

***

10. Now we need to add a camera that is the same as the one that shot the scene.  Add a **Cinematic | Cine Camera Actor** to the scene.  Rotate and position it so it frames the mannequin.  Notice that when you select this camera in the world outliner you will see the viewport. Rename this actor to `CineCamera`.

![add cine cam](../images/addCineMac.jpg)

***

11. Now we need to match the key camera settings so that the virtual camera is as identical as possible to the real one used. First adjust the sensor size.  Go to **Filmback** and select `Custom...`. Change the **Sensor Width** to `35.599998 mm` and **Sensor Height** to `20.025 mm`.  Notice that the **Sensor Aspect Ration** is updated. In **Focus Settings** set the **Manual Focus Distance** to `426.0001`.  Set the **Current Focal Length** to `35.085999` and **Current Aperture** to `9.0`.

![match camera settings](../images/matchCamSettings.jpg)

***


11.  Now this camera is going to be used in our comp layer for CGI.  Go to the **Composure** tab and right click on the parent component and select **Add Layer**.

![add new comp layer](../images/addNewCompLayer.jpg)

***

12. Now the first layer was a video and a media layer.  The manequin is in UE4 CG so select a **CG Layer**.

![select CG layer](../images/selectCGLayer.jpg)

***

13.  Name this new comp layer **Actor**.

![name layer actor](../images/nameActor.jpg)

***


14.  Now we need to tell composure what cine camera to use.  Click on **PatioComp** and click on **Input | Target Camera Actor** and select `CineCamera`.

![add cinematic camera to composite](../images/cineCamToComp.jpg)

***

15. Now lets add a sphere to represent the sky.  The team that shot this patio scene also shot a 360 panorama that we can use for image based lighting (IBL).  So our sky will be pure white to not add any effects to the IBL. Go to **Basic | Sphere** and add one to the level.   Make sure to put it in Transform Location `0, 0, 0`, Rotation `0, 0, 0` and Scale `1, 1, 1`

![add sphere for sky](../images/addSphereForSky.jpg)


***

16. Now we need to use this as the sky so we need to make it a **LOT** larger. Change the **Transform | Scale** to `1000, 1000, 1000`.  Now the object is very large. Also rename the sphere to `Sky Sphere` and take the time to organize all your scene objects into logically named folders.  

![scale sky sphere](../images/scaleSkySphere.jpg)

***

17.  Select the **Materials** folder and press **Add/Import** and create a new **Material** and call it `M_Sky`.

![add sky material](../images/addMSkyMaterial.jpg)

***

18.  Open the new material and right mouse click on the open graph.  Add a new **Const 3 Vector** node to the graph.

***

![add const 3 vectuor](../images/addCosnt3Vector.jpg)

19. Now double click on the black color inside this 3 color node.  Set the **RGB** to `1, 1, 1` which makes this color white.  Press the **OK** button.

![make color white](../images/changeToWhite.jpg)

***

19.  Now connect the output of the white color to the **Base Color** and **Emmissive Channel**.  We will create a base color of white and make sure that the sky is emissive (it is lit) as this is a daytime shot on our plate.

![connect material pins](../images/connectMatNodes.jpg)

***

20. Now this sphere is pointing outwards and we are inside it.  So the surface normals of the sphere are pointing in the wrong direction.  We do not need to take this into Maya and edit it we can just select the **Material Node** and set the **Two Sided** radio to `Selected`.  As usual you **ALWAYS** need to press **Apply** so that the material is processed and works as you programmed.

![make material two sided](../images/twoSidedMat.jpg)

***

21.  Now drag the **M_Sky** material into the **Material** slot of **SkySphere** in game. Notice that the sky now turns white!

![add material to sky](../images/setSkyMaterial.jpg)

***

--- [Next Chapter - Add CG Character To Composite II](../cg_character_ii/README.md) ------ [Back to Home Page](../README.md)