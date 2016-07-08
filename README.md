# jekyll2medium
This project is meant for those looking to migrate a Jekyll- (or Octopress-) based blog to the Medium platform. 

Medium currently [only accepts Wordpress XML](https://help.medium.com/hc/en-us/articles/218572107) ([sample XML](https://wpcom-themes.svn.automattic.com/demo/theme-unit-test-data.xml)) when importing a blog, so this plugin will shove your entire blog into a Wordpress XML, which is suitable for import into Medium. 

## Installation

Just put the `export.xml` file in your root jekyll directory (the same directory where you have your `index.html`). 

### Installation Requirements

- Replace the front matter in `export.xml` with your own details, instead of the Foo Bar stuff
- Make sure your site_root does _not_ have a trailing slash. 
- To ensure images in your posts make the transition, ensure all `src` tags have absolute URLs (eg. `http://foo.bar/img/img1.jpg` instead of `/img/img1.jpg`)
  - Alternatively, if you don't want to change anything in your `_posts` dir, you could modify the `{{ post.content }}` in the `export.xml` to be something like `{{ post.content | replace: '/img/', 'http://foo.bar/img/' }}`.

## Usage

After the file is present, re-build your Jekyll site (`jekyll build`), and you will then have an export.xml file in your site's root (the '_site' folder). Use this file to [import into Medium](https://help.medium.com/hc/en-us/articles/218445047). 
