# Welcome to Onchain Analytics Tutorial
This is a simple demo of connecting to Ethereum mainnet and monitoring the transactions using ChainStack

You will need a CHAINSTACK execution client https endpoint to run it.  See below for more details.

# Installation
1. Create a venv folder for all dependencies
`python -m venv "venv"`
2. Activate it 
`source venv/bin/activate`  (linux/mac)
`./venv/scripts/activate`   (Windows)
3. Install the dependencies 
`python -m pip install -r requirements.txt`
4. Update the ChainStack Https Endpoint address in conf.py (see below)
5. Run it
`python monitor.py`
6. Results will be displayed on screen and logged into pending_transactions.log

# Get a ChainStack execution client https endpoint
1. Register a free account on ChainStack
2. Create a project, select 'Ethereum Mainnet'
3. Open the node, find 'Access and Credentials' session, and find the https link to the end point


# Error Handling

The filter will expire after a few minutes. As a hack, in monitor.py, when an exception with the message 'filter not found' is caught, the filter is renewed. 

The exception looks like this
`An RPC error was returned by the node. Check the message provided in the error and any available logs for more information.
web3.exceptions.Web3RPCError: {'code': -32000, 'message': 'filter not found'}
`

For more information, refer to this discussion on [stackexchange](https://ethereum.stackexchange.com/questions/112467/web3-py-filter-not-found)
