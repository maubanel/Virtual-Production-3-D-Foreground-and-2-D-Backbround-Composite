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






--- [Next Chapter - Level Sequence Player](../first_sequence/README.md) ------ [Back to Home Page](../README.md)