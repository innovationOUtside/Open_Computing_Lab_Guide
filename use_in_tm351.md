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
# Use In TM351
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "skip"} -->
Jupyter notebooks have been used deliver practical activities in *TM351 Data Management and Analysis* for several years.

To date, the complex computing environment used to support the module activities has been delivered via a Virtualbox virtual machine.

From 20J, the intention is to deliver software to students:

- via Docker, using *Open Computing Lab* approaches;
- via an online OU hosted environment *not* created from the *Open Computing Lab* context *[(though it arguably could and should be...)]*.

## Accessing the TM351 Open Computing Lab Environment

The TM351 Open Computing Lab environment repository can be found at [`tm351vm-binder`](https://github.com/innovationOUtside/tm351vm-binder/).

The environment includes:

- Jupyter notebooks
- lots of preinstalled Python packages
- OpenRefine
- a PostgreSQL database server
- a MongoDB database server

The container can be retrieved from DockerHub as `ousefuldemos/tm351-binderised:latest`

### Accessing the Environment Via Mybinder
You can launch the environment on MyBinder directly from these buttons...


Open to Notebook homepage: [![Binder](https://gke.mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/innovationOUtside/tm351vm-binder/master)

Open to OpenRefine: [![Binder](https://mybinder.org/badge_logo.svg)](https://gke.mybinder.org/v2/gh/innovationOUtside/tm351vm-binder/master?urlpath=openrefine)

Open to Jupyterlab: [![Binder](https://mybinder.org/badge_logo.svg)](https://gke.mybinder.org/v2/gh/innovationOUtside/tm351vm-binder/master?urlpath=lab)


### Running the Environment on Your Own Computer

To run the environment on your own computer, you need to do the following:

- install Docker onto your computer; you can download the installation files from the Docker website: Get Docker
- open a terminal / command prompt in your desktop; from the command prompt, do the following:
- create a working directory / folder to work in by entering the command: `mkdir TM351`;
- change directory into that fold by running the command: `cd TM351`;

To run the container from the command line on a Mac:

`docker run --name tm351test --rm -d -p 8351:8888 -v $PWD/notebooks:/home/jovyan/notebooks -v $PWD/openrefine_projects:/home/jovyan/openrefine -e JUPYTER_TOKEN="letmein" ousefuldemos/tm351-binderised:latest`

This will serve the container on `http://localhost:8351` and share folders from the current directory; login with the token `letmein` or whatever token you set.

On Windows, I think you need to try something like the following [UNTESTED]:

`mkdir c:\tm351share`
`docker run --name tm351test --rm -d -p 8351:8888 -v c:\tm351share\notebooks:c:\home\jovyan\notebooks -v c:\tm351share\openrefine_projects:c:\home\jovyan\openrefine -e JUPYTER_TOKEN="letmein" ousefuldemos/tm351-binderised:latest`


### Starting and Stopping the Container
From the command line / command prompt, run the following commands:

- stop (hibernate) the container with the command: `docker stop tm351test`
- restart the container with the command: `docker restart tm351test`


### Accessing Your Files

Files that exist outside the `/home/joyan/notebooks` and `/home/jovyan/openrefine` directory paths *in the container* (which is to say, outside the notebooks and openrefine directories viewable from the notebook server homepage, will not be shared to your local desktop.

Notebooks are available from the module VLE site. They should be downloaded and placed in the `notebooks/` directory that is contained within the directory that you launched the TM351 OCL Docker contaner in. The notebooks will persist in that directory even if the Docker container is destroyed and Docker is uninstalled from your computer.