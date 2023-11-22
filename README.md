# cloudflare-worker-starterkit

## Development

the starter kit is setup with full typescript support.

run npm install to install all dependencies

````bash

npm install

```

run npm dev to start the development server

```bash

npm run dev

```

## Deployment

deployment is done via github action, so push to main will deploy the worker.
it requires a repository secret called CLOUDFLARE_API_TOKEN with the api token of your cloudflare account.
````

## Documentation

<https://developers.cloudflare.com/workers/>

## debugging

you can connect to a live log stream via the wrangler tail command. this will provide http logs and any console logs from your worker code

```bash

CLOUDFLARE_API_TOKEN=YOUR_API_TOKEN npx wrangler tail

```

## Secrets

### locally

create a file called .dev.vars in a .dotenv format

```bash
SECRET_KEY=value
```

### remotely

secrets are set via the wrangler cli. this will create the secret remotly inside of cloudflare and the secret will be available to your code at runtime

```bash

CLOUDFLARE_API_TOKEN=YOUR_API_TOKEN npx wrangler secret put SECRET_NAME

```
