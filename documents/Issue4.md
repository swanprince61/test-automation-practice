# Issue Report #4

## Dashboard page link does not work on Make's model list page

### Replication steps
1. From the dashboard, drill down to Popular Make page by clicking the image (Lamborghini make page)
2. Click on "Buggy Rating" on the top left corner

### Expected result
* The user should go back to the dashboard screen

### Current result
* The user stays on the same page

### Further Investigation
* On Make detail screen, Buggy Rating hyperlink is changed to `/broken`. This is a UI bug that needs to be fixed.

On Make detail screen, Buggy Rating hyperlink is to:
```
<a _ngcontent-whw-1="" class="navbar-brand" href="/broken">Buggy Rating</a>
```

On other screens, Buggy Rating hyperlink is to:
```
<a _ngcontent-whw-1="" class="navbar-brand" href="/">Buggy Rating</a>
```


### Test environment
* Chrome v92 on MacOS 11.5

[Back to issue list](./IssueList.md)