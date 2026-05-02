# AWS ECR Notes

## ECR vs DockerHub
| Feature          | DockerHub         | AWS ECR               |
|------------------|-------------------|-----------------------|
| Visibility       | Public/Private    | Private (default)     |
| Auth             | Username/Password | AWS IAM + temp token  |
| Cost             | Free tier limited | Pay per GB stored     |
| Best For         | Open source       | Production AWS apps   |

## Token Expiry
- ECR login token expires every **12 hours**
- Re-authenticate before each push session in CI/CD pipelines

## IAM Setup
Attach this policy to your EC2 IAM Role:
```
AmazonEC2ContainerRegistryFullAccess
```
Or use specific permissions:
- `ecr:GetAuthorizationToken`
- `ecr:BatchCheckLayerAvailability`
- `ecr:InitiateLayerUpload`
- `ecr:PutImage`

## ECR Tag Format
```
<account-id>.dkr.ecr.<region>.amazonaws.com/<repo-name>:<tag>
Example:
123456789012.dkr.ecr.ap-south-1.amazonaws.com/my-app:latest
```
