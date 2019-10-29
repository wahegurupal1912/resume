# How to create a static resume and host it on Github Pages

This is a simple resume made with a minimal design approach. The resume uses Jekyll and is hosted on Github Pages. You can checkout the resume [here](https://wahegurupal1912.github.io/resume/).

In case you are not familiar with Jekyll, it is a very popular static site generator. It allows you to write your content in Markdown and then combines that content with a template and provides you with a set of static web pages. These web pages can be easily hosted on a web server. Additionally, jekyll is the engine behind Github pages and it allows us to host web pages right from our repository for free.

## Requirements

Before we start with the installation of Jekyll, you will need to confirm that you have these softwares install on your machine

- Ruby version 2.4.0 or above.
  - You can check your ruby version by running `ruby -v`
  - Jekyll is a Ruby package so we need ruby on our computer to work with Jekyll.
- RubyGems
  - Check the version by running `gem -v`
  - RubyGems is basically a packet manager for ruby.
  - It allows us to install or update ruby packages (Jekyll in our case).
- GCC
  - You can check if gcc is available by running `gcc -v`, `g++ -v`
- Make `make -v`
  - Check make by running `make -v`

If you are missing any of these you can follow the steps available [here](https://jekyllrb.com/docs/installation/).

## Installation

There are various approaches for using Jekyll. We will set up Jekyll locally which will allow us to develop and preview the changes locally on your machine and then publish the final version on your Github account.

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
5. You can checkout a default blog site created by Jekyll at http://localhost:4000

## Instructions

#### Get the theme files

We want to change the styling on the current default website created by minima to add our own taste to it. Jekyll does not provide us with the files that are used by the theme. By default Jekyll uses the _minima_ theme. To get the files used by minima, run the following command in a terminal window

```bash
open $(bundle show minima)
```

This will open a File Explorer window with all the files used by minima to style our webpage. You can copy and paste the all the files from that window to your project.

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

As described above, Jekyll provides you with some default files when you create a new project. These files are used to create a very basic blog site to get you started. Since we are make a single page resume instead of a blog, there are some extra files that we can get rid of.

We can delete `_posts`, `404.html`, `about.markdown`. You can also delete `post.html` and `page.html` from the `_layouts` folder.

Finally, the directory should look something like this

```
resume/
├── _config.yml
├── _includes
├── _layouts
├── _sass
├── _site
├── assets
├── Gemfile
├── Gemfile.lock
├── index.markdown
├── LICENSE.txt
└── README.md
```

#### \_config.yml

This file contains all the configurations for your web page. The values in this file are accesible from everywhere in the project by using `site.variableName`.
I will recommend you to change the `title` to Resume and changing the `email`, `twitter_username` and `github_username` to your own information. We will leave `baseurl` and `url` as empty string for now. Finally, we will add two new value, name and occupation. Add these two variable right below the title.

```yml
name: YourName
occupation: YourOccupation
```
