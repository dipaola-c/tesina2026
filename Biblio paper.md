### Por leer

```dataview
Table author as author, publish as "año", tags as tags
WHERE contains(bib,"forreading")
SORT Status DESC
```

### Secundarias

```dataview
Table author as author, publish as "año", tags as tags
WHERE contains(bib,"sec")
SORT Status DESC
```
### Descartadas

```dataview
Table author as author, publish as "año", tags as tags
WHERE contains(bib,"not")
SORT Status DESC
```
- Supporting the Cage [Andy Weaver](https://pmc.iath.virginia.edu/issue.504/14.3bios.html#weaver.bio)


### Obras

```dataview
Table author as author, publish as "año", tags as tags
WHERE contains(listen,"y")
SORT Status DESC
```



