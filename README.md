# Allowing IAM access to only a specific subdomain on Route 53

We are going to create an IAM ploicy for a user to access only spefic subdomains on Route 53.

Suppose you have company(anishababu.tech) with branches in different states(for example: kerala.anishababu.tech, delhi.anishababu.tech) and you have to allow each branch admin to only access to their branch DNS zone. You can setup a IAM user with subdomain zone access privilges.

