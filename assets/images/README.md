Place your avatar images in this folder with the filenames below. These are referenced by _includes/avatar.html and the site styles.

Filenames and sizes I recommend:
- avatar-400.webp   (400×400 webp)
- avatar-200.webp   (200×200 webp)
- avatar-400.jpg    (400×400 jpeg fallback)
- avatar-200.jpg    (200×200 jpeg fallback)
- avatar-96.png     (optional 96×96 png for favicon)

Quick export settings:
- WebP: quality 75–80
- JPEG: quality 75

Quick crop for a usable avatar:
- Square crop (1:1)
- Eyes about 30% from top of image
- Include chin and small amount of shoulders

To add the images locally:
1. Export your images to the sizes above.
2. Copy them into assets/images/ in your repo.
3. Commit and push.

How to show the avatar on your site:
- Insert this include where you want the avatar to appear (header, author bio, or post layout):
  {% raw %}{% include avatar.html %}{% endraw %}

If you want, I can prepare the cropped/optimized images from the photo you uploaded and add them to the repo for you — say "Please add images" and I'll generate and commit them.