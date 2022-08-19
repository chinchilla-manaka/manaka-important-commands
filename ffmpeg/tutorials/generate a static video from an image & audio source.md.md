[..](../README.md)
# generate a static video from an image & audio source
This command is pretty useful if you are a music producer and are planning to make a bunch of music videos for YouTube streaming. What this does is that takes an image and an audio file as source and generates a video compatible with Facebook and YouTube. 

The resulting video output  is lightweight and mantains the original image's source quality, however, it converts the audio file given to mp3 for a lighter total file weight.

``ffmpeg -i "<audio file>" -loop 1 -r 1 -i "<image file>" -vcodec libx264 -preset ultrafast -crf 20 -threads 0 -acodec mp3 -shortest -r 2 <output>``

### further explanation

You will have to **replace** ``<audio file>`` with the corresponding **audio file** or **directory followed by the file**. Given the wide variety of file support ffmpeg has, you can almost certainly be sure that whatever file you give it, will work flawlessly once converted to mp3 with the ``-acodec mp3`` flag. 

Then **replace** the ``<image file>`` with **whatever image** you give it. I personally recommend to **use a high resolution ``bmp`` or ``png`` file** as that's exactly the one the output will give. Remember to **use an image with a common *aspect ratio*;** this is, because for some reason in the past, I've gotten some errors using custom resolutions. **You can use the given GIMP resolution templates if you are unsure whether it's good or not. Multiplying the resolutions will work just fine**.