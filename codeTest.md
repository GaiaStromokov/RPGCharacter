---
level: 2
testnum: 5
ability:
  secondWind: 1
---
## Level
level: `INPUT[number(class(nb-mb-css)):level]`

```meta-bind-button
style: primary
label: Update Data
actions:
  - type: command
    command: "Templates/update metadata.md"
```


```meta-bind-js-view  
<button data-type="template" data-template="Templates/update metadata.md"">Run Template</button>
```
