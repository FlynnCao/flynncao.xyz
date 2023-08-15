---
title: Customise your ESLint config
date: 2023-07-18T05:00:00.000+00:00
hide: false
lang: en
tags:
  - eslint
  - formatter
category: code
tocAlwaysOn: true
---
[[toc]]

## Starter
~~I browsed several youtube videos but no one give me right guidance and finally I find a tutorial in (掘金)['https://juejin.cn/post/7130277872412917797/'].~~

Unfortunately, tutorials related to this topic are rare and I cannot even find a new suitable one, in which I recommend official [ESLint customize tutorial](https://eslint.org/docs/latest/use/configure/plugins).

## AST
The basic of ESLint is to parse and check the page of code as a tree, which we call it AST, you can explorer it here:

https://astexplorer.net/


## Configs of Plugin

Example: https://github.com/vuejs/eslint-plugin-vue

As we are talking about plugins, it's obvious that even one kind of plugin like `eslint-plugin-vue` would consider different aspects of users, thus it has the following presets(configs):

The core module of this repository is [lib](https://github.com/vuejs/eslint-plugin-vue/tree/master/lib), where all rules, configs and utils are stored here: 

So here it is:

![20230721134006](https://raw.githubusercontent.com/FlynnCao/blog-images/main/img/20230721134006.png)


## Presets Recommendation
Although you can customize your own rules plugins for better working environment, using other's presets is not a bad idea to start with. 


If you prefer to use `prettier` to format your code in some rare contexts, you can try [Ray's preset](https://github.com/so1ve/eslint-prettier-config), without using any code formatter you can apply [Antfu's preset](https://github.com/antfu/eslint-config) directly like me! 

Just be careful about the discrepancies of their VSCode settings:

In Antfu's Preset, it's:
```json
  "prettier.enable": false,
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.organizeImports": false
  }
```
While in Ray's preset, it's:
```json
{
  "editor.defaultFormatter": "esbenp.vscode-prettier",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```
