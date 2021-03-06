## The Piano Inpainting Application
The Piano Inpainting Application (PIA) is an A.I.-based [Ableton Live](https://www.ableton.com/en/live/) plugin allowing to generate piano performances in an interactive way.

<p align="center">
<img src="docs/resources/pia_generation.gif" width="700"/>
</p>

A more detailed presentation is available on the [accompanying website](https://qhpzsefhy.github.io/pia/).


### How to use
You can download the plugin [here](https://github.com/qhpzsefhy/pia/raw/master/releases/PIA.amxd) and simply drag and drop the `PIA.amxd` file within Ableton Live's  MIDI plugin section. 

<p align="center">
<img src="docs/resources/pia.png" alt="drawing" width="150"/>
</p>

Select a region in the MIDI track you wish to edit by specifying it using the loop selector (CMD + L) and click on PIA's *Generate* button. The *density* knob controls how many notes per second the inpainted region should have. The last button is used to set the *density* knob to the actual note density of the selected region.

Since PIA is fast and responsive, you should immediately see the selected region erased and new notes appearing. You can even listen to the music while it is being generated!

Note that you must be connected to the Internet so that PIA can work.

### PIA's behavior
Here are some insights about the inner-workings of PIA:
- All notes *starting* in the selected region will be removed.
- The first note generated by PIA will start *exactly* at the beginning of the loop brace.
- The maximum number of notes PIA can generate for a single click on the *Generate* button is set to 256. If you request PIA to compose more than 256 notes (if you choose to recompose a large region with a high note density for instance), only the first 256 notes will be generated. We thus advise to focus on performing *multiple* local edits.
- If the MIDI performance disappears and reappears instantly without any change, this means that you are experiencing connectivity issues.
- Please check that the loop brace is *active* when you click on *Generate*.
- If there is no note after the region that you selected, PIA will always consider that the piece should end at the end of the loop brace.
- Even if there are notes after the region you selected, these will be removed while PIA is generating. Don't worry, these will be added back when the generation completes. Note that the offsets of these notes can be changed.
- We did not add the possibility to map the *Generate* button on a MIDI controller since this clutters the Ableton Live undo history.
- PIA only works in Session view.
- There is no way to condition PIA on a particular musical style other than providing a musical context.