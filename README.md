# NOVA Mission Operations User Interface
The front-end ui for NOVA mission control/operations. This repository is written in the Vue.JS 3 framework. Note: At the time of writing, this repository is incomplete, and should only be used as a testing playground environment.

## Installation

1. **Clone the Repository**

Add an ssh key to Github ([How to add SSH Key to Github ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)).
```
git clone git@github.com:UTATRocketry/nova-ops-ui.git
cd nova-ops-ui
```
2. **Install Dependencies**

You should have yarn, or an equivalent package manager installed first ([Yarn: Installation](https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable)). Then:

```
yarn install
```

## Usage

To start the development server:
```
yarn serve
```
'ws://localhost:8000/ws/pressure/'
This will launch the Vue.JS application on the local development server, usually accessible at `http://localhost:8080`. The server will attempt to create a WebSocket connection at `ws://localhost:8000/ws/pressure/`, and will display, in real-time, the changing pressure value of an example pressure sensor.
