## Example app using Couchbase

[Couchbase](https://www.couchbase.com/) is a modern database for enterprise applications. This example will show you how to connect to and use Couchbase in your Next.js app.

If you want to learn more about Couchbase, visit the following pages:

- [Couchbase Docs](https://docs.couchbase.com/)
- [Couchbase Developer Portal](https://developer.couchbase.com/)
- [Couchbase Cloud](https://cloud.couchbase.com/sign-up)

## Configuration

### Set up a Couchbase database

Set up a Couchbase database either locally or with [Couchbase Cloud](https://cloud.couchbase.com/sign-up).

Local installation can be accomplished through a variety of methods, but [Docker](https://docs.couchbase.com/server/current/install/getting-started-docker.html) is the simplest.

After Couchbase is installed, set up a cluster by following [this tutorial](https://docs.couchbase.com/server/current/manage/manage-nodes/create-cluster.html).

- _NOTE:_ the **eventing** and **analytics** services can be unchecked if memory is a constraint (this is often the case with docker and other local installations).

A variety of sample buckets can be installed to get up and running with a data model quickly.

### Set up environment variables

Copy the `env.local.example` file in this directory to `.env.local` (which will be ignored by Git):

```bash
cp .env.local.example .env.local
```

Set each variable on `.env.local`:

- `COUCHBASE_USERNAME` - The username of an authorized user on your Couchbase instance
- `COUCHBASE_PASSWORD` - The corresponding password for the username specified above
- `COUCHBASE_ENDPOINT` - The endpoint to connect to. Use `localhost` for a local instance of Couchbase, or the Wide Area Network address for a cloud instance.
- `COUCHBASE_BUCKET` - The bucket you'd like to connect to for testing.
- `IS_CLOUD_INSTANCE` - `true` if you are trying to connect to an instance of Couchbase Cloud, `false` otherwise.

### Run Next.js in development mode

```bash
npm install
npm run dev
# or
yarn install
yarn dev
```

Your app should be up and running on [http://localhost:3000](http://localhost:3000)! If it doesn't work, post on [GitHub discussions](https://github.com/vercel/next.js/discussions).

You will either see a message stating "You are connected to Couchbase" or "You are NOT connected to Couchbase". Ensure that you have provided the correct environment variables.

When you are successfully connected, you can refer to the [Couchbase Node.js SDK docs](https://docs.couchbase.com/nodejs-sdk/current/hello-world/start-using-sdk.html) for further instructions on how to query your database.


### Setup DB

- create a Bucket on Couchbase DB
- create a collection on Couchbase DB
- add document on the collection