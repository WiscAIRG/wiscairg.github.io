Notes
=====


Notes on maintaining this website which operates by using the static
site generator Jekyll on GitHub Pages.


References
----------

* GitHub pages basics:
  https://help.github.com/categories/github-pages-basics
* GitHub pages advanced:
  https://help.github.com/categories/customizing-github-pages
* Jekyll: https://jekyllrb.com/


Website Update Process
----------------------

* Create a branch for your updates
* Make your edits
  * Edit content in Markdown format.  If you want it to appear as a page
    on the site add "YAML front matter" enclosed in "---".  Otherwise it
    will just be copied as is.
  * Site mechanics are in `_config.yml`, `_layouts`, `_includes`, and
    `css`
* To update the archive, edit `archive.yaml` and then run

      python3 archive.py archive.yaml > archive.md

  Then commit both `archive.yaml` and `archive.md`.
* Optionally preview your work with Jekyll locally at
  http://127.0.0.1:4000/ (see https://jekyllrb.com/docs/usage/)
  * Installing Jekyll on Fedora:
    https://developer.fedoraproject.org/start/sw/web-app/jekyll.html

        sudo dnf install ruby-devel
        sudo dnf install libffi-devel # I also needed libffi
        gem install jekyll bundler # https://jekyllrb.com/docs/quickstart/
        bundle exec jekyll serve & # Run in background but not detached

  * Use `bundle update` to update gems to the latest versions allowed by
    your `Gemfile`
    * (When not bundling, use `gem outdated` to see what gems can be
      updated and `gem update` to update them.)
  * Use `bundle install` to bring things up to date with `Gemfile`.  See
    the following for more information about Gemfiles.
    * http://bundler.io/man/gemfile.5.html
    * http://bundler.io/bundler_workflow.html
    * http://yehudakatz.com/2010/12/16/clarifying-the-roles-of-the-gemspec-and-gemfile/
* Merge the branch into `master` and delete the branch
* Push `master`


Style
-----

* Use the Python convention of wrapping lines at 72 characters (Emacs
  does this well with variable `fill-column`)
* Headers with `=` and `-` "underline" style
* Two blank lines before a header, one blank line after
* Two spaces between sentences
* Copyright for file formats with comments (code, data) goes at the top
  after a brief description
* Copyright for Markdown and other (non-web) content goes at the bottom
* Omit copyright notices from web content as it will appear as part of
  the page footer (but make sure to update `copyright_year` in the YAML
  front matter)
* Use the existing style in the file if unsure
* List all relevant copyright years:

      git blame <file> | sed -e 's/^.\+\?([^[:digit:]]\+[[:space:]]\+\([[:digit:]]\{4\}\)-.*$/\1/' | sort -u


-----

Copyright (c) 2017-2018, 2020 [AIRG Authors](AUTHORS.md)
[(CC-BY)](https://creativecommons.org/licenses/by/4.0/).  This is a free
culture work licensed to the public under a [Creative Commons
Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
