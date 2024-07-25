# gitbook-theme-canyon

## Preview

&#160; &#160; &#160; &#160; You can get it's beauty by visiting https://www.modnar.zone/swift-book/.

## Usage

&#160; &#160; &#160; &#160; Add the theme to your book's configuration `book.json` or `book.js`:

```js
module.exports = {
  ...
  plugins : ['theme-canyon'],
  pluginsConfig : {
    'theme-canyon' : {
      'search-placeholder' : '🔍  输入搜索内容…'  // 搜索框提示信息
    }
  }
};

```

## Install

&#160; &#160; &#160; &#160; Enter the command in your bash:

``` bash
$ gitbook install
```

&#160; &#160; &#160; &#160; If it not works, you can also clone the repo to your environment and move it to `node_modules` directory manually.

## Recommand plugins

```js
plugins :
        [
        '-lunr', '-search', '-sharing', '-fontsettings', 'search-pro',
        'code', 'back-to-top-button', 'cuav-chapters', 'theme-canyon'
        ]
```

## NOTE

&#160; &#160; &#160; &#160; The project development base on [gitbook-theme-fexa](https://github.com/tonyyls/gitbook-plugin-theme-fexa) with some new features in `CSS3`.

&#160; &#160; &#160; &#160; And **canyon** is just the first word appeared on my words book yesterday. Have fun!
