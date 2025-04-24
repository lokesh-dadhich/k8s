Setting Up the Kubernetes Dashboard
Deploy the Dashboard Apply the Kubernetes Dashboard manifest:

$$kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

Apply the configuration:

$$kubectl apply -f dashboard-admin-user.yml

Get the Access Token Retrieve the token for the admin-user:

$$kubectl -n kubernetes-dashboard create token admin-user

Copy the token for use in the Dashboard login.

Access the Dashboard Start the Dashboard using kubectl proxy:

$$kubectl proxy  // kubectl proxy --port=8001 --address=0.0.0.0 --accept-hosts='.*'

Open the Dashboard in your browser:

$$http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
