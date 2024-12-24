# Automation of release & tags 
1. Doc url : https://docs.github.com/en/rest/repos?apiVersion=2022-11-28
      curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer API_TOKEN" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
   https://api.github.com/repos/Ayyappan-STC/demo/releases -d     '{"tag_name":"sprint_date","target_commitish":"main","name":"sprint_date","body":"body","draft":false,"prerelease":false,"generate_release_notes":false}'
   
3. GITHub token
4. Secrets
5. gitworkflow


#**CODEOWNERS feature in github **
It’s used to define who owns specific files or directories within a repository. 
When multiple users/teams are responsible for different parts of the code, the CODEOWNERS file simplifies the pull request review process by ensuring that only the necessary reviewers are added to a PR. 
Also, its help us to avoid the manual effort to assigning right reviewers and enhance the efficiency and security of the pull request review process.
Granular Ownership: You can specify ownership at a granular level for specific files or directories. For example, if only one file needs special attention, you can set specific owners for that file.
Managing Large Teams: Instead of assigning individual users to files, you can assign GitHub teams as owners. This is particularly useful in large repositories where individual file ownership may change frequently. It helps maintain the integrity of the review process without needing to constantly update the CODEOWNERS file with user names.

Why do we need this?
To Ensure that the appropriate people are notified about changes to the codebase.
To Enforce code review policies to maintain code quality and security.
Streamline the review process, making it more efficient and reducing administrative overhead.

How to Create and Use a CODEOWNERS File
1.	Location of CODEOWNERS File: /. github/CODEOWNERS 
2.	Syntax: The CODEOWNERS file follows a specific syntax to assign ownership to files or directories. Each line of the file defines a path pattern and the associated users or teams.
o	Users: GitHub usernames are prefixed with @.
o	Teams: Teams are defined using @org/team-name, where org is the GitHub organization name and team-name is the name of the team.
o	Wildcards: Patterns like * can be used to match files or directories.


For example:
# CODEOWNERS file example
# Set @user-1 as the owner for all files
* @user-1

# Assign @user-2 to all files in the docs directory
/docs/* @user-2

# Assign a team to a specific directory
/src/ @my-org/dev-users

# Assign multiple users to a specific file
/src/main.py @user-1 @user-2

3.	Matching Patterns: The CODEOWNERS file supports the following pattern types:
o	/ matches from the root directory.
o	* matches any number of characters (wildcard).
o	? matches exactly one character.
o	** matches directories and subdirectories recursively.
Example of different patterns:
o	/src/* → matches all files in the /src/ directory.
o	/src/**/*.js → matches all JavaScript files in the /src/ directory and its subdirectories.
o	/README.md → matches the README.md file in the root of the repository.
Note: The CODEOWNERS file has a hierarchical system where the most specific pattern takes priority over more general patterns. For instance, /src/main.py will take precedence over /src/*.

Best Practices:
•	Use teams: Instead of assigning individual users, it’s often better to use GitHub teams for better scalability and management.
•	Keep it simple: Make sure to define clear ownership for files that require frequent reviews, like core components or documentation.
•	Keep it up to date: Ensure that the CODEOWNERS file is updated whenever team responsibilities or file structures change.
