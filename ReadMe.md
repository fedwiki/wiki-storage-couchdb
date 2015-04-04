# Wiki Storage CouchDB [![Build Status](https://travis-ci.org/fedwiki/wiki-storage-couchdb.svg?branch=master)](https://travis-ci.org/fedwiki/wiki-storage-couchdb)

An experimental module to provide CouchDB storage for an external module for
Federated Wiki, rather than being built into the core.

The motivation for this is that not everybody is using CouchDB for storage, also
allows for the integration to be independently maintained.

## Using CouchDB for Wiki Storage

The following steps will need to be followed:

1. Take a copy of the [fedwiki/wiki-node](https://github.com/fedwiki/wiki-node)
repository. *Either create a fork on the GitHub site, or clone a copy either
locally or to where you wish to install Federated Wiki.*

2. In your copy, edit `package.json` to add the following line to the dependencies:

```
    "wiki-storage-couchdb": "*",
```

3. If you are using git for deployment, commit this change to git.

4. Install your modified version of Federated Wiki, either:

  * running `npm install 'your-github-id'/wiki-node`, if you are using github
  for deployment, or

  * if you modified `package.json` inplace by running `npm install` from within
  the modified directory. See [npm-install](https://www.npmjs.org/doc/cli/npm-install.html)
  for more ideas.

5. When starting Federated Wiki you will need to tell it to use CouchDB. This
is done by adding the following configuration setting

```
--database '{"type": "couchdb", "name": "otherpages", "host": '127.0.0.1', "port": ...}'
```

## Developer Notes

To run the tests for `wiki-storage-couchdb` install (dev) dependencies with `$ npm install` then run the tests with node_modules/.bin/mocha test
