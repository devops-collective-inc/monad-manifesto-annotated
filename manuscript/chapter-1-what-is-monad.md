# Chapter 1 - What is Monad?
___
Monad[^1-1][^1-2] is the next generation platform for administrative automation. Monad solves traditional management problems by leveraging the [.Net Platform](http://bit.ly/1PAsRao). From our prototype (though limited), we can project significant benefits to developers, testers, power users, and administrators. Monad leverages[^1-6] the [.NET Common Runtime](http://bit.ly/1Q0TrV3) to provide a powerful, consistent, intuitive, extensible and useful set of tools that drive down costs of administration and make the life of non-programmers a lot easier. 

Monad consists of:

1. [Monad Automation Model (MAM)](): An automation model based upon [.Net classes](http://bit.ly/1R9oPTO), methods and attributes to produce [Cmdlets](https://msdn.microsoft.com/en-us/library/ms714395(v=vs.85).aspx).[^1-3]
2. [Monad Shell (MSH)](): A .Net based script execution environment for exposing Cmdlets as [API](https://msdn.microsoft.com/en-us/library/ms123401.aspx)s command line tools and interactive programmable command line shell.
3. [Monad Management Models (MMM)](): The set managed code base classes (or interfaces) to implement specific management scenarios and in-the-box administrative tools to execute those scenarios.  
4. [Monad Remote Scripting (MRS)](): A set of [Web Service](https://msdn.microsoft.com/en-us/library/ms950421.aspx) based components that allow scripts to be remotely executed on many machines[^1-4].
5. [Monad Management Console (MMC)](): A .Net based model and set of services for building management GUIs on top of [MSH](https://technet.microsoft.com/en-us/magazine/2005.11.scripting.aspx) and exposing all GUI interactions as user-visible scripts[^1-5].

This [white paper](https://en.wikipedia.org/wiki/White_paper) presents the traditional approach to administrative automation, its strengths and shortcomings. Monad’s new approaches are then articulated. An overview of the major components of Monad is then presented. A set of [value propositions](https://en.wikipedia.org/wiki/Value_proposition) is then articulated for Monad’s target audiences.

___

**Notes:**

[^1-1]: (ORIGINAL) This is not a Windows PowerShell whitepaper nor is it an accurate description of how [V1.0](http://blogs.msdn.com/b/powershell/archive/2006/11/14/windows-powershell-1-0-released.aspx) works. This is a version of the original Monad Manifesto which articulated the long term vision and started the development effort which became [PowerShell](http://bit.ly/1Q0TyzZ). Many of the elements described in this document have been delivered and those that have not provide a good roadmap for the future. The document has been updated for publication. Confidential information has been culled and examples are updated to reflect the current syntax.

[^1-2]: (ORIGINAL) [Monads](https://en.wikipedia.org/wiki/Monadology) are [Leibniz’s](https://en.wikipedia.org/wiki/Gottfried_Wilhelm_Leibniz) term for the fundamental unit of existence that aggregates into compounds to implement a purpose. In this philosophy, everything is a composition of Monads. This captures what we want to achieve with [composable](https://en.wikipedia.org/wiki/Composability) management. More information on Monadology can be found at: [http://www.wise.virginia.edu/philosophy/phil206/Leibniz.html](http://www.wise.virginia.edu/philosophy/phil206/Leibniz.html)

[^1-3]: Version 1 of PowerShell shipped in 2006, and provided the implementation for these cmdlets. Cmdlets today are written in [.NET languages](https://en.wikipedia.org/wiki/List_of_CLI_languages), and consist of a single class per cmdlet. PowerShell provides a base class that does much of the heavy lifting; developers define properties of the class that become parameters, and override specific methods to participate in the pipeline lifecycle. Cmdlets, along with the overall environment, were the first of four major vision points proposed in the Manifesto.

[^1-4]: Remoting was introduced in PowerShell [version 2](http://blogs.msdn.com/b/powershell/archive/2009/07/23/windows-powershell-2-0-rtm.aspx), which shipped in the box with Windows Vista and Windows Server 2008. [Remoting](https://technet.microsoft.com/en-us/magazine/ff700227.aspx) is the second of the four major vision points proposed in the Manifesto.

[^1-5]: Although never exposed as an [MMC](https://msdn.microsoft.com/en-us/library/bb742441.aspx) per se, PowerShell's engine was implemented as a .NET class. Any .NET application can instantiate the engine, run commands, and translate the output into a GUI display. [Exchange Server 2007](https://technet.microsoft.com/en-us/magazine/2006.12.managementshell.aspx) was the first product to do so, and remains one of the best examples of the "full-on PowerShell approach" to administration.

[^1-6]: It should be noted that PowerShell very nearly didn't exist because of its dependency on .NET. At the time, in 2004-2006, a startling number of high-profile managed code projects were failing, contributing to the delays in Windows Vista. Running around Microsoft preaching about some management scripting language written in .NET wasn't politically correct at the time. In fact, it was so risky that the Exchange Server team actually built in _entire intermediate API_ under their PowerShell cmdlets, on the theory that they could trash the cmdlets and switch to something else more easily, if needed.



