SUBMISSION: 1
TITLE: Towards Graphical Configuration in the INTO-CPS Application


#  REVIEW 1
SUBMISSION: 1
TITLE: Towards Graphical Configuration in the INTO-CPS Application
AUTHORS: Christian Legaard, Casper Thule and Peter Gorm Larsen

----------- Overall evaluation -----------
SCORE: 2 (accept)
----- TEXT:
The authors describe their progress towards a graphical interface within the INTO-CPS tool that allows co-simulations to be composed and configured. The tool follows the SSP standard associated with FMI.

This looks like a promising development for INTO-CPS. My main complaint about the paper is that is blurs the distinction between SysML/SSP as abstract representations, the specifics of the GUI that makes manipulations of objects concerned with those formats (using GUI-concepts), and the storage of the model externally. So for example, in 3.2 it says that it is important to be able to compose "components" (which I think means FMUs throughout). It then explains that this is done by GUI actions (dragging from a Project view) and linking input/output ports. But presumably what is really happening is that an abstract SSP concept of a group is being used, which comprises FMUs and connections; that is then *realised* in a GUI with windows and mouse actions, and finally the result is saved to some file storage in (what?) an SSP defined XML format. So the GUI could be done many different ways, but the SSP concept at the start is the same, and the XML output at the end is the same. If!
  these separate concepts were separated, the paper would be clearer.


~~Another example, on p5 it says that artefacts do not always correspond to files, and that this is important. But files haven't been mentioned before this point. It then says that SSP will store "wt" as a part of an XML structure. But to me this is mixing different levels: SSP has abstract artefacts; the Project view displays artefacts on a UI; SSP is stored in XML. The description isn't wrong, but it is telling us something about the storage level in a section that seems to be about how the UI represents the abstract concepts.~~ **CML commented out. What is written is correct but not relevant. Main point is currently the intocps application can only show artefacts corrosponding to concrete files; multimodels, dse scripts, models, etc.**

~~On p6, at the end of 3.2, it says that a drag of output to input might "disable terminal ports" because of unit mismatches. I first read that to mean ports would be permanently disabled for some reason, but I think you're saying that the UI will not accept a drop onto a receiving port that is of the wrong unit/type? That's a good UI feature, but this is mixing things again: SSP (presumably?) defines the concept of connectivity and of types and type-matching; the UI interprets this one particular way (and there are other ways, but only one underlying rule).~~ 
**CML: rephrased**

It's a bit late to re-structure now, but perhaps in further work the authors would consider introducing the SSP concepts first, then explaining how those concepts are realised by the UI, and finally (if needed) how the result is exported/stored. 

Smaller points:

~~The text says that Figure 1 illustrates an underlying SSP representation of the model, but SSP is not shown in the diagram and this early in the paper the reader does not necessarily know what SSP does.~~ **CML: old figure replaced by "file structure"**

