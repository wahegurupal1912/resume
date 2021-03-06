# How to host a Resume using Github Pages and Jekyll

This is a simple resume made with a minimal design approach. The resume uses Jekyll and is hosted on Github Pages. You can checkout the resume [here](https://wahegurupal1912.github.io/resume/).

In case you are not familiar with Jekyll, it is a very popular static site generator. It allows you to write your content in Markdown and then combines that content with a template and provides you with a set of static web pages. These web pages can then be easily hosted on a web server.

## Who is this intended for?

This README will cover the steps to setup Jekyll and how to work with it to host your static resume on Github. You are expected to know how to work with markdown and Atom. We will go through the process of hosting the resume on Github Pages. But you should be familiar with the basics of GitHub.

## Requirements

Before we start with the installation of Jekyll, you will need to confirm that you have these softwares installed on your machine

If you are missing any of these, you can follow the steps available [here](https://jekyllrb.com/docs/installation/) to install them.

- Ruby version 2.4.0 or above.
  - You can check your ruby version by running `ruby -v`
  - Jekyll is a Ruby package so we need ruby on our computer to work with Jekyll.
- RubyGems
  - Check the version by running `gem -v`
  - RubyGems is basically a packet manager for ruby.
  - It allows us to install or update ruby packages (Jekyll in our case).
- GCC and Make
  - You can check if gcc and make are available by running `gcc -v`, `g++ -v` and `make -v`

## Installation

There are various approaches for using Jekyll. We will set up Jekyll locally which will allow us to develop and preview the changes locally on our machine and then publish the final version on our Github account.

1. Install Jekyll and Bundler using gem
   ```bash
   gem install jekyll bundler
   ```
   - You can confirm if Jekyll was installed by running `jekyll -v`.
2. Create a new project using Jekyll
   ```bash
   jekyll new resume
   ```
   - This will create a new directory called resume.
   - Jekyll creates some default files inside this directory.
3. Go into the new directory created by Jekyll
   ```bash
   cd resume
   ```
4. Now build the project and launch it on your localhost
   ```bash
   bundle exec jekyll serve
   ```
   ![bundle exec jekyll serve](https://media.giphy.com/media/hv51W7DZDOL2O4R8IL/giphy.gif)
5. You can checkout a default blog site created by Jekyll at http://localhost:4000

## Jekyll Terminologies

Here are some important things that you should know before getting started with Jekyll

1. **\_includes** - This folder contains html snippets that can be included in any other html file. `{%- include header.html -%}` will act as a placeholder and will add all the html from header.html(which is under \_includes) in it's place.

2. **\_layouts** - This folder contains html layouts with some designated place for some user content. You can mention the layout in the front-matter(discussed below) and all your content will be placed in the layout that you specified.

3. **\_sass** - This folder has all the sass files used for styling different html tags.

4. **\_site** - The files inside this folder are automatically generated by jekyll. This is where all the files for the static web pages generated by jekyll ends up.

5. **front-matter** - Front-matter is the section on top of some files enclosed by `---`.This is where you can specify page specific values in yml. For example, the top part in `index.markdown` is the front-matter for that file. The `layout: home` refers to using the home.html layout for this page.

6. **content** - The text after the front-matter is reffered as `content` in the layout file. All you markdown content is converted into html and placed at the `{{content}}` position in the layout file.

## Instructions

#### Get the theme files

We want to change the styling on the current default website created by jekyll to add our own taste to it. Jekyll does not provide us with the files that are used by the theme. Jekyll uses the _minima_ theme by default. To get the files used by minima, run the following command in a terminal window

```bash
open $(bundle show minima)
```

This will open a File Explorer window with all the files used by minima to style our webpage. You can copy and paste all the files from that window to your project.

#### Remove unwanted files

Currently your project directory should have these files.

```
resume/
├── _config.yml
├── _includes
├── _layouts
├── _posts
├── _sass
├── _site
├── 404.html
├── about.markdown
├── assets
├── Gemfile
├── Gemfile.lock
├── index.markdown
├── LICENSE.txt
└── README.md
```

As described above, Jekyll provides you with some default files when you create a new project. These files are provided to launch a very basic blog site to get you started. Since we are make a single page resume instead of a blog, there are some extra files and folders that we can delete.

We can delete `_posts`, `404.html`, `about.markdown`. We can also delete `post.html` and `page.html` from the `_layouts` folder.

#### Changes in \_config.yml

This file contains all the configurations for our web page. The values in this file are accesible from everywhere in the project by using `site.variableName`.
I will recommend changing the information in this file to your own information. Leave `baseurl` and `url` as empty string for now. You can also add more values if you want. I added a couple more for my name and occupation.

Changes in this file will require you to restart the server. You only need to restart the server if the changes are made in \_config.yml file. For all the changes in any other file, you can just refresh the browser window.

#### Start writing your markdown Resume

All your markdown for your Resume should go in `index.html`. You can leave the header for your resume for this part and add that later in the `_includes/header.html` file. All this markdown is eventually converted into html, so you can add some scss to style your markdown accordingly. If you wish to do so, your scss will go in `_sass/minima/_layout.scss`.

You can see your changes on your localhost after refreshing the web page.

#### Creating the Header and the Footer

There is a `header.html` file inside `_includes`. All the html in this file is responsible for creating the header on top of your resume. You can change the html code in here to however you want to design your header. You can also add scss in `_sass/minima/_layout.scss` to stylize the header. The same steps apply for the footer as well. The html for the footer will go under `_includes/footer.html`. I opted to remove the footer for my resume. To remove the footer, you can simply remove the include statement for the footer.html from `_layouts/default.html`.

#### Hosting on Github Pages

Create a new repository on github. In your `_config.yml` file, add your repository name to the value of baseurl.

```yml
baseurl: "/repositoryName" #add your repository name here
```

Push all your files to your repository. Now go to your repository settings and scroll down to Github Pages. Pick your master branch as the source.

![Scroll to Github Pages](https://media.giphy.com/media/YmnOZY8qcabX6UeVri/giphy.gif)

You should see a message saying "Your site is being published". Wait for a few minutes and refresh the page. Scroll down to the Github pages section again. It should now say "Your site is published at **\_\_\_\_**". You can browse to that link to checkout your site in action.

## Useful Resources

Here are some additional links if you want more information about the topics.  
**Jekyll** - https://www.mikedane.com/static-site-generators/jekyll/  
**Markdown** - https://www.markdownguide.org/cheat-sheet/  
**Github Pages** - https://help.github.com/en/github/working-with-github-pages/getting-started-with-github-pages

## FAQs

Q1. Are there any pre made jekyll templates available to use?

> Yes, there are a lot of theme templates available online that can be used with jekyll. You can find some [here](http://jekyllthemes.org/).

Q2. Why do I need to have Ruby installed to work with jekyll?

> Jekyll is a library written in Ruby. So we need ruby installed on our machine to work with jekyll.
