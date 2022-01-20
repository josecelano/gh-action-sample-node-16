# Hello world javascript action

Example from [official GitHub docs](https://docs.github.com/en/actions/creating-actions/creating-a-javascript-action#testing-out-your-action-in-a-workflow).

This action prints "Hello World" or "Hello" + the name of a person to greet to the log.

I'm using the repo to report an issue to the [act](https://github.com/nektos/act) project because I'm not able to use `act with` node16.

I'm getting this error `Error: The runs.using key in action.yml must be one of: [composite docker node12], got node16`

Full output:

```s
$ act -w ./.github/workflows/test.yml -j hello_world_job
[test.yml/A job to say hello] 🚀  Start image=catthehacker/ubuntu:act-latest
[test.yml/A job to say hello]   🐳  docker pull image=catthehacker/ubuntu:act-latest platform= username= forcePull=false
[test.yml/A job to say hello]   🐳  docker create image=catthehacker/ubuntu:act-latest platform= entrypoint=["/usr/bin/tail" "-f" "/dev/null"] cmd=[]
[test.yml/A job to say hello]   🐳  docker run image=catthehacker/ubuntu:act-latest platform= entrypoint=["/usr/bin/tail" "-f" "/dev/null"] cmd=[]
[test.yml/A job to say hello]   🐳  docker exec cmd=[mkdir -m 0777 -p /var/run/act] user=root workdir=
[test.yml/A job to say hello]   🐳  docker cp src=/tmp/testact/gh-action-sample-node-16/. dst=/tmp/testact/gh-action-sample-node-16
[test.yml/A job to say hello]   🐳  docker exec cmd=[mkdir -p /tmp/testact/gh-action-sample-node-16] user= workdir=
[test.yml/A job to say hello] ⭐  Run Checkout
[test.yml/A job to say hello]   ✅  Success - Checkout
[test.yml/A job to say hello] ⭐  Run Hello world action step
[test.yml/A job to say hello]   ❌  Failure - Hello world action step
^CError: The runs.using key in action.yml must be one of: [composite docker node12], got node16
```

I'm using:

- Node version: v16.13.2
- Act version:  0.2.25

## Inputs

### `who-to-greet`

**Required** The name of the person to greet. Default `"World"`.

## Outputs

### `time`

The time we greeted you.

## Development

Install:

```shell
npm install
```

Build:

```shell
npm run build
```

Run:

```shell
node dist/index.js
```

## Testing

```shell
act -w ./.github/workflows/test.yml -j hello_world_job
```
