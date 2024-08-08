---

# TypeScript Amplifier: AWS Amplify Gen 2 Starter Template

This repository provides a starter template for AWS Amplify Gen 2 development with TypeScript and React. It includes a bash script (`initialize.bash`) that automates the setup of the necessary tools and configuration for AWS Amplify on a new environment.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Repository Contents](#repository-contents)
3. [Setup Instructions](#setup-instructions)
   - [Copy AWS Credentials](#1-copy-aws-credentials)
   - [Clone the Repository](#2-clone-the-repository)
   - [Run the Initialization Script](#3-run-the-initialization-script)
4. [Script Workflow](#script-workflow)
5. [Verify Installation](#verify-installation)
6. [Start Developing with AWS Amplify](#start-developing-with-aws-amplify)
7. [Troubleshooting](#troubleshooting)
8. [Contributing](#contributing)
9. [License](#license)

## Prerequisites

Before running the setup script, ensure you have the following:

- An **AWS account** with sufficient permissions to create and manage Amplify projects.
- An **existing Amplify app created in the AWS Console** (you'll need the App ID).
- Access to an **Ubuntu** environment (local or EC2 instance) with internet connectivity.

## Repository Contents

- `transfer-aws-configuration.bash`: Script to securely transfer AWS credentials to a remote server [run from your local machine].
- `initialize.bash`: Main script to set up a Gen 2 Amplify project with TypeScript and React.

## Setup Instructions

### 1. Copy AWS Credentials

If using a remote environment, set up the SSH config file and copy AWS credentials using the `transfer-aws-configuration.bash` script:

```bash
bash transfer-aws-configuration.bash
```

### 2. Clone the Repository

Clone this repository to your local machine or remote environment:

```bash
git clone https://github.com/incrementalcapitalist/typescript-amplifier.git
cd typescript-amplifier
```

### 3. Run the Initialization Script

Run the initialization script:

```bash
bash initialize.bash
```

## Script Workflow

When you run the script, it will perform the following actions:

1. **Prompt for Project Details:**
   - You will be asked to enter a name for your AWS Amplify project, the App ID, and the branch name.

2. **System Update and Upgrade:**
   - Updates the package index and performs a full system upgrade (requires sudo).

3. **Install Dependencies:**
   - Installs `unzip` and `curl` if not already installed (requires sudo).

4. **Install AWS CLI:**
   - Downloads and installs the AWS CLI (version 2) if not already installed.

5. **Install Node Version Manager (NVM) and Node.js:**
   - Installs NVM if not already installed.
   - Uses NVM to install the latest version of Node.js and npm.

6. **Install Amplify CLI:**
   - Installs the Amplify CLI globally using npm if not already installed.

7. **Configure AWS CLI and Amplify CLI:**
   - Sets up AWS CLI with your credentials.
   - Configures Amplify CLI for use with your AWS account.

8. **Initialize a New Amplify Gen 2 Project:**
   - Creates a new directory for your project.
   - Initializes a new Amplify Gen 2 project with the provided App ID and branch name.

## Verify Installation

After running the script, verify the installation by checking the versions of the installed tools:

```bash
nvm -v
node -v
npm -v
aws --version
amplify --version
```

## Start Developing with AWS Amplify

Navigate to the newly created Amplify project directory:

```bash
cd your-project-name
npm start
```

Replace `your-project-name` with the name you provided during script execution.


## Script Details

### AWS Credentials Transfer

The `transfer-aws-configuration.bash` script securely copies your local AWS credentials to a remote server.

### Initialize 

The `initialize.bash` script for a Typescript/React Gen 2 Amplify project.


## Troubleshooting

- **AWS CLI or Amplify CLI not recognized**: Ensure that your PATH is correctly set. You can manually add paths to your `.bashrc` or `.bash_profile` if necessary.
- **Permission Denied Errors**: Make sure you are running the script with sufficient permissions (`sudo` may be required for some commands).
- **Script Errors:** If any errors occur during script execution, they will be logged. Review the log for troubleshooting.

## Contributing

If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the GNU General Public License (GPL) v3.0. See the [LICENSE](LICENSE) file for more information.

### Why GPL v3?

The GPL v3 license enforces strong copyleft requirements and ensures that all derivative works of this project remain open source. This license also provides additional protections against patent claims, which aligns with the goal to keep contributions and derivatives freely available and to safeguard the project's integrity and freedom.

---