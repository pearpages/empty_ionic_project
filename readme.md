## Installation

```bash
sudo npm install -g ionic cordova
```

```bash
ionic --v
```

```bash
cordova --v
```

```bash
ionic start <project-name> blank
```

```bash
ionic serve
```

## Info

We are usin the eggly src code. [eggly](https://github.com/eggheadio/egghead-angularjs-from-scratch-getting-started).

## Build, Emulate and Debug

```bash
ionic platform add ios
```

```bash
ionic build ios
```

```bash
# l -> live reload
# c -> console log
# s -> server log output
ionic emulate ios -lcs
```

## ionic-plugins

```bash
# list all the ionic plugins
ionic plugin
```

```bash
# inappbrowser
ionic plugin add cordova-plugin-inappbrowser
```

```javascript
// in a controller

bookmarksListCtrl.goToUrl = function goToUrl(bookmark) {
    window.open(bookmark.url, '_system');
}
```

```html
<a ng-click="bookmarkListCtrl.goToUrl(bookmark)">URL</a>
```