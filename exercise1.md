For a web application written in Python, in development by a team of 6, will be released soon, discuss in ca. 300 words:
- tools for linting, testing, and building 
- alternatives other than Jenkins and Github actions to set up the CI
- Would this setup be better in a self-hosted or a cloud-based environment? Why? 


Linting
In a team of 6, a linter is needed both to ensure stylistic consistency and to detect logical errors. Flake8 https://flake8.pycqa.org/ combines PyFlakes (logical linting), pycodestyle (stylistic linting) and Mccabe, but does not support autoformatting to enforce styles, which would allow to gain time given the imminent release. Therefore, I would use pyflakes for logical linting (https://github.com/PyCQA/pyflakes) and in the following step, https://pypi.org/project/autopep8/ for autoformatting. 


Testing
With an imminent release, both unit tests and smoke tests are needed to ensure that individual components of software work and that it runs in production. There are multiple testing frameworks (Robot, PyTest, unittest), which can all be integrated into a CI pipeline. 

Building
In order to ensure portability across platforms, the software should be built from a docker file. Alternatives, such as poetry or pipenv, would be suitable during development, but might be less safe given the imminent release.  

Alternatives to Jenkins and Github Actions.
GitLab is open source and has the advantage of integrating with Docker, as has the commercial software Travis CI. Furthermore, most cloud providers offer their native CICD tools, such as AWS code pipeline, Azure pipelines and Bitbucket pipelines for Atlassian's bitbucket clouds. As we are at the very beginning of the project, I would choose GitLab because it is not tied to a particular cloud provider. 

Self-hosted or cloud environment?
This decision depends on various factors. If the team works remotely, a cloud hosted-solution may be easier accessed by all developers. It might be more cost-effective, especially if the company has no infrastructure in place. 
