# Alpine Utils

A collection of precompiled tools, patches, and compatibility layers for Alpine Linux.

## Overview

**Alpine Utils** enhances Alpine Linux by adding precompiled tools, patches, and compatibility layers while respecting the system's minimalistic approach. Contributors can extend and customize utilities following a straightforward directory structure aligned with the [Filesystem Hierarchy Standard (FHS)](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard).

## Project Structure

```
alpine-utils/
├── docs/                      # Documentation for each tool or patch
│   └── {tool-name}.md         # Documentation file
├── {category}/                # Category for related tools/patches
│   ├── bin/                   # Binaries and scripts
│   │   ├── {tool_name}.{arch}   # Precompiled tool (e.g., glib_patch.x86_64)
│   │   └── {tool_name}.noarch   # Architecture-independent tool (e.g., glibc_path.noarch)
│   ├── lib/                   # Libraries and scripts required by the tools
│   │   ├── {tool_name}/        # Subdirectory for tool-specific libraries
│   │   │   ├── lib_helper.noarch  # Example of an architecture-independent library / tool
│   │   │   └── lib_helper.x86_64  # Example of an architecture-specific library / tool
├── bin/                       # Repo-wide helper scripts
│   └── install                # Script to install tools based on "path"
└── LICENSE                    # Main repository license file
```

### Example Tool: glib_patch

Each category will include a sample tool for illustration:

```
bin/                         # Binaries and scripts
├── glib_patch.x86_64        # Precompiled tool for x86_64 architecture, if dynamic place libraries in lib/glib_patch/
lib/                         # Libraries and scripts required by the tools
├── glib_patch/
│   ├── patch_helper.noarch      # Architecture-independent tool required by glib_patch
│   ├── patch_helper.x86_64      # Architecture-specific tool required by glib_patch
```

### Categories

Each category groups related precompiled tools, patches, and compatibility layers. Each category includes:

- **`bin/`** – Contains precompiled binaries and installation scripts.
- **`lib/`** – Contains libraries and scripts required by the tools.

## Adding a New Tool, Patch, or Compatibility Layer

To contribute a new tool or patch:

1. **Choose/Create a Category**: Select an existing category or create a new one if necessary.
2. **Add Your Precompiled (or Script) Tool**: Place precompiled binaries or scripts in `bin/`, using the naming conventions:
   - For architecture-specific binaries: `{tool_name}.{arch}` (e.g., `glib_patch.x86_64`)
   - For architecture-independent binaries: `{tool_name}.noarch` (e.g., `glibc_path.noarch`)

    Note: If you are adding a precompiled binary and its dynamic place libraries in lib/{tool_name}/
3. **Ensure Shebang for Scripts**: For any script (e.g., Bash or Python), include a shebang at the top of the file to specify the interpreter.
4. **Add Documentation**: Include documentation in `docs/{tool-name}.md`.

## Licensing

### Main Repository License

**Alpine Utils** is licensed under the GNU General Public License version 3 (GPL v3) or later with an exception:

**Exception**: Each tool, patch, or compatibility layer should have its own license. Users must follow these specific licenses.

### Tool-Specific Licensing

Each tool should include its own license. We recommend permissive licenses like **MIT** or **Apache 2.0**. Example notice for your tools:

```plaintext
// Copyright (C) 2024 {Your Name}
// Licensed under the {License Name} License. See LICENSE file for details.
```

Refer to the `LICENSE` file in the root for more details.

## Contributing Guidelines

1. **Directory Structure**: Maintain the defined structure.
2. **Documentation**: Include concise documentation in `docs/`.
3. **Lightweight Philosophy**: Focus on minimalism and efficiency.
4. **Licensing**: Ensure proper licensing for each contribution.

We welcome your contributions!

## Contact

For questions or issues, contact:

**Kevin Alavik**  
Email: kevin@alavik.se  
Git: [git.shittydev.com](https://git.shittydev.com)  
GitHub: [github.com/KevinAlavik](https://github.com/KevinAlavik)

## License

Full license text can be found in the `LICENSE` file.
