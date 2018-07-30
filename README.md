# Simple NFS Filesystem #

This project installs and configures a simple standalone NFS filesystem which may be mounted by other clusters.

The NFS server created in this sample has a single storage volume, exported at `/mnt/exports/data`.   For real
file server deployments, a wide variety of options are supported.

See the CycleCloud documentation for the full set of options for mounting and raiding volumes on the server, and configuring NFS exports and mounts:

- How to mount persistent storage volumes:
    - [Mounting Volumes](https://docs.cyclecomputing.com/user-guide-v6.6.1/storage/_mounting_volumes)
- How to create an NFS export and mount it:
    - [Exporting and Mounting NFS](https://docs.cyclecomputing.com/user-guide-v6.6.1/storage/_mounting_nfs)


<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Table of Contents**

- [Simple NFS Filesystem](#simple-nfs-filesystem)
    - [Pre-Requisites](#pre-requisites)
    - [Configuring the Project](#configuring-the-project)
    - [Deploying the Project](#deploying-the-project)
    - [Importing the Cluster Template](#importing-the-cluster-template)

<!-- markdown-toc end -->


## Pre-Requisites ##


This sample requires the following:

  1. CycleCloud must be installed and running.

     a. If this is not the case, see the CycleCloud QuickStart Guide for
        assistance.

  2. The CycleCloud CLI must be installed and configured for use.

  3. You must have access to log in to CycleCloud.

  4. You must have access to upload data and launch instances in your chosen
     Cloud Provider account.

  5. You must have access to a configured CycleCloud "Locker" for Project Storage
     (Cluster-Init and Chef).

  6. Optional: To use the `cyclecloud project upload <locker>` command, you must
     have a Pogo configuration file set up with write-access to your locker.

     a. You may use your preferred tool to interact with your storage "Locker"
        instead.


## Configuring the Project ##


The first step is to configure the project for use with your storage locker:

  1. Open a terminal session with the CycleCloud CLI enabled.

  2. Switch to the nfs_filer project directory.


## Deploying the Project ##


To upload the project (including any local changes) to your target locker, run the
`cyclecloud project upload` command from the project directory.  The expected output looks like
this:

``` bash

   $ cyclecloud project upload my_locker
   Sync completed!

```


**IMPORTANT**

For the upload to succeed, you must have a valid Pogo configuration for your target Locker.


## Importing the Cluster Template ##


To import the cluster:

 1. Open a terminal session with the CycleCloud CLI enabled.

 2. Switch to the nfs_filer project directory.

 3. Run ``cyclecloud import_template NFS -f templates/nfs.txt``.
    The expected output looks like this:
    
    ``` bash
    
    $ cyclecloud import_template NFS -f templates/nfs.txt --force
    Importing template NFS....
    ----------------------------
    NFS : *template*
    ----------------------------
    Keypair:
    Cluster nodes:
	filer: off
    Total nodes: 1
    ```



# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.