#NAMING CONVENTIONS

- Our product = Persistence Portal
- When referencing the app as a whole = Portal
- When explicitly referencing the API = API

For everything else...

Like the scientific convention for naming animals (as proposed by Aristotle), good names have a genus and a species--the genus being a broad and general classification; the species being an identifying sub-category of the genus.

##NAMING ENVIRONMENTS

###LICENSEES

We have many potential licensees, but each licensee is a genus unto itself.

* ETA--prepended to any product we roll for ourselves
* NOVA--our first licensee
* SULLIVAN--a potential second licensee
* FULLSAIL--another potential licensee


###ENVIRONMENTS

We have only four types of specific environments. Each licensee may have more than one environment. Hence, within each licensee genus, are several environment species.

* LOCAL--exists only on developers' workstations
* DEMO--a demonstration environment in AWS
* DEV--a staging environment in AWS
* PROD--a production environment in AWS

###COMBINE THEM BOTH

Combine the Licensee name and Purpose of the Environment name, separating each with a dash, to create a discrete identifier for any given environment...

<LICENSEE_NAME> + <PURPOSE_OF_ENVIRON>

Examples...

* ETA-DEMO
* NOVA-DEV
* SULLIVAN-PROD


##GIT REPOS AND BRANCHES

The Git repo associated with any environ should be all lowercase, to distinguish code from environment.

This is a physical environ...

    NOVA-DEV

This is the code in the repo, and specifically references the master branch...

    nova-dev

A feature branch (to be eventually merged into master)...

    NSD-1-nova-reskin

We follow the Git Flow methodolgy of branching wherever possible. The repo for versioned releases of code are prepended with the version number. Note: we have not set this up yet.

##JIRA 

###PROJECTS

These follow similar conventions as above. Jira project names are in ALL CAPS. Jira issues are lowercase. An important difference between the way projects in Jira should be represented vs. environments in AWS--Jira projects should use underscores to separate words in their titles.

####Examples:

An AWS environ...

    NOVA-DEV

A Jira project...

    NOVA_DEV

###ISSUES (TASKS, ETC.)

Continue to use dashes when creating issues or tasks within Jira. Within each project, Jira automatically prepends issues with an abbreviation of the project's title and a number as unique identifier. So, in a Jira project titled NOVA_DEV, the title for an issue like "change-background-images" will automatically be generated as "ND-1-change-background-images". Since Git branches will be instantiated from within Jira, the issue title in Jira becomes the branch name in Git.

####EXAMPLES

So in chat, we reference the NOVA staging environ thusly...

    NOVA-DEV

And, in chat, we reference the related NOVA Jira project thusly...

    NOVA_DEV

In chat, we reference the repo thusly...

    nova-dev

...and a new feature branch like so...

    ND-1-change-background-images

...or the new feature branch may be abbreviated to...

    ND-1

The point of all of this is to make articulate in text-chat based conversations which resources or platform is being referenced, without having necessitating explicitly calling it out, and to avoid having to ask for iterative clarification.

#AN EXAMPLE TEXT CHAT

###Without Naming Conventions (BAD)

"Today, we're deploying nova. I've closed the project in Jira. I've merged nova-dev into NOVA reskin. I also merged the social branch into nova dev."


###With Naming Conventions (GOOD)

"Today, we're deploying to NOVA-DEV. We've closed some issues in NOVA_DEV. ND-1-change-background-images has been merged into nova-dev." 

###With Naming Conventions (GOOD...ANNOTATED)

"Today, we're deploying to NOVA-DEV" **an environ in AWS**. "We've closed some issues in NOVA_DEV" **a project in Jira**. "ND-1-change-background-images..." **a branch in GitHub** "...has been merged into nova-dev" **a repo in Git (master branch is implied)**.


#CHEAT SHEET

* Environs: All CAPS, dashes only--like so: LICENSEE-PURPOSE
* Repo: All lowercase, dashes only--like so: licensee-purpose
* Branch: All lowercase, dashes only--like so: uid-licensee-purpose
* Jira Projects: All CAPS, underscores only--like so: LICENSEE_PURPOSE
* Jira Issues: All lowercase, dashes only; uid-licensee-purpose

