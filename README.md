# How to run bootstrap-4.1.1 documentation locally
This is a guide on how you can run and access the bootstrap document on your local machine. No more need to always access online website for lookups.
 
First you need to download and extract bootrap-4.1.1 on any directory on your pc. You can download bootstrap v4.1.1 from this [link](https://github.com/twbs/bootstrap/archive/v4.1.1.zip) or find download link on the bootstrap [website](https://http://getbootstrap.com/). 

From you terminal window, ``cd`` to the root directory of the bootstrap you just extracted and follow the bellow steps.

## 1. Install jekyll
Jekyll is a simple, blog-aware, static site generator.

You create your content as text files ([Markdown](https://daringfireball.net/projects/markdown/)), and organize them into folders. Then, you build the shell of your site using [Liquid](https://shopify.github.io/liquid/)-enhanced HTML templates. Jekyll automatically stitches the content and templates together, generating a website made entirely of static assets, suitable for uploading to any server.

To install jekyll on linux, run the following commands
```
$ sudo apt-get update
```
```
$ sudo apt-get install ruby-full
```
```
$ gem install jekyll
```

Test if jekyll is working
```jekyll -v
```
## 2. Install Gem Bundler
Gem Bundler helps you track and install the gems you need for Ruby projects.
Intall this by doing:

```
$ gem install bundler
```
## 3. Run jekyll
Next you have to run jekyll to bundle the project and run a local server so you can access the project from browser. To do this just run:
```
$ jekyll serve
```
On first run of the above command I got an error saying something like: 
```
... gems/2.3.0/gems/bundler-1.16.2/lib/bundler/runtime.rb:313:in `check_for_activated_spec!': You have already activated kramdown 1.17.0, but your Gemfile requires kramdown 1.16.2. Prepending `bundle exec` to your command may solve this. (Gem::LoadError) ...
```
To solve this, just edit **Gemfile.lock** file at the root of the bootstrap project. Find the line that says ``kramdown (1.16.1)`` and change version to fit that mentioned in the error message above. So that line will finally say ``kramdown (1.17.0)``.

Now you can re-run ``$ jekyll serve``.
You should have some output that looks like this
```
WARN: Unresolved specs during Gem::Specification.reset:
      ffi (< 2, >= 0.5.0)
WARN: Clearing out unresolved specs.
Please report a bug if this causes problems.
Configuration file: /my/bootstrap/path/bootstrap-4.1.1/_config.yml
            Source: .
       Destination: ./_gh_pages
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 5.793 seconds.
 Auto-regeneration: enabled for '.'
    Server address: http://0.0.0.0:9001/
  Server running... press ctrl-c to stop.
  ```
Just open your favorite browser and type the address **localhost:9001**.
That's it... You are done.





