# NAMING CONVENTIONS

One of the most critical choices developers can make when it comes to starting a new repository is its name. There are some standard conventions in this regard. A good naming standard does much to avoid confusion, sidesteps refactoring of directory trees, and is an enabler of effective version control. Most importantly, it allows for clarity when referencing the project either verbally, or in a written format (within e-mail and/or within a messenging app like Slack or Skype).

- Our product or solution = "The Wonderful App Project"
- When referencing the app as a whole = "Wonderful"
- When explicitly referencing the application layer = "App"
- When explicitly referencing the API layer = "API"

Beyond the above, and most importantly...

Like the scientific convention for naming animals (as proposed by Aristotle), good names have a *genus* and a *species*--the genus being a broad and general classification; the species being an identifying sub-category of the genus.

Follows are some examples of how this philosophy of naming might be applied to code.

## STAKEHOLDERS OR LICENSEES

The product may be rolled out to one or more stakeholder groups during its evolution. For example--hypothetically...

* ACME -- our company
* CYBERDYNE -- a department or division within ACME
* WONKA INDUSTRIES -- a licensee
* STARK INDUSTRIES -- a licensee
* WAYNE INDUSTRIES -- a licensee

## NAMING ENVIRONMENTS

Each stakeholder may have more than one deployable environment. Hence, within each stakeholder or licensee *genus*, are several potential environment *species*. Environments are generally named for their *purpose*. For example...

* LOCAL--exists only on developers' workstations
* DEMO--a demonstration environment deployed to an on prem network or the cloud.
* DEV or STAGING--a staging environment deployed to an on prem network or the cloud.
* QA--an environment explicitly for user acceptance testing deployed to an on prem network or the cloud.
* PROD--a production environment deployed to an on prem network or the cloud.

### COMBINE THEM BOTH

Combine the Stakeholder name and the Purpose of the Environment name, separating each with a dash, to create a discrete identifier for any given environment...

<STAKEHOLDER_NAME> + <PURPOSE_OF_ENVIRON>

Examples...

* WONKA-DEMO
* STARK-STAGING
* CYBERDYNE-PROD

## DATABASES

Database names should include the service which uses it, and the type of engine employed. The name should be lowercase. No dashes or underscore should be used; if and only if required, default to underscore.

#### Examples:

* appsql
* apinosql **or** api_nosql

...or more explicitly...

* apppostgres
* apimongo


##GIT REPOS AND BRANCHES

The Git repo associated with any environ should be all lowercase, to distinguish code from environment.

This is a physical environ...

    WAYNE-QA

This is the code in the repo, and specifically references the master branch...

    wayne-qa

A feature branch (to be eventually merged into master)...

    TASK-1-wayne-ui-widget

We follow the Git Flow methodolgy of branching wherever possible. The repo for versioned releases of code are prepended with the version number. Note: we have not set this up yet.

## JIRA, TFS, Other Scrum Tools

### PROJECTS

These follow similar conventions as above. Project names ought to be in ALL CAPS. Issues are lowercase. An important difference between the way projects in scrum tools or a kanban board should be represented vs. environments in the cloud--projects in the scrum tool should use underscores to separate words in their titles.

#### Examples:

An AWS environ...

    ACME-DEV

A Jira project...

    ACME_DEV

### ISSUES (TASKS, ETC.)

Continue to use dashes when creating issues or tasks within your scrum tool. Reason: this becomes critical for end-to-end continuous deployment pipelines. For example--with Jira: within each project, Jira automatically prepends issues with an abbreviation of the project's title and a number as unique identifier. So, in a Jira project titled ACME_DEV, the title for an issue like "change-background-images" will automatically be generated as "ND-1-change-background-images". Since--ideally--Git branches should be instantiated from within the scrum tool, the subsequent issue title automatically becomes the branch name in Git.

#### EXAMPLES

So in chat, we reference the ACME staging environ thusly...

    ACME-DEV

And, in chat, we reference the related ACME project in TFS or Jira thusly...

    NOVA_DEV

In chat, we reference the repo thusly...

    nova-dev

...and a new feature branch like so...

    ND-1-change-background-images

...or the new feature branch may be abbreviated to...

    ND-1

The point of all of this is to make articulate (especially in e-mail or text-chat based conversations) which resources or platform is being referenced, without having necessitating explicitly calling it out, and to avoid having to ask for iterative clarification.

# AN EXAMPLE TEXT CHAT

### Without Naming Conventions (BAD)

"Today, we're deploying wonka. I've closed the project in TFS. I've merged wonka-dev into WONKA reskin. I also merged the other UI branch into wonka dev."


### With Naming Conventions (GOOD)

"Today, we're deploying to WONKA-DEV. We've closed some issues in WONKA_DEV. ND-1-change-background-images has been merged into wonka-dev." 

### With Naming Conventions (GOOD...ANNOTATED)

"Today, we're deploying to WONKA-DEV" **caps and dash indicate an environ in AWS or GCP**. "We've closed some issues in WONKA_DEV" **caps and underscore indicate a project in TFS**. "ND-1-change-background-images..." **task ID number, lowercase, and dashes indicate a branch in Gitlab** "...has been merged into wonka-dev" **stakeholder and environ name presented in lowercase and dashes indicate a repo in Gitlab (master branch is implied)**.


# CHEAT SHEET

* Environs: All CAPS, dashes only--like so: STAKEHOLDER-PURPOSE
* Repo: All lowercase, dashes only--like so: stakeholder-purpose
* Branch: All lowercase, dashes only--like so: uuid-stakeholder-purpose
* Scrum Projects: All CAPS, underscores only--like so: STAKEHOLDER_PURPOSE
* Scrum Tasks or Issues: All lowercase, dashes only; uuid-licensee-purpose

