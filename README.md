# ethgasstation
Adaptive Gas Price Oracle for Ethereum Blockchain

This python script is designed to monitor a local ethereum node (geth, not tested with Parity).  It will record data about pending and mined transactions, including the transactions in your nodes transaction pool.  Its main purpose is to generate adaptive gas price estimates that enable you to know what gas price to use depending on your confirmation time needs. It generates these estimates based on miner policy estimates as well as the number of transactions in the txpool and the gas offered by the transaction.

It also stores transaction data in a mysql database.  Create a user named 'ethgas' password 'station'.  This allows you to run the model_gasprice script to reestimate the regression model used to generate the predictions.

Note:  you need to create a folder 'json' in the parent directory and then a new json file will be written to the folder each block containing the gas price predictions and the prediction table.  The gas price in ethgasAPI is currently in 10gwei units, so divide them by 10 to get in gwei.

usage:  `python3 ethgasstation.py`

requirements: `pip3 install -r requirements.txt`
