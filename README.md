HMT
======

![HMT logo](https://github.com/andrew-lowell/HMT/blob/master/hmt_logo_01.png)

**Houdini Music Toolset**, extends the users' capabilities into the domain of music composition.

HMT makes use of Houdini's powerful geometry and simulation processing in a set of new tools and workflows specifically designed for music. It uses point clouds and attributes within the graphical 3D environment to perform sequencing tasks present in music composition packages. It uses CHOPs as a back-end to import or export MIDI file data either to the midi file format, or directly to a MIDI port. It allows for artists or composers to make use of powerful simulation tools and Houdini's open node-based architecture normally dedicated to producing photorealistic simulations of natural phenomenon and apply the same tools if desired to manipulating or generating patterns of notes.

Because of the modular and node based nature of the toolset present in HMT, and that it adheres when possible to existing Houdini conventions, it allows users to easily develop their own workflows and tools for music creation or processing.

### Installation:

Download the desired release directly from the [releases page](https://github.com/andrew-lowell/HMT/releases) and extract it to your hard drive or network share.

**Plugin (17.5+ only)**
Create a folder inside your Houdini preferences directory (where the houdini.env typically lives) called "packages", and place the HMT.json file from the HMT download into that folder. Then edit HMT.json and change the "HMT" variable to match the install path.

**OS Support (Full functionality Windows only)**
While the toolset is based entirely in Houdini and will perform it's sequencing functions regardless of operating system, the MIDI Output CHOP will only perform live/real-time export to a MIDI channel on the Windows operating system. When Apple/Linux are supported this page will be updated. Exporting to MIDI files is supported on all operating systems.

### Useful Software used in Conjunction with HMT:
**[loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) forms a virtual MIDI port on Windows**. This can then be used to send MIDI data directly to audio and sequencer software without an external device or cable.

**Audio sampler/sequencing software.** Popular audio sampler/synthesizer software includes **Reason**, **Ableton**, or other commercial and free applications. The HMT does not produce audio directly. It sends MIDI notes and events via the MIDI Out CHOP to your application of choice to produce the sound.


### Usage basics:
***Tutorial Links***

***Shelf Tools***
* **MIDI IO Setup**: This will create a MIDI Output to a `.midi` file. Then downstream read the same file in and play it back through a live MIDI channel (Windows only).
* **Random Notes**: This setup is useful to observe the necessary point attributes being assigned manually then output through a live MIDI channel.
* **Mode Progression**: The mode progression setup is useful because there is a certain order of operations and mode attributes necessary upstream to produce the `i@note` attribute downstream. First the mode attributes are assigned based on common mode, octave, and base note. Then the final `i@note` attribute is computed and output through a live MIDI channel.

For more detailed examples, see the [provided examples](https://github.com/andrew-lowell/HMT/tree/master/examples) folder for Houdini (.hip) files.

### Technical Specifications:

Point attributes needed for the proper functionality of HMT:
* `f@time`: The time the MIDI note occurs in seconds
* `i@note`: The pitch of the note in MIDI values (`0-127`)
* `f@vel`: The MIDI velocity of the note, represented in values from `0.0-1.0` (for `0-127`)
* `f@duration`: The duration of the note in seconds
* `i@channel`: The MIDI channel output of the note, often in a range of `1-16`

Point attributes used for workability in HMT:
* `s@note_letter`: The commonplace keyboard letter assignment of the note
* `s@mode_name`: The name of the mode corresponding with the `i@mode` attribute
* `f@pan`: An optional attribute for more flexible panning workflows

Point attributes which are optional for output but needed in some HMT workflows:
* `i@base_note`: The key or modal starting point, for instance "The key of Ab Minor." Represented in MIDI note values (`0-127`)
* `i@note_octave`: The octave on the common MIDI keyboard when dealing with mode progressions
* `i@mode`: The mode index from `0-7`
* `i@mode_progression`: The modal progression of the notes contained within an octave in values from `0-7`. `0` being the root note. When numbers go beyond this value they will progress into the next or previous octave
* `i@minor_type`: The minor style of the Aeolian mode common in western minor scales. `0-2` represent Natural, Harmonic, and Melodic types.

Point attributes used for visualization:
* `v@P`: The time(x) and note(y) of the notes
* `f@pscale`: The velocity of the notes
* `v@N`: The duration(x) of the notes
* `v@Cd`: Used for various color visualizations representing velocity, pan, channel, or mode

Detail attributes used for visualization:
* `f@notation_viz_height`: When using tools which alter the vertical position of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes
* `f@notation_viz_scale`: When using tools which alter the `pscale` of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes

### Developers:
**HMT (Houdini Music Toolset)** is developed and maintained by ***Andrew Lowell***. 

### Notice:
This software is provided AS-IS, with absolutely no warranty of any kind, express or otherwise. We disclaim any liability for damages resulting from using this software.
