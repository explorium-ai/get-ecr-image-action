# Get Latest ECR Image

Query and get latest ECR image of a specific tag and pull it if needed
<!-- ## Inputs

| Input | Type | Description | Default | Required
| ------ | ------ | ------ | ------ | ------
| install_local_cluster | Boolean (String) | Install a local K3d Cluster | true | Yes -->

## Full Example usage

```yaml
- name: Pull From ECR, Retag and Push
  id: ecr
  uses: explorium-ai/get-ecr-image-action@main
  with:
    AWS_ACCESS_KEY_ID: fadsfads********
    AWS_SECRET_ACCESS_KEY: fadsfads********
    REGION: eu-west-1
    REPOSITORY: my-service
    TAG: latest
    METHOD: contains
    PULL: true
    RETAG: localhost:5000/my-service:github
    PUSH: true
- name: Get Outputs
  run: |
    echo ${{ steps.ecr.outputs.image }}
    echo ${{ steps.ecr.outputs.tag }}  
```