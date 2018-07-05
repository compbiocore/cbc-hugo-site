# Brown Computational Biologt Core Hugo Site


## Requirements

- [Hugo](https://gohugo.io/)
- [Node](https://nodejs.org/en/)
- [NPM](https://nodejs.org/en/)
- [Gulp](https://gulpjs.com)


## Install Dependencies

```bash
npm install
```

## Set up `.env` file with Embed.rocks API key
Sensitive environment variables are stored in the .env file. This file is included in .gitignore intentionally, so that it is never committed.
- Create a `.env` file and copy into it the contents of `.env.template`
- Create an account at [Embed.rocks](https://embed.rocks/)
- Go to the dashboard and copy the key and add that to your `.env` file

## Local Development

```bash
npm start
```

When you run `npm start`, a Gulp pipeline will start. That will collect the embeds based on the list of urls listed in
`config.yaml` and dump the data into `data/embeds.json` so that can be used in Hugo templates. CSS will be compiled and a Hugo server will start.
To see the site, navigate to `localhost:1313`.
