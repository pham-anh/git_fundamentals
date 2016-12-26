# Set up an SSH connection between Clients and Git

1. Check if you have an SSH key
 You ca find your SSH key in your PC at
 * ~/.ssh/xxx_rsa -> This is your private key
 * ~/.ssh/xxx_rsa.pub -> This is your public key
1. If you have no SSH key, generate one
1. If you have an SSH key:
 * Add the private key into the ssh-agent (of your PC)
 * Add public key to GitHub (or GitLab)
 
 
 ---
 
 
 ## Add the private key into the ssh-agent
 
1. Start ssh-agent

 `eval $(ssh-agent -s)`
 
1. Add your private key

  `ssh-add ~/.ssh/xxx_rsa`
  
 
