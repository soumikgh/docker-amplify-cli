# docker-amplify-cli
A minimal Alpine image with the [AWS Amplify CLI package](https://www.npmjs.com/package/@aws-amplify/cli) installed.

## Usage

It is encouraged to set up an alias so that you don't have to write or memorise a lengthy `docker run` command with volumes.

```
cat >> ~/.bash_aliases
alias amplify='docker run --rm -tiv $HOME/.aws:/root/.aws -v $HOME/.amplify:/root/.amplify -v $(pwd):/opt/node/app/src ellimistgh/amplify-cli amplify'
```

Or if you prefer, you can run it directly like

```
# docker run --rm -tiv $HOME/.aws:/root/.aws -v $HOME/.amplify:/root/.amplify -v $(pwd):/opt/node/app/src ellimistgh/amplify-cli amplify init
```

It mounts the present working directory to run the Amplify commands on, and also `~/.aws` and `~/.amplify` to read the AWS credentials and Amplify `plugins.json` file respectively
