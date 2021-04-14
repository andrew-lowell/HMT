**Point attributes** needed for the proper ***functionality*** of notes in HMT:
* `f@time`: The time the MIDI note occurs in seconds
* `i@note`: The pitch of the note in MIDI values (`0-127`)
* `f@vel`: The MIDI velocity of the note, represented in values from `0.0-1.0` (for `0-127`)
* `f@duration`: The duration of the note in seconds
* `i@channel`: The MIDI channel output of the note, often in a range of `1-16`

**Point attributes** needed for the proper ***functionality*** of controllers in HMT:
* `f@time`: The start time of the controller animation in seconds
* `f@duration`: The duration of the controller animation in seconds
* `i@channel`: The MIDI channel of the controller, often in a range of `1-16`
* `i@controller_channel`: The controller channel designation of the controller, often in a range of `0-127`
* `s@controller_channel_format`: Either `anim` or `ramp` The ramp format stores key positions, values, and interpolation type. The anim format stores evenly spaced values.
* `s@controller`: The controller channel data.
* Either the `ramp` format `k.kk k.kk k.kk: v.vv v.vv v.vv: interp interp interp` or the `anim` format `v.vv v.vv v.vv v.vv v.vv`
* `f@sample_rate`: The sample rate of the controller. It's either a samples-per-second rate for the `anim` format or -1 for the `ramp` format.
* `s@controller_name`: The controller channel name or label. While this attribute is note required for final output it is used extensivly in the functionality of many controller channel nodes.

**Point attributes** used for ***workability*** in HMT:
* `s@note_letter`: The commonplace keyboard letter assignment of the note
* `s@mode_name`: The name of the mode corresponding with the `i@mode` attribute
* `f@pan`: An optional attribute for more flexible panning workflows

**Point attributes** which are optional for output but ***needed in some HMT workflows***:
* `i@base_note`: The key or modal starting point, for instance "The key of Ab Minor." Represented in MIDI note values (`0-127`)
* `i@note_octave`: The octave on the common MIDI keyboard when dealing with mode progressions
* `i@mode`: The mode index from `0-6` indicating brightness and assigning the appropriate mode
* `i@mode_progression`: The modal progression of the notes contained within an octave in values from `0-7`. `0` being the root note. When numbers go beyond this value they will progress into the next or previous octave
* `i@minor_type`: The minor style of the Aeolian mode common in western minor scales. `0-2` represent Natural, Harmonic, and Melodic types.
* `i@melody_id`: An attribute used in the note-spline and doppler workflows for per melody processing
* `i@note_id`: An attribute used in the doppler workflows for per note tracking and processing
* `s@chord`: An attribute used in the chord workflow for per input-note chord propagation

**Point attributes** used for ***visualization***:
* `v@P`: The time(x) and note(y) of the notes
* `f@pscale`: The velocity of the notes
* `v@N`: The duration(x) of the notes
* `v@Cd`: Used for various color visualizations representing velocity, pan, channel, or mode

**Detail attributes** used for ***visualization***:
* `f@notation_viz_height`: When using tools which alter the vertical position of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes
* `f@notation_viz_scale`: When using tools which alter the `pscale` of a point-cloud, this detail attribute is used to preserve a uniform visualization scheme in downstream nodes
