---
aliases:
  - Pokedex Documentation
tags: 
title: Pokedex Documentation
date created: Friday, September 23rd 2022, 9:06:56 pm
date modified: Friday, September 23rd 2022, 9:10:44 pm
---

# Pokedex Documentation

The Documentation for the Pokédex uses a Jamstack approach in contrast to the Application itself. It uses Gatsby as the frontend framework without a headless CMS (this is subject to change), GitHub for versioning and deployment, and assumes NGINX for serving.

## Important

This repository was created as submodule of the [Pokedex](https://github.com/Kanto-Pharmaceuticals/pokedex) with the intention of re-using it's code for scaffolding other projects. It is important to have some knowledge of working with `git` and `submodules` in CLI in order to avoid breaking pointer references.

Documentation in Markdown format, and Obsidian configuration files for the Pokédex project.  This is a submodule for the [Pokedex Documentation Framework](https://github.com/Kanto-Pharmaceuticals/pokedex-documentation-framework) and should be reviewed before being pushed to documentation framework build.  Content can be updated in the framework repo using `yarn update`.
