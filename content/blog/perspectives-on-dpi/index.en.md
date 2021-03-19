---
title: "Perspectives on DPI / PPI"
date: 2021-03-17T00:50:38+01:00
tags: ["dpi", "imaging"]
draft: false
---
#### Monitors / Displays

Often DPI is advertized on products you buy. Such as monitors, phones, printers, scanners and inside software. It's actually not so complicated to understand what it is in general. But it can be a little opaque sometimes especially when you talk printing, and image files. Then it's easy to get a little confused. Actually DPI should be used when talking about prints, and PPI (Pixels Per Inch) should be used for displays. But basically they are the same thing.

In consumer products I feel that when Apple introduced the First iPhone with a Retnia display. A lot of consumers also started being more attentive to the PPI on screens. The first Retnia display was a huge step in display quality, but now it's hard to find a low resolution display. So no need to pay too much attention. It later progressed into NoteBook computers and monitors, nicely branded like 4K or Retnia Display. What ever it's called, it just means for every inch of display you have this many pixels. (One inch is 25,40mm)

So if you display a picture 600 pixels wide and 600 pixels high on a 300 PPI monitor. Your displayed image will be a two inch square (5,08mm x 5,08mm). 

A few examples of display PPI's
- Google Pixel 4A 5G Phone: 413 PPI
- Philips 328P6VU 32" 4K monitor: 139 PPI
- Lenovo P27h-10 27" monitor: 109 PPI
- Macbook Pro 15" 2018: 220 PPI

>So a question, what is the PPI on a 4K TV (4K being `4096px x 2160px`) Where px stands for Pixels? This can not be answered, there are one very important piece of information missing! We need to know how large the dispalayed image is, once we know that it can be calculated, or counted. The bigger the TV the lower the PPI, with the resolution being constant at 4K.

#### Files

A file is a computer resource for recording data. It's what we use to save our image files to disk, so they don't get lost! Files does not care what you store inside them, it can be movies, text, images or music. In our case we store image data. Very often this means jpeg image data. But it could be other formats too.

>So as enthusiasts of pictures and photograpy, we will of course need to make sure we save our files in a very high DPI, right? This does not make sense, a file can not have a DPI! Always remember, the DPI comes down to the display- or print size. You can choose to have your file printed at different DPI's, which if you do not change the resolution of the image will result in different sizes of prints. 

#### Cameras

Your camera has a PPI, this is counted on the sensor. Which is the digital eqvivalent of old fashioned film in the camera. The sensor has a resolution, in the case of a Fujifilm XT-20, this resolution is `6016px x 4016px` and with the sensor being of the size `23,6mm x 15,6mm` it can be calculated how high the PPI is on this particular sensor.

For this calculation we use this formula: `DPI = (Pixels * 25,4mm) / [displayed size in mm]`

Here the numbers are plotted in: `(6016px * 25,4mm) / 23,6mm = 6474 PPI`. Thats a huge PPI, compared to my main monitor which has 139 PPI.

>So what is the DPI of the image files that comes out of this camera ? Files still have no PPI, it needs to be displayed at a specific scale to count that. This does not change because it comes from a sensor with a specific PPI.

#### Prints

You wish to print one of your pictures taken with the XT-20 used as an example here. So your image is in the resolution: `6016px x 4016px`, and you print it in the size `600mm x 400mm` (60cm x 40cm). How high is the DPI ?

We find that the DPI is: `(6016px * 25,4mm) / 600mm = 254 DPI` this sounds reasonable for a prin this sizet.

What about if we print it 10 times larger (6m x 4m)? I'll spare you the formula, we can do this in our heads. Just divide it by ten, which gives us 25 DPI. This means that each dot the printer prints is 1,016 mm wide. Thats a big dot! Try and visualise this in your mind. Normal printers don't have this size dots. Except maybe for large scale banner printers. Where printing at 300DPI makes no sense at all.

>But we wish to print at 60 DPI, what now? Is it even possible? Yes what we need is to "up-scale" / "resample" the image, to a higher resolution. There is a formula for this too which looks like this: `Pixels = (DPI * [displayed size in mm]) / 25,4mm`. For our example this gives us an image size of: `14.173px x 9.448px` with the width to height ratio being 1,5. So for large prints like this, you better have a high resolution image to begin with. Because upscaling uses interpolation (Mathematichal formulas for guessing the missing content between the pixels). These are good, but only to a certain extent.

We can also print a smaller and more photo album friendly size, lets select `120mm x 80mm` (12cm x 8cm), using the same formula as the large scale print we get `6016px * 25,4mm) / 120mm = 1273 DPI` This is a problem, because our printer only prints at 300 DPI. So we ned to down-scale the picture to a lower resolution. Again wuth the same formula: `(300 * 120mm) / 25,4mm = 1417px` we can see that the picture needs downscaling to `1417px x 944px` again with the width to height ration being 1,5. Downscaaling has no quality issues, as the large image has all the information needed for the smaller image.

>Scaling is usually not something you need to fiddle with, it's mostly done transparantly by the printing software.

There are also a limit to how high a DPI the human eye can see. So in all practical terms, an image of 6000 x 4000 is enough, for all normal non special use cases.

#### Hold on, not so quick!!

When I open the image in my Photoshop, and view the image size. It tells me that the image is 72 DPI. Thats quite low!!!

True that actually sounds low, but to be honest it's a confusing number. It's at best just informational, it lets you see which size the image will be at different DPI's Just play a little with the numbers and you can see the sizes change. 

Do not only look at the DPI, also look at the size they write!

We need another formula:

`[displayed size in mm] = (Pixels * 25,4mm) / DPI`

So 6016 pixels wide printed at 72 DPI:

`2.122mm = (6016px * 25,4mm) / 72dpi`

That's a print of 2,1 meters x 1,4meters. Should match what Photoshop writes in the image size dialog.

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