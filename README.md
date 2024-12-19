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
