# Troll

Jamajam February 2024

A troll asset. 

## Revisions

 * 1.1  - Painted texture, big improvement. Added backdrop and improved lighting in thumb. 
 * 1.1.1 - packed resources (oops)

## Roadmap

 * Add constraints to mesh bones
 * Add hand and foot IK
 * Add a couple accessories - a hammer and a rock
 * Add animations
  * Walk
  * Idle
  * Growl
  * Pet kitty
  * Menace with rock
  * Menace with hammer
  * Throw rock
  * Swing hammer
  * Preston mouth shapes
  * Expressions - smile, angry, etc. as blendshapes
 
## Parts
 
 * troll (and trollmesh) are marked as assets
 * looktarget is an independent object where the troll looks (asset)
 * cave, and all lights and camera are just to make the thumbnail

## Rig usage

The eyes track the looktarget. If you want them to track another object, change the target in eyepointer bone's bone constraint.

The fingers all grip together. Move the X axis of the ring (outside, no pinkies) and the others move.


TBD - pole targets

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




