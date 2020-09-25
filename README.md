# Hello world JavaScript Github Action

This action prints "Hello World" or "Hello" + the name of a person to greet to the log. To learn how this action was built, see "[Creating a JavaScript action](https://help.github.com/en/articles/creating-a-javascript-action)" in the GitHub Help documentation.

## Inputs

### `who-to-greet`

**Required** The name of the person to greet. Default `"World"`.

## Outputs

### `time`

The time we greeted you.

## Example usage

```yaml
uses: actions/hello-world-javascript-action@master
with:
  who-to-greet: 'Mona the Octocat'
```


# PERSONAL NOTE 
The private action is calling index.js to do the actual work. It reads the input param using
```
core.getInput('who-to-greet')
```
, then do the work and pass over the output values using
```
core.setOutput("time", time)
```
The output values can be used inside the workflow step like 
```
      - name: Get the output time
        run: echo "The time was ${{ steps.hello.outputs.time }}"
```
When an action is in a private repository, the action can only be used in workflows in the same repository. Public actions can be used by workflows in any repository. You can publish an action out to public.

## Rules to publish an action
https://github.community/t/unable-to-publish-github-action-to-github-marketplace/16927/2