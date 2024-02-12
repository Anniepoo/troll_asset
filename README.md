# Troll

Jamajam February 2024

A troll asset. 

## Motivating the maintainer

I built this for an asset jam and decided to keep working on it afterwards. If you use it and would like it
to be better, let me know you're using it.

This is released under the MIT License. Use it as you will. But as a "suggested donation" I'm asking if you use
him for something, please contribute. This can be small, like adding an animation, but please do something.
There's a list of suggestions below.

I understand for some users this might not be practical. Eg - if you give him a new skin texture, please
add that as an alternate skin in the textures/  directory, but if you need to give him a new rig for your
weird game engine or it would massively complicate your copyright life, then take this brother, and may
it serve thee well. 

## Revisions

 * 1.1  - Painted texture, big improvement. Added backdrop and improved lighting in thumb. 
 * 1.1.1 - packed resources (oops)
 * 1.2  - Rigged
 
## Limitations and Contributions

Some things you the user could do:

The hands are "goofy" - a PR of better hands would be welcomed

Additional skin textures would be welcomed.

The pelvis rigging is questionable. This is a big hulky guy who should do a lot of contraposta to
keep his balance, and I'm not sure the current rig is the best way forward.

In many places his topology isn't well reduced. A retopo is a big project but would be awesome. Be aware that
facial animation is on the roadmap

He has no teeth. There's a minimal mouth interior, but the little mouth could become a big troll-y "going to eat you" mouth
with jaggy monster teeth.



## Roadmap

 * Add a couple accessories - a hammer and a rock
 * Add animations
  * Walk
  * Idle
  * Growl
  * Pet kitty
  * Menace with rock
  * Menace with hammer
  * Blacksmith with hammer
  * Throw rock
  * Swing hammer
  * Preston mouth shapes
  * facial animations - smile, angry, etc. as blendshapes
 
## Parts
 
 * troll (and trollmesh) are marked as assets
 * looktarget is an independent object where the troll looks (asset)
 * cave, and all lights and camera are just to make the thumbnail

## Rig usage

Note that the troll isn't quite standing in the undistorted stance. In particular, the IK targets have moved things a bit.
If you're going to mess with the mesh, I recommend turning off the IK before doing so.

The eyes track the looktarget. If you want them to track another object, change the target in eyepointer bone's bone constraint.

The fingers all grip together. Move the X axis of the ring (outside, no pinkies) and the others move.

The armature has 4 custom properties that turn on and off IK for the limbs. These are 'factor', so you can make a transition,
say from the troll leaning on a wall with one hand to some other pose, by putting a curve in this custom factor's animation.

## To rebake the procedural texture

I started with a procedural material called 'body', (and some for parts like eyes),
then baked it to images and manually altered the images

To redo this, obviously save work elsewhere first, then 

* Select trollmesh
* Change the material in slot 1 to body
* in shader editor select the troll_diffuse texture node in the shader graph (bizarre, but yup, do it)

* Properties -> Render -> render engine : Cycles
* Properties -> Render -> Sampling -> Render : I used 2048 samples and 15 sec time limit
* Properties -> Render -> Bake -> Bake Type : diffuse
* Properties -> Render -> Bake -> Contributions : uncheck Direct and Indirect, check Color
* click the bake button, then check that the troll_diffuse image has the diffuse color in it

* Select trollmesh
* Change the material in slot 1 to body
* in shader editor select the troll_bump texture node in the shader graph (bizarre, but yup, do it)
* Properties -> Render -> Bake -> Bake Type : normal
* click the bake button, then check that the troll_normal image has the normal map in it

* Save the images troll_diffuse and troll_normal externally and edit
* Select trollmesh
* Change the material in slot 1 to troll_from_images




