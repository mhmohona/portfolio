# Packaging `mwparserfromhell` for the Conda-Forge 

My journey into the world of Conda packages began with a single aim: bring the `mwparserfromhell` library to the fingertips of the Python community through the **conda-forge** channel. This report recounts the technical steps and lessons learned, serving as a roadmap for fellow contributors and a testament to the power of open-source collaboration.

## Setting the Stage

My trusty tools? Anaconda/Miniconda and `conda-build`, the conductor of this packaging symphony.

## Crafting Recipe

With the `conda skeleton pypi mwparserfromhell` command, I created the foundation – a dedicated `mwparserfromhell` directory housing the initial recipe file - `meta.yml`. 

## Mastering `meta.yaml`

Within the `meta.yaml` file, I defined the package's identity – name, version, dependencies and other necessary fields. After updating everything, and addressing reviewes from conda-forge maintainer this is how my YML file looked like: 

```yml
{% set name = "mwparserfromhell" %}
{% set version = "0.6.5" %}

package:
  name: "{{ name|lower }}"
  version: "{{ version }}"

source:
  url: "https://pypi.io/packages/source/{{ name[0] }}/{{ name }}/{{ name }}-{{ version }}.tar.gz"
  sha256: 2bad0bff614576399e4470d6400ba29c52d595682a4b8de642afbb5bebf4a346

build:
  number: 0
  script: "{{ PYTHON }} -m pip install . -vv"

requirements:
  build:
    - {{ compiler('c') }}
  host:
    - pip
    - python
  run:
    - python

test:
  imports:
    - mwparserfromhell
    - mwparserfromhell.nodes
    - mwparserfromhell.nodes.extras
    - mwparserfromhell.parser
    - mwparserfromhell.smart_list
    - mwparserfromhell.parser._tokenizer
  requires:
    - pip
  commands:
    - pip check

about:
  home: "https://github.com/earwig/mwparserfromhell"
  license: MIT
  license_family: MIT
  license_file: LICENSE
  summary: "MWParserFromHell is a parser for MediaWiki wikicode."
  doc_url: "https://mwparserfromhell.readthedocs.io/en/latest/"
  dev_url: "https://github.com/earwig/mwparserfromhell"

extra:
  recipe-maintainers:
    - earwig
    - mhmohona
```

## Local Testing

Before unleashing the package upon the world, I tested it using `conda build .`. This command ran without build errors.

## Joining the Community

Following the conda-forge contribution guidelines, I submitted the package for review on their GitHub repository - [https://github.com/conda-forge/staged-recipes/pull/24068](https://github.com/conda-forge/staged-recipes/pull/24068). The experienced maintainer provided invaluable feedback, ensuring the package met their high standards and aligned with community expectations. After incorporating their suggestions and addressing any issues raised, I was thrilled to see my pull request merged!

This marked a significant milestone, as it not only validated my efforts but also resulted in the official creation of the `mwparserfromhell-feedstock` repository: [https://github.com/conda-forge/mwparserfromhell-feedstock](https://github.com/conda-forge/mwparserfromhell-feedstock). This repository now houses the recipe files, build scripts, and documentation for the `mwparserfromhell` Conda package, ensuring its long-term sustainability and accessibility for the broader Python community.


## Beyond Deployment

Maintenance became an ongoing commitment to keep the package in sync with `mwparserfromhell` releases and address user-reported issues. 

Through this journey, the `mwparserfromhell` Conda package was born, offering a valuable asset to the Python community. This report captures the technical steps and skills applied, serving as a testament to my understanding of Conda package development and my dedication to contributing to open-source software projects.

The knowledge gained and the community connections forged pave the way for future contributions, ensuring that valuable tools like `mwparserfromhell` remain accessible to all.
