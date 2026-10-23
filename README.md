# Vincent Del Vecchio

I'm a software developer based in Florida. I've modernized legacy web applications
using PHP and CodeIgniter MVC and maintained Java/Spring applications. I also build
C++ graphics and emulation projects.

**Seeking remote software development opportunities in the United States.**

## Selected work

### Legacy web application modernization

At Florida DEP, I migrated most of the WACS application from Classic ASP to
PHP/CodeIgniter MVC and maintained the Java/Spring-based DEP Cleanup Sites application.
I checked migrated reports against ASP output, repaired site-watch email notifications
and added database error logging with daily supervisor reports. I also collaborated
with the GIS team to add a customer-requested map-layer visibility toggle.
[Read the case study](docs/dep-modernization.md).

### CHIP-8 emulator — C++17 / Vulkan / Win32

Windows emulator with opcode dispatch, a 64 × 32 framebuffer, XOR sprite drawing,
collision reporting, keyboard input and working miniaudio sound. The emulator source
and build instructions are on `main`.

[Source and build instructions](https://github.com/DVecc/Chip8Emulator) ·
[Windows x64 preview](https://github.com/DVecc/Chip8Emulator/releases/tag/v0.1.0) ·
[Gameplay recording](https://github.com/DVecc/Chip8Emulator/blob/main/docs/media/pong-gameplay.gif)

CMake builds compile the shaders, and Windows CI runs core regression checks for
sprite drawing, collisions, timers, key-wait behavior and oversized-ROM rejection.
Local testing includes Pong and Tetris. Windows is the only supported
platform, and CHIP-8 compatibility is partial. Bring your own ROMs; none are included
in the current source tree or release package.

### Witch's Workbench — OpenGL

A staged 3D scene with a movable camera and switchable projections.
[Source and preview](https://github.com/DVecc/3D-Rendering-of-a-Witches-Workbench-Using-OpenGL).

## Skills

- **Professional web development:** PHP, CodeIgniter MVC, Java, Spring, JavaScript, HTML/CSS, SQL and PL/SQL.
- **Additional languages and projects:** Python, C++, graphics programming, Vulkan and OpenGL.
- **Education:** B.S. Computer Science, Southern New Hampshire University.

## Contact

[LinkedIn](https://linkedin.com/in/dvecc) · [Email](mailto:vincent.delvecchio@dvecc.simplelogin.com)
