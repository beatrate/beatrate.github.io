---
layout: default
permalink: /
endOfDaysScreenshots:
    - "/assets/img/eod-screenshot1.png"
    - "/assets/img/eod-screenshot2.png"
    - "/assets/img/eod-screenshot3.png"
catsPortalsScreenshots:
    - "/assets/img/cats-portals.png"
---

# Beatrisa Ivanova aka Beatrate
**Unity Developer**

email: [beatrisa.ivanova.dev@gmail.com](mailto: beatrisa.ivanova.dev@gmail.com)

Github: [https://github.com/beatrate](https://github.com/beatrate)

Itch: [https://beatrate.itch.io/](https://beatrate.itch.io/)

## About Me
Hi! My name is Beatrisa and I'm a game developer. I've been working in gamedev since 2018.
I'm a generalist Unity developer with experience in most areas of development from prototyping
to graphics programming.

### Skills:
* Unity
* Unity tools
* C#
* Shaders programming in HLSL, GLSL, Shader Graph
* UI integration with uGUI
* ECS
* Job system
* Addressables
* FMOD
* DOTween
* Git
* Blender

## Projects
### cats;portals
<div class="screenshot-row">
    {% for screenshot in page.catsPortalsScreenshots %}
    <div class="screenshot-row-element">
        <img src="{{ screenshot }}">
    </div>
    {% endfor %}
</div>
[Itch](https://beatrate.itch.io/catsportals)

**cats;portals** is a linear **3d platformer** prototype.

This prototype was a personal project for testing systems useful for future projects.

I developed a **responsive platforming character controller** with support for jumping, dashing, bouncing up the walls and climbing ledges.
I also implemented bouncy level objects and a modular system for linking buttons to toggleable objects such as air fans that can lift up the character.

One of the big challenges of the project was development of a **modular saving system**
that doesn't require boilerplate for adding saving to new components. I developed **QuirkySave**, a reflection based saving system
that can **save development time thanks to a simple workflow** that only requires adding a special attribute to each field of a component that needs to be saved.

The project required combining 3d environment with 2d characters. For this goal I developed the **KiwiSprite** package that allows **rendering 2D sprites in 3D** using GPU-based billboards.
Mecanim isn't well suited for easy management of 2d animations so I also developed a custom animator that allows simply switching between animations at runtime with no transitions.
This approach let me **save production time by removing unnecessary Mecanim setup** from the workflow.

### LIMINAL;WASTE
<div class="screenshot-row">
    <div class="screenshot-row-element">
        <video controls="false" allowfullscreen="false" muted="true" loop="true" autoplay="true">
            <source src="/assets/video/rails-demo.mp4" type="video/mp4">
        </video>
    </div>
</div>
[Itch](https://beatrate.itch.io/liminalwaste)
[Reference code for ledge detection](https://github.com/beatrate/LedgeDetector)

LIMINAL;WASTE is a **first person parkour** prototype.
The goal for the project was to explore approaches to creating a **freeform movement based game** where every single object is climbable.

I was mainly inspired by the Dying Light GDC talk called **"Parkour: How to Improve Freedom of Movement in First-Person Games in 20 Simple Steps"**.

I had to develop a way to make every object in the world climbable without any extra setup from a game designer. For this I needed to implement robust
ledge detection. Considering the lack of strict constraints on what could be considered a ledge, weeks of R&D were required.

The final approach I implemented consisted of multiple steps:
* Casting a ray of raycasts to sample nearby obstacles. 
* Applying multiple levels of constraints between potentially viable ledge points such as angle limits between valid ledge points, angle of an edge relative to the player direction and so on.
* Connecting viable ledge points in view space.

<div class="screenshot-row">
    <div class="screenshot-row-element">
        <img src="/assets/img/detection.png">
    </div>
</div>

This approach with enough parameter tweaking has produced an acceptable result where the player **character could climb up any reasonable ledge**.
The goal was reached and **game design setup has been optimized** since a game designer wouldn't need to do extra work for adding extra obstacles to an open map besides
just dragging it onto the scene.

### End of Days: Survival
<div class="screenshot-row">
    {% for screenshot in page.endOfDaysScreenshots %}
    <div class="screenshot-row-element">
        <img src="{{ screenshot }}">
    </div>
    {% endfor %}
</div>
[App Store](https://apps.apple.com/us/app/end-of-days-survival/id1478121968)
[Google Play](https://play.google.com/store/apps/details?id=com.BlackVoidStudios.EndOfDays)

**End of Days: Survival** is a card-based game with **branching narrative** and **RPG elements**.

I was the lead developer on the project and was responsible for **gameplay**, **tools** and **UI implementation**.

I developed custom tools for card creation where a designer could freely **create new cards with no involvement from a programmer**.
With these tools a designer can specify conditions for each random card appearance, set up card effects that affect player stats,
randomize outcomes, give a new card to the player depending on player's choice.

I developed a **conversion tool** from the old gameplay framework to the new one and **sped up the production** by removing the need to recreate all card gameplay settings manually.

The project required **creating a lot of custom UI components** since the builtin layout components proved to be lacking when it comes to tricky responsive layouts.

###  Reliable Mecanim Events
[Github](https://github.com/beatrate/ReliableMecanimEvents "Github")

Enhanced **animation events** for Unity's animator.

Allows attaching events to animator states.

Supports regular events, events that will always be called even if the state is transitioned out of, events that can be triggered on each loop or only once.

Provides allocation free animation events with no SendMessage() usage.

### Quirky Save
[Github](https://github.com/beatrate/QuirkySave "Github")

Modular reflection based **saving system**.

Allows adding saving to any component by applying an attribute to a serialized field.

### Kiwi Sprite
[Github](https://github.com/beatrate/KiwiSprite "Github")

Package for rendering 2d sprites in 3d levels using **GPU-based billboards**.

Supports multiple billboarding methods.

Useful for 3d games mixing 3d models and billboarded sprites.

### PeachFSM
[Github](https://github.com/beatrate/PeachFSM "Github")

A **hierarchical fixed state machine** library for Unity.

Allows nested state machine states, state transitions between state hierarchies, forwarding game
events to states.

## Tech Art
<hr>
<div class="showcase">
    <div class="showcase-slide">
        <video class="videogif" controls="false" allowfullscreen="false" muted="true" loop="true" autoplay="true">
            <source src="/assets/video/lighto.mp4" type="video/mp4">
        </video>
        <h3>Stencil based world colorizing shader</h3>
    </div>
    <div class="showcase-slide">
       <img src="/assets/img/light.png" class="screenshot">
       <h3>Custom black and white lighting</h3>
    </div>
    <div class="showcase-slide">
        <video class="videogif" controls="false" allowfullscreen="false" muted="true" loop="true" autoplay="true">
            <source src="/assets/video/rainy.mp4" type="video/mp4">
        </video>
        <h3>VFX Graph rain with support for rain occluders outside the camera view</h3>
    </div>
</div>
<hr>