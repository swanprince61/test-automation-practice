# Issue Report #3

## Models are randomly sorted on Make's model list page

### Replication steps
1. From the dashboard, drill down to Popular Make page by clicking the image (Lamborghini make page)
2. On Make page, click "Votes" (or any other list header)

### Expected result
* Models are sorted by Votes from highest to lowest

### Current result
* Models are sorted randomly

### Further Investigation
The frontend is calling the API with `/prod/makes/{model}?modelsOrderBy=random` parameter, which is incorrect. The frontend code needs to be fixed to use the correct parameter.

### Test environment
* Chrome v92 on MacOS 11.5

[Back to issue list](./IssueList.md)