~~I did wonder, on p6, whether the use of a parameter for the gravitational constant was to allow for co-simulations to be run in different planetary environments :-)  But in the end I decided it was just a "named constant" rather than a parameter that one might adjust - is there no distinction here in SSP? (It's just that FMI has different ScalarVariable settings for parameter and constant, so I thought SSP would too).~~ **CML: elaborated this, the goal is really to be able to adjust parameter value centrally**

~~On p4, introducing SSP with Fig3, it would help if it could explain a bit more about the sort of information that SSP defines. The diagram suggests that it is (what?) a collection of FMUs, but not(?) the port interfaces (since that is within "FMI" box)??~~ **CML: Figure removed**

Typos

* ~~Abstract, "eliminates the need [for] external tools"~~ PGL fixed
* ~~Abstract, "by making use [of] a complementary standard"~~
* ~~p1, "The INTO-CPS project [has] created a tool chain"~~
* ~~p1, "configuration of co-simulations has[,] in the past[,] most conveniently"~~
* ~~p2, "Figure 1 illustrate[s] the change"~~
* ~~p3, "semantic adaptations [are] currently established"~~
* ~~p3, "as different kinds of annotation[s]." (singular) p3, "existed to define such data" - but there is no "such" data in this context. What data do you mean?~~ **CML: rephrased**
* ~~p4, Fig3 would be much clearer on a b/w printer if you used different shades.~~ **CML: no longer relevant, since figure has been replaced**
* ~~p4, "to express certain graphics[-]related aspect[s]"~~
* ~~p5, "is defining instance[s] of components"~~
* ~~p6, "which [do] not match its type"~~
* ~~p6, "There is an important difference [between] how parameters are"~~
* ~~p7, "it allows [for the] composition of a system from"~~
* ~~p7, "to allow these mismatches to [be] corrected without"~~
* ~~p7, "commonly used types of adaptation[s]" (singular)~~
* ~~p8, "A specific example[:] two views that"~~
* ~~p9, Fig9 caption, "of semantic adaptation[s]"~~
* ~~p11, "Maestro supporting the [SSP]" (not SPP!)~~
* ~~p11, "as early in the development cycle [as possible]."~~
* ~~p11, "investigate [whether] a suitable method exists"~~
* ~~p11, "each run is evaluated by [means of] one or more"~~
* ~~p11, "and therefore require[s] the user to manually define"~~



# REVIEW 2
SUBMISSION: 1
TITLE: Towards Graphical Configuration in the INTO-CPS Application
AUTHORS: Christian Legaard, Casper Thule and Peter Gorm Larsen

----------- Overall evaluation -----------
SCORE: 1 (weak accept)
----- TEXT:
This paper proposes a graphical editor for the architectural structure of multimodels in the INTO-CPS Application. The editor appears to cover the description of multi-model architecture in the SSP supplementary standard notation, and supports the description of hierarchical multi-models, semantic adapters, and Design Space Exploration (through exposure of design parameters). 

The paper's proposal appears sensible, and is described in a straightforward, well structured way. I miss an adequate description of the SSP notation at the outset that justifies our interest in it. I also miss a brief discussion of the semantics of the proposed hierarchical subsystem selection (the example does not seem to show how one deals iwht a selection from a subset of available components). The contribution is practical ad broadly sound. 

There were only some small language typos to fix. 

* ~~Abstract: mking use *of* a complementary standard~~

* ~~pg 1 "The iNTO-CPS project *has* created a tool chain"~~

* ~~Throughout, I was confused between "the profile" "the SysML CPS profile" etc. Please use a single name for the profile (unless there is more than one profile to consider here, in which case be clearer about which is which).~~**cml: rephrased**

* ~~pg 3 "This *results* from the fact ...."~~ **CML: rephrased**

* Section 2.2 can confuse the reader about the relationship between semantic adaptation and hierarchical co-simulations. You might almost think that a HCS is a kind of SA. Clarify? Maybe a simple example would help here. **cml: agree, at the surface they seem somewhat different, but HCS can be acheived by SA?**

* ~~Section 2.3 first sentence. "such data" - what data do you mean?~~ **CML: rephrased**

* ~~pg 4 "It is the clear ambition of the developers ..." Where have the developers said this?~~ PGL commented out

* ~~I could not understand the final sentence of Section 2. Do you mean that you are imagining some editor which has these capabilities?~~ **CML: can find the sentence in question, is it gone?**

* ~~Section 3. Is the "Integrated Graphical Editor" the same thing as the "Scenario Editor"? Use terms consistently.~~ **CML: considering changing name to simply "graphical editor", its a bit generic, but in the context of the application it arguably conveys the nature of the editor. Now referred to as graphical editor!** 

* ~~Everywhere in the paper, use ther term "in Figure X" instead of "on Figure X".~~ PGL fixed

* ~~Section 3. Can you say something about what if any type restrictions and invariants can be applied to component parameters? They do appear to be an abstract specification of a black-box component (the FMU), so it's worth knowing how rich or limited the language is and hence what the potential is for defining inconsistent parameter sets (with respect to the FMU's internal semantics).~~ **CML: i thought about this too. It does not seem like the standard defines any constraint mechanisms, however these could be implmented as a layered standard. Added description of this to section 3.3**

* ~~pg 11, Section 6.2.2 "SPP" should be "SSP"~~
* ~~Section 6.3 line 1 "validate a *system's* behaviour"~~
* ~~Section 6.4 line 3 shoudl be ""... is evaluated by means of one or more cost functions, each defined in its own Python script. The scripts take as input the traces ..." (if that's what you meant)~~. 

References

~~[7] looks weird: note capitalisation of FMI, volumne number 0(0) and repetition of partial DOI~~ **PGL fixed**

In all the refs, if you want to, include the DOIs but not the full URLs. 

[12] ~~Note "ISBN" not "iSBN"~~ **PGL fixed**

[15] ~~looks weird~~ **PGL fixed**



# REVIEW 3
SUBMISSION: 1
TITLE: Towards Graphical Configuration in the INTO-CPS Application
AUTHORS: Christian Legaard, Casper Thule and Peter Gorm Larsen

----------- Overall evaluation -----------
SCORE: 1 (weak accept)
----- TEXT:
* Please disregard my previous review as this was intended for another submission. Apologies for any confusion *

This paper decsribes the use of SSP (System Structure and Parameterisation) for configuring co-simulations in FMI (Functional Mock-up Interface). The work is timely and of interest to the community. I include a few comments below.

~~I did not get a sense of what a "semantic adaptation" is in the beginning of the paper. It would be really useful to include a concrete example, plus ideally examples of how this would look in the current and SSP version much earlier in the paper. Perhaps the watertank example could be made as a running example in this section (would be good to add a couple of sentences for non-insiders as well), maybe a modified version of hierarchical watertank (e.g. three-tank or variation)?~~ **CML: expanded on SA and gave simple example based on the running example.**

~~Is there any other SSP work going on that we know about? Are there wider implications, e.g. like making INTO-CPS cross-comatible with other tools?~~**CML: Added a few sentences about the implications in terms of cross-compatability of SSP and the current adoptation**

A general proofread is required (some capitalisation, missing spaces before parantheses).
