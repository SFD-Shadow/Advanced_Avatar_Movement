## Advanced_Avatar_Movement
A collection of various Unity packages made for tweaking and improving your movement in VRChat via avatar prefabs.  
 
> [!CAUTION]
> The Unity packages / prefabs in this repository are meant for quality of life and conceptual use.  
> If the systems in this repository cause issues to world creators, VRChat, or me, then it will be taken down.  

### Description
This repository consists of 2 Unity packages, `"Faster_Avatar_Sprint_Speed"` which allows you to sprint faster (only on desktop) and `"Faster_Avatar_Flight"` which is a box collider flight system that allows you to fly ridiculously fast in any direction (along a 2D plane).  
 
Both of the Unity packages contain a README that explains how to incorporate the system onto your own avatar.  

### How it Works
`"Faster_Avatar_Sprint_Speed"`  
This system is almost entirely animation driven, it animates your avatar's muscle groups to shove your avatar forward, which also moves your player capsule, POV, etc.  
It very slowly plays through an animation that is moving your avatar 5,000 meters forward, so if you use it for long enough, it will eventually end.  
This is possible because of the `"(VRC Animator Temporary Pose Space)"` script, which changes the position of your avatar's viewport to the current location of your avatar's head bone.  
> [!IMPORTANT]
> This system only works on desktop, and when you turn it off, you teleport backwards an equal distance to how far forward you went.

 `"Faster_Avatar_Flight"`  
This system suspends your avatar in-air using a box collider; While being suspended, a 4-axis radial can be used to send you flying in that respective direction (forward, back, left, right) relative to the direction you're looking.  
It works by constraining your avatar's main object to an object under it, and behind it. This creates an infinite feedback loop that will send you in the opposite direction of where that object is.  
It also constrains your armature to an object in front of you to offset the other object, this makes your avatar stay where it is supposed to visually, rather than being sent behind you.  
An object above the 2 offsets controls your speed, based off how far away they are from the origin, and the direction you are flying, based off that objects rotation.  
