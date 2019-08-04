# FossilJ is a plugin for fossil data acquisition by image analysis, using ImageJ. This first version is optimised for bivalves.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3336200.svg)](https://doi.org/10.5281/zenodo.3336200)

The plugin provides free, open source tools for semi-automated measurements of both drilled and undrilled bivalve shells. 

FossilJ v0.2.1 was built in the FIJI distribution of ImageJ v1.52n.
FIJI is available to download here: https://fiji.sc/

Cite as: Fiona Pye, & Nussaibah Raja-Schoob. (2019, July 15). FossilJ (Version v0.2.1). Zenodo. http://doi.org/10.5281/zenodo.3336200

FossilJ is licensed under a [AGPLv3 License](https://tldrlegal.com/license/gnu-affero-general-public-license-v3-(agpl-3.0)#summary).

The program's documentation is available here:

Summary: 
<ul>
  <li>FossilJ semi automatically collects morphometric data from images of bivalves. </li>
  <li>The measurements are collected in mm and are: </li>
    <p style="text-indent: 40px"><ul style="list-style-type:disc;">
      <li>width (anterio-posterior) </li>
      <li>height (dorso-ventral) </li>
      <li>broken/complete specimen </li>
      <li>number of drillholes per specimen </li>
      <li>drillhole diameter </li>
      <li>incomplete/complete drillhole </li>
      <li>internal or edge drilling </li>
    </p></ul>
  <li>Collected measurements are shown in verification images, which can be cross referenced with the data. This data is produced as two CSV files, general specimen data and drillhole data.</li>
  <li>All specimens and drillholes are given numbers which are unique when used in combination with the image name. </li>
</ul>  

Inputs: 
<ul>
  <li>Input directory containing images with: </li>
  <p style="text-indent: 40px"><ul style="list-style-type:disc;">
    <li>A good contrast between object and background (pale object, dark background). </li>
    <li>Blue scale bar (rgb (0,0,255)) with units of mm or &micro;m (all converted to mm). </li>
    <li>Space between specimens ~&frac13; of specimen size </li>
  </ul></p>
  <li>Output directory (empty) </li>
</ul>

Outputs:
<ul>
  <li>CSV data </li>
  <p style="text-indent: 40px">
    <ul style="list-style-type:disc;">
      <li> "shellmeasurements.csv" </li>
      <ul style="list-style-type:none;">
      <li>Label - Image name </li> 
      <li>Width - Anterio-posterior </li> 
      <li>Height - Dorso-vental </li> 
      <li>Shell - Specimen number (unique per image) </li> 
      <li>Broken - Broken shell = 1, complete shell = 0 </li>
      </ul>
      <li> "drillmeasurements.csv" </li>
      <br>Label - Image name </br> 
      <br>Name - Drillhole reference </br> 
      <br>Shell - Specimen number (unique per image, same as in "shellmeasurements.csv") </br> 
      <br>Type - Internal or edge drill </br> 
  </ul></p>
  <li>Verification Images ("*" indicates where image name is appended) </li>
  <p style="text-indent: 40px">
    <ul style="list-style-type:disc;">
      <li>*measurements - displays length and width measurements </li>
      <li>*valve - shows allocated chirality </li>
      <li>*original_edited - copy of original image with a cleaned black background </li>
      <li>*drillholes - specimens with printed drillhole masks </li>
      <li>*drillholes_drawn - original image with the drillholes as drawn by user </li>
  </ul></p>
</ul>  

Setup:
<ol>
  <li>Install FIJI distribution of ImageJ https://fiji.sc/ </li>
  <li>Download the "FossilJ.ijm" file and the "Macros" folder </li>
  <li>Place the "FossilJ.ijm" file in the "~Fiji.app\plugins" folder </li>
  <li>Place the files from the "Macros" folder in the "~Fiji.app\plugins\Macros" folder </li>
  <li>Open ImageJ using the executable file </li>
  <li>Install the plugin: Plugins tab &rArr; Install PlugIn &rArr; select the "FossilJ.ijm" file </li>
  <li>Restart ImageJ </li>
</ol>

Operation:



Requires blue scalebars (rgb : 0,0,255)
Units can be um or mm, all are converted to mm
Results are better if the screen is bigger
Image windows can be maximised for interaction
Process up to 15 images in one go, but no more as if something goes wrong the data is comprimised and you have to start over
Create input directory for images to be batch processed.
Create output directory to store output verification images and data
Open FIJI
Plugins --> Macros --> Run --> Select the downloaded ijm file
The plugin will start, follow the provided instructions.
Things to note

5a. to calibrate the scale click once on both ends

5b. drawing lines

click and hold to draw line
just release and draw again to correct/make new
specimen order on the page doesn't matter, but do the lines on each specimen in the same order (this will make data processing easier)
Next image will open, repeat process
After all images are processed, results will be saved in the output folder
7a. In the csv file

each measurement is given a line number
each specimen is given a number
line length is called "length", 3rd to last column
7b. In measurement images

each line measured is drawn in red
line number is printed in green on the line
specimen number is printed in the upper left hand corner
Move data into a folder denoting the first run, with original and measured images alongside the data
Place the new set of images into the input folder, check output folder is empty
Repeat from step 4 until all images are processed
