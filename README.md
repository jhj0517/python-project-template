# Python Project Template
This is basic python project template with basic CI/CD GA workflow & GH issue & PR template. Anyone can use this template to start a new python project.

## Directory Structure
You can remove the `(optional)` directories if you don't need them. (e.g. `docker/`, `setup.py`, etc.)
```
python-project-template/    
├── .github/                # GA workflows & PR, Issue templates
├── docker/                 # (optional) Dockerfile & docker-compose files related to the project.  
├── tests/                  # Test codes with pytest
├── .gitignore              # gitignore file 
├── README.md               # README file
└── requirements.txt        # Project dependencies 
```

## Github Actions
1. [`ci.yml`](https://github.com/jhj0517/python-project-template/tree/master/.github/workflows/ci.yml)
Basic CI workflow with pytest. It runs tests in the [`tests`](https://github.com/jhj0517/python-project-template/tree/master/tests) directory, with master branch commit & PR triggers by default.
2. [`publish-dockerhub.yml`](https://github.com/jhj0517/python-project-template/tree/master/.github/workflows/publish-dockerhub.yml)
Basic CD workflow for DockerHub. This workflow is optional, only needed when you want to publish the docker image to the dockerhub. You can remove this workflow if you don't need it.<br>
It will build the docker image with [`docker/Dockerfile`](https://github.com/jhj0517/python-project-template/tree/master/docker/Dockerfile) and [`docker/docker-compose.yaml`](https://github.com/jhj0517/python-project-template/tree/master/docker/docker-compose.yaml) for the project and publish it to the dockerhub with the tag `latest`.<br>
The auto-trigger for this workflow is disabled by default. You can edit the workflow to enable it.<br>
Before using the workflow, you need to set the `DOCKERHUB_USERNAME` & `DOCKERHUB_TOKEN` in the repository secrets.

[image](URL)

And make sure to edit the `image-name` in the workflow.

[code-url](URL)

3. [`publish-pypi.yml`](https://github.com/jhj0517/python-project-template/tree/master/.github/workflows/publish-dockerhub.yml)
Basic CD workflow for pypi package. This is the workflow that only used in case when your project is a python package that will be published in the pypi. You can remove this workflow if you don't need it.<br>
It will build it and publish it to pypi whenever you make a new "release" in the repository.<br>
The auto-trigger for this workflow is disabled by default. You can edit the workflow to enable it.<br>
Before using the workflow, edit package name to yours in the workflow.

[code-url](URL)

## Issue & PR Template
There are some basic templates for the issue & PR. You can edit them or add more to fit your project's needs.

- Issue Templates:
  1. [`bug_report.md`](https://github.com/jhj0517/python-project-template/tree/master/.github/ISSUE_TEMPLATE/bug_report.md) : Basic bug report template
  2. [`feature_request.md`](https://github.com/jhj0517/python-project-template/tree/master/.github/ISSUE_TEMPLATE/feature_request.md) : Feature request template

- PR Template: [`pull_request_template.md`](https://github.com/jhj0517/python-project-template/tree/master/.github/pull_request_template.md)


## Docker

The [`docker/`](https://github.com/jhj0517/python-project-template/tree/master/docker) directory and [`publish-dockerhub.yml`](https://github.com/jhj0517/python-project-template/tree/master/.github/workflows/publish-dockerhub.yml) are associated with building the docker image and publishing to dockerhub. You can remove them if you don't need them.<br>
Before building image, make sure to edit the variable in the [`docker/Dockerfile`](https://github.com/jhj0517/python-project-template/tree/master/docker/Dockerfile):

[code-url](URL)

And in [`docker/docker-compose.yaml`](https://github.com/jhj0517/python-project-template/tree/master/docker/docker-compose.yaml) as well:

[code-url](URL)

The image is built and published automatically by the action, but you can also manually build and run the image with the following commands.

1. git clone this repository
```bash
git clone https://github.com/your-name/your-project-name.git
```
2. Build the image
```bash
docker compose -f docker/docker-compose.yaml build
```
3. Run the container
```bash
docker compose -f docker/docker-compose.yaml up
```

## PyPI
The [`setup.py`](https://github.com/jhj0517/python-project-template/tree/master/setup.py), [`pyproject.toml`](https://github.com/jhj0517/python-project-template/tree/master/setup.py) and [`publish-pypi.yml`](https://github.com/jhj0517/python-project-template/tree/master/.github/workflows/publish-dockerhub.yml) are associated with building the package and publishing to PyPI. You can remove them if you don't need them.<br>
Make sure to edit dependencies & variables in the [`pyproject.toml`](https://github.com/jhj0517/python-project-template/tree/master/setup.py) as your project's needs.


## How to start 
Click "Use this template" and "Create a new repository". Then git clone it and you can start your own project. 

[image-url](URL)



