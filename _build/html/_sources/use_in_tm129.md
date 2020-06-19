---
jupyter:
  jupytext:
    notebook_metadata_filter: rise
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.4.2
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  rise:
    enable_chalkboard: true
    scroll: true
---

<!-- #region slideshow={"slide_type": "slide"} -->
## Use in TM129 
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "skip"} -->
Jupyter notebooks have been used deliver practical activities in *TM351 Data Management and Analysis* for several years.

To date, the complex computing environment used to support the module activities has been delivered via a Virtualbox virtual machine.

From 20J, the intention is to deliver software to students:

- via Docker, using *Open Computing Lab* approaches;
- via an online OU hosted environment *not* created from the *Open Computing Lab* context *[(though it arguably could and should be...)]*.

## Accessing the TM129 Open Computing Lab Environment

The TM129 Open Computing Lab environment repository can be found at [`tm129-robotics2020`](https://github.com/innovationOUtside/tm129-robotics2020/).

The environment includes:

- Jupyter notebooks
- the `nbev3devsim` 2d robot simulator;
- Tensofrflow playground.

The container can be retrieved from DockerHub as `ousefuldemos/tm129-robotics2020:latest`


### Accessing the Environment Via Mybinder
You can launch the environment on MyBinder directly from this button...

[![Binder](https://mybinder.org/badge_logo.svg)](https://gke.mybinder.org/v2/gh/innovationOUtside/tm129-robotics2020/master?urlpath=content)


### Running the Environment on Your Own Computer

To run the environment on your own computer, you need to do the following:

- install Docker onto your computer; you can download the installation files from the Docker website: Get Docker
- open a terminal / command prompt in your desktop; from the command prompt, do the following:
- create a working directory / folder to work in by entering the command: `mkdir TM129`;
- change directory into that fold by running the command: `cd TM129`;

To run the container from the command line on a Mac:

`docker run --name tm129test -p 8129:8888 -v $PWD:/home/jovyan/notebooks -e JUPYTER_TOKEN="letmein" ousefuldemos/tm129-robotics2020:latest`

If you have not already downloaded and installed the `ousefuldemos/tm129-robotics2020` container image, it will be automatically downloaded the first time you try to run a container instance from it.

The previous command will serve the container on `http://localhost:8129` and share folders from the current directory (that is, the directory you started the cntainer in); login with the token `letmein` or whatever token you set.

On Windows, I think you need to try something like the following [UNTESTED]:

`mkdir c:\tm129share\notebooks`
`docker run --name tm129test -p 8129:8888 -v c:\tm129share\notebooks:c:\home\jovyan\notebooks -e JUPYTER_TOKEN="letmein" ousefuldemos/tm129-robotics2020:latest`

### Starting and Stopping the Container
From the command line / command prompt, run the following commands:

- stop (hibernate) the container with the command: `docker stop tm129test`
- restart the container with the command: `docker restart tm129test`


### Accessing Your Files
Files that exist outside the `/home/joyan/notebooks`  directory path *in the container* (which is to say, outside the notebooks and openrefine directories viewable from the notebook server homepage, will not be shared to your local desktop.

Notebooks and .md source files are available from the public module Github repository. They should be downloaded and placed in the `notebooks/` directory that is contained within the directory that you launched the TM129 OCL Docker contaner in. The notebooks will persist in that directory even if the Docker container is destroyed and Docker is uninstalled from your computer.

