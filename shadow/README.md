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

Now we need to add a layer to our composite with the player, the ground and shadow and the white sky sphere.  We also need a layer with just the player and the sky sphere but no ground/or shadow. 







***

--- [Next Chapter - Add Shadow Matte](../shadow_matte/README.md) ------ [Back to Home Page](../README.md)