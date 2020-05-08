**Point attributes** needed for the proper ***functionality*** of HMT:
* `f@time`: The time the MIDI note occurs in seconds
* `i@note`: The pitch of the note in MIDI values (`0-127`)
* `f@vel`: The MIDI velocity of the note, represented in values from `0.0-1.0` (for `0-127`)
* `f@duration`: The duration of the note in seconds
* `i@channel`: The MIDI channel output of the note, often in a range of `1-16`

**Point attributes** used for ***workability*** in HMT:
* `s@note_letter`: The commonplace keyboard letter assignment of the note
* `s@mode_name`: The name of the mode corresponding with the `i@mode` attribute
* `f@pan`: An optional attribute for more flexible panning workflows

**Point attributes** which are optional for output but ***needed in some HMT workflows***:
* `i@base_note`: The key or modal starting point, for instance "The key of Ab Minor." Represented in MIDI note values (`0-127`)
* `i@note_octave`: The octave on the common MIDI keyboard when dealing with mode progressions
* `i@mode`: The mode index from `0-7`
* `i@mode_progression`: The modal progression of the notes contained within an octave in values from `0-7`. `0` being the root note. When numbers go beyond this value they will progress into the next or previous octave
* `i@minor_type`: The minor style of the Aeolian mode common in western minor scales. `0-2` represent Natural, Harmonic, and Melodic types.

**Point attributes** used for ***visualization***:
* `v@P`: The time(x) and note(y) of the notes
* `f@pscale`: The velocity of the notes
* `v@N`: The duration(x) of the notes
* `v@Cd`: Used for various color visualizations representing velocity, pan, channel, or mode

**Detail attributes** used for ***visualization***:
* `f@notation_viz_height`: When using tools which alter the vertical position of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes
* `f@notation_viz_scale`: When using tools which alter the `pscale` of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes
