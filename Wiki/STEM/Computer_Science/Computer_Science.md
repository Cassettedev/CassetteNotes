[[Home]]
[[Cassette]]
[[Wiki]]
[[Blog]]

[[Humanities]]
[[STEM]]
[[Health]]
[[Docs]]
[[Adulting]]

[[Computer_Science]]

# Computer Science is the study of computation
# Notes on Permacomputing from XXIIVV
## A holistic approach to computing and sustainability inspired from permaculture.
#webnotes

The abundance of digital storage and processing power has caused an explosion in wastefulness, which shows in things like ridiculous hardware requirements for computing even the most trivial tasks. Permacomputing aims at only using computing when it has a strengthening effect on ecosystems.

Permacomputing does not advocate for _going back in time_, despite advocating a dramatic decrease in use of artificial energy, but trusts in human ingenunity to finding clever hacks for turning problems into solutions, competition into co-operation and waste into resources.

It values maintenance and encourages programmers to refactor and rewrite programs to keep them small and efficient, instead of counting on Moore's law to compensate for software bloat.

Instead of planned obsolescence, permacomputing practices planned longevity, reuse and repair of existing technology and approaches waste as a resource.

- Frugal Computing
	- Utilizing computational resources as finite and precious, to be utilised only when necessary, and as effectively as possible.
- Salvage Computing
	- Utilizing only already available computational resources, to be limited by that which is already produced.
- Collapse Computing
	- Utilizing what has survived the collapse of industrial production or network infrastructure.

Rustic Computing refers to the construction of calculation machines using pre-industrial or even pre-historic technology. It reveals a history of computing as the pastime of dilettantes, amateur scientists and tabulators who construct machines to manipulate abstract symbols with no practical application. As these machines are generally less efficient than conventional pencil and paper computation, they allude to a more epicurean practice of computing for pleasure rather than production.

"What is the most suitable programming language for permacomputing?", is akin to asking what is the most suitable plant for permaculture – the entire question contradicts itself.

## Figuring out how to make the best possible use out of the millions of devices which already exist.

**Designing for Disassembly** ensures that all elements of a product can be disassembled for repair and for end of life. This allows for and encourages repairs, with the result that a product's life cycle is prolonged; and it allows for a product to be taken apart at the end of its life so that each component can be reclaimed. Among other shifts in thinking and making, this means minimizing materials, using simple mechanical fasteners instead of adhesives, clearly labeling components with their material type, and ensuring components can be disassembled with everyday tools.

Unlike the nebulous goal of designing a _sustainable_ product, designing a product for disassembly is a more concrete, quantifiable approach to ecologically sound making and to consumption.

| Technique                  | Description | Pros | Cons |
|-----------                 |-------------|------|------|
| Migration                  | Periodically convert digital data to next-generation formats | Data are “fresh” and instantly accessible | Copies degrade from generation to generation
| Emulation                  | Write software mimicking older hardware or software, tricking old programs into thinking they are running on their original platforms | Data won’t need to be altered | Mimicking is seldom perfect; chains of emulators eventually break down |
| Encapsulation              | Encase digital data in physical and software “wrappers,” showing future users how to reconstruct them | Details of interpreting data are never separated from the data themselves | Must build new wrappers for every new format and software release; works poorly for nontextual data |
| Universal virtual computer | Archive paper copies of specifications for a simple, software-defined decoding machine; save all data in a format readable by the machine | Paper lasts for centuries; machine is not tied to specific hardware or software | Difficult to distill specifications into a brief paper document |

Emulation is essentially a way of preserving the functionality of and access to digital information which might otherwise be lost due to technological obsolescence. One of the benefits of the emulation strategy compared with migration is that the original data need not be altered in any way. It is the emulation of the computer environment that will change with time.

>Wait. What nostalgia? This is not about reliving fond memories or fetishize about an imaginary past, it's about being tactical in our choice of medium, so as to propagate a political perspective efficiently

What is meant by "scavenge-friendly electronic parts" is parts that can be assembled with low-tech tools. Parts that can't be manufactured any more, but that are available by the billions in landfills. Those who can manage to create new designs from those parts with low-tech tools will be able to preserve electronics, a power that significantly advantages communities that manage to continue mastering it.

## Collapse informatics is software engineering taking advantage of today's abundance in computing power to prepare for a future in which current infrastructures have collapsed.

It is based on decentralisation, not only because current centralised services and networks will break down, but also because peer-to-peer infrastructures are more resilient and flexible. It aims for simplicity, software should function on existing hardware and rely on modularity in order to enable a diversity of combinations and implementations.

>That which cannot be repaired is already broken

Systems need to be resilient to intermittent energy supply and network connectivity. Collapse informatics prioritizes community needs and make use of open-source licenses to contribute to a knowledge commons in order to be able to succeed in case of economic collapse. The practice of engaging with the discarded with an eye to transforming what is exhausted and wasted into renewed resources.

A post-collapse society that has eventually lost all of its artificial computing capacity may still want to continue the practice of computer science in a purely theoretical level, as a form of mathematics.

Nothing new needs producing and no e-waste needs processing. If your new software no longer runs on old hardware, it is worse than the old software.

### Black Start

Power stations take power to run. So if the electric grid goes down, and the power station goes offline too, how do you restart it? The electric power used within the plant is provided by the station’s own generators. If all of the plant’s main generators are shut down, station service power is drawn from the grid. However, during a wide-area outage, off-site power from the grid is not available. In the absence of grid power, a so-called black start needs to be performed to bootstrap the power grid into operation.

https://wiki.xxiivv.com/site/permacomputing.html

***

# Notes on programming from XXIIVV
### programming practices
-   Prototype before polishing. Get it working before optimizing it.
-   Separate policy from mechanism, separate interfaces from engines.
-   Write simple modular parts connected by clean interfaces.
-   Design programs to be connected to other programs.
-   Write programs to write programs when you can.
-   Design for the future, because it will be here sooner than you think.
-   In interface design, always do the least surprising thing.
-   When a program has nothing surprising to say, it should say nothing.
-   When a program must fail, it should fail noisily and as soon as possible.
-   Write big programs only when it is clear by demonstration that nothing else will do.
-   Consider how you would solve your immediate problem without adding anything new.


https://wiki.xxiivv.com/site/development.html
