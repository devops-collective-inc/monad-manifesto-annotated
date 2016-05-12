# Chapter 9 - The Monad Management Console (MMC)
Monad provides a rich set of management framework service Cmdlets to facilitate to build management consoles. These services reduce development and test costs to produce admin UIs and consoles while enabling an integrated and admin experience. The services are used to produce an in-the-box management console but can also be used by third parties or in-house IT to implement their ownmanagement console. The goal is to be able to provide 50-70% of a generic management GUI tool for free just by building the right type of Cmdlets. Monad provides the following resources and services:

1. A script execution environment which provides GUIs uniform and consistent access to local and remote resources.
2. Integrated GUI and command line environment so that GUI interactions are displayed in a command line console. Users can use this to learn the automation layer and can also directly execute command line actions as well. This mechanism is also leveraged to provide macro record/playback.
3. Application-specific scripting. The application can expose its inner workings (e.g. buttons, displays, internal data structures etc) via Cmdlets to allow application specific scripting, debugging, and supportability.
4. Base UI controls associated with specific MMMs. (E.g. Navigation controls, lifecycle controls, diagnostic controls).
5. Rich set of base error messages which will be localized by MMC.
6. Declarative UI framework to allow metadata driven custom management GUIs.
