## Basics of a LaTeX document

Simply create a file with the .tex extension. The first thing a document needs is a preamble, which can be as simple as `\documentclass{article}`, followed by the body of the document inside the `\begin{document}` and `\end{document}` environment.

A very minimal document will look something like this: 
```
\documentclass{article}

\begin{document}

This is the text that will appear in the compiled document.

\end{document}
```

## Compiling the PDF

There are several compilers to choose from, but in general `latexmk` is a good option. You may need to install it using your LaTeX package manager (tlmgr or MikTeX).
To use it, either go to the options in your editor and check what compiler is set, or open a terminal in the folder of your .tex file and run `latexmk -pdf document.tex`, and you should get a file named document.pdf.

Every document compilation generates several auxiliary files. You can typically ignore these. They will make subsequent compilations of the document slightly faster, but occasionally when compilation fails for no apparent reason, you may need to clean the auxiliary files and try again. You don't need to share these files with co-authors or push them to a git repo.
To clean these files, simply run `latexmk -c`. Be careful to use a lowercase c, as uppercase C will also clean any generated PDFs as well.

## Loading a document style and packages

In the preamble of the document, packages are loaded with `\usepackage{packagename}`, or if the package has options you wish to set, `\usepackage[options]{packagename}`. Options are comma-separated.

For example, the `\documentclass{}` command has options that can be set for font size and paper size, among others, by including something like [12pt, letterpaper], i.e. `\documentclass[12pt, letterpaper]{article}`.

You may also want to set the margins of your paper smaller than the default LaTeX uses, in which case you can add `\usepackage[letterpaper, margin=1in]{geometry}` do your preamble as well.

## Setting the title and author

Before your `\begin{document}` command, use the `\title{}` command with your document title in the braces.

To list authors, add a line with `\author{Author Name}` for each author.

Just after your `\begin{document}` command, add the `\maketitle` command. Your document class will handle the font size and formatting for the title and authors list. 

Most document classes will insert the current date as part of the title block. To avoid the date being inserted altogether, you can include `\date{}` above the `\being{document}` command, with nothing in the brackets.

## Images

First, load the graphicx package by adding `\usepackage{graphicx}` in your preamble.

```
\begin{figure}[h]
	\centering
	\includegraphics[width=0.8\textwidth]{figure_filename}
	\caption{An example figure. \label{fig:example}}
\end{figure}
```

This example uses the figure environment to encapsulate the figure itself and a caption.

The `[h]` option tells LaTeX to try to position the figure as close as possible to its location in the source code, with some leeway to preserve the flow of the document.

Using `\centering` will center the figure and caption within the text column, rather than justifying it to the left side of the page.

The `[width=0.8\textwidth]` option for the `\includegraphics` command sets the width of the figure to be 0.8 times the `\textwidth`, meaning 80% of the width of the text column the figure appears in.

Including `\label{fig:example}` will allow you to reference this figure in the text later on by typing `Figure~\ref{fig:example}` which will be replaced with 'Figure 1' in the compiled document.

The tilde (~) between the word Figure and the \ref command is to insert a non-breaking space, ensuring that the word Figure and the figure number will be kept together regardless of line and page breaks.

## Tables

Tables are created in the `tabular` environment as follows: 

```
\begin{tabular}{l c r}
  item 1 & item 2 & item 3 \\
  item 4 & item 5 & item 6 \\
  item 7 & item 8 & item 9
\end{tabular}
```
where the {l c r} options for the tabular environment are used to specify both the number of columns and also denote whether each column should be justified left, centered, or justified right.
Each item in a row is separated by the & symbols, and each row is ended with `\\`, the new line command.

Tables can quickly get messy and difficult to read, but fortunately there websites, such as [https://tablesgenerator.com/](https://tablesgenerator.com/latex_tables), that you can use to visually build a table and get the LaTeX code to copy to into your document.

If you prefer an offline solution, there is the package [Excel2LaTeX](https://ctan.org/pkg/excel2latex) that can be used to turn a table from Excel into LaTeX, even carrying over cell colors and font effects.

## Equations

Equations can be placed inline in text by surrounding them with `$`, which works well for single-line equations with no fractions, e.g. `$y = mx + b$`.

For equations that should be numbered in the text, use the equation environment:
```
\begin{equation}
  \gamma = \frac{1}{\sqrt{1 - \frac{v^2}{c^2}}}
\end{equation}
```

## References

Create a file in the same folder and with the same name as your .tex file, but with the .bib extension.
In this file, you can paste the BibTeX output you get from the library or journal website for the article you wish to cite.

At the end of your LaTeX document, before the `\end{document}` command, you will place a line with `\bibliography{file.bib}` with your .bib file's name there.

The first part of each BibTeX block is the citation key, which is how you'll refer to it in the source of your LaTeX document.

For example:
```
@article{maiman1960,
  title = {Stimulated Optical Radiation in Ruby},
  author = {Maiman, T. H.},
  year = {1960},
  month = aug,
  journal = {Nature},
  volume = {187},
  number = {4736},
  pages = {493--494},
  publisher = {Nature Publishing Group},
  issn = {1476-4687},
  doi = {10.1038/187493a0},
  langid = {english},
}
```

To cite this in your text, you would simply type `\cite{maiman1960}`, and the in-text citation will be formatted according to the bibliography style you're using, typically set by the journal's document class.

Multiple inline citations can be added by simply separating the citation keys with commas in the cite command: `\cite{maiman1960, otherauthor2008}`.

As you write and cite more articles, LaTeX will make sure that they are always numbered correctly so when you add a reference earlier in the document, you never need to worry about renumbering anything.

## [Next - Citation Management](citations.md)
