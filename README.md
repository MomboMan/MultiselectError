# MultiSelectTextFunc Error
Shows the MutliSelectTextFunc error

A small demonstration of the MudBlazor MultiSelectionTextFunc Error.

What happens:  The MultiSelectionTextFunc callback gets called numerous times, often when it shouldn't be involved at all.

How:  Build and run the project while the Output window is open, click on the MudBlazor tab then click on the Report dropdown.  You should see this:<br>
<div>
  ...<br>
Host extension connected<br>
Initializing host services...<br>
[0m[48;5;127m[38;5;231mblazor[0m[1m Loaded 10.77 MB resources<br>
[0mThis application was built with linking (tree shaking) disabled. Published applications will be significantly smaller.[0m<br>
Loaded 10.75 MB resources from cache<br>
Loaded 0.03 MB resources from network<br>
GetMultiSelectionText<br>
GetMultiSelectionText<br>
The thread 0xc0f4 has exited with code 0 (0x0).<br>
...<br>
The thread 0x85e0 has exited with code 0 (0x0).<br>
rptPicked<br>
GetMultiSelectionText<br>
GetMultiSelectionText<br>
rptPicked<br>
GetMultiSelectionText<br>
GetMultiSelectionText<br>
...<br>
</div>

Problem:  The first two calls to GetMultiSelectionText are for no reason at all then everytime rptPicked is called GetMultiSelectionText gets called twice.
