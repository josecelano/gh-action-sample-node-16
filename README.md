# Hello world javascript action

Example from [official GitHub docs](https://docs.github.com/en/actions/creating-actions/creating-a-javascript-action#testing-out-your-action-in-a-workflow).

This action prints "Hello World" or "Hello" + the name of a person to greet to the log.

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
