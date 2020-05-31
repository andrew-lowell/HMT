HMT
======

![HMT logo](https://github.com/andrew-lowell/HMT/blob/master/hmt_logo_01.png)

**Houdini Music Toolset**, extends the users' capabilities into the domain of music composition.

HMT makes use of Houdini's powerful geometry and simulation processing in a set of new tools and workflows specifically designed for music. It uses point clouds and attributes within the graphical 3D environment to perform sequencing tasks present in music composition packages. It uses CHOPs as a back-end to import or export MIDI file data either to the midi file format, or directly to a MIDI port. It allows for artists or composers to make use of powerful simulation tools and Houdini's open node-based architecture normally dedicated to producing photorealistic simulations of natural phenomenon and apply the same tools if desired to manipulating or generating patterns of notes.

Because of the modular and node based nature of the toolset present in HMT, and that it adheres when possible to existing Houdini conventions, it allows users to easily develop their own workflows and tools for music creation or processing.

* * * * *

### Installation:

Download the desired release directly from the [releases page](https://github.com/andrew-lowell/HMT/releases) and extract it to your hard drive or network share.

**Plugin (17.5+ only)**
Create a folder inside your Houdini preferences directory (where the houdini.env typically lives) called "packages", and place the HMT.json file from the HMT download into that folder. Then edit HMT.json and change the "HMT" variable to match the install path.

**OS Support (Full functionality Windows only)**
While the toolset is based entirely in Houdini and will perform it's sequencing functions regardless of operating system, the MIDI Output CHOP will only perform live/real-time export to a MIDI channel on the Windows operating system. When Apple/Linux are supported this page will be updated. Exporting to MIDI files is supported on all operating systems.


* * * * *
### Workflows:
* **[Software Connectivity Flowchart](https://github.com/andrew-lowell/HMT/blob/master/hmt_workflows.pdf)**
* **[Supplementary Software](https://github.com/andrew-lowell/HMT/blob/master/SOFTWARE_LINKS.md)**


* * * * *

### Usage basics:
***Tutorial Links***
* **[00 Sound Check](https://vimeo.com/416777838/0fd198367a)**
* **[01 Simple Note](https://vimeo.com/416991416/ce039a640a)**
* **[02 Note Patterns](https://vimeo.com/417402929/5641115d20)**
* **[03 MIDI IO](https://vimeo.com/417931944/cf73e3c470)**
* **[04 Time Adjustment](https://vimeo.com/417932182/136981fe15)**
* **[05 Timing Setup](https://vimeo.com/419194667/45c7c1920a)**
* **[06 Pitch Setup](https://vimeo.com/419194847/4fbf7f4a63)**
* **[07 Duration Setup](https://vimeo.com/419451031/f14a24291a)**
* **[08 Panning Setup](https://vimeo.com/420559800/bc32c908e5)**
* **[09 Velocity Setup](https://vimeo.com/420579796/589035a1a0)**
* **[10 Timing Distortion](https://vimeo.com/421363770/237feecce3)**
* **[11 Velocity Impulse](https://vimeo.com/422014745/f2e11f5794)**
* **[12 Modal Setup](https://vimeo.com/424223637/36ab669554)**
* **[13 Modal Assignment](https://vimeo.com/424411732/a4d7c11f24)**
* **14 Velocity Impact**
* **15 Velocity Distance**
* **16 Doppler Setup**
* **17 Doppler Application**

***Shelf Tools***
* **MIDI IO Setup**: This will create a MIDI Output to a `.midi` file. Then downstream read the same file in and play it back through a live MIDI channel (Windows only).
* **Random Notes**: This setup is useful to observe the necessary point attributes being assigned manually then output through a live MIDI channel.
* **Mode Progression**: The mode progression setup is useful because there is a certain order of operations and mode attributes necessary upstream to produce the `i@note` attribute downstream. First the mode attributes are assigned based on mode, octave, base note, and mode progression. Then the final `i@note` attribute is computed and output through a live MIDI channel.
* **Sound Check**: This will create test spacial MIDI composition with visualization and play it back through a live MIDI channel (Windows only).

For more detailed examples, see the [provided examples](https://github.com/andrew-lowell/HMT/tree/master/examples) folder for Houdini (.hip) files.

* * * * *

### Technical Specifications:
[Geometry attributes used by HMT](https://github.com/andrew-lowell/HMT/blob/master/ATTRIBUTE_SPECS.md)

* * * * *

### Developers:
**HMT (Houdini Music Toolset)** is developed and maintained by ***Andrew Lowell***. 

* * * * *

### Notice:
This software is provided AS-IS, with absolutely no warranty of any kind, express or otherwise. We disclaim any liability for damages resulting from using this software.
