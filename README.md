# Capital City MTB site

This site uses Hugo with the Blowfish theme.

## Photos in page text

Put photos under `assets/` and insert a figure immediately before the text that
should wrap around it. For example, a photo at `assets/people/example.jpg` can
be floated to the right:

```markdown
{{< figure src="people/example.jpg" alt="Describe the photo" figureClass="bio-photo" >}}

Your paragraph goes here.
```

For a left float, use `figureClass="bio-photo bio-photo-left"` instead. Photos
are displayed above the text on small screens; on wider screens, text may wrap
around them across multiple paragraphs.

## Publishing

In the GitHub repository, open **Settings > Pages** and select **GitHub Actions**
as the build and deployment source.

The [deployment workflow](.github/workflows/hugo.yml) builds and publishes the
site to GitHub Pages on every push to `main`. To publish manually, open
**Actions > Deploy Hugo site to GitHub Pages > Run workflow** and select `main`.

The workflow checks out the theme submodule, builds with Hugo Extended, and uses
the GitHub Pages URL as the production base URL (including any repository path).
No deployment secrets are required; the workflow uses `GITHUB_TOKEN`.
