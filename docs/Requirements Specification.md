# JADE Requirements Specification [0.1]
This document describes the intentions and requirements of JADE, as well as further useful information.

TODO Table of contents

# 1. Introduction
TODO write
## 1.1. Purpose
The purpose of JADE is to provide a unified and open-source approach to algorithmic design (AD).  

Currently, many open-source projects within AD research are fairly isolated in their design, which impedes code reusability and the expansion upon promising codebases.  
The modular nature of JADE should encourage developers to use a "universal" format, with the intention of reducing development time, lowering the barrier for entry and increasing the accessibility of future codebases.  
Licencing should encourage open-source practices and positive feedback loops, where suggestions and contributions can be easily adopted to continuously improve the product.
## 1.2. Intended Audience
There are three primary audiences which should be catered to:
1. First-time users
2. Advanced users
3. Framework developers

TODO For further information, see Chapter {INSERT LINK}

## 1.3. Intended Use
The JADE specifications cater to two forms of usage:
1. Use of a JADE implementation for AD
2. Development of a JADE implementation, extension or plug-in

### 1.3.1. Use for Algorithmic Design

### 1.3.2. Use for Further Development

## 1.4. Scope
## 1.5. Definitions and Acronyms
Since various platforms and languages make use of different terminologies, JADE attempts to use more general definitions.
A translation table between common terminologies is provided below.

### 1.5.1. Translation Table
TODO: {CREATE TABLE}
### 1.5.2. General
- AD: Algorithmic design, including procedural generation, generative design and etc.
- JADE a.k.a. JADE specification: The current and all affiliated documents {INSERT LINK}
- JADE implementation: A specific implementation of the JADE specification, e.g. Jade-Py
- JADE extension: An optional extension as described by the JADE specification
- Plug-in: Non-JADE extension to a JADE implementation
- Simulation: A running AD process
- TODO: improve User or end user: A user of audience type 1. or 2. and use case 1. 
### 1.5.3. Model
- Graph type: The format determining node arrangement. May be one of the following:
  - 2D orthogonal: A graph type based on pixel-like nodes, akin to a 2D matrix
  - 3D orthogonal: A graph type based on voxel-like nodes, akin to a 3D matrix
  - *Amorpheous: A graph type where nodes are not arranged in an orthogonal grid*
- World: The container for a simulation, consisting of a predetermined amount of nodes. 
  - A world cannot have any interaction with another world.
  - A world cannot be nested.
- Environment: A sub-division of a world with unique rule-sets. May include dimensions, biomes or other spacial regions.
  - Interactions between environments are possible.
  - Environments may be nested.

- Node: An atomic unit representing e.g. a node in a graph, a pixel or a voxel.
  - A node occupies a finite space that cannot be shared by other nodes.
  - A node cannot be nested.
- Cluster: A structured collection of nodes that act cohesively,
    such as a building, machine or settlement.
  - A Cluster can be nested.
- Entity: An atomic unit that may exist within one or multiple nodes
    simultaneously and may share the same space with other entities, such as
    various creatures. Entities may also occupy
  - An Entity can be nested.

### 1.5.4. Interface
#### 1.5.4.1. User Interface
- User feature: A data structure, function, etc. intended for use by a user

## 1.6. Related Documents
TODO
## 1.7. Currently Supported Implementations
### Jade-Py [0.1.1]
Jade-Py implements JADE in Python 3 and provides the following extensions:
- `minecraft`, providing data structures and functionality for Minecraft simulations
- TODO: add more
# 2. Overall Description
## 2.1. User Needs
### 2.1.1. First-time Users
First-time users are users who have not used a JADE implementation previously and may have limited programming knowledge. 
TODO A feature tutorial {INSERT LINK} should always be supplied for this reason.
Optionally, a beginner tutorial can be provided which demonstrates a functional simulation and serves as a starting point for further simulations of that kind.
### 2.1.2. Advanced Users
Advanced users are likely to be interested in optimising simulations or making use of more complex features. 
TODO For this reason, a feature tutorial {INSERT LINK} should always be provided with all functionality displayed.
Additionally, interfaces should provide optional asynchronous behaviours where possible.
Optionally, an advanced tutorial may be provided which demonstrates a functional simulation and serves as inspiration for further simulations of that kind.
### 2.1.3. Framework Developers
Framework developers will need to gain an understanding for their relevant JADE implementation fairly quickly. For this reason, JADE implementations and extensions should provide docstrings for every public function, method or data structure, and typing should always be clearly defined.

