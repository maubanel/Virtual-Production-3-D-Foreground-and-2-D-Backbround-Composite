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








***

--- [Next Chapter - Level Sequence Player](../first_sequence/README.md) ------ [Back to Home Page](../README.md)