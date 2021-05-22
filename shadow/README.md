## Add Shadow

1. Now our current scene does not factor in the ceiling.  We want the player's light to be affected by it.  We will need to add this to our **Actor** layer comp.  Lets start by select the **Ceiling** object in the W and going to the **Layers** tab and right clicking creating a new layer with this object.  Name it `Ceiling`.  

![adjust ceiling to self named layer](../images/addCeilingToOwnLayer.jpg)

***

2.  Now open up the **Composure** tab and select the **Actor** layer. Go to **Input | Capture Actors** and press **+**.  Then select the new **Ceiling** layer to add to this scene so that it impacts the lighting.

![add ceiling to actor comp layer](../images/addCeilingToActingLayerOnComp.jpg)

***

3.  You will notice a small difference when the player goes into and from shadows when you scrub the scene.

![dipping in and out of shadow](../images/dipsIntoShadow.jpg)

***

4. Now we need to add a layer to our composite with the player, the ground and shadow and the white sky sphere.  We also need another layer with just the player and the sky sphere but no ground/or shadow. We will then take a difference between them to extract the shadow and project it onto the background plate.  Go to **Composure** and right click on **Patio Comp** and add a third **Layer Element**.


![add third layer to comp](../images/addThirdLayerToComp.jpg)

***

5. This will be a CG layer. Name it `Shadows`.

![select another CG layer](../images/secondCGLayer.jpg)

***

6. Do the same thing again and name this third CD layer `NoShadows`.

![add another third CG layer no shadows](../images/noShadowsLayer.jpg)

***

7. Now lets select the **SkySphere** and create a self-named layer for it as well.

![add sky sphere to self named layer](../images/skySphereLayer.jpg)

***

8. 













***

--- [Next Chapter - Add Shadow Matte](../shadow_matte/README.md) ------ [Back to Home Page](../README.md)