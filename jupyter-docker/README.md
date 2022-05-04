# Using IPUs with Jupyter and docker

This folder contains instructions and scripts to help you get started
running your first application on the IPU using Jupyter notebooks.


| Requirements | Installation                             |
| ------------ | ---------------------------------------- |
| Docker       | `sudo apt-get install docker`            |
| V-IPU        | pre-installed on IPU-PODs and Graphcloud |

## Quick start: Run on Spell

Run the [GroupBERT code](https://github.com/graphcore/examples/tree/master/applications/tensorflow/bert#readme) in IPUs through [Spell.ml](https://spell.ml/graphcore).

 <a href="https://web.spell.ml/workspace_create?workspaceName=Graphcore-BERT-Finetuning-demo&machineType=IPUx16&githubUrl=https%3A%2F%2Fgithub.com%2Fgraphcore%2Fdemo-in-a-box&apt=git-lfs&pip=huggingface-hub&isLab=false&dockerImage=graphcore%2Fpytorch-jupyter%3Alatest"><img src=https://spell.ml/badge.svg height=20px/></a>


## Quick start: On Graphcloud


In order to use this script you will need to be connected to a machine which
has access to IPUs. This is usually done by connecting via SSH to an IPU-POD or to
Graphcloud. In order to start Jupyter you will need to call the script in `scripts/run-docker`
with the V-IPU partition name and the folder in which the docker file you want to use.

To find out the name of the V-IPU partition you should be using run the command:

```sh
$ vipu list partitions
 Partition   | Cluster  | ILDs | GW Routing | ILD Routing | Size | GCDs | State
---------------------------------------------------------------------------------
 p64         | c64_1-16 | 1    | DEFAULT    | RINGSWNC    | 64   | 1    | ACTIVE
---------------------------------------------------------------------------------
```

In this case the partition name is `p64`. To launch the Jupyter server run the command:

```sh
$ bash scripts/run-docker <your partition name> .
```

In my case this is:

```sh
$ bash scripts/run-docker p64 .

```

This will start a jupyter server with support for TensorFlow 2 in a container on port 44300 of the machine which hosts the IPUs.
You can choose which deep learning framework the notebook server will have available by passing one of `tf1`, `tf2` or `pytorch` to the `run-docker` command. The port on which the server is connected can also be modified by using the `-p` option.

Launching a server with PyTorch support on port 1234 can be done with:

```sh
$ bash scripts/run-docker <your partition name> . pytorch -p=1234
```

Run `bash scripts/run-docker -h` to see a full list of options.

To access the notebooks you will likely need to forward the port from the remote machine (which has access to IPUs) to the machine you are working on. For a server started with the default port configuration (port 44300), the port forwarding is easily done via SSH using the command:

```sh
ssh -NL 44300:localhost:44300 <user>@<host>
```

Where `user` and `host` are your user name and the name or IP address of the machine connected to the IPUs.


## Licensing

The code presented here is licensed under the MIT License, see the LICENSE file at the root of this repository.

