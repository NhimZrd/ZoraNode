![image](https://github.com/Mozgiii9/Zora/assets/74683169/10457959-a93a-48e2-b36b-b106040ca546)

## Zora

## This guide provides an overview of the Zora project, as well as detailed instructions on how to set up a node in the project.

**Zora** is a Layer-2 solution on Ethereum and the NFT Marketplace. They also provide various SDKs for developers.

**Invested: $60,000,000**

**Investors: Paradigm, Coinbase Ventures and others**.

## Server Specifications:

- **CPU: 4-6 cores;**
- **RAM: 16 GB:**
- **Storage: 200 GB SSD;**
- **OS: Ubuntu 22.04**

## Convenient [service](https://ru.hostings.info/hostings/filter_page#vps) for choosing the right hosting ##

## Instructions for installing node:

**1. Go to [Alchemy](https://www.alchemy.com/), register an account if you haven't done it before. Create a new app by clicking Create new app.**

![image](https://github.com/Mozgiii9/Zora/assets/74683169/098d3ab4-ba4c-4dd3-bf02-ac6f2fca6a36)

**2. In the Name field specify Zora, it is not necessary to add a description. Leave Chain and Network as Ethereum and Ethereum Mainnet respectively.**

![image](https://github.com/Mozgiii9/Zora/assets/74683169/fc74b1d5-1a85-4d22-bffc-3f644de66cf3)

**3. After the application has been successfully created, go to the server. Let's perform a package update:**

```bash

sudo apt-get update && sudo apt-get upgrade -y

```

**4. Install the necessary software to run the node:**

```bash

sudo apt install curl build-essential git screen jq pkg-config libssl-dev libclang-dev ca-certificates gnupg lsb-release -y

```

**5.Separately install Docker on the server. Execute the commands one by one:**

```bash

sudo mkdir -p /etc/apt/keyrings

```

```bash

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

```

```bash

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```

```bash

sudo chmod a+r /etc/apt/keyrings/docker.gpg

```

**6. Еще раз обновим пакеты:**

```bash

sudo apt-get update

```

```bash

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose

```

**7. Download Zora software:**

```bash

git clone https://github.com/conduitxyz/node.git

```

![image](https://github.com/Mozgiii9/Zora/assets/74683169/cccb3d77-af4b-460c-a905-a4e002c927f6)


**8. Go to the Zora folder:**

```bash

cd node

```

**9. Initialize the folder **

```bash

./download-config.py zora-mainnet-0

```

![image](https://github.com/Mozgiii9/Zora/assets/74683169/5590ff98-d0ff-4ca4-bed7-5b3a28c26614)

**10.**

```bash

export CONDUIT_NETWORK=zora-mainnet-0

```

**11. Go to edit the file with API keys:**

```bash

cp .env.example .env

```

**12. Open the text file:**

```bash

nano .env

```

**13. Copy from Alchemy API key application.**

![image](https://github.com/Mozgiii9/Zora/assets/74683169/8a74f9c4-74b7-4f67-af1e-6c5735731a37)

**14. Navigate back to the file. Replace the value of "OP_NODE_L1_ETH_RPC" with the previously copied API key. In "OP_NODE_L1_BEACON", paste the link from the example:**

```

# [recommended] replace with your preferred L1 (Ethereum, not Conduit) node RPC URL:
OP_NODE_L1_ETH_RPC=<HTTP://...> <- Your API key
OP_NODE_L1_BEACON=https://beaconstate.info/ <- Fill in this field as in the example.

```

![image](https://github.com/Mozgiii9/Zora/assets/74683169/acb41df1-3bde-4bef-9f1a-efe764b37a66)


**14. Save the file by pressing CTRL+X, followed by Y and then Enter.**

**15. Run the node with the command:**

```bash

docker compose up --build -d

```

![image](https://github.com/Mozgiii9/Zora/assets/74683169/397ddef3-29a5-444e-9134-f73293f21f59)


** Wait for the containers to be prepared **

**16. You can check the logs with the command:**

```bash

docker logs -f node-op-node-1

```

![image](https://github.com/Mozgiii9/Zora/assets/74683169/26e5895b-b35e-416f-baf3-58015dccc94c)

** Your Alchemy profile will display the node's uptime information**
