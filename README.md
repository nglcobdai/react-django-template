# react-django-template

|                 |                                                                                                                                                                                                                                                                                                      |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **License**     | ![LICENSE](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)                                                                                                                                                                                                                             |
| **Environment** | ![Ubuntu](https://img.shields.io/badge/-Ubuntu_22.04_LTS-fad9c1.svg?logo=ubuntu&style=flat) <br> ![Docker](https://img.shields.io/badge/-Docker_v26.0.2-0055a4.svg?logo=docker&style=flat) ![Docker Compose](https://img.shields.io/badge/-Docker_Compose_v2.22.0-0055a4.svg?logo=docker&style=flat) |
| **Frontend**    | ![React](https://img.shields.io/badge/-React-61DAFB.svg?logo=react&style=flat)                                                                                                                                                                                                                       |
| **Backend**     | ![Python](https://img.shields.io/badge/-Python_3.10-F9DC3E.svg?logo=python&style=flat) ![Poetry](https://img.shields.io/badge/-Poetry-2c2d72.svg?logo=python&style=flat) ![Django](https://img.shields.io/badge/-Django-092E20.svg?logo=django&style=flat)                                           |

## Requirements

- Docker and docker-compose are required. The versions are as follows.
  - Docker: v26.0.2
  - Docker Compose: v2.22.0

## Getting Started

### 1. Clone Repository

```sh
$ git clone git@github.com:nglcobdai/react-django-template.git
$ cd react-django-template
```

### 2. Create .env file

- copy .env.example to .env

```sh
$ cp .env{.example,}
```

### 3. Docker Build & Run

```sh
$ docker-compose run backend django-admin startproject src .
$ docker-compose run --rm frontend sh -c "npm install -g create-react-app && create-react-app frontend"
$ docker-compose build --no-cache
```

### 4. Run Docker

```sh
$ docker-compose up -d
```

### 5. Access to the following URL

- Frontend: [http://localhost:3000](http://localhost:3000)
