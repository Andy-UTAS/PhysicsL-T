# Web-based material

There are a countless philosophies around the production and distribution of materials to students. I subscribe to a model whereby people are facilitated to engage with content during lectures, which hinges on having easily accessed, high-quality resources available to all students. My goal in to have in essence an interactive textbook, which is open source, and students are both encouraged and required to perform calculations and computations within the notes. The burden of production is high, but the end result is appreciated by students, and is more generally a useful resource to others at the university and further afield.

## Where to start?

There are many options for hosting web content. My journey for making web content started with using commercial CMS systems including [Squarespace](https://www.squarespace.com/) for a [personal site](https://peak-exposure.com/), [Joomla](https://www.joomla.org/), and [WordPress](https://wordpress.com/), but these are not really ideal for educational content. I did build a site from the ground up in HTML ([POLUS](http://physlabpi.phys.utas.edu.au/), the undergraduate lab website), but this was not efficient, robust or configurable. I did consider a [wiki format](http://physlabpi.phys.utas.edu.au/dokuwiki/), which definitely could be adapted for an educational setting, but the best solution that I came across when researching this was [MkDocs](https://www.mkdocs.org/), a static site generator which is designed around producing technical documentation, and maps very naturally to educational content. Without shilling too much for MkDocs, it produces aesthetically pleasing sites, which are highly configurable and critically can have maths and computational content embedded in myriad ways. Moreover, given it a documentation suite, unsurprisingly, the documentation is top notch!

!!! warning "MkDocs or bust"

    Despite the title of this section being "Web-based material", it would probably read better as "MkDocs for web-based material", with all content here on out only discussing MkDocs.

## How does one set up a website?

Depending on one's web development experience, the concept of creating, hosting, deploying and maintaining a website might be daunting, but the point of this page it to demonstrate that it is not difficult, indeed, if one has a rudimentary command over either `Latex` and/or `markdown`, one is 95% of the way there.

### Specifics and peculiarities

#### MkDocs à la Andy

To paint an overview of how
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

#### Hosting: a tale of all things UTAS

### Git

``` git
git init
```

``` git
git add .
```

``` git
git commit -m "<comment>"
```

``` git
git remote add origin <remote repository URL>
```

??? info "Changing the remote repository"

    ``` git
    git remote set-url origin <URL>
    ```

``` git
git remote -v
```

``` git
git push origin master
```

!!! Error "git push error: src refspec main does not match"

    One of the most commonly encountered errors when working with GitHub, and a full explanation of the origins of the error, along with how to fix it, is given [here](https://stackoverflow.com/questions/65173291/git-push-error-src-refspec-main-does-not-match-any-on-linux).

### GitHub

[GitHub Pages](https://pages.github.com/)

https://www.mkdocs.org/user-guide/deploying-your-docs/

``` python
mkdocs gh-deploy
```



--8<-- "includes/abbreviations.md"
