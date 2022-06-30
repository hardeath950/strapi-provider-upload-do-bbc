# Strapi Upload Provider for Digital Ocean Spaces
- This provider is a fork of [shorwood](https://github.com/shorwood) [strapi upload provider](https://github.com/shorwood/strapi-provider-upload-digitalocean) for Digital Ocean spaces.

This provider will upload to the space using the AWS S3 API.

## Parameters
- **key**: [Space access key](https://cloud.digitalocean.com/account/api/tokens)
- **secret**: [Space access secret](https://cloud.digitalocean.com/account/api/tokens)
- **endpoint**: URL of the space (e.g. 'fra.digitaloceanspaces.com')
- **space**: Name of the space in the Digital Ocean panel.
- **directory**: Name of the sub-directory you want to store your files in. (Optional - e.g. '/example')
- **cdn**: CDN Endpoint - URL of the CDN of the space (Optional - e.g. 'cdn.example.com')

## How to use

1. Install this package

```
// npm
npm i strapi-provider-upload-do-bbc

// yarn 
yarn add strapi-provider-upload-do-bbc
```

2. Create or update (if exist) config 
 - in strapi v3.x ./extensions/upload/config/settings.js
 - in strapi v4.x ./config/plugins.js 

with content: 

```
// for strapi v3.x
module.exports = {
  provider: "do-bbc",
  providerOptions: {
    key: process.env.DO_SPACE_ACCESS_KEY,
    secret: process.env.DO_SPACE_SECRET_KEY,
    endpoint: process.env.DO_SPACE_ENDPOINT,
    space: process.env.DO_SPACE_BUCKET,
    directory: process.env.DO_SPACE_DIRECTORY,
    cdn: process.env.DO_SPACE_CDN,
  }
}

// for strapi v4.x
module.exports = ({env}) => ({
  // ...
  upload: {
    config: {
      provider: "strapi-provider-upload-do-bbc", 
      providerOptions: {
        key: process.env.DO_SPACE_ACCESS_KEY,
        secret: process.env.DO_SPACE_SECRET_KEY,
        endpoint: process.env.DO_SPACE_ENDPOINT,
        space: process.env.DO_SPACE_BUCKET,
        directory: process.env.DO_SPACE_DIRECTORY,
        cdn: process.env.DO_SPACE_CDN,
      }
    },
  }, 
  // ...
})
```

3. Create `.env` and add to them 

```
DO_SPACE_ACCESS_KEY
DO_SPACE_SECRET_KEY
DO_SPACE_ENDPOINT
DO_SPACE_BUCKET
DO_SPACE_DIRECTORY
DO_SPACE_CDN
```

with values obtained from the tutorial:

> https://www.digitalocean.com/community/tutorials/how-to-create-a-digitalocean-space-and-api-key

Parameter `DO_SPACE_DIRECTORY` and `DO_SPACE_CDN` are optional and you can omit them both in `.env` and `settings`.

## Resources

- [MIT License](LICENSE.md)

## Links

- [Strapi website](http://strapi.io/)
- [Strapi community on Slack](http://slack.strapi.io)
- [Strapi news on Twitter](https://twitter.com/strapijs)
- [Strapi docs about upload](https://docs.strapi.io/developer-docs/latest/plugins/upload.html)

## Contributors
<a href="https://github.com/hardeath950"><img src="https://avatars.githubusercontent.com/u/21207498?s=96&v=4" title="hardeath950" width="60" height="60"></a>
<a href="https://github.com/shorwood"><img src="https://avatars.githubusercontent.com/u/4062779?v=3" title="shorwood" width="60" height="60"></a>
<a href="https://github.com/gustawdaniel"><img src="https://avatars.githubusercontent.com/u/16663028?v=3" title="gustawdaniel" width="60" height="60"></a>
