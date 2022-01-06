# Summary

Key points before we compare:
- We should compare the images with same dimensions, a larger image always looks better than the smaller one.

Actions can certainly imporve quality:
- Pillow 9.0.0 has better quality(we use 9.0.0 in our demo) with the same params, we are using 7.0.0 on production.
- For jpeg images, make quality = 95 (which is the highest number for common use) can imporve a bit than 75(we are using now) in theory,
  but it's hard to tell by human eyes. you can check it in compare-jpg.html.
- Still have a color change on webp form, even we save it directly without resize, and make all params highest:
```
>>> from PIL import Image as PilImage
>>> image = PilImage.open("pillow_images/source_posters/4afd31cc-3d0b-4535-a6ed-26e7a567a73e.jpg")
>>> image.save("pillow_images/source_posters/4afd31cc-3d0b-4535-a6ed-26e7a567a73e.webp", "WEBP", lossless=True, icc_profile=icc_profile, method=6, quality=100)
```
Xugang use cwebp to do the same thing(jpg->webp with resize) manually, also see the color change:
![](image.png)

- Check canvas jpg with original image in original size:
result/compare-canvas.html

- Check canvas jpg with different quality - compare with Mac Preview:
result/compare-jpg.html

- Check canvas jpg with webp:
result/compare-webp.html