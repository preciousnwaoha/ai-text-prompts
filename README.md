# Pseudo Code 

## Webhooks
1. Listen to PR on Backend 
2. Get repo name 
3. Query db for automations with identical repo params
4. Filtering for ONLY "auto"
5. Pull md contents from db
6. Pull diff from github repo 
7. Generate new content based on diff and previous content
8. update db (automation & markdown)
9. Frontend commit call
10. comment in pr
11. If `type` is "auto-merge" commit updated markdown to head and merge.


## Generating JSON Repo Content Context
1. provide parameters: `repo`,`readme`
3. prompt ai to decide if readme is useful,
4. if readme is useful, add it to context object.
5. fetch top level files 
6. feed ai top level files JSON,
7. prompt ai to generate a JSON object with values `projectStack` as a string
8. `notableFiles` as a list of files to look into (INCLUDING MAIN FILE)
9. fetch each notable file content e.g `packageJSON = "some-content"`
10. based on the `mainFile`.
11. `topLevelFolders` to look into one file within.
12. fetch the contents of each file in top level
13. we have object.


## Use AI with GitHub link
1. provide parameters: `codeLink`
2. Destruct `codeLink` into `repo`, `owner`, `path=""`
3. Identify path type; tree, md file, or root
4. If path type is a tree, get `sha` of tree folder
5. If path type is an md file or root, then we commit
6. If path type is a tree, if has md files fetch all md files in
7. if tree or root has no md, create new readme.md based on JSON Repo Content Context.
8. if tree or root has an existing md; fetch it and update it based on context and readme content(if applicable).
9. if tree or root has multiple mds; generate JSON Repo Content Context
10. generate readme with ai using genrated context and desciption(if available)
11. update the db
12. add automation prop to db
13. route to file




## Link File to Github and Push
1. 


## Use Template with GithubLink
1. template: 





