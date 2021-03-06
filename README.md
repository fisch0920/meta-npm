# meta-npm [![travis](https://img.shields.io/travis/fisch0920/meta-npm.svg)](https://travis-ci.org/fisch0920/meta-npm) [![npm](https://img.shields.io/npm/v/meta-npm.svg)](https://npmjs.org/package/meta-npm) [![downloads](https://img.shields.io/npm/dm/meta-npm.svg)](https://npmjs.org/package/meta-npm)

#### Meta package manager for managing projects comprised of many npm modules

Node and npm encourage the use of small, reusable modules, and many npm authors have [embraced](http://substack.net/how_I_write_modules) this approach. Large node projects are now commonly broken up into dozens of isolated submodules and their respective repositories, which is great from software engineering standpoint, but this fragmentation can make it more difficult to develop on and contribute to the project as a whole.

`meta-npm` is a meta npm package manager designed to solve this problem by allowing you to easily checkout a top-level project and all of its dependencies, creating any forks as neccessary and handling `npm link`ing them together for local development. It also makes synchronizing changes to the submodules a breeze both on github and the npm registry.

It uses `npm` and `git` under the hood the same way you would if you were developing across multiple modules simultaneously. It just makes this process as easy as it would be if you were working on a single module.

## install

```
npm install meta-npm
```

## usage

```meta-npm -u fisch0920 -p ****** -w feross,fisch0920 init webtorrent```
This will recursively find all npm module dependencies of the `webtorrent` project published by `feross` or `fisch0920` that're backed by github repositories and clone / fork them as necessary, `npm link`ing and `npm install`ing the results together for a fresh local development environment.

## todo

* ~~Create project.~~
* meta-npm init
* meta-npm fetch
* meta-npm pull
* meta-npm push
* meta-npm pull-request
    * create PRs for each fork where HEAD is newer than upstream

## license

MIT. Copyright (c) Travis Fischer.
