# Text Recognition & Transcription

## Optical character recognition (OCR)

### OCR API Services
- **Google Vision**
	https://cloud.google.com/vision
	https://cloud.google.com/vision/docs/pdf
- **Online OCR**
	https://www.onlineocr.net/
	http://www.ocrwebservice.com/

### Manual Implementation
- **Text Recognition System with TensorFlow**
	https://github.com/githubharald/SimpleHTR
	https://towardsdatascience.com/build-a-handwritten-text-recognition-system-using-tensorflow-2326a3487cd5

## Image Manipulation

### Auto-detect Lines & Rotate

- **Fourier Transform Processing With ImageMagick**
	http://www.fmwconcepts.com/imagemagick/fourier_transforms/fourier.html
 - **Forum Tutorial**
	 https://legacy.imagemagick.org/discourse-server/viewtopic.php?t=31193


> FFT can be used to determine the rotation from the lines in the image. However, I caution that since your lines are not straight, I doubt you can get accuracy to the third decimal position.
> 
> For a tutorial on FFT processing, see [Fourier Transforms](http://www.fmwconcepts.com/imagemagick/fourier_transforms/fourier.html)
> 
> Here is how it works from your example. I took your image and cropped a 512x512 region near the top center that had good contrast. I saved as png so that the images would display below. The process is just to get the angle, so keeping as tif is not important.
> 
> For reasons I will explain later, I rotated it 90 degrees so that the lines were nearly horizontal.
> 
> Next, I generated the FFT spectrum.

```
convert test_crop.png -fft -delete 1 -evaluate log 100000 test_crop_spectrum.png
```

> The FFT spectrum will show lines that are perpendicular to those in the input image and will be spaced further. But these lines in the FFT spectrum will intersect the coordinate axes and show dots. Those dots can be located and a least square fit performed to get the rotation angle.
> 
> The reason I rotated the image was that I have a script, [textdeskew](http://www.fmwconcepts.com/imagemagick/textdeskew/index.php), that already does this extraction of the rotation angle and correction. It was designed to unrotate images of lines of text that are horizontal bands of white and dark from the text.
> 
> So processing your rotated subsection, I get two images. The unrotated image and the mask showing the dots. And of course the rotation angle used. You can then rotate your original image by this same angle to correct it. However, note, that it is also sensitive to the size of the mask dots and outliers. So again, I am not sure of the accuracy of this process.

```
textdeskew -r 3 test_crop_r90.png test_crop_r90_deskew.png test_crop_r90_deskew_mask.png
```

> Rotated image and mask image

## Resources
http://www.fmwconcepts.com/imagemagick/textdeskew/index.php