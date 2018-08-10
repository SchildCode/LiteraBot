# LiteraBot
LiteraBot is a macro-enabled spreadsheet that is compatible with Microsoft Excel 2013+ for Windows.
It is a tool to aid literature reviews involving text searches in multiple documents (PDF and TXT files). It combines features from JabRef, Mendeley, Zotero, Bookends, and Endnote, giving more powerful text search functions and more intelligent automatic generation of BibTeX references.

Homepage: https://github.com/SchildCode/LiteraBot

Author: © Peter.Schild@OsloMet.no, first released May 2017

### Installation:
- Unzip the LiteraBot ZIP file and put all the files in your working directory. That's it. No installation needed.
Note that the files "pdftotext.exe" and "pdfinfo.exe" that are bundled with LiteraBot should be put in the same directory as the workbook file.
"pdftotext.exe" and "pdfinfo.exe" are 32-bit and 64-bit Windows binaries that can be downloaded from http://www.xpdfreader.com/
- At first use, LiteraBot might ask you to change a setting in Edge (or Internet Explorer) to give LiteraBot access to DOI-lookup webservices.

### How to use:
- Collect all your PDF files for a specific literature review in a project dicrectory. The files can stored in multiple subdirecories if you wish. It can be hundreds of files.
- LiteraBot can read only PDF and TXT files. Documents that are not PDF files (e.g. Word etc) should be exported as TXT files.
- LiteraBot uses Regular Expressions (RegEx) for text search. The user does not need to undertands the syntax of RegEx, but it helps a lot if the user wants to build complex searches.
- The user can enter multiple text search strings, each one in a different column. There is no limit to the number of simultaneous searches.
- LiteraBot has 3 macros that you activate by pressing CTRL+L, CTRL+A or CTRL+D:
-- CTRL+L = List all PDF & TXT files in a directory (and subdirectories). You can do this multiple times to collate publications from multiple directories.
-- CTRL+D = Delete the file listed in the active row (e.g a duplicate or irrelevant file) from the project directory. You should first select the row in sheet 'Analyse'.
-- CTRL+A = Analysis: Conduct the user-defined RegEx text search in all the documents, after you have entered one or more RegEx text search strings in columns G+. This macro tries to automatically generate a BibTex reference for each document based on either doi, or PII in the document (and a DOI lookup web service), or XMP metadata stored in PDF files. If no BibTeX reference is found, a hyperlink is made to arXiv, PubMed (PMID), or Google Scholar (if ISBN number os found, otherwise a title search) so that you can access BibTeX for the document from these sites. You can manually edit the BibTeX entries in column 'BibTeX' by keying function key F2.
  CTRL+E: Export as a BibTeX bibliography file (.bib). This can then be used directly in your preferred LaTeX application, or converted to other bibliometric file formats using an application such as JabRef.
- For tips about RegEx search commands, click on the 'SEARCH STRINGS' hyperlink in sheet 'Analyse'.
- For tips about the BibTeX format, see the Wikipedia page about BibTeX. BibTeX files can be imported to many other programs, including JabRef.

### Licence:
- The LiteraBot workbook and source code are licensed under Creative Commons lisence CC BY-NC-SA (Attribution-NonCommercial-ShareAlike). This license lets others remix, tweak, and build upon your work non-commercially, as long as they credit you and license their new creations under the identical terms.
- The stand-alone executables "pdftotext.exe" and "pdfinfo.exe" are both copyright 1996-2017 Glyph & Cog, LLC. They are redistributed free and licensed under GPL v2 and GPL v3. (http://www.xpdfreader.com/). To comply with the GPL, you must redistribute the Xpdf documentation along with the executables. For this reason, files "Xpdf_README.txt" and "Xpdf_3.txt" are bundled together with LiteraBot.
