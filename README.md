# guld-git-config-ini

[![source](https://img.shields.io/badge/source-bitbucket-blue.svg)](https://bitbucket.org/guld/tech-js-node_modules-guld-git-config-ini) [![issues](https://img.shields.io/badge/issues-bitbucket-yellow.svg)](https://bitbucket.org/guld/tech-js-node_modules-guld-git-config-ini/issues) [![documentation](https://img.shields.io/badge/docs-guld.tech-green.svg)](https://guld.tech/lib/guld-git-config-ini.html)

[![node package manager](https://img.shields.io/npm/v/guld-git-config-ini.svg)](https://www.npmjs.com/package/guld-git-config-ini) [![travis-ci](https://travis-ci.org/guldcoin/tech-js-node_modules-guld-git-config-ini.svg)](https://travis-ci.org/guldcoin/tech-js-node_modules-guld-git-config-ini?branch=guld) [![lgtm](https://img.shields.io/lgtm/grade/javascript/b/guld/tech-js-node_modules-guld-git-config-ini.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/b/guld/tech-js-node_modules-guld-git-config-ini/context:javascript) [![david-dm](https://david-dm.org/guldcoin/tech-js-node_modules-guld-git-config-ini/status.svg)](https://david-dm.org/guldcoin/tech-js-node_modules-guld-git-config-ini) [![david-dm](https://david-dm.org/guldcoin/tech-js-node_modules-guld-git-config-ini/dev-status.svg)](https://david-dm.org/guldcoin/tech-js-node_modules-guld-git-config-ini?type=dev)

A git config ini encoder/decoder for guld

### Install

##### Node

```sh
npm i guld-git-config-ini
```

##### Browser

```sh
curl https///bitbucket.org/guld/tech-js-node_modules-guld-git-config-ini/raw/guld/ini.min.js -o ini.min.js
```

### Usage

Consider an git config ini-file `.git/config` that looks like this:

    [core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = true
    [remote "origin"]
        url = https://github.com/nfer/git-config-ini
        fetch = +refs/heads/*:refs/remotes/origin/*
    [user]
        name = Nfer Zhuang

You can read, manipulate and write the ini-file like so:

    var fs = require('fs')
      , ini = require('ini')

    var config = ini.parse(fs.readFileSync('.git/config', 'utf-8'))

    config.core.filemode = false
    config.user.name = 'nfer'
    config.user.email = 'nfer@nferzhuang.com'

    fs.writeFileSync('.git/config', ini.stringify(config))

#### Browser

This script has been bundled for browser use and is available as global var `gitConfigIni`.

```
<html>
  <body>
    <script src="ini.min.js"></script>
    <script>
      console.log(gitConfigIni)
    </script>
  </body>
</html>
```

### API

#### decode(inistring)

Decode the ini-style formatted `inistring` into a nested object.

#### parse(inistring)

Alias for `decode(inistring)`

#### encode(object)

Encode the object `object` into an ini-style formatted string.

#### stringify(object)

Alias for `encode(object)`

### License

MIT Copyright Nfer Zhuang <nfer.zhuang@gmail.com>

