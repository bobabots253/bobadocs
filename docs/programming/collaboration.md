# Git and Github

Git is a tool our software team uses to collaborate

- [Intro to git](version-control.md)

## Github Practices

The following is a set of guidelines for contributing on Github for our team. These are guidelines, not hard rules.

- The `master` branch is for competition ready code only. **Do not use master for testing.**
- The `development` branch should consist of relatively recent development code. Experimental code should be branched off of here. Merge into the development branch if your code is deployable and tested. 
- If writing test code, create a new branch or add onto another.
- The `README` should be updated with useful information about the repository or programming team (ie. branch descriptions, checklists, etc.)
- Write useful commit messages; Describe what changes you made. (<action\>, <changes\>) is a good format. For example,
`"add initial drivetrain logic"` is good, `"robot drive haha yes"` is not good.
    - Keep commit messages in present-tense. ie: ~~"Added shooter PID"~~ should instead be `"Add shooter PID"`