## 2.2. Assumptions and Dependencies
The primary assumption is that all JADE implementations will take place in an object-oriented programming language.
Additionally, it is presumed that JADE implementations will be run on contemporary operating systems which make use of a file system and fulfil the following minimum system requirements:
- Dual-core 500 MHz CPU
- 512 MB RAM
- Sufficient memory to store the JADE implementation and appropriate language compilers/interpreters

A graphical user environment should not be required, but extensions may have their own requirements (such as requiring additional software or certain operating environments).
The core JADE implementation should be able to run solely on the standard libraries included in the appropriate implementation language. 

# 3. System Features and Requirements
## 3.1. Functional Requirements
JADE implementations must fulfil the following requirements to be considered for release:
1. Tested with > 95% coverage
2. Testing resulted in 0 crashes and 0 errors
3. A debug mode is provided (see `"docs/extensions/testing"`)

## 3.2. Extensions
JADE implementations may support various extensions which provide aspects of the JADE implementation.

Extensions are compliant with JADE specifications and are therefore more strictly regulated, though authors should have a lot of freedom on how to implement the specified behaviours.

The following are considered part of the core implementation and must be provided:
- `jade.logging`: Provides functionality for logging to files or other outputs
- `jade.files`: Provides functionality for reading and writing files
- `jade.console`: Provides functionality for writing to and from consoles and command lines
- `jade.testing`: Provides functionality for unit tests and manual testing

See `docs/extensions` for further information.
## 3.3. Plug-ins
Plug-ins come in all shapes and sizes and are not bound to any specifications, but make use of or enhance JADE functionality.
Sometimes plug-ins may inspire future JADE specifications.

## 3.5. Non-functional Requirements
### 3.5.1. Versioning
JADE implementations should make use of a `major.minor.patch` versioning scheme, where `major` and `minor` are JADE specification versions and `patch` may be used freely to indicate an implementation version.
Versions with the same `major` are backwards compatible and optionally forwards compatible. This implies that any breaking changes in the specification (e.g. refactoring or removal of obsolete functionality) result in the `major` being incremented and the `minor` being reset to 0.
In the case of changes which are compatible with the previous version, the `minor` is incremented.
It is strongly recommended that `patch` is reset to 0 when updating to a different JADE specification version.
Developers are free to partially implement later versions without guaranteeing compatibility, under the condition that the `major` and `minor` are of versions where full compatibility is guaranteed.
#### 3.5.1.1. Versioning Example
In the following example "implementation" refers to a JADE implementation and "developer" refers to a developer of the implementation. The example is fictional and serves demonstrative purposes only.
1. The current version of an implementation is `0.1.34`. It is fully compatible with JADE `0.1`.
2. The maintainer or developer of the implementation implements support for a future feature, the implementation version becomes `0.1.35`.
3. A new JADE specification with minor improvements is released (JADE `0.2`). The developer updates the implementation to be compatible. The implementation version becomes `0.2.0`.
4. The developer finds and fixes a bug. The implementation version becomes `0.2.1`.
### 3.5.2. Licencing
JADE and all JADE implementations and extensions are licenced under the GPL 3 and all source-code files contained therein should contain the following comment at the start of the file:
```py
# <one line to give the program's name and a brief idea of what it does.>
# Copyright (C) <year>  <name of author>
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

To prevent legal issues, it is strongly recommended that all software deriving from or making use of JADE and JADE implementations or extensions includes a `plugin_is_GPL_compatible` constant that contains a truthy value to confirm GPL compatibility.
For example:
```c
const bool plugin_is_GPL_compatible = true;
```
This value can then be checked to prevent usage of license-incompatible products where required.

***The following is not legal advice and represents only the author's limited and possibly incorrect understanding of licencing.***
> The GPL license also applies to any use of JADE, its implementations and extensions or any other GPL-licensed product in a derivative product, e.g. a simulation.  
> As a result, if the derivative product is distributed, even under a different license, you must make source code of your derivative product available to the public.  
> 
> **TL;DR:**  
> If you use something that uses the GPL license in your product and you distribute it, your product legally becomes open-source when distributing, regardless of how or what part of it you distribute.

### 3.5.3. Donations and Monetisation
JADE, JADE implementations and extensions will remain public and open-source free of charge, but derivative products may be commercialised in accordance with the license agreements used by JADE.  
In the case that a derivative product is commercialised, the author of said product has no obligations towards the developers of JADE to pay a contribution, but donations are welcome and will be distributed on a case-by-case basis, based on the donator's preferences.  
Donations will be publicly listed.