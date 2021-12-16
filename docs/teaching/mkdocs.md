# MkDocs

Perhaps unsurprisingly, a package built around making documentation has excellent documentation. A [user guide for MkDocs](https://www.mkdocs.org/user-guide/) has some introductory material for making content, but the [Material of MkDocs documentation](https://squidfunk.github.io/mkdocs-material/) is the best reference, with more detail and examples of the features unique to the theme.

## Configuration

The `mkdocs.yaml` file is where the magic happens. The `.yaml` format (commonly `.yml`) is a human readable language commonly used for configuration files, and stands for "YAML Ain't Markup Language". Basically, one loads in the desired libraries and extensions for the site, in addition to specifying the site structure by pointing to markdown files which actually contain the content for each page. Best practice would dictate that one only load the content strictly necessary to make the site run, but I have adopted a master `.yaml` approach, which can be accessed [here](lol).

## Elements

### Tables

``` markdown
| Method      | Description                          |
| :---------: | :----------------------------------: |
| Line 1      | :material-check:     This  |
| Line 2      | :material-check-all: is a  |
| Line 3      | :material-close:     test  |
```

### Tabs

### Code

Information on code blocks can be found in the [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/)

``` yaml
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
```

#### Annotations

!!! Warning ".yaml configuration"
    Annotation to code requires the `content.code.annotate` feature to be enabled in the theme configuration of `mkdocs.yaml`:

    ``` yaml
    theme:
      features:
        - content.code.annotate
    ```


## Images

!!! info "Material for MkDocs documentation"
    Information on inserting images can be found in the [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/reference/images/)

Placing images in markdown (well, HTML) is not a simple as it should be. In the simples form, one uses markdown of the form:

``` markdown
![image name](link to image)
```

for example, the code `![malamute](malamute.jpg)` places the image `malamute.jpg`:

![malamute](malamute.jpg){width="300"}

It is unlikely that one will place images without some configuration; the image above is left justified and rather small. Below, methods for simple image manipulation are outlined.

!!! Warning ".yaml configuration"
    Most image manipulation is performed using the [attribute lists extension](https://python-markdown.github.io/    extensions/attr_list/) which should be enabled in the `mkdocs.yaml`:

    ``` yaml
    markdown_extensions:
      - attr_list
    ```

### Sizing

Sizing is most easily achieved (with consistent outcomes) using the `width` attribute. Using this, one can specify the width of the image (in pixels) or as a percentage of the page width. No width designation will place the image at full size or the page width, whichever is smaller. To alter the `width` attribute, one should use place the width parameter inside curly brackets `{}`, for example:

``` markdown
![Image title](image location){width=<width>}
```

Shown below are the same image placed with a range of width parameters:

=== "width = 300"
    ![malamute](malamute.jpg){width="300"}

    The markdown used to produce the above image is `![malamute](malamute.jpg){width="300"}`

=== "width = 50%"
    ![malamute](malamute.jpg){width=50%}

    The markdown used to produce the above image is `![malamute](malamute.jpg){width=50%}`

=== "width unspecified"
    ![malamute](malamute.jpg)

    The markdown used to produce the above image is `![Image title](malamute.jpg)`

### Alignment

If you have spent any time with HTML, you will appreciate that alignment is non-trivial. So whilst the `align` attribute is now depreciated, it is still supported by all browsers, and that is unlikely to change. It also provides a relatively easy way to perform alignment. As with the `width` attribute, one should place the alignment flag inside curly brackets `{}`, for example:

``` markdown
![Image title](image location){align=<alignment flag>}
```

Shown below are the same image placed with different alignment flags:

=== "Left"
    ![malamute](malamute.jpg){width="400" align=left }

    Text written below the markdown to place the image will be wrapped on the right of the image.

    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

=== "Right"
    ![malamute](malamute.jpg){width="400" align=right }

    Text written below the markdown to place the image will be wrapped on the left of the image.

    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


#### Centring

Most likely, one will want to centre images, which can be achieved not with an alignment flag, but rather a workaround of the form `{: .center}`. For example, the markdown `![malamute](malamute.jpg){width="600" : .center}` gives the placement:

![malamute](malamute.jpg){width="600" : .center}

### Captions

In order to have a caption for an image, it is necessary to use HTML directly:

``` HTML
<figure markdown>
  ![Image title](image location)
  <figcaption>Image caption</figcaption>
</figure>
```

Object attributes can be specified, but unlike image placement with markdown, the image will be placed centrally by default. For example, the HTML

``` HTML
<figure markdown>
  ![malamute](malamute.jpg){ width="300" }
  <figcaption>This is both a malamute and a good boi</figcaption>
</figure>
```

yields

<figure markdown>
  ![malamute](malamute.jpg){ width="300" }
  <figcaption>This is both a malamute and a good boi</figcaption>
</figure>


--8<-- "includes/abbreviations.md"
