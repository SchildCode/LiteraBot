# LiteraBot
LiteraBot enables literature reviews involving full-text search in multiple documents (PDF and TXT files), and automatically generates a BibTeX reference list. It combines features from JabRef, Mendeley, Zotero, Bookends, and Endnote, giving more powerful text search functions and more intelligent automatic generation of BibTeX references.
LiteraBot is a macro-enabled spreadsheet that is compatible with Microsoft Excel 2013+ for Windows.

Homepage: https://github.com/SchildCode/LiteraBot

Author: © Peter.Schild@OsloMet.no, first released May 2017

### Installation:
- Unzip the LiteraBot ZIP file and put all the files in your working directory. That's it. No installation needed.
Note that the files "pdftotext.exe" and "pdfinfo.exe" that are bundled with LiteraBot should be put in the same directory as the workbook file.
"pdftotext.exe" and "pdfinfo.exe" are 32-bit or 64-bit Windows binaries that can be downloaded from http://www.xpdfreader.com/
- However, this is a Visual Basic macro-enabled spreadhseet. You must activate macros for it to function: 
  - When you open the file for the first time in Excel, you will see a yellow bar at the top of the window, with the message *"PROTECTED VIEW Be careful... [Enable Editing]"*. Click on the 'Enable Editing' button. 
  - Next, depending on the security settings on your installation of Microsoft Excel, a red bar may appear at the top of the window, with the message *"BLOCKED CONTENT Macros in this document have been disabled..."*. This can be solved by moving the file to a directory on your PC that you designate for files that you trust, then open the file in Excel. To designate a 'trusted directory', click on **File > Options > Trust Center > Trust Center Settings > Trusted Locations > Add new location**, then browse to a directory, e.g. C:\TEMP\. Finally check that **Trust Center Settings > Trusted Documents > Disable Trusted Documents**  is not ticked.
  - When macros are properly activated, **EpXL** shows a small square splash-screen when you open the file. This splash screen shows the licence info, and advises you if an update is available for download from GitHub. Simply press 'Close' button to close the splash-screen. 
  - If still no splash-screen appears, then you might be able to fix it by menu option **File > Options > Trust Center > Trust Center Settings > Macro Settings > Disable all macros with notification**, which is a suitable level of security.
- At first use, LiteraBot might ask you to change a setting in Edge (or Internet Explorer) to give LiteraBot access to DOI-lookup webservices.
- You might need administrator priveleges for LiteraBot to be allowed to execute "pdftotext.exe" and "pdfinfo.exe".

### How to use:
- Collect all your PDF files for a specific literature review in a project dicrectory. The files can stored in multiple subdirecories if you wish. It can be hundreds of files.
- LiteraBot can read only PDF and TXT files. Documents that are not PDF files (e.g. Word etc) should be saved as PDF or TXT files.
- LiteraBot uses Regular Expressions (RegEx) for text search. The simplest type of search is a single word. You do not need to undertand the syntax of RegEx, but it helps a lot if you want to build complex searches.
- The user can enter multiple text search strings, each one in a different column. There is no limit to the number of simultaneous searches.
- LiteraBot has 3 macros that you activate by pressing CTRL+L, CTRL+A or CTRL+D:
  - CTRL+L = List all PDF & TXT files in a directory (including its subdirectories). You can do this multiple times to collate publications from multiple directories.
  - CTRL+D = Delete the file listed in the active row (e.g a duplicate or irrelevant file) from the project directory. You should first select the row in sheet 'Analyse'.
  - CTRL+A = Analysis, which involves three things: 
    - Conduct a full-text search in all the documents, after you have entered one or more RegEx text search strings in columns G+. The number of search results is tabulated in columns G+, and text extracts together with page number are added as pop-up comments. In addition the 5 most relevant documents are listet in a pop-up comment at the top of each column.
    - Extracts an abstract from each file and shows this as a pop-up comment in column A ine ach row. This same column has a hyperlink that you can click to open the document.
    - Automatically generate a BibTex reference for each document based on either doi, or PII in the document (and a DOI lookup web service), or XMP metadata stored in PDF files. If no BibTeX reference is found, a hyperlink is made to arXiv, PubMed (PMID), or Google Scholar (if ISBN number os found, otherwise a title search) so that you can access BibTeX for the document from these sites. You can manually edit a BibTeX entry in column 'BibTeX' by pressing function key F2.
  - CTRL+E: Export as a BibTeX bibliography file (.bib). This can then be used directly in your preferred LaTeX application, or converted to other bibliometric file formats using an application such as JabRef.
- For tips about RegEx search commands, click on the 'SEARCH STRINGS' hyperlink in sheet 'Analyse'.
- For tips about the BibTeX format, see the Wikipedia page about BibTeX. BibTeX files can be imported to many other programs, including JabRef.

### Licence:
- The LiteraBot workbook and source code are licensed under Creative Commons lisence CC BY-NC-SA (Attribution-NonCommercial-ShareAlike). This license lets others remix, tweak, and build upon your work non-commercially, as long as they credit you and license their new creations under the identical terms.
- The stand-alone executables "pdftotext.exe" and "pdfinfo.exe" are both copyright 1996-2017 Glyph & Cog, LLC. They are redistributed free and licensed under GPL v2 and GPL v3. (http://www.xpdfreader.com/). To comply with the GPL, you must redistribute the Xpdf documentation along with the executables. For this reason, files "Xpdf_README.txt" and "Xpdf_3.txt" are bundled together with LiteraBot.

### BibTeX for citing LiteraBot

```bibtex
@Misc{Schild23,
  author = {Schild, Peter G.},
  title = {{LiteraBot}: Software tool to analyse and cite publications},
  howpublished = {\url{https://github.com/SchildCode/LiteraBot/}},
  year = {2023}
}
```
