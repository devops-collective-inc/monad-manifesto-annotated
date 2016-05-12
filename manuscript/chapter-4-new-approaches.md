# Chapter 4 - New Approaches
___
Monad takes new approaches to the issues of 1) building commands, 2) composing solutions 3) management models and 4) management GUIs.  The Monad architecture flows from the following observations:

1.  Most solutions are home brewed and composed out of existing commands by administrators.
2.  Most solutions are focused on either automating management or providing _ad hoc_ fixes.
3.  Most administrators are para-programmers.  They either don't have the desire, skill or (more often), the time to do sophisticated programming.
4.  Most application developers won't make their code manageable unless there is immediate and substantial user benefit.

## 4.1 - A New Approach to Building Commands
The traditional approach to building commands is inefficient.  Much of the effort is spent rewriting the same functions over and over again by different people in different ways.  They all:

   * Parse, validate, and encode user input.
   * Document usage.
   * Log activity.
   * Format data, output results and report errors.
   * Operate on remote nodes or sets of remote nodes.
   
Yet, despite all this commonality, most platforms[^4][^5] provide little to no support for doing these activities in common consistent ways. The result is that today's commands are inefficient to develop and inconsistent to use.

Monad takes a different approach providing developers maximal leverage and end users maximal consistency by defining an **automation model** for applications which factors out common functions so they can be implemented once in a common runtime environment[^6].  Developers no longer produce stand alone executables.  Instead, they write narrowly focused .Net classes ( **Cmdlets** ) which then are exposed as APIs, commands, and GUIs.  The common functions are implemented and tested once and provide a single set of semantics as well as a consistent and uniform set of error messages.

## 4.2 - A New Approach to Composing Solutions
The traditional approach to composing solutions is difficult and fragile.  It uses pipelines to perform prayer-based parsing of text streams[^7]. These mechanisms are awkward, inconsistent, and imprecise.  Admins spend the majority of their thought process on mechanisms instead of problem solving.  Monad takes a different approach providing a precise, powerful **script execution engine** for creating pipelines of .Net objects. Instead of piping unstructured text, we pipe .Net objects.  This allows the downstream pipeline components to operate directly on the objects and their properties using the .Net [Reflection](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/cpguide/html/cpconreflectionoverview.asp) APIs.  (The reflection APIs allow a utility to find the type of an object, what properties/methods it has, get its property values and invoke its methods)

The Monad Runtime environment provides a means to access Cmdlets and run scripts on remote machines via Web Services.

## 4.3 - A New Approach to Management Models
The traditional approach to management models produces an inconsistent admin experience.  Today there are thousands of locally optimized commands.  Each command developer defines his own management model with a set of names, and concepts.  While copying of popular commands occurs, there is no systemic incentive for doing so.  Efforts have been made to provide guidelines which would drive global optimization but the weight of legacy has made it difficult for such efforts to gain much traction.

A similar situation exists with today's instrumentation technologies which languish due to lack of tool support.  Instrumentation evangelization efforts are difficult as groups reject the "build it and they will come" strategy.  Tool developers balk at the vast surface area of objects and respond by either providing generic functionality (like monitoring or browsing) across a broad range of objects or providing rich features for a narrow set of objects.

Monad takes a different approach: it minimizes the cost of automation and provides immediate end-user benefit by providing **scenario-based automation** extension classes and in-the-box tools that exploit those classes.  Monad can support almost any automation schema but strongly encourages the use of standard schemas by providing a set of base classes for specific administrative scenarios. Those base classes include: Navigation, Diagnostics, Configuration, Lifecycle,  and Operations.  These classes provide common syntax, switches, internationalized error messages and solutions to common scenario problems (e.g. a common implementation of a directory stack for all the naviagation commands]).  Monad also provides a set of UI controls and tools that ship with the OS that drive those extensions to perform a particular management task.


## 4.4 - A New Approach to Management GUI Tools

The traditional approach to management GUIs provides minimal developer leverage.  Today's Windows management GUI tools are developed in the same way that a full blown application is.  They have GUI code, domain logic/constraint enforcement, and API access to local and remote managed objects.  Management GUI services are largely limited to a UI container which facilitates multiplexing multiple tools and a certain level of integration.  This approach requires a sophisticated developer and an exhaustive test matrix.  Because much of the domain logic and constraint enforcement is embedded into the GUI, it is common for the command lines to expose a subset of the functions of a GUI.  The traditional approach works against automation.

Monad takes a different approach providing a **rich set of management oriented services** for developing management GUI tools.  These services allow management GUIs to be layered on top of the scripting engine and Cmdlets.  This provides auditing, macro record/playback and integrated GUI/command line tools.  This decreases the skill level required to develop a management GUI by simplifying both the access to and control of management objects and by providing transparent remoting for free.  It also allows users to see the scripts run by GUI interactions which helps them learn the automation layer and create their own automated scripts.  The layering reduces the test matrix by leveraging the testing done on the command line and scripts and only needing to test the GUI paths to invoke those functions.  The management GUI can also expose its inner workings via Cmdlets which provides developers, testers, and support easy access to the internal state and control of the GUI for debugging/diagnostics/automated test.
___
**Notes:**
[^4]: UNIX has the [getopt()](http://www.gnu.org/software/libc/manual/html_node/Using-Getopt.html) call for simple command option parsing. 

[^5]: [VMS DCL](http://h71000.www7.hp.com/doc/732final/9996/9996pro.html) and AS400’s CL are the exceptions to this.  They provide a common command parser so the commands that use this have a high degree of syntactic consistency.

[^6]: There is a wonderful synergy between programmer’s desire to minimize the amount of code they write for management and customers desire to have a consistent management experience.

[^7]: Prayer based parsing is when you parse the text and pray that you got it right. e.g. Cut off the first 3 (or was it 4?) lines, cut out column 30-40 (assuming that those spaces are not tabs), cast that as an integer (hmm. – does anyone use 64 bits?...well let’s just hope its 32 bits).
