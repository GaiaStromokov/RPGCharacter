---
title: Force
fileclass: Dimensions
type: Sub_Dimension
outputs: []
---
~~~meta-bind-js-view
{Class} as title
{fileclass} as fileclass
{type} as type
save to {outputs}
hidden
---

let values = [];
const outputs = context.metadata.frontmatter.outputs =[];

if (context.bound.title !== "") {
    if (context.bound.fileclass !== "") {
        values.push("[[" + context.bound.title + "|" + context.bound.fileclass + "]]");
    }
    if (context.bound.type !== "") {
        values.push("[[" + context.bound.title + "|" + context.bound.type + "]]");
    }
}

return values.concat(outputs)

~~~

`VIEW[{outputs}][link]`
