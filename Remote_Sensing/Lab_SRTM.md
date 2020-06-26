# Lab: Downloading and analyzing the SRTM data

* [Overview](#overview)
* [Data Subsetting](#DS)
* [Data Moaisicing](#DM)
* [Data Cropping](#DC)

## Overview 
<a id="overview"></a>
DEM data is obtained from many sources. One of the source is SRTM. You can freely download the SRTM data of various resolution. In this lab we will do the following

1. Download the data
    Data is acquired in the rectangular tiles. Please click on [Remote Pixel](https://remotepixel.ca/projects/srtm1arc-gl.html#5.87/62.433/-3.535/-1.2). You can see the individual tiles. Locate Pakistan and see the respective tile information. These tiles do not honor the geographic boundaries. Therefore you need to do the mosaicking and clipping to the shape boundary of the country 
2. Mosaicking of the data by QGIS
3. Analyze and calculate attributes by the ```Whitebox tool```
### Data Sub setting
<a id="DS"></a>
Let us first subset the few areas from Pakistan's shapefile. There are number of way you can accomplish this task. We are going to follow a simple way.
**Step1.** Export Pakistan shape file 

You can do that by dragging the required file the QGIS. 

![image-20200626151529502](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626151529502.png)



Or you can add the file by going to 

![image-20200626151802532](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626151802532.png)



**Step2.** From *Select Features* choose the *Select Features by Polygon*. Place the cursor on the required polygon and right click the mouse button. After you have selected few polygon by right clicking, now click the left button. It will highlight the selected polygons.

![image-20200626152101469](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626152101469.png)



**Step3.** Now go to `Edit` :arrow_right: `copy Features`

![image-20200626152615064](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626152615064.png)

**Step4.** Now go to `Edit` :arrow_right: `Paste Features As`:arrow_right:  `New Vector Layer`. 

Click on `New Vector Layer`

![image-20200626154722915](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626154722915.png)



It will pop up a new window as shown below

![image-20200626154946036](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626154946036.png)



Click on right side button in front of `File name`. supply the name of file to be saved and click on ok

![image-20200626155922804](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626155922804.png)



Now this file will appear in the lower left panel

![image-20200626155515204](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626155515204.png)



You can check the properties of this file .

### Data Mosaicking

<a id="DM"></a>

**Step1.** Store the individual tiles in a folder. I have supplied you with individual tiles. Open the QGIS software and click on Layers

   

![image-20200626160542062](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626160542062.png)

**Step2.**Navigate to the folder where individual tiles are stored. Select the following files 

`srtm_50_06` `srtm_51_05` `srtm_51_06` `srtm_52_05` `srtm_52_06`

and click on open.

![image-20200626160936038](C:\Users\Toqeer\AppData\Roaming\Typora\typora-user-images\image-20200626160936038.png)

![image-20200626161109955](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626161109955.png)

Click on `Add`

![image-20200626161929128](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626161929128.png)



![image-20200626161229932](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626161229932.png)

**Step3.** Then click on *Raster*  :arrow_right: *Miscellaneous*:arrow_right: *Merge*

![image-20200626162621470](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626162621470.png)



Click on `Input Layers`

 ![image-20200626162732779](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626162732779.png)



A new window will pop-up. click on `Select All`

![image-20200626162853874](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626162853874.png)

Click on `Ok`. These 5 layers will be selected

![image-20200626163016696](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163016696.png)

scroll down and click on `Merge` and then `Save to Files`

![image-20200626163155863](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163155863.png)

A new window will pop-up. Select an appropriate name and store to an appropriate folder.

![image-20200626163349310](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163349310.png)



Then click on `Run`

![image-20200626163444596](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163444596.png)

The software will start the job

![image-20200626163526147](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163526147.png)

After a while, depending on your computer hardware, the job will be completed

![image-20200626163626488](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163626488.png)

Click on `close`. You will see the newly merged file at left side panel

![image-20200626163809570](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163809570.png)



Change the symbology and the resulting DEM is

![image-20200626163953757](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626163953757.png)



You can notice that the DEM is in a rectangular form.
### Data Cropping

<a id="DC"></a>

To crop the data according to the shape file 

**Step1.** Go to `Raster` :arrow_right:`Extraction` :arrow_right: `ClipRaster by Mask Layer`

![image-20200626170526985](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626170526985.png)

By clicking on `Clip`, a new window will open 

choose `Input Layer` and `Mask Layer`. Note `Input Layer` is merged DEM file whereas `Mask Layer` is shape file of the selected area. Then click on `Clipped` and `save to File`

![image-20200626170644309](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626170644309.png)

Scrol down and `save to File`

![image-20200626170809305](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626170809305.png)

Supply an appropriate name and click on `Run`

![image-20200626170926235](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626170926235.png)

The software will complete the job. Click on close

![image-20200626171039705](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626171039705.png)

You will see the clipped DEM according to the shape file

![image-20200626171140906](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626171140906.png)



Change the symbology. Click on the Transparency  and set the `Additional no data value` to `0`. and click on ok.

![image-20200626171345361](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626171345361.png)

Voila a nice looking clipped DEM 

![image-20200626171617788](D:\MarkDown_Tutorials_Notes\Remote_Sensing\media\image-20200626171617788.png)

Superimposed geographic boundary to the DEM Data

![image-20200626172155216](D:\MarkDown_Tutorials_Notes\Remote_Sensing\image-20200626172155216.png)

Now perform the DEM analysis

