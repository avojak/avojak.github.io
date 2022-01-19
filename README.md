# avojak.com

Forked and modified from [elementary/blog-template](https://github.com/elementary/blog-template).

## Editing workflow

Use the GitHub workflow!

1. **Use PRs to propose** and work. That means draft PRs for things that aren't ready to publish, too.
2. **All PRs should be reviewed** and approved before publishing.
3. **Use reviews and inline comments**/suggestions to collaboratively edit.

### Handling Images

Ideally, images are put into the `images/` directory with a folder name matching the post slug. Since the normal maximum width of articles is 800 pixels, image sizes should be as follows:

- Up to 800px wide for normal width loDPI
- Up to 1600px for normal-width HiDPI
- Up to 800px for half- or third-width images on loDPI
- Up to 1600px for half- or third-width images on HiDPI
- 2560px wide for full-bleed (higher than this, even for HiDPI, gets really heavy)

When scaling down, use a high quality interpolator like Sinc (Lanczos3) or NoHalo in GIMP to avoid too much blur/fuzziness.

Name your sized images something sane like `image-name_800.jpg` for the loDPI version, and `image-name_1600.jpg` for the HiDPI version. When writing the markdown, use this format:

```markdown
![Alt Text]({{ site.baseurl }}/images/post-name/image-name_800.jpg){: srcset="{{ site.baseurl }}/images/post-name/image-name_1600.jpg 2x"}
```

This is a bit verbose, but ensures:

- Images stay valid even if we ever move the blog
- We only load the largest version necessary on loDPI or HiDPI
- Both loDPI and HiDPI images are loaded at the correct physical size

Optimize images with the lowest JPG percent that looks good (i.e. manually in GIMP), and use something like [Image Optimizer](https://appcenter.elementary.io/com.github.gijsgoudzwaard.image-optimizer) for PNGs.

Also consider JPGs instead of PNGs when the majority of the image is photographic or a gradient (i.e. not solid colors), as that will compress way better than a PNG.

## Building & Running Locally

The blog is a simple Jekyll-powered site hosted by GitHub Pages. To run it locally, see [the GitHub docs](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/).

### Dependencies

This guide assumes you're on elementary OS or a similar Ubuntu-based environment.

#### Packages

- `ruby-full` (should include `ruby` and `ruby-dev`)
- `build-essential`
- `zlib1g-dev`

#### Ruby Stuff

- `jekyll` and `bundler`

We recommend installing gems to a (hidden) directory in your home folder:

```shell
echo '' >> ~/.bashrc
echo '# Install Ruby Gems to ~/.gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/.gems"' >> ~/.bashrc
echo 'export PATH="$HOME/.gems/bin:$PATH"' >> ~/.bashrc
echo '' >> ~/.bashrc
source ~/.bashrc
```

Install jekyll and bundler:

```shell
gem install jekyll bundler
```

Install gems:

```shell
bundle install
```

(Adapted from https://jekyllrb.com/docs/installation/)

### Serve

```shell
bundle exec jekyll serve --host 0.0.0.0
```

The site should now be available at http://0.0.0.0:4000/ on your local machine, and your local machine's IP address on your network—great for testing on mobile OSes.

#### Drafts & Future Posts

Append `--drafts` to the serve command, and drafts in the `_drafts` folder will show up based on their last-edited time. Similarly, append `--future` to the serve command to show future posts.
