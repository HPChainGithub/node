# ![image](https://github.com/HPChainGithub/node/assets/90428559/e990b2ac-0458-45f2-bbe4-2ffb0e2b9bbe) 
# HPCHAIN - Decentralized physical infrastructure network (DePIN) 
------------------------------------------------------------------
HPCHAIN is a secure, suistainable and decentralized cloud computing marketplace aimed to connect  

For a high-level overview of the HPchain platform, protocol and tokenomics, check out the whitepaper and website (https://www.hpchain.ai/); 
The main branch contains new features and is under active development; the mainnet/main branch will be realised soon.

Run with Docker

# Requirements

    Install Docker
    Install Postgres
    Create an Infura account
        Click the Projects section and create a new project.
        In the KEYS section you will see a list of different credentials. Under ENDPOINTS tab change the select to Ropsten.
        Underneath this you will have two links. Notice the wss://ropsten.infura.io/ws/v3/... link. You will need this in a second

# Running the Node

    Run cd run-node

    Open the .env file and where ETH_URL=INFURA_ROPSTEN_LINK_HERE is paste your infura link.

    Create $PATH_TO_DIR/polygon-volume directory

    Create $PATH_TO_DIR/polygon-volume/password.txt - Password used within Polygon node for access Add the following:

secret

    Create $PATH_TO_DIR/polygon-volume/apicredentials.txt - Credientials to login into the Polygon UI Add the following:

test@test.tech
chainlinkPassword

    Add shared paths to Docker
        Docker -> Preferences -> Resources -> File Sharing
        Add $PATH_TO_DIR/chainlink-volume
        Add $PATH_TO_POSTGRES_DATA
    Run docker-compose up - This will run our docker-compose.yml and spin up a Postgres/Polygon node instance.
    This will run our Postgres instance but fail when starting the Polygon node because there is no chainlink postgres database created. We can solve this by entering the CLI of our Postgres(pg_chainlink) instance inside Docker.
    Open the Docker dashboard and click on chainlink-ropsten then open the CLI for chainlink-ropsten_database_1.
    Enter the Postgres console by typing: psql -U postgres -h localhost
    Now create the database: CREATE DATABASE chainlink;
    Run docker-compose up once again and your Polygon node should be running as expected.
    Goto: http://localhost:6688 and you will be greeted with a login page.
    Type in the credentials specified in your apicredentials.txt file and boom! You are logged into your locally running Chainlink node.
    You can locate your account address by clicking on the Configuration tab in the top right corner and locating the ACCOUNT_ADDRESS key variable.
    From here you should fund your address LINK and ETH. You can do that by copying your account address and going to the LINK ropsten faucet and ETH ropsten faucet.

# Join the community

https://t.me/hpchain



