Creo_v1
=======

This is a simple webpage designed to provide automation to tedious Creo tasks through PTC's integrated Pro/Weblink API.

The first automation task attempted was automatically saving drawing PDFs. To that end, when the "EXPORT DRAWINGS" link is clicked, a table appears populated with all the drawings currently in your Windchill workspace. Based on the part number, the program will determine the correct target directory  to save the file and even determine whether the drawing already exists there. The three options available for each drawing are: Color (Color or Black-and-White), where to save the PDF to (Desktop or Automatically Determined Target Directory), and whether to overwite the existing PDF or not. 

The drawing exports functionality is actually quite full featured and could be easily expanded to work on STL files for rapid prototyping. 

The site WAS hosted temporarily hosted at: [dev.okdane.com](http://dev.okdane.com). To get it working locally on your computer, just change the jQuery CDN url from "https:" to "http:" in index.html.

**Screenshots**
![Creo_v1 Screenshot](/pic/screenshot_Creo_v1.png)

PDF Release Table
![Creo_v1 Screenshot](/pic/screenshot_Release_Table.png)

**Current Status**

I've worked through several of the non-trivial cases (atleast non-trivial to me). This included:

1. Listing all the *.drw's in your active workspace.
2. Exporting a pdf with custom settings (the settings were no-pdf_viewer and mono-color).
3. Based on the part number the drawing is given a target directory. This is broken out into a dirTarget function (or something like that), so you can change it to suit your needs.
4. A data grid is populated with relevent information using jqGrid. This information contains the drawing description, target directory, and part number.
5. If you click the column header for Color and Target Directory, it will toggle through all the options for every drawing at once.
6. The data grid allows you to toggle between the target directory or just the desktop, toggle whether to override the existing file, and what color option to export it with.

**Next Areas of Improvement**

1. Expand the function that gets the description for the drawing. A lot of companies don't actally draw the description from the drawing parameneter, they use the Description from the part. My function currently just assumes the part used in the drawing has the same partnumber as the .drw, and otherwise returns Not Available. I plan on eventually expanding this function to determine the active part in the drawing and then pulling the description.
2. Make jqGrid
3. Change the OverRide/Re-use and Color options into icons instead of text that indicates which option is selected.
4. Make the target directory bold if they have changed it to target the Desktop. This currently works, but it only bolds the column after sorting it.
5. Refactor all the functions into a more appropriate library. This was just kind of a prototype and proof of concept. It would be nice to refactor it and make it work for DXFs, STLs, etc.

Feel free to use any of this, but I would hugely appreciated if you'd teach me anymore you figure out.

D
