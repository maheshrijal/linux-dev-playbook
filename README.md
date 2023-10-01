# Linux Development Playbook

This Ansible playbook automates the setup and configuration of Linux and WSL (Windows Subsystem for Linux) for development purposes.

## Getting Started

### Running Locally

To use this playbook, follow the steps below:

1. Clone the repository:

   ```bash
   git clone https://github.com/maheshrjl/linux-dev-playbook.git
   ```

2. Change into the project directory:

   ```bash
   cd linux-dev-playbook
   ```

3. Run the playbook:

   ```bash
   ansible-playbook local.yml -K
   ```

### Running on a Remote Machine

To run the playbook directly on a remote machine, you can use the `ansible-pull command`. **Variables from [vars/main.yml](https://github.com/maheshrjl/linux-dev-playbook/blob/main/vars/main.yml) will be applied by default.**

```
ansible-pull -U https://github.com/maheshrjl/linux-dev-playbook.git -K
```

`ansible-pull` must be present in path for this to work. All ansible binaries can be install with this [shell script](https://github.com/maheshrjl/shell-scripts).

## Features

### Tools Installed

The playbook installs the following tools with package manager: curl, wget, unzip, vim, python3, python3-pip, htop, build-essential, lsof, tar, jq, git, tree, bind9-dnsutils, tmux, gpg

The following tools are also installed:

- **AWS CLI V2**: Latest version of the AWS Command Line Interface.
- **Terraform**: Latest version of the Terraform
- **Go**: Latest version of the Go programming language.
- **NodeJS 18.x**: Node.js JavaScript runtime with npm (version can be changed in `vars/main.yml`).

### SSH Key Setup

The playbook automates the following SSH key setup tasks:

- Generates an SSH key pair.
- Adds the private key to the ssh-agent for secure key-based authentication.
- Outputs the public key to the console for easy copying.

## Contributing

Contributions are welcome! If you have any suggestions or improvements for this playbook, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
