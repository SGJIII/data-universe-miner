# Chat GPT Prompt

You are an ML engineer. Your job is to tell me what to do to set up a high performing Bittensor miner on this subnet: https://github.com/RusticLuftig/data-universe Please read the Bittensor repo https://github.com/opentensor/bittensor and the subnet repo https://github.com/RusticLuftig/data-universe and familiarize yourself with Bittensor by reading this website: https://docs.taostats.io/Glossary.html Then please give me a high level strategy for setting up a high performing Miner on the pretraining subnet. I'd prefer to rent GPUs and pay as I go than buy a machine.  Please optimize for cost as I have a low startup capital. 

Ok as an expert ML engineer your job is to help me execute this by telling me exactly what to do.

I just ran the command to see all the possible flags but it had to be done while bittesnor was activated fyi. Now I want to customize the miner. 

Use askthecode to read https://github.com/RusticLuftig/data-universe/blob/main/docs/miner.md#miner_setup then tell me how to create the best possible miner

(base) samjohnson@Sams-MacBook-Pro data-universe % python ./neurons/miner.py -h
╭─────────────────────────────── Traceback (most recent call last) ────────────────────────────────╮
│ /Users/samjohnson/bittensor_miner_SN_13/data-universe/./neurons/miner.py:27 in <module>          │
│                                                                                                  │
│    24 import typing                                                                              │
│    25 import bittensor as bt                                                                     │
│    26 import datetime as dt                                                                      │
│ ❱  27 from common import constants, utils                                                        │
│    28 from common.data import CompressedMinerIndex                                               │
│    29 from common.protocol import GetDataEntityBucket, GetMinerIndex                             │
│    30 from neurons.config import NeuronType                                                      │
╰──────────────────────────────────────────────────────────────────────────────────────────────────╯
ModuleNotFoundError: No module named 'common'
(base) samjohnson@Sams-MacBook-Pro data-universe % conda activate bittensor
(bittensor) samjohnson@Sams-MacBook-Pro data-universe % python ./neurons/miner.py -h
usage: miner.py [-h] [--wallet.name WALLET.NAME] [--wallet.hotkey WALLET.HOTKEY]
                [--wallet.path WALLET.PATH] [--subtensor.network SUBTENSOR.NETWORK]
                [--subtensor.chain_endpoint SUBTENSOR.CHAIN_ENDPOINT]
                [--subtensor._mock SUBTENSOR._MOCK] [--logging.debug] [--logging.trace]
                [--logging.record_log] [--logging.logging_dir LOGGING.LOGGING_DIR]
                [--axon.port AXON.PORT] [--axon.ip AXON.IP]
                [--axon.external_port AXON.EXTERNAL_PORT] [--axon.external_ip AXON.EXTERNAL_IP]
                [--axon.max_workers AXON.MAX_WORKERS] [--netuid NETUID]
                [--neuron.epoch_length NEURON.EPOCH_LENGTH]
                [--neuron.events_retention_size NEURON.EVENTS_RETENTION_SIZE]
                [--neuron.dont_save_events] [--neuron.database_name NEURON.DATABASE_NAME]
                [--neuron.max_database_size_gb_hint NEURON.MAX_DATABASE_SIZE_GB_HINT]
                [--neuron.scraping_config_file NEURON.SCRAPING_CONFIG_FILE] [--config CONFIG]
                [--strict] [--no_version_checking] [--no_prompt]

options:
  -h, --help            show this help message and exit
  --wallet.name WALLET.NAME
                        The name of the wallet to unlock for running bittensor (name mock is
                        reserved for mocking this wallet)
  --wallet.hotkey WALLET.HOTKEY
                        The name of the wallet's hotkey.
  --wallet.path WALLET.PATH
                        The path to your bittensor wallets
  --subtensor.network SUBTENSOR.NETWORK
                        The subtensor network flag. The likely choices are: -- finney (main
                        network) -- test (test network) -- archive (archive network +300 blocks) --
                        local (local running network) If this option is set it overloads
                        subtensor.chain_endpoint with an entry point node from that network.
  --subtensor.chain_endpoint SUBTENSOR.CHAIN_ENDPOINT
                        The subtensor endpoint flag. If set, overrides the --network flag.
  --subtensor._mock SUBTENSOR._MOCK
                        If true, uses a mocked connection to the chain.
  --logging.debug       Turn on bittensor debugging information
  --logging.trace       Turn on bittensor trace level information
  --logging.record_log  Turns on logging to file.
  --logging.logging_dir LOGGING.LOGGING_DIR
                        Logging default root directory.
  --axon.port AXON.PORT
                        The local port this axon endpoint is bound to. i.e. 8091
  --axon.ip AXON.IP     The local ip this axon binds to. ie. [::]
  --axon.external_port AXON.EXTERNAL_PORT
                        The public port this axon broadcasts to the network. i.e. 8091
  --axon.external_ip AXON.EXTERNAL_IP
                        The external ip this axon broadcasts to the network to. ie. [::]
  --axon.max_workers AXON.MAX_WORKERS
                        The maximum number connection handler threads working simultaneously on
                        this endpoint. The grpc server distributes new worker threads to service
                        requests up to this number.
  --netuid NETUID       Subnet netuid
  --neuron.epoch_length NEURON.EPOCH_LENGTH
                        The default epoch length (how often we set weights, measured in 12 second
                        blocks).
  --neuron.events_retention_size NEURON.EVENTS_RETENTION_SIZE
                        Events retention size.
  --neuron.dont_save_events
                        If set, we dont save events to a log file.
  --neuron.database_name NEURON.DATABASE_NAME
                        The name of the database.
  --neuron.max_database_size_gb_hint NEURON.MAX_DATABASE_SIZE_GB_HINT
                        Hint for the size of the database to target in GBs. Expect additional some
                        additional overhead.
  --neuron.scraping_config_file NEURON.SCRAPING_CONFIG_FILE
                        The location of the scraping config JSON file to use
  --config CONFIG       If set, defaults are overridden by passed file.
  --strict              If flagged, config will check that only exact arguments have been set.
  --no_version_checking
                        Set true to stop cli version checking.
  --no_prompt           Set true to stop cli from prompting the user.
