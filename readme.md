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

## Ionic Components

### Navigation

```html
<ion-side-menus enable-menu-with-back-views="true">
    <ion-side-menu-content>
        <ion-nav-bar class="bar-calm"></ion-nav-bar>
        <ion-nav-view name="bookmarks">
            <!-- where bookmarks template gets loaded, that's why we use the *name* attribute -->
        </ion-nav-view>
    </ion-side-menu-content>
    <ion-side-menu side="left">
        <ion-nav-view name="categories"></ion-nav-view>
    </ion-side-menu>
</ion-side-menus>
```

### ion-content and ion-list

**ion-content** handles the scroll for content.

```html
<ion-view>
    <ion-content>
        <a menu-close class="logo" ui-sref="eggly.categories">
            <img src="assets/img/eggly-logo.png">
        </a>
        <ion-list>
            <ion-item
                menu-close
                href="" 
                ng-repeat="category in categoriesListCtrl.categories"
                ui-sref="eggly.categories.bookmarks({category:category.name})"
                ui-sref-active="active">
                    {{category.name}}
            </ion-item>
        </ion-list>
    </ion-content>
</ion-view>
```

## Ionic Components

- **ion-side-menus** : A container element for side menu(s) and the main visible content.
- **ion-side-menu-content** : A container for the main visible content, sibling to one or more ionSideMenu directives.
- **ion-side-menu** : A container for a side menu, sibling to an ionSideMenuContent directive.
- **ion-nav-view** : Used to render templates in your application. Each template is part of a state. States are usually mapped to a url, and are defined programatically using angular-ui-router (see their docs for reference).
- **ion-view** : A container for view content and any navigational and header bar information. Used as a child of ionNavView.
- **ion-nav-bar** : If we have an ionNavView directive, we can also create an ionNavBar, which will create a topbar that updates as the application state changes.
- **ion-nav-buttons** : Use nav buttons to set the buttons on your ionNavBar from within an ionView.
- **ion-content** : Provides an easy to use content area that can be configured to use Ionic’s custom Scroll View, or the built in overflow scrolling of the browser.
- **ion-list** : The List is a widely used interface element in almost any mobile app, and can include content ranging from basic text all the way to buttons, toggles, icons, and thumbnails.
- **ion-item** : Used to create items inside of an ionList.