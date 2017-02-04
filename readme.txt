# steps to setup github
# github token a6e228ed61ba4aa86fe01a183e93081e12ceb906
git clone https://github.com/toddteta/container-service-dotnet-continuous-integration-multi-container.git container-service-dotnet-continuous-integration-multi-container

# steps to setup azure steps
az group create --name myacs-rg --location eastus
az acs create   --resource-group myacs-rg --name myacs --dns-prefix myacs  --ssh-key-value ~/.ssh/id_rsa.pub
az container release create --target-name myacs --target-resource-group myacs-rg --remote-access-token a6e228ed61ba4aa86fe01a183e93081e12ceb906
az container release list --target-name myacs --target-resource-group myacs-rg



#open dc/os
az acs dcos browse -g myacs-rg -n myacs