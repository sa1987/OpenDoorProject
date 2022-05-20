# Example plain HTML site using GitLab Pages

The open science group developed during the [Opening Doors Network PhD
Education](https://openingdoors4phd.eu/) online course held in 2022.  We decided
to develop a online course on open science philosophy and methodologies aimed at
early-stage scientists and researches.  This is a tentative to build a website
that would host the course.

---

[[_TOC_]]

## Project status

- **2022-03-03 Thu**: Creation of the project.

## GitLab CI

This project's static Pages are built by [GitLab CI][ci], following the steps
defined in [`.gitlab-ci.yml`](.gitlab-ci.yml):

```
image: alpine:latest

pages:
  stage: deploy
  script:
  - echo 'Nothing to do...'
  artifacts:
    paths:
    - public
  only:
  - main
```

The current CI build the page from all the HTML files in the `public/`
directory.

## Useful resources

Learn more about GitLab Pages at https://pages.gitlab.io and the official
documentation https://docs.gitlab.com/ce/user/project/pages/.

## Troubleshooting

## Authors

- Marco Prevedello <m.prevedello1@nuigalway.ie> [@Preve92](https://twitter.com/Preve92)

## Licensing

This project is currently unlicensed.

## Acknowledgments
