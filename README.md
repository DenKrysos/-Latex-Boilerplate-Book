# -Latex-Boilerplate_Book

A Boilerplate/Template together with some Macros and ready-to-use set-up surroundings for LaTeX.
This Project is mainly optimized for using "KOMA Script".
<br/>

Lead development \documentclass is "scrbook": Document-Type on the level of a *Book*, which is usually used for large documents and enables *Chapter* as Structuring Level (as opposed to "Article").
Nonetheless, "scrarticle" is also included to work (of course then without \chapter).
<br/>

Just saying, there are also Boilerplates for "target-specific" Article-type Documents (e.g. IEEE, ACM, etc):<br/>

> [https://github.com/DenKrysos/-Latex-Boilerplate-Paper_Poster](https://github.com/DenKrysos/-Latex-Boilerplate-Paper_Poster "DenKr Latex Paper/Poster-Boilerplate Sophisticated")

> [https://github.com/DenKrysos/-Latex-Boilerplate-Paper-Modest](https://github.com/DenKrysos/-Latex-Boilerplate-Paper-Modest "DenKr Latex Paper-Boilerplate Modest")
<br/>

## Compilation
* This here is meant to be compiled with 'LuaLaTeX'
* Remember to add "--shell-escape" to your compiler's arguments in order to make all that Standalone & TikZ stuff working
* For Overleaf refer to the here included file "latexmkrc"
* Examplary proper compiler argument setup
  * TeX Live / Texlipse
    * -synctex=1 -interaction=nonstopmode --shell-escape %input
  * Overleaf 'latexmkrc'
    * $lualatex = 'lualatex %O %S --synctex=1 --interaction=nonstopmode --shell-escape';

## Description
* Layout and Skeleton Setup is well separated from the content
* Set up for Biblatex
* Set up for glossaries (requires external builder, pretty easy to configure)
* All the layout regarding stuff is inside "0organization"
  * There mostly only thing has to be touched: Choose your prefered Author-Format (different Files for different Formats) and also write the correct Authors themselves there
* "2ProjectSetup.tex" has some Makros set-up to unify directory-references. For easy use, just leave it as is and use the Macros when e.g. including files out of the set folders.
* The structuring of your Project Skeleton starts from "3Disposition.tex". The rest happens inside the directory "4chapter".
  * I suggest to just leave "3Disposition.tex" as is and work inside "4chapter". But if you prefer, changing "3Disposition.tex" is fine as well.


## Some Features:
* Macro to automatically include a "standalone tikz picture" with the best options.
  * Ensures, that the picture does not exceed the page/environment size on any side
  * Allows several options, like rotate, crop, insert as plain-text (render together with main file) or as pre-rendered pdf-picture.
  * If desired the pictures can be included as "buildnew". Means: They are only rendered new, if they changed. Saves a lot of compilation time.
  * Allows explicit scaling and positioning
* tikz:
  * Some 3-Dimensional Graphic Generation done in tikz
  * Flow Graph Toolset

* For sure some more features I can't quite recall. That thing is huge...


### Templates, Examples
A File that provides Templates for proper Bibtex-Entry-Definition is
  > "./0organization/1main/8templates/literature_1Template.tex"


## Modus Operandi, Nodes, Tipps, Tricks


## Project Divergence
A lot of Files in here are linked from other Projects.<br/>
When working "Git-based", this won't be an issue anytime, because then already distinct standalone copies of these files are created.<br/>

But when working with an Overleaf-Project that you created as a Copy of this Overleaf-Project directly inside Overleaf, the files are still links. This is partly cool, because then you always have updates right at hand, whenever I perform such. But on the other hand, sometimes you might want to change things, like Package-Options. And it appears like that's not possible, because you can't modify linked files.<br/>
In that case, create the project divergence yourself: Go into the file in question (e.g. "./0organization/1main/2includes/packages/figure_subfigure_caption.tex"), copy its content, remove (delete) the linked file, create a new one with the same file-name and paste the content into. Then adjust to your needs (e.g. modify the caption formatting).

### Recommendation
Actually, for most cases, I would recommend performing a "Deep Copy" of the Project. I.e. not taking over the links referring to files in other projects, but having own duplicates so that the new Project works fully standalone.<br/>

You can achieve this for example via downloading the Project as .zip from the GitHub-Repository, then in Overleaf choose "New Project -> Upload Project" and give the downloaded .zip.

#### Deep Copy'd Overleaf-Project
Now it might become a little confusing, but bear with me, it actually makes it easier for all of us, including you. Above, I talked about stuff like "originating Overleaf Project" and "linked to GitHub" and "linked Files".<br/>
Actually, all that stuff hasn't to concern you at all. I found a solution to make it most easy for third users of my Boilerplate. I created yet another Overleaf-Project!<br/>
That means, nobody beside me has access to actual source of this Boilerplate (which is the Overleaf Project in first instance). A second Overleaf-Project now originates form the GitHub-Repo (which in turn is a Fork of the actual origin) and has the Name-Suffix "-DC" (for Deep-Copy).<br/>
So it is a uni-directional Sequence of Pull-instances, where one depends on the previous that looks like
> [Overleaf-Origin-Project] -> [GitHub-Repository] -> [Overleaf-Project-DeepCopy]

By this, the Overleaf-Project for access by others has just ordinary hard-copies of the initially linked files, i.e. works standalone and after fork is independent of things I might be doing sometime later on.<br/>
The ReadOnly-Link to the Overleaf-Project for further Use:<br/>
> [https://www.overleaf.com/read/zwmwhtvzdgng](https://www.overleaf.com/read/zwmwhtvzdgng "DenKr Latex Book-Boilerplate - Overleaf ReadOnly-Link to Deep-Copy'd Project")
<br/>

> What we are now all doing, is either:
> 1. Work with the GitHub-Repository: Download and work locally with your own LaTeX Editor or Download as .zip and use this with "Upload Project" to create an Overleaf-Project
> 2. Take the ReadOnly-Link to the Deep-Copy Overleaf-Project. By that, this Project is added to your Account (as Read-Only). And then just copy this Project to have a a detached standalone new one, fully free to your disposal.
<br/>

Note to myself: The Deep-Copy Project is to only be pulled, never make changes inside that project or push from it. Only copy



## Overleaf
The Basis for this is actually an Overleaf Project. This is linked with a GitHub-Repository and every now and then synchronized to this. So the Git-Repo is actually "only" a fork of the Overleaf-Project.

The TikZ-relating Files are actually not residing within this Overleaf-Project ("3settings", "8templates", "2layout/tikz_standalone") but inside an own, disjoint Project. These files from another Project are then linked to the Boilerplate.<br/>
So inside the Overleaf-Project, these files are links. But when synchronizing to the GitHub-Repo, copies are created that are then factually existing own files.