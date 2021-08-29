# Issue Report #1

## Popular Make vote count is one count higher than actual votes

### Replication steps
1. Go to the dashboard screen, check the vote count of Popular
2. Drill down to Popular Make by clicking on Popular Make image
3. Sum each model's vote counts

### Expected result
* Vote count on dashboard and sum of each models' counts match

### Current result
* Vote count on the dashboard is one count higher than sum of models' votes
* As of Sun 29/Aug 7:55pm,
   * On Dashboard, 7,103 votes for Lamborghini
   * On Make's model vote count, sum is 7,102 votes
      * Diablo:	2,478
      * Vereno: 802
      * Aventador: 721
      * Reventon: 710
      * Murcielago: 704
      * Miura: 511
      * Countach: 495
      * Gallardo: 495
      * Huracan: 186

### Further Investigation
Dashboard is getting data from API `prod/dashboard` where Make page is getting data from `/prod/makes/{make}`. It is suspicious that dashboard API returns an incorrect value.

`prod/dashboard` return body snippet
```
    "make": {
        "id": "c0bm09bgagshpkqbsuag",
        "name": "Lamborghini",
        "image": "Lamborghini-Logo.png",
        "votes": 7103
    },
```

`/prod/makes/{make}` return body snippet
```
{
    "name": "Lamborghini",
    "models": {
        "models": [
            {
                "name": "Diablo",
                "votes": 2478,
            },
            {
                "name": "Veneno",
                "votes": 802,
            },
            ...
        ]
    }
}
```

### Test environment
* Chrome v92 on MacOS 11.5

[Back to issue list](./IssueList.md)