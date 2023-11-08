# SonarQube docker-compose
* SonarQube docker-compose custom by [phamquiduong](https://github.com/phamquiduong)

<br>

# Introduction
* [SonarQube Official website](https://www.sonarsource.com/products/sonarqube/)

* [SonarQube Scanner](https://docs.sonarsource.com/sonarqube/9.9/analyzing-source-code/scanners/sonarscanner/)

### Docker Image

* [SonarQube Docker image](https://hub.docker.com/_/sonarqube)

<br>

# Copy environment file
#### Copy `.env.example` file to `.env`
#### Using command line
```bash
cp .env.example .env
```

<br>

# Install Docker and Docker compose
### Windows and Mac OS
- Visit [Docker Official Website](https://www.docker.com/) and download and install latest version

### Ubuntu OS
- Follow the [documentation to install docker-compose in docker official website](https://docs.docker.com/engine/install/ubuntu/)

- Uninstall old versions
    ```bash
    for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
    ```

- Install using the apt repository
    - Add Docker's official GPG key:
        ```bash
        sudo apt-get update
        sudo apt-get install ca-certificates curl gnupg
        sudo install -m 0755 -d /etc/apt/keyrings
        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
        sudo chmod a+r /etc/apt/keyrings/docker.gpg
        ```

    - Add the repository to Apt sources:
        ```bash
        echo \
        "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
        "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
        sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
        ```

    - Update your system's repository list by entering the following command
        ```bash
        sudo apt update
        ```

- Install the Docker packages.
    ```bash
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    ```

<br>

# Build and start docker-compose
- Build docker-compose
    ```bash
    docker-compose build
    ```

- Up docker-compose
    ```bash
    docker-compose up
    ```
    > [!NOTE]
    > Using `-d` option for run docker-compose in the background <br>
    > Using `--build` option for build and up docker-compose

- Down docker-compose
    ```bash
    docker-compose down
    ```

<br>

# Using SonarQube
* Visit `http://localhost:[PORT]`
    > [!NOTE]
    > `[PORT]` is set up in [.env file](#copy-environment-file)

* Default login account
    > **Login**: admin <br>
    > **Password**: admin

* In the first login website require you change the password

<br>

# Project structure
```
sonarqube
├─ 📁sonarqube_data             # SonarQube data
├─ 📁sonarqube_extensions       # SonarQube extensions
├─ 📁sonarqube_logs             # SonarQube logs
├─ 📄.env.example               # Environment example
└─ 📄docker-compose.yml         # Docker compose
```

<br>

# Thank you so much
