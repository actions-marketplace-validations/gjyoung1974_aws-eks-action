# Hello world docker action

Control your EKS cluster via `kubectl` in a Github Action

## Example

This GitHub Action requires AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY and the AWS_REGION

```yaml
jobs:
  jobName:
    name: Push Latest Container image
    runs-on: ubuntu-latest
    steps:
      - name: Deploy new docker image
        uses: gjyoung1974/aws-eks-kubectl
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_REGION: ${{ secrets.AWS_REGION }}
          KUBE_CONFIG_DATA: ${{ secrets.KUBE_CONFIG_DATA_BASE_64_ENCODED }}
        with:
          args: set image --record deployment/pod-name pod-name=DOCKER_IMAGE_URL
```
2021 - gjyoung1974@gmail.com