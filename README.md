# Unreal Minimum Viable Flecs
Minimum viable Flecs entity component system implementation in Unreal Engine.

Intended as a super simple starting point / reference for using Flecs in Unreal.


* Flecs v4.1.2 & Unreal Engine 5.4
* Simple
* It does a thing
* ISM based entity rendering
* Uses the Flecs c++ API
* [Flecs Explorer](https://github.com/flecs-hub/explorer) integration
* Basic c++ entity <--> blueprint communication example

Huge thans to [Red J](https://github.com/jtferson) for his [flecs space battle tutorial](https://jtferson.github.io/blog/quickstart_with_flecs_in_unreal_part_1/), check it out if you want a deeper dive
## Demo: Corn gun

Shoot to spawn corn entities that grow.

Look at the corn entity in game do display it's current growth value.

Open [Flecs Explorer](https://www.flecs.dev/explorer/) to inspect entities




![image](https://user-images.githubusercontent.com/1968543/210174464-71ec9862-891d-439b-925b-19dea5617324.png)
![alt text](demo.gif "Logo Title Text 1")

[Corn Model](https://sketchfab.com/3d-models/corn-corn-corn-10187bc37c9e42ef8770b28452ee7cd3) by [Tiia Tuulia
](https://sketchfab.com/tiiatuulia)


## Why

Sometimes you need an ECS to make heavy stuff work performance-wise, Unreal doesn't have one built-in.

[Mass](https://docs.unrealengine.com/5.1/en-US/mass-entity-in-unreal-engine/) is still experimental (but if you want to use it [check out this](https://github.com/Megafunk/MassSample))

Flecs is a well built performant solution for doing ECS used by [ConfettiFX's The Forge](https://github.com/ConfettiFX/The-Forge#release-153---october-5th-2022---steamdeck-support--app-life-cycle-changes--shader-byte-code-offline-generation--gtao-unit-test--improved-gradient-calculation-in-visibility-buffer--new-c-containers--reorg-tf-directory-structure--upgraded-to-newer-imgui--the-forge-blog) who are powering Bethesda's next-gen game Starfield and a bunch of other projects.

Flecs has [great documentation](https://www.flecs.dev/flecs/#/?id=getting-started) and an [active community](https://discord.gg/BEzP5Rgrrp) where you can ask your questions

It's hard to find starting points that are simple.

## Updating to newer flecs releases

If there are no breaking changes all you need to do is replace 

[flecs.h](Source/FlecsLibrary/Public/flecs.h) and
[flecs.c](Source/FlecsLibrary/Private/flecs.c)
With the updated .h and .c files from the [Flecs Github](https://github.com/SanderMertens/flecs) repo and comment out `#define flecs_STATIC` On the first line of [flecs.h](Source/FlecsLibrary/Public/flecs.h).

After a rebuild you should be good to go.
