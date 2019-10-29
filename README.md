# Jekyll - Resume

This is a simple resume made with a minimal design approach. The resume uses Jekyll and is hosted on Github Pages. You can checkout the resume [here](https://wahegurupal1912.github.io/resume/).

## Requirements

Before we start with the installation of Jekyll, you will need to confirm that you have these softwares install on your machine

- Ruby version 2.4.0 or above.
    - You can check your ruby version by running `ruby -v`
- RubyGems
    - Check the version by running `gem -v`
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
2. Create a new project using Jekyll
    ```bash
    jekyll new resume
    ```
3. Go into the new directory created by Jekyll
    ```bash
    cd resume
    ```
4. Now build the project and launch it on your localhost
    ```bash
    bundle exec jekyll serve
    ```
5. You can checkout a basic blog site created by Jekyll at http://localhost:4000
