+++
author = "Sofia Popova"
title = "How Github Does Authorization"
date = "2022-12-24"
description = "Sample article showcasing basic Markdown syntax and formatting for HTML elements."
tags = [
    "markdown",
    "css",
    "html",
    "themes",
]
categories = [
    "themes",
    "syntax",
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
+++
Github is a platform used by many organizations and individuals to manage their projects, code, and other digital resources. Github has a specific model for managing access and permissions for organizations and repositories to ensure that access and permissions are managed with security and privacy in mind. Understanding this model makes it possible to create a secure and effective access control system.
## GENERAL SCOPES - ALL USERS ACCESS
Github has implemented general scopes as a way to simulate permissions. General scopes are authorization rules applied to all users, regardless of their individual permissions. These scopes can be used to restrict access to certain parts of the system, such as repositories, projects, and user data. Scopes can also be used to limit the ability of users to access confidential information or make changes to the system. By using general scopes, Github is able to provide a more secure and reliable system for its users.
## GRANULAR ROLES
Github allows access to your code and repositories to other users by assigning granular roles to individual users or groups (teams).
Granular roles are the key to access authorization. They determine who can access what part of the code or repository and what they can do with it. Access roles can also be assigned to groups rather than individual users, allowing access control to be delegated.
Before authorizing access, it is crucial to understand the access roles associated with each user or group. This understanding ensures that only users and groups with the appropriate level of access can view and modify the code or repository.
Github makes it easy to modify access roles for individual users and groups, allowing you to update access control quickly. This flexibility ensures that only those with the correct access roles can access the code and repository.
Remember that the system of controlling access is called Role-based Access Control (RBAC). With RBAC, you can assign roles to individual users or groups, helping to ensure that only the right people have access to the right resources.

## ROLES IN-DEPTH
Organizations have an owner responsible for managing members, teams, and outside collaborators. The owner can create teams to manage groups of members and assign different roles and permissions to each team. Individual members can also be assigned specific roles and permissions to resources.
Outside collaborators are non-members who can be invited to a specific repo and given specific roles and permissions. They do not have access to the organization's entire collection of repos.
### RESPONSIBILITIES OF THE ROLES
All members of the repository are responsible for the following:
* Following the organization's coding style guidelines
* Following the organization's contribution guidelines
* Ensuring that the code is of high quality
* Keeping the repository up to date
#### Admin
* Admin is responsible for access control, including:
* Managing security
* Deleting a repository
* Managing access to the repository
* Defining code owners
* Managing protected branches
* Renaming the repository's default branch
#### Repository Maintainer
* The Repository Maintainer is responsible for managing the repository, including:
* Setting up the repository and controlling access
* Updating repository settings
* Resolving conflicts related to the contents of the repository
#### Contributor
* Contributors are responsible for creating, updating, and managing the contents of the repository, including:
* Creating new branches, commits, and pull requests
* Reviewing and merging pull requests
* Updating existing branches and commits
#### Reviewer
* Reviewers are responsible for reviewing the changes made to the repository and ensuring they meet the organization's standards, including:
* Reviewing pull requests
* Identifying potential issues
* Providing feedback on changes
* Approving changes
#### Reader
* Readers are non-code contributors who want to view or discuss your project. Their capabilities are:
* Viewing published releases
* Creating new discussions
* Commenting on existing discussions
* Reporting abusive or spammy content
* Opening issues
## OAUTH
OAuth scopes and apps provide two ways to control access to GitHub resources. OAuth scopes control access to specific features and operations, while OAuth apps control access to multiple repositories. Remember that OAuth App isn't a regular Github App because it acts as a GitHub user other than using its own identity. An authorized OAuth App can access all of the user's or organization owner's accessible resources. This type of app can't use granular permissions.
### OAUTH APPS
#### REPO HOOK
One of the available OAuth apps is the repo_hook, which allows admins to configure automated triggers for specific events in a repository. This app is helpful for tasks such as running automated tests, sending notifications, and more. The repo_hook is also part of the security measures to ensure that access and permissions are adequately managed. Admins can use it to enforce specific policies, such as requiring a certain number of approvals before merging a pull request, or to set up notifications for any changes to the repo.
#### ORG HOOK
Another OAuth app is org_hook which allows admins to configure automated triggers for events in an organization, such as adding or removing members to a team. This app can be used to add or remove members from teams, send notifications when access privileges change, and more. This hook helps to ensure that access and permissions are managed securely and efficiently, as admins can set up automated triggers for specific events.
### OAUTH SCOPES
Github does provide an OAuth scope for granting read/write access to repositories, but this should only be used by applications that need to interact with the API. OAuth scopes should not be used to grant users different access levels and permissions, as it can easily lead to permission creep and security vulnerabilities.
One of the deeper reasons why OAuth scopes should not be used is scope explosion. Scope explosion is a term used to describe the situation when a user's access and permissions in Github become unmanageable due to a large number of OAuth scopes they have been granted. When users have access to more resources than they need, this can lead to permission creep, where users have access to resources they don't need, and potential security risks.
Another reason against using OAuth scopes is stale permissions. Stale permissions are user access privileges that are no longer valid or necessary. When stale permissions are present, users may be able to access resources that they should not have access to or be unable to access resources that they should have access to. This can happen when users are added or removed from a project, and the corresponding permissions are not updated in the GitHub repository.
Lastly, when managing access and permissions in Github, short-lived tokens can lead to performance issues. Short-lived tokens expire after a certain time, usually a few minutes. This quality can lead to performance problems, as users must constantly authenticate themselves with a new token. Tokens can also lead to additional security risks, as they can be stolen and used to access resources.
## SUMMARY
Github provides several tools and features to manage access to organizations and repositories. It is crucial to understand these tools before authorizing access. Github's authorization model can be complicated and messy. General scopes are related to users, but users can have different roles assigned to them in the organization, team, or even per repo. This assignment means that Github's model is not purely RBAC (Role-Based Access Control); it is a mixture of OAuth apps, roles that limit the set of permissions on a resource, and resource-specific permissions.
