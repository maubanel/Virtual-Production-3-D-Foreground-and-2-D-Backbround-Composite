## Add Shadow

1.  Now lets look at the lighting in our scene.  First, we need to adjust our **Directional Light** which in UE4 represents the **Sun**.  This light's location is irrelevant as its light rays extend to infinity.  What we want to do is match the direction of the sun in the scene that was shot.  We can look at the shadow in the scene as well as the texture used in the **Skylight** as a hint.  Enter the **Transform | Rotation** to be `-179.9, -73.99, -154.91` for **X, Y & Z**. Now our character is moving and we are not baking our lights so lets make the **Directional Light** `Movable`.

![adjust sunlight](../images/adjustSunToMatchScene.jpg)

***







***

--- [Next Chapter - Add Shadow Matte](../shadow_matte/README.md) ------ [Back to Home Page](../README.md)