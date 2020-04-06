---
layout: default
title: How to Merge Cell
published: true
nav_order: 1
parent: Contentful
comments: true
---

## How to merge table cell in Contentful

The table plugin in Contentful is using [GitHub-flavored Markdown syntax](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax), which does not support cell merging.

There is an alternative way to implement cell merging is to use html syntax.

```html
<table>
  <tr>
    <th>HTTP Method</th>
    <td colspan="2">GET</td>
  </tr>
  <tr>
    <th rowspan="5">Production URL</th>
    <td colspan="2">https://public-api.ssg-wsg.sg/dp-oauth/oauth/authorize?response_type=code&client_id={clientId}&redirect_uri={redirectUri}&state={state}</td>
  </tr>
  <tr>
    <td>client_id</td>
    <td>Obtained from Developer Portal</td>
  </tr>
  <tr>
    <td>redirect_uri</td>
    <td>Need to use the same value as given in the Developer Portal <br/> Subscription Settings > Redirect URL</td>
  </tr>
  <tr>
    <td>state</td>
    <td>State can be the hash code of session id or a random generate string value (Suggested minimum length = 32)</td>
  </tr>
  <tr>
    <td>scope</td>
    <td>Not required as there is no consent for partial Scope.</td>
  </tr>
</table>
```

The markdown preview for the above table is:
![table](../../../assets/images/contentful/table.png)

Conclusion:
In addition to native markdown syntax to genereate table with basic feature, html syntax is also supported in markdown.