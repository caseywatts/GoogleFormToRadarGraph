SkillsEvaluation
================

Tool to plot google form data as a radar graph. Data collected with a google form, manipulated with Sheetsee.js, and visualized by D3.js.

![Example Visualization](/img/radar1.png "Example Visualization")
![Example Visualization](/img/radar3.png "Example Visualization")


##Setup

1. Create a google form input type "Grid" to collect information from students. See above for an example.
  - The form must have "allow users to edit their responses" enabled.
2. Collect Data
2. In the form output, create a sheet named `Summary` and have it
   transfer summary information you'd like to plot. This will be made
   public, so it shouldn't have identifiable information (other than an
   obscured unique identifier). See above for an example.
  - Share publically the one sheet of the google spreadsheet you don't mind being public. [instructions](https://github.com/jlord/sheetsee.js/blob/master/docs/basics.md#publishing-your-spreadsheet)
3. Set up your index.html file from this repository. This file has
   instructions at the top to configure the file.


##Example of Use
###
- [Example google form that students fill out](https://docs.google.com/a/yale.edu/forms/d/1Kgj2TaeOA-BO2vChj4YZ8xPcTAKuNfncil9Br8yKOtY/viewform)
- [Example form output as a google spreadsheet](https://docs.google.com/a/yale.edu/spreadsheet/ccc?key=0AopzqThqXEKfdC1SUUxKRjU0Y0dGcTJhMmQwdnFfTEE#gid=0)
- Images above show the ouput

###Publishing the File
I recommend publishing this on google drive, since that's a very quick
and easy way to host/share a file this lightweight. [see Google's 
instructions](https://support.google.com/drive/answer/2881970?hl=en). Any other server would be good too, of
course.

###Sending the form to students
Here's an example email with instructions

```
Please do the following:

1. Take this skills evaluation <link>
2. Save the “Edit your responses” link that appears after you submit (in your bookmarks or email). This is how you will keep track of what you know/don’t know. Don’t lose it!
```

###Distributing the Visualization Links
There are at least two ways

1. Use mail merge to send links to the students
2. Tell the students their usernumbers and let them construct the links
   themselves.

##Development
I'm happy to accept pull requests of course :)

The hard part is that local html files can't easily use local js files like it needs to? (was this my problem?)
But if you host it to google drive it syncs in seconds and then can import the relevant js files.

###Application Structure
1. Data is collected with a google form
1. Data is stored in a google spreadsheet
1. Data is coerced and averaged in a google spreadsheet
1. Data is imported to an HTML file via Sheetsee.js
1. Data is visualized in the HTML file using D3.js
1. Links to the many visualizations are shared manually.

###Desired Improvements
* The google spreadsheet output could auto-calculate the groups somehow. Headers from "grid" type google input get headers like `UnixSection[mv, cp, pwd]`. There is probably a clever google sheets equation that could automatically do this.
* Automatically email the result link after submission (maybe via a google script)
* The D3.js part could probably pretty easily be made to be [fork-n-go](https://github.com/jlord/sheetsee.js/blob/master/docs/fork-n-go.md) or a [module](https://github.com/jlord/sheetsee.js/blob/master/docs/custom-charts.md) to be used with google spreadsheets data more generally.

##Credits
D3.js Radar Chart example taken from [here](http://bl.ocks.org/nbremer/raw/6506614/)

