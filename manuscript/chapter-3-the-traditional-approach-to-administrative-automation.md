# Chapter 3 - The Traditional Approach to Administrative Automation

The traditional[^3-1] model for administrative automation is powerful and successful.  It consists of:

1.    A programmatic shell (e.g. sh, csh, ksh, bash)[^3-5] 
2.    A set of administrative commands (e.g. ifconfig, ps, chmod, kill) 
3.    A set of text manipulation utilities (e.g. awk, grep, sed).  
4.    Administrative GUIs layered on top of commands and utilities

This model's philosophy is that every executable should do a narrow set of functions and complex functions should be composed by pipelining or sequencing executables together.  This model has been extremely successful despite serious drawbacks.  Upon inspection, what is widely considered a UNIX stronghold is in fact a flawed implementation of this model[^3-2].

When you step back and examine what is really going on when someone uses a pipelined command like "$ a | b | c", you conclude that the first command "a" did not accomplish what the admin wanted to do.  If it had, the admin would have just type "a" and been done with it.  So then the question is why didn't "a" do what the admin wanted?  The answer is that in this traditional model, the stand-alone executables tightly bind three operations together: 1) getting objects; 2) processing objects; 3) outputting results as text[^3-4].  One of those operations does not do what the admin needs so the rest of the pipeline is an attempt to fix that.

Because the executable outputs text, the downstream elements must use text manipulation utilities to try to get back to the original objects to do additional work.  While the basic model is extremely powerful, its intrinsic flaw is the tight binding of these operations and the use of unstructured text for integration[^3-3].  This requires clumsy, lossy, imprecise text manipulation utilities.

The traditional model reflects the state of the technology that was available at the time it emerged.  .Net provides[^3-6] a new set of capabilities and opens up the possibility of new approaches.  These new approaches allow us to replace the traditional model with a decisively superior one.  That model is Monad.

---
**Notes**

[^3-1]: Traditional in the Linux/Unix world; certainly not in Windows. This is in fact the change Snover was proposing: to make administrative administration work more like it does in Unix, since Unix is a decades-proven model for success. It probably didn't hurt that Snover came from Digital Computer, a company with more than a passing familiarity with Unix variants and similar operating systems.

[^3-2]: People who view PowerShell as a "linux-ification" of Windows should note that Snover wasn't _enamored_ of the Unix command-line model. He felt it was inconsistent (and, having grown organically, it is) and often lacked good semantics. In many ways, PowerShell was the first "second comer" to Unix's command-line model, taking its strengths but re-thinking what had become somewhat obvious weaknesses.

[^3-3]: There's an enormous point here that's often missed. When you write a tool that produces text, downstream tools have to know how to process that text in the exact format you produced it. Your data is unstructured. If you change the output of your tool, everything that used to work with it, won't. Object orientation - that is, presenting data in a standardized structure that could be consumed by anything understanding "objects" - was one of the biggest differences between PowerShell and what had come before. Much of a Linux admin's time is spent in the grep/sed/awk cycle, since they've got to parse out text so the next tool has data to work with; PowerShell all but eliminates that entirely ancillary work.

[^3-4]: Practical upshot of this is that tools - cmdlets, in the PowerShell world - should do one thing, and one thing only. Get objects, process objects, or format objects into text - pick just one, and do only that. If you do more than one, you start creating a monolithic tool that's less easy to re-use elsewhere. This do-one-thing concept has become a driving foundation for best practices in the PowerShell community, especially around toolmaking.

[^3-5]: These examples emphasize the influence mainframe and UNIX had on Snover's design choices. 

[^3-6]: Realistically, COM could have provided the same capabilities as it was object-oriented. However, by the time the Manifesto was written, COM was effectively deprecated and Microsoft had moved on to .NET.

