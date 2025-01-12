# Git Workflow :

- it's some recipes & recommendations to do in order to have more consistent and productive manner in work(coding).
- it give users lots of flexibility to manage the code base and its changes.
- before using it, it's important to make sure that every member of team are on the same page and all are in agreement to using certain git workflow.

##### ```Good to know : There is No standardized way to use Git!``` 

## There is a winner ??? 🧐

In order to choose the best workflow to work with in a team, we have to evaluate it and see if its in sync -(sync?, could'nt find better word here, so..)- culture and does this enhance the productivity of the team or just make more limits to that.

- Does it scales, when team grows ?
- Is it easy to fix the mistakes & errors in it ?
- Does it make cognitive overhead to the team ?



## So, How many workflows are out there?
Not gonna explain each them here, just mentioning their name.

```Good to Know : Using Git to power your development workflow presents a few advantages over SVN. First, it gives every developer their own local copy of the entire project. This isolated environment lets each developer work independently of all other changes to a project - they can add commits to their local repository and completely forget about upstream developments until it's convenient for them. ```


- **Centralized workflow** : Put everything in one place & easy to use for newbies 👼

- **Feature Branch workflow** : Like centralized, but for each feature, new branch is made, and then, will be merge to the main again

- **GitFlow workflow** : There is long-lived branches like , `main` for production , `dev/develop` for integration and task-based branches. It's ideal for scheduled releases 🤷‍♂️

- **GitHub workflow** : It's like GitFlow, but more simpler, work on `feature branches` and merge them into `main` only after `reviews`. Its good for continuous deployment

- **GitLab Flow** : Combines feature branches with environment-specific branches (e.g., production, staging). Aligns with CI/CD pipelines and deployment strategies.

For more detailed information, you can refer to [Atlassian's Git Workflow Guide](https://www.atlassian.com/git).

