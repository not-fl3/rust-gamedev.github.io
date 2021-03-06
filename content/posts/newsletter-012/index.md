+++
title = "This Month in Rust GameDev #12 - July 2020"
date = 2020-08-03
transparent = true
draft = true
+++

Welcome to the twelfth issue of the Rust GameDev Workgroup’s
monthly newsletter.
[Rust] is a systems language pursuing the trifecta:
safety, concurrency, and speed.
These goals are well-aligned with game development.
We hope to build an inviting ecosystem for anyone wishing
to use Rust in their development process!
Want to get involved? [Join the Rust GameDev working group!][join]

You can follow the newsletter creation process
by watching [the coordination issues][coordination].
Want something mentioned in the next newsletter?
[Send us a pull request][pr].
Feel free to send PRs about your own projects!

[Rust]: https://rust-lang.org
[join]: https://github.com/rust-gamedev/wg#join-the-fun
[pr]: https://github.com/rust-gamedev/rust-gamedev.github.io
[coordination]: https://github.com/rust-gamedev/rust-gamedev.github.io/issues?q=label%3Acoordination

Table of contents:

- [Game Updates](#game-updates)
- [Learning Material Updates](#learning-material-updates)
- [Library & Tooling Updates](#library--tooling-updates)
- [Popular Workgroup Issues in Github](#popular-workgroup-issues-in-github)
- [Meeting Minutes](#meeting-minutes)
- [Requests for Contribution](#requests-for-contribution)
- [Jobs](#jobs)
- [Bonus](#bonus)

<!--
Ideal section structure is:

```
### [Title]

![image/GIF description](image link)

A paragraph or two with a summary and [useful links].

_Discussions:
[/r/rust](https://reddit.com/r/rust/todo),
[twitter](https://twitter.com/todo/status/123456)_

[Title]: https://first.link
[useful links]: https://other.link
```

Discussion links are added only if they contain
some actual interesting discussions.

If needed, a section can be split into subsections with a "------" delimiter.
-->

## Game Updates

### [Crate Before Attack][cba-site]

[![Golf Club in Crate Before Attack](crate-before-attack.gif)][cba-site]

^ _A new weapon: the Golf Club_

[Crate Before Attack][cba-site] by [koalefant (@CrateAttack)][@CrateAttack]
is a skill-based grappling hook multiplayer game where frogs combat their friends
while navigating the landscape with their sticky tongues.

A summary of July changes:

- Gameplay: added a new melee weapon:
  [the Golf Club][cba-youtube-golf-club].
- Maps: added new map [Ruins][cba-youtube-observation]
  by [Kesha Astafyev][cba-spoon-tar]
- Animation: added eye tracking, frogs will track the closest danger
  with their eyes such as a projectile or a pet.
- Lobby: it is now possible to observe a match after it was started,
  added chat, user list with country flags, match details, and map previews.
- Localization: the game comes in three languages now: English, Spanish, Russian.
- Numerous bugfixes and tweaks.

Here is [a Playable Browser build][cba-play].
More details are on [the YouTube channel][cba-youtube]
and in [July Update DevLog-entry][cba-july-update].

[cba-site]: https://cratebeforeattack.com
[cba-july-update]: https://cratebeforeattack.com/posts/20200731-july-update/
[cba-play]: https://cratebeforeattack.com/play
[cba-youtube]: https://youtube.com/channel/UC_xMilPTLuuE5iLs1Ml9zow
[cba-youtube-golf-club]: https://youtu.be/UYxZQh68T6E
[cba-youtube-observation]: https://youtu.be/D63xy7sXStk
[cba-spoon-tar]: https://www.behance.net/spoon_tar
[@CrateAttack]: https://twitter.com/CrateAttack

### [Wonder]

[![Lines drawn with a ball ready to roll down them](wonder-screenshot.png)][Wonder]

[Wonder] ([source code][Wonder-source]) is a casual physics puzzle game by [@kettlecorn]
made for the web with WebAssembly, browser APIs, and no game framework.
The objective is to collect all the stars on each level
by drawing lines for the ball to roll along.

The game was made in 48 hours for the
[Ludum Dare game jam][ludum-dare] that occurred in April.
@kettlecorn recently published an article going into the technical and
creative challenges encountered making the game:
["Making a Game in 48 hours with Rust and WebAssembly"][48-hour-jam].

Wonder can be [played in the browser on itch.io][Wonder].

[Wonder]: https://kettlecorn.itch.io/wonder
[Wonder-source]: https://github.com/kettle11/LD46
[@kettlecorn]: https://twitter.com/kettlecorn
[ludum-dare]: https://ldjam.com
[48-hour-jam]: https://ianjk.com/rust-gamejam/

### [Tennis Academy Dash][tennis-academy-dash]

![gameplay](tennis_academy.gif)

[@oliviff] released [Tennis Academy Dash][tennis-academy-dash]
[v0.2][tennis-academy-update]:

This release features:

- a layering/scene management system
- transitioning between UI scenes and game scenes
- improving the level loading to work with string config files
- adding a 5th level

[@oliviff]: https://twitter.com/oliviff
[tennis-academy-dash]: https://iolivia.itch.io/tennis-academy-dash
[tennis-academy-update]: https://twitter.com/oliviff/status/1285298082033348609

### [Canon Collision][canon-collision]

![Basic Projectiles](canon-collision.png)

[Canon Collision][canon-collision] by [@rukai] is an Undertale + Homestuck
fan-made platform fighter with powerful tools for modding.

This month, he started work on the project again after taking a break.
Notable changes:

- [basic projectiles](https://twitter.com/thisIsRukai/status/1287377878460456963),
- [WIP grab implementation (with some humorous results)](https://www.youtube.com/watch?v=sSrBGpT-Ebs),
- [New animations + attacks](https://www.youtube.com/watch?v=AaPkRSNhoSM)
- and [custom shaders](https://twitter.com/thisIsRukai/status/1279324105125163008).

[canon-collision]:https://canoncollision.com
[@rukai]: https://twitter.com/thisIsRukai

### pGLOWrpg

![Improved river pathfinding, paths respect topography](pglowrpg_12.gif)

The [@pGLOWrpg] (Procedurally Generated Living Open World RPG) is a long-term
project in development by [@Roal_Yr], which aims to be a text-based game with
maximum portability and accessibility and focus on interactions and emergent
narrative.

For the past month(s) the main focus of the development was on the river
generation system in the worldgen. Main features of the river generator are:

- High robustness with most edge cases covered;
- Single-pass with subsequent iterations generation, with numerous options to
  tweak the process for either precision of the pattern or speed of generation;
- Rivers are sorted upon intersections, their widths are adjusted, waterfalls
  are formed when necessary;
- Inflow and outflow directions are recorded for each cell, which allows to
  follow the river upstream or downstream;
- Simple yet effective erosion model implemented, which ensures no upwards flows
  are allowed;
- Each stream has its unique ID, which will later be linked to the stream data;
- Streams have 12 orders of magnitude from smallest brooks to major rivers;
- All the options are available to user under "General", "Advanced" and
  "Very advanced" sections for any level of fine-tuning;

Further development will involve re-factoring of the code and making it ready
to be published prior to implementing new features. For small dev reports follow
[@pGLOWrpg] on Twitter.

[@Roal_Yr]: https://twitter.com/Roal_Yr
[@pGLOWrpg]: https://twitter.com/pglowrpg

### [Sandbox]

![Sandbox screenshot](sandbox_screenshot.png)

[Sandbox] is a falling sand game by JMS55 that provides a variety of fun
particle types to place, and then you get to watch the resulting interactions!

As they didn't make it in time for last month's newsletter, this month's edition
covers the work they did in June and July:

- Released version 1.0 and 1.1, created a flatpak package and associated metadata,
  and published it to [Flathub].
- Several new particles such as Fire, Mirror, Glitch, and some hidden ones,
  and tweaked or overhalled almost every other particle!
- A fancy new glow post process effect for Acid/Fire/Electricity,
  created using wgpu-rs compute shaders.
  - As a precursor to this, they made a PR to the pixels crate that removes the
    old RenderPass approach in favor of giving the user direct access to wgpu.
- Made a slick new icon and background for the game.
- Added a video recording feature using gstreamer-rs and x264enc,
  and then later removed it (for now).
  - Moving from recording the raw texture generated for pixels
    to the post-processed texture from wgpu
    involved a major overhaul, and it proved too glitchy and slow.
    Hopefully it will be revived later, in the form of recording user inputs.
- Many structural improvements, such as less glitchy particle
  placement with Bresenham's line algorithm,
  better error handling, and ensuring particles
  are only ever stored on the heap.
- Performance improvements, including generating noise in a separate thread.
- Currently WIP: UI using imgui.

![Sandbox icon](sandbox_icon.svg)

Got any ideas? Leave an [issue on github][Sandbox], or add it yourself!

[Sandbox]: https://github.com/JMS55/sandbox
[Flathub]: https://flathub.org/apps/details/com.github.jms55.Sandbox

### [Pushin' Boxes][pushin-homepage]

[![Pushin' Boxes gameplay](pushin_boxes_gameplay.gif)][pushin-itch]

[Pushin' Boxes][pushin-homepage] ([itch][pushin-itch])
is a [Sokoban][pushin-sokoban] clone made with [ggez][pushin-ggez] by
[@septum][septum-twitter]. It features 16 levels of puzzling box-pushin' action
where the player controls a little robot (named プシン).
Check out a [blog post][pushin-post] about the game's release.

[The source code is available on GitLab][pushin-repository].

[pushin-homepage]: https://septum.io/games/pushin-boxes
[pushin-itch]: https://septum.itch.io/pushin-boxes
[pushin-sokoban]: https://en.wikipedia.org/wiki/Sokoban
[pushin-post]: https://septum.io/blog/my-first-game
[pushin-ggez]: https://github.com/ggez/ggez
[pushin-repository]: https://gitlab.com/septum___/pushin_boxes
[septum-twitter]: https://twitter.com/septum___

### [On FPS Game Progress \#2][on-fps-game-2]

[![fps-game-screenshot](fps-game-2.jpeg)][on-fps-game-2-youtube]

^ _Click to watch a [footage from the game's current state][on-fps-game-2-youtube]._

On this update, [@pingFromHeaven] talks about the lighting implementation that
sets the tone for the game, how Rust is good at shortening the debugging
times, which is especially valuable when working directly with OpenGL and why
he doesn't describe what the game is about.

The next update is going to be about establishing the mood further, which
includes a more elaborate environment with more details, basic SFX and
particles.

[on-fps-game-2-youtube]: https://youtu.be/NIJNgr9zeXk
[on-fps-game-2]: http://atilkockar.com/on-fps-game-progress-2/
[@pingFromHeaven]: https://twitter.com/pingFromHeaven

## Learning Material Updates

### [Rust on iOS with SDL2][rust-ios-sdl2-post]

[![Rust on iOS with SDL2 demo](rust-ios-sdl2-screenshot.png)][rust-ios-sdl2-post]

[@aclysma] published a [tutorial][rust-ios-sdl2-post] that describes setting up
Rust/SDL2 on iOS. The resulting app can run in the simulator as well as on
physical devices. [SDL2][sdl2-project] is a mature library providing basic rendering,
audio, and input support. It can also be used to set up an opengl or vulkan
surface. This demo is using [Rust-SDL2][rust-sdl2] for bindings.

[rust-ios-sdl2-post]: https://blog.aclysma.com/rust-on-ios-with-sdl2/
[@aclysma]: https://twitter.com/aclysma
[sdl2-project]: https://www.libsdl.org/download-2.0.php
[rust-sdl2]: https://crates.io/crates/sdl2

### [Rust Sokoban Tutorial][sokoban_book]

![sokoban update](rust_sokoban.png)

The Rust Sokoban tutorial is an online book aimed at Rust gamedev beginners
which walks through making a simple Sokoban game using ggez and ECS (with specs).
It tries to teach the basics of architecting in ECS and basic Rust concepts
through a hands-on approach.

This month:

- the book was officially released on July 10th;
- the project received 3 external contributions;
- a few text edits were done, including fixing an issue with code
  snippets not appearing correctly;
- work on translations has started (🇨🇳 translation coming soon 🤞).

You can follow
the release discussion [on Twitter][sokoban_release],
provide feedback [on github][sokoban_github] and
read the book at [sokoban.iolivia.me][sokoban_book].

[sokoban_release]: https://twitter.com/oliviff/status/1281641563257360384
[sokoban_book]: https://sokoban.iolivia.me
[sokoban_github]: https://github.com/iolivia/rust-sokoban

### [An Introduction to Data-Oriented Design in Rust][dod]

![vector vs linked list perf](data_oriented_design.svg)

Data-Oriented Design is an approach to program optimisation focused on
considering the features and limitations of the target hardware, and
carefully controlling the memory layout of data to take advantage of
those.

In [this article][dod], [jamesmcm][jamesmcm] provides benchmarks and
code for four example scenarios:

- [Array of Structs vs. Struct of Arrays][wikisoa]
- Branching in a hot loop
- Iteration in a vector vs. a linked list
- Monomorphisation vs. [Dynamic Dispatch][traitobj]

The full article is available [here][dod].

[jamesmcm]: https://github.com/jamesmcm
[wikisoa]: https://en.wikipedia.org/wiki/AoS_and_SoA
[traitobj]: https://doc.rust-lang.org/book/ch17-02-trait-objects.html#trait-objects-perform-dynamic-dispatch
[dod]: http://jamesmcm.github.io/blog/2020/07/25/intro-dod/#en

## Library & Tooling Updates

### [This Month in Mun][mun-july]

[![Mun logo](mun-logo.png)][Mun]

[Mun] is a scripting language for gamedev focused on quick iteration times
that is written in Rust.

[Rustacean Station][rustacean] released [a podcast about Mun][rustacean-mun]
in which the Mun Core Team sat down with host Jeremy
to talk about why they chose Rust to develop Mun. If you are interested in
having an inside look into Mun's origins and evolution, we recommend you check
it out - or any of Rustacean Station's other podcasts for that matter!

Their additional [July updates][mun-july] include:

- initial support for the Language Server Protocol;
- a community entry for the [Make It or Break It content] of Spaceship
  recreated with Mun & Rust;
- CLI support for creating Mun projects;
- performance benchmarks and improvements;
- bugfixes and improved documentation.

[Mun]: https://mun-lang.org
[mun-july]: https://mun-lang.org/blog/2020/07/30/this-month-july
[rustacean]: https://rustacean-station.org
[rustacean-mun]: https://rustacean-station.org/episode/020-mun
[Make It or Break It content]: https://github.com/mun-lang/mun/issues/220

### [miniquad]

![miniquad ios](miniquad_ios.jpg)

[miniquad] is a safe and cross-platform rendering library
focused on portability and low-end platforms support.

This month opengl backend of miniquad was successefully ported to iOS.
With this update [macroquad], [good-web-game] and all the games
build directly with [miniquad] can be run on IOS, Android, WASM,
Linux, macOS and Windows!

[miniquad]: https://github.com/not-fl3/miniquad
[macroquad]: https://github.com/not-fl3/macroquad
[good-web-game]: https://github.com/not-fl3/good-web-game

### [wgpu][wgpu-site]

![procgen dynamic "grass field"](tuitui-grass-field.jpeg)

^ _[@MacTuitui]'s everyday [nannou] experiement #1274_

The work is ongoing to validate all the incoming commands and guarantee API safety.
Special thanks to [@GabrielMajeri] for helping to convert assertions
into errors at `wgpu` level.
The wgpu devs are also introspecting shader requirements
and matching them against the pipelines, but this will take more effort
before it will become universally available.

[@cwfitzgerald] has been busy adding a few handy native-only extensions,
such as descriptor indexing and push constants.
They have also converted the project's logging to [tracing](https://crates.io/crates/tracing),
setting up the infrastructure for CPU profiling.

In the past 2 months, the API for descriptor structures in `wgpu-rs`
have been undergoing a turbulent period.
First, non-exhaustive semantics led to introduction of constructors.
Then, efforts to reduce code duplication inside `wgpu` project has led to the
[bovine invasion](https://github.com/gfx-rs/wgpu-rs/pull/460) on wgpu-rs API side.
The devs are figuring out the plan to address that with a builder pattern now,
which will address both the `Cow`s and non-exhaustives,
hopefully putting the end to the turbulence.

In the meantime, `wgpu-rs` ecosystem is flourishing with applications and libraries.
The [showcase gallery](https://wgpu.rs/#showcase) was updated with a few shiny images.

------

Finally, [@kunalmohan] has been busy
[implementing WebGPU in Servo][webgpu-in-servo], based on `wgpu`.
Thanks to this work, Servo is currently ahead of Gecko
in terms of API being up-to-date and covered 🎉.
It's already capable of rendering most of the examples,
and the devs are looking forward to the day when the same Rust code
(rendering with `wgpu-rs`) will be deployable to the Web,
and viewable from Firefox, Servo, Chrome, and other browsers.

[@GabrielMajeri]: https://github.com/GabrielMajeri
[@cwfitzgerald]: https://github.com/cwfitzgerald
[@kunalmohan]: https://github.com/kunalmohan
[webgpu-in-servo]: https://github.com/servo/servo/projects/24
[@MacTuitui]: https://twitter.com/MacTuitui
[nannou]: https://nannou.cc
[wgpu-site]: https://wgpu.rs

### [Graphene][graphene] - Vulkan Render Graph

![execution flow example](graphene.png)

[Graphene][graphene] is a Vulkan render graph. Still heavily a work in progress,
it is built to be a simpler abstraction over Vulkan, with long-term ambitions to
serve as a graphics test-bench.

Currently, it implements a mesh render pass followed by a chromatic aberration
post-process in less than [250 lines of Rust code][graphene_example_code].
Current features include easy Vulkan initialization, automatic swapchain
resizing, glTF mesh loading, and shader hot-reloading.
Check out a ["Render graphs" blog post][graphene_blog]
for a more in-depth introduction to the project.

![chromatic aberration demo](graphene-demo.jpeg)

You can follow progress on [GitHub][graphene] or on [Twitter][apoorvaj].

[graphene]: https://github.com/ApoorvaJ/graphene
[graphene_blog]: https://apoorvaj.io/render-graphs-1/
[graphene_example_code]: https://github.com/ApoorvaJ/graphene/blob/a1ee574d92445f4cff195ca517af2912ebfce697/src/demos/00/main.rs
[apoorvaj]: https://twitter.com/ApoorvaJ

### Vulkan Renderer (Name TBD)

[![Vulkan renderer on iOS prototype](vulkan-renderer-prototype.jpeg)][vulkan-renderer-prototype-video]

^ _Click to watch [the video demo][vulkan-renderer-prototype-video] running on iOS._

[@aclysma] published a [new vulkan-based renderer][renderer-prototype] that
uses [atelier-assets] to load 3D scenes exported from blender.

> The objective of this repo is to build a scalable, flexible, data driven
> renderer. Scalable in the sense of performance as well as suitability for
> use in large, real-world projects. This means streaming, LODs, visibility
> systems, and multi-threaded draw call submission need to be possible.
> Additionally it means thinking through how an asset pipeline would work for
> a team with dedicated artists and supporting workflow-friendly features
> like hot reloading assets, possibly on remote devices.

This video demonstrates the renderer running on iOS and receiving asset updates
via wifi. The scene is "sponza" exported from blender. Vulkan is supported on
windows and linux natively. Support for macOS and iOS is via the
well-established [MoltenVK][moltenvk] project.

The demo was ported from PC to iOS over a single weekend and out of
approximately 300 crate dependencies (including complex, OS-specific ones like
tokio), all but a few worked out-of-the-box!

[@aclysma]: https://twitter.com/aclysma
[renderer-prototype]: https://github.com/aclysma/renderer_prototype
[atelier-assets]: https://github.com/amethyst/atelier-assets
[vulkan-renderer-prototype-video]: https://www.youtube.com/watch?v=Ks_HQbejHE4
[moltenvk]: https://github.com/KhronosGroup/MoltenVK

### [Ludusavi]

![Demo of Ludusavi GUI](ludusavi.gif)

[Ludusavi] is a tool written in Rust by [@mtkennerly] for backing up PC game
save data. It has backup info for more than 7,000 games, is cross-platform for
Windows, Linux, and Mac, and has a GUI as well as a command line interface.
The GUI was created using the [Iced] crate.

The [backup info] is sourced from [PCGamingWiki] so that everyone can help to
expand the data, and it's stored in a documented format so that other backup
tools can share the same data set. A [plugin] for [Playnite] was also just
released.

[Ludusavi]: https://github.com/mtkennerly/ludusavi
[@mtkennerly]: https://twitter.com/mtkennerly
[Iced]: https://crates.io/crates/iced
[backup info]: https://github.com/mtkennerly/ludusavi-manifest
[PCGamingWiki]: https://www.pcgamingwiki.com/wiki/Home
[plugin]: https://github.com/mtkennerly/ludusavi-playnite
[Playnite]: https://playnite.link

### [Langcraft]

[Langcraft] is the Minecraft LLVM target you've never wanted.

Langcraft started as a dare to the `#lang-dev` channel of the Rust
Community Discord to be able to parse Rust code in Minecraft.
Naturally, it grew into a full code generator that can translate
most LLVM IR to
[Minecraft data packs](https://minecraft.gamepedia.com/Data_Pack),
the game's deliberately-limited in-game scripting language. Langcraft
is entirely language independent, so any language with an LLVM-based
compiler can (with the right API bindings) run in Minecraft. Currently
bindings to both C and Rust exist. While not as visually impressive as
a redstone computer, Langcraft does stretch the bounds of the game quite
a bit, using jukeboxes for memory, armor stands to represent pointers,
and rearranging compiled code to make it run in the bounds of the data
packs' fixed instruction limit.

This is all, naturally, entirely useless. The project is also still
heavily work-in-progress and does not pretend to be stable, but it is
usable. A handwritten interpreter for a Rust-like language has already
been demonstrated running, and even more complex projects like [CHIP-8
emulators](https://github.com/Dhole/chip8-rs.git) function (albeit at
extremely slow speed).

You can watch a [video of Rust interpreter running Fizzbuzz][langcraft-video]:

[![youtube preview](longcraft-video.jpeg)][langcraft-video]

[Langcraft]: https://github.com/SuperTails/langcraft
[langcraft-video]: https://youtube.com/watch?v=Cx0w5Wn9pPU

## Popular Workgroup Issues in Github

<!-- Up to 10 links to interesting issues -->

## Meeting Minutes

<!-- Up to 10 most important notes + a link to the full details -->

[See all meeting issues][label-meeting] including full text notes
or [join the next meeting][join].

[label-meeting]: https://github.com/rust-gamedev/wg/issues?q=label%3Ameeting

## Requests for Contribution

<!-- Links to "good first issue"-labels or direct links to specific tasks -->

- [Embark's open issues][embark-open-issues] ([embark.rs]);
- [winit's "Good first issue" and “help wanted” issues][winit-issues];
- [gfx-rs's "contributor-friendly" issues][gfx-issues];
- [wgpu's "help wanted" issues][wgpu-help-wanted];
- [luminance's "low hanging fruit" issues][luminance-fruits];
- [ggez's "good first issue" issues][ggez-issues];
- [Veloren's "beginner" issues][veloren-beginner];
- [Amethyst's "good first issue" issues][amethyst-issues];
- [A/B Street's "good first issue" issues][abstreet-issues];
- [Mun's "good first issue" issues][mun-issues];

[embark.rs]: https://embark.rs
[embark-open-issues]: https://github.com/search?q=user:EmbarkStudios+state:open
[winit-issues]: https://github.com/rust-windowing/winit/issues?utf8=✓&q=is%3Aissue+is%3Aopen+label%3A%22status%3A+help+wanted%22+label%3A%22Good+first+issue%22
[gfx-issues]: https://github.com/gfx-rs/gfx/issues?q=is%3Aissue+is%3Aopen+label%3Acontributor-friendly
[wgpu-help-wanted]: https://github.com/gfx-rs/wgpu-rs/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22
[luminance-fruits]: https://github.com/phaazon/luminance-rs/issues?q=is%3Aissue+is%3Aopen+label%3A%22low+hanging+fruit%22
[ggez-issues]: https://github.com/ggez/ggez/labels/%2AGOOD%20FIRST%20ISSUE%2A
[veloren-beginner]: https://gitlab.com/veloren/veloren/issues?label_name=beginner
[amethyst-issues]: https://github.com/amethyst/amethyst/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22
[abstreet-issues]: https://github.com/dabreegster/abstreet/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22
[mun-issues]: https://github.com/mun-lang/mun/labels/good%20first%20issue

## Jobs

<!-- An optional section for new jobs related to Rust gamedev -->

## Bonus

<!-- Bonus section to make the newsletter more interesting
and highlight events from the past. -->

Just an interesting Rust gamedev link from the past. :)

------

That's all news for today, thanks for reading!

Subscribe to [@rust_gamedev on Twitter][@rust_gamedev]
or [/r/rust_gamedev subreddit][/r/rust_gamedev] if you want to receive fresh news!

<!--
TODO: Add real links and un-comment once this post is published
**Discussions of this post**:
[/r/rust](TODO),
[twitter](TODO).
-->

[/r/rust_gamedev]: https://reddit.com/r/rust_gamedev
[@rust_gamedev]: https://twitter.com/rust_gamedev
