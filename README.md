# Stellar Theme for Statiq

A port of the [HTML5 UP "Stellar"](https://html5up.net/stellar) design into a [Statiq Web](https://statiq.dev/web/) blog theme.

This theme was converted from the [Wyam Stellar theme](https://github.com/Wyamio/Wyam/tree/develop/themes/Blog/Stellar) to work with Statiq Web, using [CleanBlog](https://github.com/statiqdev/CleanBlog) as a structural template reference.

## Credits

- **Stellar** design by [HTML5 UP](https://html5up.net) ([@ajlkn](https://twitter.com/ajlkn)) — licensed under [CCA 3.0](https://html5up.net/license)
- Original Wyam port by Richard Burte (AreBee)
- The `.cshtml` template files are covered by the [Unlicense](LICENSE)

## Features

- Responsive Stellar HTML5 UP design
- Blog archive with pagination
- Tag-based filtering and listing
- RSS and Atom feeds
- Search support (via Statiq's built-in search index)
- Sample posts and an about page

## Requirements

- [.NET SDK](https://dotnet.microsoft.com/download) 6.0 or later
- [Statiq Web](https://statiq.dev/web/) `1.0.0-beta.36` or later

## Getting Started

### 1. Create a new Statiq Web project

```bash
dotnet new console
dotnet add package Statiq.Web --version 1.0.0-beta.36
```

Update `Program.cs`:

```csharp
using Statiq.App;
using Statiq.Web;

return await Bootstrapper
    .Factory
    .CreateWeb(args)
    .RunAsync();
```

### 2. Copy theme files

Copy the contents of this repository's `input/` directory and `settings.yml` into your project.

### 3. Configure settings

Edit `settings.yml` to update your site title, description, and other preferences:

```yaml
SiteTitle: My Blog
SiteDescription: A blog about things I find interesting
SiteIntro: Welcome to my little corner of the internet
Copyright: => $"Copyright © {DateTime.Now.Year} My Name"
```

### 4. Build and run

```bash
dotnet run -- preview
```

Your site will be available at `http://localhost:5080`.

## Theme Structure

```
input/
  _layout.cshtml              # Main page layout
  _header.cshtml              # Page/post header
  _navigation.cshtml          # Top navigation bar
  _navbar.cshtml              # Navigation items
  _footer.cshtml              # Footer with feeds
  _copyright.cshtml           # Copyright text
  _head.cshtml                # Extra <head> content (override to customise)
  _scripts.cshtml             # Extra scripts (override to customise)
  _sidebar.cshtml             # Sidebar (override to add content)
  _post.cshtml                # Single post preview card
  _posts.cshtml               # Paginated post list
  _post-after-content.cshtml  # Content shown after each post (tags)
  _post-comments.cshtml       # Comments section (configure in here)
  _common-after-content.cshtml
  _page-after-content.cshtml
  index.cshtml                # Home page
  feed.yml                    # RSS/Atom feed configuration
  search.cshtml               # Search page
  about.md                    # Sample About page
  posts/
    index.cshtml              # Posts archive
    welcome.md                # Sample post
    another-post.md           # Sample post
  tags/
    index.cshtml              # Tags index and tag-filtered post lists
  assets/
    css/
      main.css                # Stellar theme CSS (from HTML5 UP)
      ie8.css                 # IE 8 compatibility
      ie9.css                 # IE 9 compatibility
    js/
      jquery.min.js           # jQuery
      jquery.scrollex.min.js  # Stellar scroll events plugin
      jquery.scrolly.min.js   # Stellar smooth scroll plugin
      skel.min.js             # Skel framework
      util.js                 # Stellar utilities
      main.js                 # Stellar main script
    sass/                     # SASS source files for customisation
  images/
    pic01.jpg                 # Sample images from HTML5 UP Stellar
    ...
settings.yml                  # Site-wide settings
```

## Customising

To override any partial, create a file with the same name in your project's `input/` directory. Statiq will use your version instead of the theme's default.

### Adding to `<head>`

Create or edit `input/_head.cshtml` in your project to add extra styles, meta tags, or other head content.

### Adding scripts

Create or edit `input/_scripts.cshtml` to include extra JavaScript.

### Sidebar

The `_sidebar.cshtml` partial is included in the home page's right column. Edit it to add custom sidebar content such as social links, a bio, or recent comments.

### Footer

The `_footer.cshtml` partial renders the site footer. It includes feed links and the copyright notice. Override it or `_copyright.cshtml` to customise the footer.

## License

The `.cshtml` template code is released under the [Unlicense](LICENSE).  
The Stellar CSS, JavaScript, and image assets are from [HTML5 UP](https://html5up.net) and are licensed under the [Creative Commons Attribution 3.0 Unported License](https://creativecommons.org/licenses/by/3.0/).
