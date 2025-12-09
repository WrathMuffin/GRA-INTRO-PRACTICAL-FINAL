# GRA INTRO PRACTICAL FINAL
PRACTICAL FINAL, Charleen Chu, 100784133

Shaders implemented:
- Stencil for the bridge
- Polygon surface deformation for the water

Additional 2 shaders are used to enhance the water:
- Reflection (first half)
- Scrolling (second half)

Watched a short gameplay of the game scene in question:

https://www.youtube.com/watch?v=rfOm8o0-GLQ

# What was done:
I watched a short video to see how it looks like in realtime to get refrences.

I have added the stenctil shader and polygon surface deform shader. For stencil, I used 2 shaderlab scripts: stencil front, and stencil readhole.

These two are then applied to two object: the bridge supports and 8 planes infront of it. For polygon surface deformation, I put it on a plane below the bridge, this is the basis of my water shade.

I also duplicated and add onto the playrcontroller because i wanted to give it more of a platformer movement (though it's pretty janky for the jump, but I'm not too focused on that since I'm more focused on the shaders themselves).

For my 2 additional shaders, I decicded to add them to the water base as I want to improve on its looks: relfection and scrolling foam and textures.

# How it was done:

  # Stencil:
For stencils scripts, I have grabbed the two shaderlab scripts from canvas. I applied these materials to two objects: the bridge support have the readhole script, and the 8 planes that uses the stencil front. By placing the 8 planes infront of the solid cube, I can see through the cube to see the player.

Bridge supports:

<img width="1124" height="393" alt="image" src="https://github.com/user-attachments/assets/948b73cd-d413-4e54-b20e-833bd89050ef" />

8 planes:

<img width="1108" height="398" alt="image" src="https://github.com/user-attachments/assets/2dde9716-12dc-4cb8-9de3-476111745623" />


Since the bridge in the image is dark purple, as well as taking place at night (it seems), I decided to modify the stencil readhole by adding a color propety that was then multiplied to the base texture to change the color.

<img width="455" height="134" alt="image" src="https://github.com/user-attachments/assets/62c732c9-2be1-4dd1-afba-fac295341d65" />

<img width="548" height="181" alt="image" src="https://github.com/user-attachments/assets/71875140-ed72-4d97-b73d-5db3148629e8" />


When I built the scene, stencil shaders didn't appear, after asking, I removed the "Render" in UniveralRenderPipeline, so now it is UniversalPipeline. I did this on both stencil shaders too.

<img width="510" height="226" alt="image" src="https://github.com/user-attachments/assets/3730cae7-be34-4874-afce-ad81e1e1aab5" />

<img width="473" height="197" alt="image" src="https://github.com/user-attachments/assets/3bc203f7-3605-489e-82f6-1f4260de023a" />


  # Polygon surface deform + scrolling + reflection:
This is applied to the plane to represent water under the bridge. For this shader, I decided to do it in shadergraph as I need constant visual feedback for testing (which the preview in the graph is really helpful).

Shadergraph for the water:

<img width="833" height="370" alt="image" src="https://github.com/user-attachments/assets/c07d0747-b295-4073-9e4c-db3049426247" />

<img width="744" height="371" alt="image" src="https://github.com/user-attachments/assets/7b9b2fee-81dd-4dbd-bdb9-ac9c9ee9949e" />

<img width="766" height="388" alt="image" src="https://github.com/user-attachments/assets/01e5ec0b-7170-48ef-a6f5-088b070d540b" />

# Why it was done:

Stencil acts as a window/x-ray sort, and since the bridge is detailed in terms of structure, I decided that putting these stencil planes on a cube lets me create these strcucture similar to the wario brigde, without having open blender and modeled this net-like structure of the beams.

Water is naturaly reflective, so having reflection allows easier identification by the player that this is water. Since wario also dies (i think) in the water, having it moving and swaying around convays a sense of danger and powerful waves from the sea. Having scrolling textures for the foam and water it self conveys movements and using noise makes it chaotic and more random in general.

More info in shadergraph notes.
