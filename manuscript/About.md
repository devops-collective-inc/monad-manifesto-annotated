# The Monad Manifesto - Annotated

by Jeffrey Snover
as annotated by the PowerShell Community

---

This project is intended to preserve and annotate "[The Monad Manifesto](http://www.jsnover.com/blog/2011/10/01/monad-manifesto/)," a paper written by Windows PowerShell inventor[Jeffrey Snover](https://social.technet.microsoft.com/profile/Jeffrey%20Snover%20Windows%20Server) at Microsoft in [2002](http://takemeback.to/08-August-2002#.VWsXW1xVhBc). The idea for this project came from Pluralsight author [Tim Warner](http://www.pluralsight.com/author/tim-warner), with the initial annotations being made by Tim and Microsoft MVP [Don Jones](https://twitter.com/concentrateddon). 

The original Manifesto was a forward-looking document, predating the public release of PowerShell by around 4 years. In the years since PowerShell's [2006 release](http://blogs.msdn.com/b/powershell/archive/2006/11/14/windows-powershell-1-0-released.aspx), the product has evolved substantially - but always around the broad brush strokes outlined in the Manifesto.

We felt that it was not only important to preserve the document for historical purposes, but also to annotate and expand upon the various concepts it introduces. We'll attempt to link to references for the now-real technologies that the Manifest predicted, and to provide contextual explanations around some of the Manifesto's directives. 

You'll notice [^1] footnotes in the text. These are a [MultiMarkdown](http://fletcherpenney.net/multimarkdown/) feature that aren't supported by our publishing platform, but they're meant to link to corresponding footnotes at the bottom of the page. In some cases, these are Jeffrey's original footnotes, and we've marked those with "ORIGINAL" to set them apart from footnotes we've added ourselves.

---

This guide is released under the Creative Commons Attribution-NoDerivs 3.0 Unported License. The authors encourage you to redistribute this file as widely as possible, but ask that you do not modify the document.

**Was this book helpful?** The author(s) kindly ask(s) that you make a tax-deductible (in the US; check your laws if you live elsewhere) donation of any amount to [The DevOps Collective](https://devopscollective.org/donate/) to support their ongoing work.

**Check for Updates!** Our ebooks are often updated with new and corrected content. We make them available in three ways:

* Our main, authoritative [GitHub organization](https://github.com/devops-collective-inc), with a repo for each book. Visit https://github.com/devops-collective-inc/
* Our [GitBook page](https://www.gitbook.com/@devopscollective), where you can browse books online, or download as PDF, EPUB, or MOBI. Using the online reader, you can link to specific chapters. Visit https://www.gitbook.com/@devopscollective
* On [LeanPub](https://leanpub.com/u/devopscollective), where you can download as PDF, EPUB, or MOBI (login required), and "purchase" the books to make a donation to DevOps Collective. You can also choose to be notified of updates. Visit https://leanpub.com/u/devopscollective

GitBook and LeanPub have slightly different PDF formatting output, so you can choose the one you prefer. LeanPub can also notify you when we push updates. Our main GitHub repo is authoritative; repositories on other sites are usually just mirrors used for the publishing process. GitBook will usually contain our latest version, including not-yet-finished bits; LeanPub always contains the most recent "public release" of any book.
