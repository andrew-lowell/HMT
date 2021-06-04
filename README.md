HMT
======

![HMT logo](https://github.com/andrew-lowell/HMT/blob/master/hmt_logo_01.png)

**Houdini Music Toolset**, extends the users' capabilities into the domain of music composition.
* **[HMT 1.0 Demonstration](https://vimeo.com/425382356/a4a52d71c1)**
* **[HMT 2.0 Demonstration](https://vimeo.com/536214871)**

HMT makes use of Houdini's powerful geometry and simulation processing in a set of new tools and workflows specifically designed for music. It uses point clouds and attributes within the graphical 3D environment to perform sequencing tasks present in music composition packages. It uses CHOPs as a back-end to import or export MIDI file data either to the midi file format, or directly to a MIDI port. It allows for artists or composers to make use of powerful simulation tools and Houdini's open node-based architecture normally dedicated to producing photorealistic simulations of natural phenomenon and apply the same tools if desired to manipulating or generating patterns of notes.

Because of the modular and node based nature of the toolset present in HMT, and that it adheres when possible to existing Houdini conventions, it allows users to easily develop their own workflows and tools for music creation or processing.

* * * * *

### Installation:

Download the desired release directly from the [releases page](https://github.com/andrew-lowell/HMT/releases) and extract it to your hard drive or network share.

**Plugin (17.5+ only)**
Create a folder inside your Houdini preferences directory (where the houdini.env typically lives) called "packages", and place the HMT.json file from the HMT download into that folder. Then edit HMT.json and change the "HMT" variable to match the install path.

***This toolset does not produce sound,*** it acts as a sequencer and sends MIDI data to an audio application or MIDI file. Most professional or popular music programs will support a MIDI port which can be used to then trigger real-time sound and instruments. See the [supplementary software page](https://github.com/andrew-lowell/HMT/blob/master/SOFTWARE_LINKS.md) for more on getting your system up and running.

**OS Support (Full functionality Windows only)**
While the toolset is based entirely in Houdini and will perform it's sequencing functions regardless of operating system, the MIDI Output CHOP will only perform live/real-time export to a MIDI channel on the Windows operating system. When Apple/Linux are supported this page will be updated. Exporting to MIDI files is supported on all operating systems.


* * * * *
### Workflows:
* **[Software Connectivity Flowchart](https://github.com/andrew-lowell/HMT/blob/master/hmt_workflows.pdf)**
* **[Supplementary Software](https://github.com/andrew-lowell/HMT/blob/master/SOFTWARE_LINKS.md)**


* * * * *

### Usage basics:
* **[Version 1 Introduction and Demonstration](https://vimeo.com/425382356/a4a52d71c1)**
* **[Version 2 Introduction and Demonstration](https://vimeo.com/536214871)**

***Version 1 Tutorial Links - Musical Notes***
* **[Installation and Sound Check](https://vimeo.com/416777838)**
* **[Simple Note](https://vimeo.com/416991416)**
* **[Note Patterns](https://vimeo.com/417402929)**
* **[Chords](https://vimeo.com/428397014)**
* **[MIDI IO](https://vimeo.com/417931944)**
* **[Time Adjustment](https://vimeo.com/417932182)**
* **[Timing Setup](https://vimeo.com/419194667)**
* **[Pitch Setup](https://vimeo.com/419194847)**
* **[Duration Setup](https://vimeo.com/419451031)**
* **[Panning Setup](https://vimeo.com/420559800)**
* **[Velocity Setup](https://vimeo.com/420579796)**
* **[Timing Distortion](https://vimeo.com/421363770)**
* **[Velocity Impulse](https://vimeo.com/422014745)**
* **[Modal Setup](https://vimeo.com/424223637)**
* **[Modal Assignment](https://vimeo.com/424411732)**
* **[Velocity Impact](https://vimeo.com/424437612)**
* **[Velocity Distance](https://vimeo.com/424655810)**
* **[Doppler Setup](https://vimeo.com/424996327)**
* **[Doppler Application](https://vimeo.com/425016788)**
* **[Note Editing](https://vimeo.com/460053769)**

***Version 2 Tutorial Links - MIDI Controller Channels***
* **[New Features in HMT 2.0](https://vimeo.com/536575305)**
* **[Controller Channel I/O](https://vimeo.com/536575516)**
* **[Controller Conversion and Resampling](https://vimeo.com/540892566)**
* **[Controller Duplication](https://vimeo.com/544867864)**
* **[Example: Particle Position](https://vimeo.com/547344452)**
* **[Exacting Controller Functions](https://vimeo.com/557082144)**
* ** Controller Shaping**
* ** Controller Timing**
* ** Controller Triggering**
* ** Example: Rotating Cube**
* ** Example: Color/Tone Blending**
* ** Example: Orbital**

***User Tutorials***
* **[Drum Loops](https://vimeo.com/437284890)** ***(User Tutorial)***

***Shelf Tools***
* **MIDI IO Setup**: This will create a MIDI Output to a `.midi` file. Then downstream read the same file in and play it back through a live MIDI channel (Windows only).
* **Random Notes**: This setup is useful to observe the necessary point attributes being assigned manually then output through a live MIDI channel.
* **Mode Progression**: The mode progression setup is useful because there is a certain order of operations and mode attributes necessary upstream to produce the `i@note` attribute downstream. First the mode attributes are assigned based on mode, octave, base note, and mode progression. Then the final `i@note` attribute is computed and output through a live MIDI channel.
* **Sound Check**: This will create test spacial MIDI composition with visualization and play it back through a live MIDI channel (Windows only).

For more detailed examples, see the [provided examples](https://github.com/andrew-lowell/HMT/tree/master/examples) folder for Houdini (.hip) files.

* * * * *

### Technical Specifications:
* [Geometry attributes used by HMT](https://github.com/andrew-lowell/HMT/blob/master/ATTRIBUTE_SPECS.md)
* [VEX variables used by HMT controller channel nodes](https://github.com/andrew-lowell/HMT/blob/master/CONTROLLER_CHANNEL_SPECS.md)

* * * * *

### Developers:
**HMT (Houdini Music Toolset)** is developed and maintained by ***Andrew Lowell***.

Additional contributions by Adam Katz, Sujil Sukumaran

* * * * *

### Notice:
This software is provided AS-IS, with absolutely no warranty of any kind, express or otherwise. We disclaim any liability for damages resulting from using this software.
