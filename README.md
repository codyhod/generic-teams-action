# Microsoft Teams Actions #

This is a GitHub Action that sends a message to a given channel in Microsoft Teams. 
It is completely generic and fully customizable.


## Inputs ##

* `webhook_uri` (**Required**): Incoming webhook URI to Microsoft Teams
* `summary` (**Required**): Message summary
* `title`: Message title
* `text`: Message text
* `theme_color`: Message theme color
* `sections`: JSON array for message sections
* `actions`: JSON array for message actions

## Outputs ##

* `message`: Message sent to Microsoft Teams


## Example Usage ##

```yaml
steps:
  name: Send a message to Microsoft Teams
  uses: codyhod/generic-teams-action@v0.9.0
  with:
    webhook_uri: ${{ secrets.MS_TEAMS_WEBHOOK_URI }}
    title: <Message Title>
    summary: <Message Summary>
    text: <Message Text>
    theme_color: <Message Theme Color>
    sections: '[{ "activityTitle": "hello world" }, { ... }]'
    actions: '[{ "@type": "OpenUri", "name": "lorem ipsum", "targets": [{ "os": "default", "uri": "https://localhost" }] }, { ... }]'
```

> For more details about `sections` and `actions`: [https://docs.microsoft.com/outlook/actionable-messages/message-card-reference](https://docs.microsoft.com/outlook/actionable-messages/message-card-reference?WT.mc_id=aliencubeorg-github-juyoo)

It is recommended that your webhook_uri be a repository secret, although this is not mandatory.

## License ##

**Microsoft Teams Actions** is released under [MIT License](http://opensource.org/licenses/MIT)

> The MIT License (MIT)
>
> Copyright (c) 2020 [aliencube.org](https://aliencube.org)
> 
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
> 
> The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
> 
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
