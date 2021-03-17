---
title: "Perspectives on Dpi"
date: 2021-03-17T00:50:38+01:00
tags: ["dpi", "imaging"]
draft: false
---
## DPI strange and confusing

So what is DPI? 
- It stands for dots per inch.
- One inch is 25,40mm
- So 300 DPI means that for each 25,40 millimeters, there are 300 dots / pixels.

So you wish to have high quality pictures from a technical perspective? You need high DPI right?

Well not quite, it's actually not that simple. A picture file, lets say a .jpg file without changeing the file one bit, can be concidered to have multiple DPI's. It all comes down to the display size vs. the number of pixels of the image.

So for a deeper understanding of DPI, lets follow the complete flow of the pixels:

1. Your camera captures an image, lets say it's `6016px x 4016px` where px stands for pixels. (With an image sensor of the size: `23,6mm x 15,6mm`)
2. You save this image file to your disk on your computer.

How many DPI is the file ?
: It's a trick question, It's got no DPI at all!

Why?
: It's **not** being displayed, **so it can't be measured**.

So, I promished a deeper understanding! Here comes the first part, to calculate DPI you can use the following formula:

`DPI = (Pixels * 25,4mm) / [displayed size in mm]`

#### Camera sensor DPI

This means that the **on the camera sensor** the image you captured above has: 

`6474 DPI = (6016px * 25,4mm) / 23,6mm`

#### Lets give a practical example:
- You print the image in the size 600mm x 400mm (60cm x 40cm) (Without doing any editing or modification to the file at all)

How many DPI is the print?

It can be calculated with the already provided formula like this: `254 DPI = (6016px * 25,4mm) / 600mm`

#### Another example:
- You now print the image in the size 6000mm x 4000mm (6m x 4m) (Still without modifying the file at all!!!)

How many DPI is the print ?

Again, using the same formula: `25 DPI = (6016px * 25,4mm) / 6000mm`

Lets have a closer look, 25 DPI. This means that each dot the printer prints is 1,016 mm wide. Thats a big dot! Try and visualise this in your mind. Normal printers don't have this size dots. Except maybe for large scale banner printers. Where printing at 300DPI makes no sense at all.

So what do we do, we need to "up-scale" / "resample" the image, to a higher resolution.

Let's just for the example say that the large scale banner printer prints in 60 DPI.

We can use this formula to calculate the pixel width of the image:

`Pixels = DPI * ([displayed size in mm]) / 25,4mm`

This translates to: `14.173px = (60dpi * 6016px) / 25,4mm`

So before printing up-scale the picture to: `14.173px x 9.448px`

So for large prints, you better have a very high resolution to begin with. because up-scaling uses interpolation (Mathematical formulas for guessing the missing content between the existing pixels) these algorithms are good, but only to a certain extent. 

#### A more realistic example:
- The aforementioned unmodified file will now be printed in 120mm x 80mm (12cm * 8cm). Sounds reasonable.

How many DPI is the print ?

Once again, lets calculate with the same formula: `1273 DPI = (6016px * 25,4mm) / 120mm`

Oh no! Not again, the image is in the wrong resolution. This time its not too low, it's actually too high!

The reason being that the photo printer only prints in 300 DPI. So to which size should the image be "down-scaled" / "resampled"?

We use the second formula introduced again: `1417px = (300 * 120mm) / 25,4mm` this means for the picture to be printed, it needs to be down-scaled to `1417px * 944px`

Downscaling causes no problems for the quality of the print, as the source images actually has more information than the printer can use.

There are also a limit to how high a DPI the human eye can see. So in all practical terms, an image of 6000 x 4000 is enough, for all normal non special use cases.

#### Hold on, not so quick!!

When I open the image in my Photoshop, and view the image size. It tells me that the image is 72 DPI. Thats quite low!!!

True that actually sounds low, for a high quality print!

**But** do not only look at the DPI, also look at the size they write!

We need another formula:

`[displayed size in mm] = (Pixels * 25,4mm) / DPI`

So 6016 pixels wide printed at 72 DPI:

`2.122mm = (6016px * 25,4mm) / 72dpi`

That's a print of 2,1 meters x 1,4meters.

I hope you see that DPI is a moving target, you need more information than just this number.

#### Back to the image sensor on the camera.

I've heard someone say to me, that the image sensor in the camara is 240 DPI. 

Picture this in your head:
- At 240dpi each pixel has a size of: `25,4mm / 240dpi = 0,1058mm`
- This means that for each millimeter you have: `1 / 0,1058 mm = 9,4518px`
- Your image sensor is 6016 pixels wide.
- This means that the image sensor needs to be `6016 * 0,1058mm = 636,49mm` wide
- That's `63,5` centimeters wide. I doubt that even the sensor on the Hubble telescope in space has this big a sensor!!

From the description first in this article it was mentioned that the image sensor size is `23,6mm wide`, so what would the resolution on the width axis of the sensor be at 240 DPI?

We use the formula: `(240dpi * 23,6mm) / 25,4mm = 222 pixels` wide

The width to height ratio on the sensor is `3 / 2 = 1,5`. So the height would be `222px / 1,5 = 148px.`

A camera like this would have a maximum resolution of: `222px x 148px` I think you might find an old web camera from the late nineties with this sort of resolution.

Question: Can this small image be printed at 600 dpi ?

If you say no, then I'd like to know why?

But of course you can print it at 600dpi, or even 1200 dpi. Lets test it out, with the provided formulas.

At 600dpi the width of the printed image would be: `(222px * 25,4mm) / 600dpi = 9,398mm` wide. So the printed picture would be `9,398mm x 6,265mm`