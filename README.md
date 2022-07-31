# JADE
An open-source framework for algorithmic design.

JADE (Jade Algorithmic Design Engine) is a framework specification designed with modularity and ease-of-use in mind. Created in 2022, it aims to improve on its spiritual predecessor, the Generative Design Python Client (GDPC), by means
of a platform-agnostic architecture.
This should allow for the same generative design program to easily make use of
other I/O opportunities and allows for any node-based simulation to be ported
between interfaces and across algorithmic approaches.
It should also organise and facilitate development to allow for users to easily create their own extensions to JADE.

The following document outlines the intentions and requirements of the architecture. Should any comments or questions arise, please get in touch via Discord or E-mail or make use of the GitHub Issues board.

# 1. Introduction
TODO write
## 1.1. Purpose
The purpose of JADE is to provide a unified and open-source approach to algorithmic design (AD). Currently, many open-source projects within AD research are fairly isolated in their design, which impedes code re-use and expansion upon promising codebases.
The modular nature of JADE should encourage developers to use a "universal" format, with the intention of reducing development time, lowering the barrier for entry and increasing the accessibility of future codebases.
## 1.2. Intended Audience
There are three primary audiences which should be catered to:
1. First-time users
2. Advanced users
3. Framework developers

TODO For further information, see Chapter {INSERT LINK}

## 1.3. Intended Use
The JADE specifications cater to two forms of usage:
1. Use of a JADE implementation for AD
2. Development of a JADE implementation or plug-in

## 1.4. Scope
## 1.5. Definitions and Acronyms
Since various platforms make use of different terminologies, JADE attempts to use abstract and neutral definitions.
A translation table between terminologies is provided below.

### 1.5.1. Translation Table
### 1.5.2. General
- AD: Algorithmic design, including procedural generation, generative design and similar
- JADE a.k.a. JADE specification: The current and all affiliated documents {INSERT LINK}
- JADE implementation: A specific implementation of the JADE specification, e.g. Jade-Py
- JADE extension: An optional extention as discribed by the JADE specification
- Plug-in: Non-JADE extension to a JADE implementation
- Simulation: A running AD process
- 
### 1.5.3. Model
- Graph type: The format determining node arrangement. May be one of the following:
  - 2D orthogonal: A graph type based on pixel-like nodes, akin to a 2D matrix
  - 3D orthogonal: A graph type based on voxel-like nodes, akin to a 3D matrix
  - *Amorpheous: A graph type where nodes are not arranged in an orthogonal grid*
- World: The container for a simulation, consisting of a predetermined amount of nodes. 
  - A world cannot have any interaction with another world.
  - A world cannot be nested.
- Environment: A sub-devision of a world with unique rulesets. May include dimensions, biomes or other spacial regions.
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
    various creatures. Enteties may also occupy
  - An Entity can be nested.

### 1.5.4. Interface


## 1.6. Related documents
## 1.7. Currently supported implementations
# 2. Overall Description
## 2.1. User Needs
### 2.1.1. First-time Users
First-time users are users who have not used a JADE implementation previously and may have limited programming knowledge
### 2.1.2. Advanced Users
### 2.1.3. Framework Developers

## 2.2. Assumptions and Dependencies
# 3. System Features and Requirements
# 3.1. Functional Requirements
# 3.2. External Interface Requirements
# 3.3. System Features
# 3.4. Nonfunctional Requirements
# 3.4.1. Versioning
JADE implementations should make use of a `major.minor.patch` versioning scheme, where `major` and `minor` are JADE specification versions and `patch` may be used freely to indicate an implementation version.
Versions with the same `major` are backwards compatible and optionally forwards compatible. This implies that any breaking changes in the specification (e.g. refactoring or removal of obsolete functionality) result in the `major` being incremented and the `minor` being reset to 0.
In the case of changes which are compatible with the previous version, the `minor` is incremented.
It is strongly recommended that `patch` is reset to 0 when updating to a different JADE specification version.
Developers are free to partially implement later versions without guaranteeing compatiblity, under the condition that the `major` and `minor` are of versions where full compatibility is guaranteed.
# 3.4.1.1. Versioning Examples
TODO