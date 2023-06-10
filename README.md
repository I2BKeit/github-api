# github-api
    #!/bin/bash


       USERNAME=""
       TOKEN=""




# Make an API request to fetch your repositories
repos_info=$(curl -s -u "$USERNAME:$TOKEN" https://api.github.com/user/repos)

# Print the retrieved repository information
echo "Repositories:"
echo "$repos_info"

# Loop through each repository to fetch branches
repo_names=$(echo "$repos_info" | jq -r '.[].name')

echo "Branches:"

for repo_name in $repo_names; do
    branches_info=$(curl -s -u "$USERNAME:$TOKEN" https://api.github.com/repos/$USERNAME/$repo_name/branches)
    echo "Repository: $repo_name"
    echo "$branches_info"
    echo ""
done
