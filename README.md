# Game Development Tools
A set of tools for game development, written in several different languages.

# Structure
# General
The root directory contains a folder for each package. Each package will contain folders for each language (e.g. `<package-name>/<language-name/`).
Each package will contain its own `README.md` with a description of its contents, and each language will contain a `BUILDING.md` which contains instructions on how to build the package from source. 


## Core
The core library for each language. Contains a common api which is mirrored across languages to make development easier, and a renderer interface which can be implemented for any graphics api or framework. Also may contain language specific utilities, which will be documented as such accordingly.

# Packages
| Package Name | Version | Summary                                                               |
|--------------|---------|-----------------------------------------------------------------------|
| core         |   N/A   |                                                                       |
| opengl       |   N/A   | drop-in opengl renderer                                               |
| vulkan       |   N/A   | drop-in vulkan renderer                                               |
| particle     |   N/A   | a particle system                                                     |
| ui           |   N/A   | a hierarchical ui system                                              |
| config       |   N/A   | a simple configuration system                                         |
| cache        |   N/A   | a simple configurable cache                                           |
| noise        |   N/A   | a collection of noise functions                                       |
| graph        |   N/A   | a collection of graph data structures                                 |
| scene        |   N/A   | a simple scene graph                                                  |
| event        |   N/A   | an asynchronous event system                                          |
| entity       |   N/A   | an entity-component system                                            |
| command      |   N/A   | a command based development framework                                 | 
| statemachine |   N/A   | a state machine framework                                             |
| doublebuf    |   N/A   | a generic double buffer type                                          |
| app          |   N/A   | a wrapper for a generic application                                   |
| vm           |   N/A   | a simple language & vm for scriptable behavior                        |
| vm-runtime   |   N/A   | a runtime interpreter for the language defined by the `vm` package    |
| vm-asm       |   N/A   | an assembly-like interface for the vm, allows compilation to & from   |
| ai           |   N/A   | a simple extension to `statemachine` that adds features for simple ai |
| lazyupdate   |   N/A   | a wrapper for an updatable object which makes the update lazy         |
| pooling      |   N/A   | a basic object pool                                                   |
| db           |   N/A   | a wrapper for SQLite database interface libraries                     |
| msdf-font    |   N/A   | multichannel signed distance field fonts.                             |
| wang-tiles   |   N/A   | a 2d and 3d implementation of wang tiles for procedural generation    |
| autotile     |   N/A   | the partial reverse of wang tiles for autotiling                      |
| physics2d    |   N/A   | 2d physics                                                            |
| physics3d    |   N/A   | 3d physics                                                            |
| animation    |   N/A   | animation framework                                                   |
| console      |   N/A   | ingame console framework                                              |
| tilemap      |   N/A   | generic tilemap implementations                                       |
| voxel        |   N/A   | generic voxel map implementations                                     |
| light2d      |   N/A   | 2d lighting framework                                                 |
| light3d      |   N/A   | 3d lighting framework                                                 |
| image        |   N/A   | image processing and loading framework                                |
| controller   |   N/A   | unified controller framework/interface                                |
| metrics      |   N/A   | metric collection framework                                           |
| net          |   N/A   | basic networking framework                                            |
| net-http     |   N/A   | basic http 1.1/2 framework                                            |
| net-tls      |   N/A   | framework/interface providing tls 1.3                                 |
| async        |   N/A   | framework for developing asynchronous applications                    |
| json         |   N/A   | json parser/writer                                                    |
| yaml         |   N/A   | yaml parser/writer                                                    |
| xml          |   N/A   | xml parser/writer                                                     |
| toml         |   N/A   | toml parser/writer                                                    |
| task         |   N/A   | system for passing tasks across threads                               |
| metal        |   N/A   | drop-in metal renderer                                                |
| authenticate |   N/A   | framework for providing federated and non-federated logins            |
| interact     |   N/A   | framework for developing context-aware interaction sequences          |
| log          |   N/A   | unified logging interface                                             |
| chat         |   N/A   | ingame chat system implementation                                     |
| meshloader   |   N/A   | loader for various mesh formats                                       |
| compress     |   N/A   | wrapper for various compression libraries                             |
| encrypt      |   N/A   | simple wrapper for various encryption & cryptographic hash libraries  |
| i18n         |   N/A   | internationalization framework                                        |
| serialize    |   N/A   | framework for serializing data in a binary format                     |
| freetype     |   N/A   | wrapper for freetype                                                  |
| pipeline     |   N/A   | framework for wrapping complex actions into pipelines                 |
| cloth        |   N/A   | 2d & 3d forward and inverse kinematics and cloth simulations          |
| pathfinding  |   N/A   | implementations of various pathfinding algorithms (A*, Dijkstra, etc) |
| video        |   N/A   | wrapper for various video read/write libraries                        |
| asset        |   N/A   | asset management system                                               |

\* any package marked with version `N/A` is not yet implemented, and therefore has no version.

# Package interaction
Packages often must interact with eachother, and occasionally some may want to define custom behavior when a package is present. It is guarenteed that no optional dependency will cause api functionality to be removed or broken. However, underlying implementation may change or additional api functions might be added. For example, `ui` may add sound functionality to various features when the `audio` package is present, or `net-http` would allow for HTTPS when `net-tls` is present. Each package will provide documentation containing the full featureset, assuming all required and optional dependencies are present. Any functions which are only present when another package is available will be annotated as such. 
