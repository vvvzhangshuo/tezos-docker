# tezos-cli-docker



tezos-cli-docker is a set of scripts to build the tezos-cli tools and containerize them, as well as some convenience scripts to invoke the different binaries. Currently it is a work in progress, so __expect things to break__!

## Features

  - tezos-node convenience script, generates identity before starting the node, if it doesn't already exist.
  - tezos-client wrapper script, simply runs tezos-client and passes all arguments. 
  - more to come, continue reding. 



## Instructions

### Building the image
__Note:__ This is the recommended way of working with this repository. There is also a public image, but I do not recommend trusting me (or anybody else) with your private information:

>     # generate your working directory
>     git clone
>     cd tezos-docker
>
>     # build the image
>     docker build -t tezos-docker .
>     Grab a coffee, since ocaml has a lot of work to do to build tezos-cli.


### Pulling the image
>     docker pull  vvvzhangshuo/tezos-node


### Using the convenience scripts: 
You can now start a node and use tezos-cli to transact with the mainnet. All instructions below are working from inside the repo directory. 

#### start a node:
The following command will start a node, working with the identity file found in `./tezos-node`. If it is the first execution, an identity will be generated and the node will be started afterwards. 
>     ./tezos-node run
>


#### run tezos client: 
This will execute tezos-client, which will connect to the already-running node from last step. 
>     ./tezos-client <args>



### Future work

Things under consideration:
  - wrapper scripts for all binaries
  - more intelligent scripts. 
  - Reduce the image size even further.