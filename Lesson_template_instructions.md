# Elixir Training Lesson template

[![DOI](https://zenodo.org/badge/564252010.svg)](https://zenodo.org/badge/latestdoi/564252010)


For instruction on how to use the template, please follow this documentation: 
https://elixir-europe-training.github.io/ELIXIR-TrP-LessonTemplateInstructions-MkDocs/


**Any issues?** Contact Geert van Geest (@GeertvanGeest) 



## If working locally

This website is generated with [MkDocs](https://www.mkdocs.org/), with the theme [Material](https://squidfunk.github.io/mkdocs-material/).

To host it locally, install MkDocs:
```bash
pip install mkdocs
```

and Material with some plugins:
```bash
pip install mkdocs-material
pip install mkdocs-video
pip install mkdocs-bibtex 
pip install neoteroi-mkdocs
```

Clone this repository to your local computer. Then, make the repository your current directory and type:

```bash
mkdocs serve
```

To host it locally.

Check it out with your browser at [http://localhost:8000/](http://localhost:8000/).


## Additional instructions for the FAIR course

This course uses mike to host several versions of the course. Default is the latest version, that builds from the `main` branch. Once a course is done, and a new release has been created, a new version should be created manually with mike, to keep latest free for the next course instance.

To create a new version from the release, first install mike if you don't have it yet:
```bash
pip install mike
```

Make sure you are in the the release version you want to create. 

```bash
mike deploy <YYYY-MM> --push
```

This will create a new versioned folder in the `gh-pages` branch. The `--push` option will push the changes to the remote repository.

If the content is not pushed, checkout the gh-pages branch and run `git push`

## Citation

Please cite as

> Geert van Geest, Elin Kronander, Jose Alejandro Romero Herrera, Nadja Žlender, & Alexia Cardona. (2023). 
> The ELIXIR Training Lesson Template - Developing Training Together (v1.0.0-alpha). Zenodo. 
> https://doi.org/10.5281/zenodo.7913092
