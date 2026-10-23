# Vincent Del Vecchio

Software developer based in Florida, with professional experience modernizing legacy
web applications using PHP and CodeIgniter MVC. I also build C++ graphics and emulation
projects to explore how software works below the framework level.

**Seeking remote software development opportunities in the United States.**

## Selected work

### Legacy web application modernization

At Florida DEP, I worked on migrating Classic ASP functionality to PHP/CodeIgniter while
maintaining existing business workflows. [Read the high-level case study](docs/dep-modernization.md).

### CHIP-8 emulator — C++17 / Vulkan / Win32

Windows emulator with opcode dispatch, a 64 × 32 framebuffer, XOR sprite drawing,
collision reporting, keyboard input and working miniaudio sound. The emulator source
and build instructions are on `main`.

[Source and build instructions](https://github.com/DVecc/Chip8Emulator) ·
[Windows x64 preview](https://github.com/DVecc/Chip8Emulator/releases/tag/v0.1.0) ·
[Gameplay recording](https://github.com/DVecc/Chip8Emulator/blob/main/docs/media/pong-gameplay.gif)

CMake builds compile the shaders, and Windows CI runs core regression checks for
sprite drawing, collisions, timers, key-wait behavior and oversized-ROM rejection.
The app has been run locally with Pong and Tetris. Windows is the only supported
platform, and CHIP-8 compatibility is partial. Bring your own ROMs; none are included
in the current source tree or release package.

### Witch's Workbench — OpenGL

A staged 3D scene with a movable camera and switchable projections.
[Source and preview](https://github.com/DVecc/3D-Rendering-of-a-Witches-Workbench-Using-OpenGL).

## Skills

- **Professional web development:** PHP, CodeIgniter MVC, JavaScript, HTML/CSS, SQL.
- **Additional languages and projects:** Java, Python, C++, graphics programming, Vulkan and OpenGL.
- **Education:** B.S. Computer Science, Southern New Hampshire University.

## Contact

[LinkedIn](https://linkedin.com/in/dvecc) · [Email](mailto:vincent.delvecchio@dvecc.simplelogin.com)

Profile and case-study drafts prepared with AI assistance for author review.
