# Contributing

## Installing Software

### Python 3

If you do not have Python installed, download it from the official website and follow its install instructions: https://www.python.org/downloads/

!!! tip
	Make sure to add python to PATH during the install process, it makes life a bit easier.

A TextEditor such as Sublime Text3 or some other text editor is highly recommended. 

### Source Code

Clone the bobadocs repository from Github. https://github.com/MillsRoboticsTeam253/bobadocs.git

### Python Dependencies 

This site uses the MkDocs Python package to convert Markdown files to a website, and a few more packages to provide additional functionality and theming. You can install all the necessary dependencies by running `pip install -r requirements.txt` while in the root directory of the repository.

Alternatively, run the following in the repository's root directory.

```
pip install mkdocs
```

```
pip install mkdocs-material
```

```
pip install pymdown-extensions
```

```
pip install pygments
```

## Development Workflow

### Local Changes

To develop locally, run `mkdocs serve` in the root directory of the project. This will generate a local version of the website from the code at http://127.0.0.1:8000/ and will autorefresh whenever changes are made in docs/. 

Adding or modifying the documentation is fairly simple, each page of the website is contained within its own `.md` file. Adding new pages are as simple as creating new `.md` files 

Make sure your Markdown files are placed in the correct subfolders. For example, `javabasics.md` should be placed in the Intro to Java folder in the repository. This helps others find your documentation later when they want to edit or add information.

Page settings are configured in the `mkdocs.yml` YAML file. All the settings have already been setup for you, simply edit the nav section when making changes

!!! attention
	Do not forget to add new `.md` pages to the `nav` section of `mkdocs.yml`. New pages not added to the YAML configuration file will not show up on the document. 

When you are happy with your changes/additions, run `mkdocs build --clean` to build the site. This will create a site/ directory within the repository. The `.gitignore` file has been setup so that the local build will not be pushed to Github. 

Proofread your documentation and make sure that your documentation displays as intended. 

!!! hint
	The purpose of writing documentation is to pass down knowledge to current and future team members. Make sure your documentation is clear and understandable. Add pictures to illustrate your explanations. Adding too much detail is sometimes as bad as putting nothing there in the first place. 

### Push changes to Github

All Done? Simply push/merge it to the master branch of the [bobadocs](https://github.com/MillsRoboticsTeam253/bobadocs)repository. ReadTheDocs will automatically update the clone the bobadocs repository and update the documentation within a few minutes.

!!! fail
	If the readthedocs site does not update within a few minutes of your Github push, it is likely that the virtual python docs compiler has failed build. Check your local changes for syntax errors and push again. If the issue occurs again, ask your programming lead to check the readthedocs build logs. 





