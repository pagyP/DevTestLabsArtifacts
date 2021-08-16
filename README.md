# DevTestLabsArtifacts

A domain join artifact, which is based on https://github.com/RogerBestMsft/DTL-SecureArtifactData but strips out some unneeded stuff

An artifact to add a VM data disk and format the disk at deployment time.  

Use user assigned managed identities for the above artifacts to work https://docs.microsoft.com/en-us/azure/devtest-labs/enable-managed-identities-lab-vms 

The domain join artifact gets the relevant creds from an Azure keyvault.  Relevant access policy will need to be in place on the KV for the VM managed identity to read the secrets https://docs.microsoft.com/en-us/azure/key-vault/general/assign-access-policy-portal

If you have all the resources for devtest labs contained in a single resource group https://docs.microsoft.com/en-us/azure/devtest-labs/resource-group-control you will need the following permissions set for the VM user managed identity on that RG:
Contributor
Managed Identity Operator
