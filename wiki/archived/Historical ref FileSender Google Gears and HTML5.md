FileSender uses the Gears plugin to allow transfers of files larger then 2 GB.  The Google Gears team recently issued a statement about shifting their effort towards bringing all of the Gears capabilities into web standards like HTML5, implying that Gears development has effectively been halted.  We have been aware of this issue for some time as Google came with a similar but preliminary announcement in December 2009.  After that December announcement we have made some inquiries with Google and started planning for the future.

What does this mean for FileSender? 

For the short term: not much.  First, the Gears team stated they will make sure the Gears plugin will keep working on popular browsers, as long as those don't undergo major architectural changes.  As long as Google's own applications (Google Apps and GMail) depend on Gears we feel it is reasonable to expect them to stick to this promise.  Secondly, Gears is open source and a community has already begun to grow around it as demonstrated by the release of Gears for Linux64 (something Google didn't supply) and a portable XPI for Gears making it work for Firefox 3.6 on Win32 before Google issued a compatible version.

We are likely to have to change our pointers to working versions of the Gears plugin with some frequency as we can no longer simply point to Google's gears page.



For the longer term we plan to move the FileSender user interface to HTML5.  To transfer files larger then 2 GB we chunk the files and transfer those chunks using a blobbing method built into Gears.  This is the only dependency we have on Gears.   We have ensured that we can just as easily use the blobbing method from the file handling interface in HTML5 and from what we know so far of HTML5, the two methods have a strong resemblance.  Midt 2010 we will start work on a HTML5 prototype user interface to verify our assumptions on HTML5's abilities for transfering files larger then 2 GB are correct.  Once we have proven it to work we will start work on integrating it in the production release.



To sum up:

-the functionality for transferring files smaller then 2 GB is not affected at all by the future of Gears

-the functionality for transferring files larger then 2 GB will be supported using Gears on popular browsers for enough time to come, as Google itself depends on it for Google Apps and GMail.

-for the future of FileSender's larger then 2 GB file transfer capability we are looking into HTML5.

If you have questions, please contact the development team through the mailinglist or directly.



On behalf of the FileSender team,

Jan Meijer
