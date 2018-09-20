# patternlab-plugin-error-report
Quick repo to reproduce an error with patternlab-node

## Steps to reproduce


```bash
$ npm init -y && npx @pattern-lab/cli -c patternlab init
npx: installed 442 in 19.63s
? Please specify a directory for your Pattern Lab project. ./
? Which edition do you want to use (defaults to edition-node)? edition-node
? Which starterkit do you want to use? starterkit-mustache-base
? Are you happy with your choices? (Hit enter for YES)? (Y/n) y

$ npx patternlab install --plugins @pattern-lab/plugin-tab
```
This results in this being added into the config

`patternlab-config.json`
```
...
  "plugins": {
    "@pattern-lab/plugin-tab": {
      "enabled": true,
      "initialized": false,
      "'options": {
        "tabsToAdd": []
      }
    }
  }
...
```
**NOTE** the unescaped options string.

---
```bash
$ npm run pl:build

> patternlab-plugin-error-report@1.0.0 pl:build /home/johannes/Projects/patternlab-plugin-error-report
> patternlab build --config ./patternlab-config.json

Pattern Lab Node v3.0.0-beta.1
Pattern Engine mustache: good to go
⊙ patternlab → TypeError: undefined is not a function
```