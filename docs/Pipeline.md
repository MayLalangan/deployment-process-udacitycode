# Pipeline Process

This project uses **CircleCI** for Continuous Integration and Continuous Deployment (CI/CD). The pipeline is defined in `.circleci/config.yml`.

## Pipeline Workflow
The pipeline consists of the following jobs executing in a logical order:

### 1. Build Job (`build`)
- **Environment**: Node.js v14 docker image.
- **Steps**:
    1. Checkout code from GitHub.
    2. Install Frontend dependencies (`npm install`).
    3. Install Backend dependencies.
    4. Run Frontend Linting (`npm run lint`).
    5. Build Frontend (`npm run build`).
    6. Build Backend (`npm run build`).

### 2. Hold Step (`hold`)
- **Type**: Manual Approval.
- **Purpose**: Pauses the workflow after a successful build to allow manual verification before deployment.

### 3. Deploy Job (`deploy`)
- **Trigger**: Runs only after the `hold` step is approved.
- **Steps**:
    1. Install AWS CLI and Elastic Beanstalk CLI (`eb/setup`, `aws-cli/setup`).
    2. Configure AWS credentials from CircleCI Environment Variables.
    3. **Deploy Frontend**:
        - Runs `npm run deploy` in `udagram-frontend`.
        - Uploads the specific build artifact (`www/`) to the S3 bucket.
    4. **Deploy Backend**:
        - Runs `npm run deploy` in `udagram-api`.
        - Initializes the EB CLI environment.
        - Deploys the application archive to Elastic Beanstalk.

## Secrets Management
- AWS Access Keys and Region are stored as **Environment Variables** in CircleCI Project Settings, ensuring no sensitive credentials are committed to the repository.
