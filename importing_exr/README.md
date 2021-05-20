## Importing EXR Sequence 

1.  First lets get started by creating a composite.  Think of this as like a **After Effects** project where the 2-D compositing will take place. Select the **Composure** tab at the bottom.  If this does not show up go up to **Window | Composure Compositing**.  If this does not show up you do not have the plug-in installed. **Right Mouse Click** in the empty area in the tab and select **Create New Comp**.

![create new composite](../images/newComp.jpg)

***

2.  Select an empty composite by pressing the **Empty Comp Shot** button.
![select empty comp shot](../images/emptyCompShot.jpg)

***

3. Rename this layer **Patio Comp**.

![rename to patio composite](../images/renamePatioComp.jpg)

***

4.  Right click on the **PatioComp** name and select **Add Comp Layer**.

![add comp layer](../images/addCompLayer.jpg)

***

5. Now we will be adding the background film plate that was shot in camera.  Press the **Add Media Plate** button.

![add media plate](../images/addMediaPlateLayer.jpg)

***

6. Now it looks like nothing happened.  In the Unreal editor a lot is hidden inside these little arrows that expand.  Press the **Arrow** next to the name of the comp and you will see the media plate.  Rename it to `BackgroundPlate`.

![rename background plate](../images/renameBackgroundPlate.jpg)

***

7.  This sequence is based on **Epic's** [documentation](https://docs.unrealengine.com/en-US/WorkingWithMedia/MediaFramework/HowTo/ImgMediaSource/index.html).  First lets create a new folder called `Plates`. First to see our folders in our project click on the little arrow in the **Content Browswer** tab.  Right click on **Content** and select **New Folder**.

![add new folder](../images/addPlateFolder.jpg)

***

8. Rename the folder to **Plates**.

![rename folder to plates](../images/renameToPlates.jpg)

***

9.  Now normally we always import assets through the Unreal interface.  This is the **ONE** exception.  We will be adding the **.exr** files manually into the project and they will **NOT** show up in the browser. Right click on plates and select **Open In Explorer**.

![right click on plates and select open in explorer](../images/showPlatesInExplorer.jpg)

