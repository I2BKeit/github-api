# github-api
    #!/bin/bash


      USERNAME="your_username"
      TOKEN="your_personal_access_token"

      # Make an API request to fetch your user information
      user_info=$(curl -s -u "$USERNAME:$TOKEN" https://api.github.com/user)

      # Print the retrieved information
      echo "$user_info"
