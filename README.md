## NAME
   lncli - control plane for your Lightning Network Daemon (lnd)

## USAGE
   lncli [global options] command [command options] [arguments...]
   
## VERSION
   0.15.2-beta commit=v0.15.2-beta
   
## COMMANDS
|command|description|
| --- | --- |
|getinfo |Returns basic information related to the active daemon.|
|getrecoveryinfo |Display information about an ongoing recovery attempt.|
|debuglevel |Set the debug level.|
|stop |Stop and shutdown the daemon.|
|version |Display lncli and lnd version info.|
|sendcustom|
|subscribecustom|
|help, h|Shows a list of commands or help for one command|

#### Autopilot
|command|description|
| --- | --- |
|autopilot |Interact with a running autopilot|

#### Channels
|command|description|
| --- | --- |
|openchannel |Open a channel to a node or an existing peer.|
|batchopenchannel |Open multiple channels to existing peers in a single transaction.|
|closechannel |Close an existing channel.|
|closeallchannels |Close all existing channels.|
|abandonchannel |Abandons an existing channel.|
|channelbalance |Returns the sum of the total available channel balance across all open channels.|
|pendingchannels |Display information pertaining to pending channels.|
|listchannels |List all open channels.|
|closedchannels |List all closed channels.|
|getnetworkinfo |Get statistical information about the current state of the network.|
|feereport |Display the current fee policies of all active channels.|
|updatechanpolicy |Update the channel policy for all channels, or a single channel.|
|exportchanbackup |Obtain a static channel back up for a selected channels, or all known channels|
|verifychanbackup |Verify an existing channel backup|
|restorechanbackup |Restore an existing single or multi-channel static channel backup.|
|listaliases |List all aliases.|
|updatechanstatus |Set the status of an existing channel on the network.|

#### Graph
|command|description|
| --- | --- |
|describegraph |Describe the network graph.|
|getnodemetrics |Get node metrics.|
|getchaninfo |Get the state of a channel.|
|getnodeinfo |Get information on a specific node.|

#### Invoices
|command|description|
| --- | --- |
|addinvoice |Add a new invoice.|
|lookupinvoice |Lookup an existing invoice by its payment hash.|
|listinvoices |List all invoices currently stored within the database. Any active debug invoices are ignored.|
|decodepayreq |Decode a payment request.|
|cancelinvoice |Cancels a (hold) invoice.|
|addholdinvoice |Add a new hold invoice.|
|settleinvoice |Reveal a preimage and use it to settle the corresponding invoice.|

#### Macaroons
|command|description|
| --- | --- |
|bakemacaroon |Bakes a new macaroon with the provided list of permissions and restrictions|
|listmacaroonids |List all macaroons root key IDs in use.|
|deletemacaroonid |Delete a specific macaroon ID.|
|listpermissions |Lists all RPC method URIs and the macaroon permissions they require to be invoked.|
|printmacaroon |Print the content of a macaroon in a human readable format.|
|constrainmacaroon |Adds one or more restriction(s) to an existing macaroon|

#### Mission Control
querymc    Query the internal mission control state.
queryprob  Estimate a success probability.
resetmc    Reset internal mission control state.
getmccfg   Display mission control's config.
setmccfg   Set mission control's config.

#### Neutrino
     neutrino  Interact with a running neutrino instance.

#### On-chain
|command|description|
| --- | --- |
|estimatefee |Get fee estimates for sending bitcoin on-chain to multiple addresses.|
|sendmany |Send bitcoin on-chain to multiple addresses.|
|sendcoins |Send bitcoin on-chain to an address.|
|listunspent |List utxos available for spending.|
|listchaintxns |List transactions from the wallet.|

#### Payments
|command|description|
| --- | --- |
|sendpayment |Send a payment over lightning.|
|payinvoice |Pay an invoice over lightning.|
|sendtoroute |Send a payment over a predefined route.|
|listpayments |List all outgoing payments.|
|queryroutes |Query a route to a destination.|
|fwdinghistory |Query the history of all forwarded HTLCs.|
     trackpayment    Track progress of an existing payment.
     deletepayments  Delete a single or multiple payments from the database.
     importmc        Import a result to the internal mission control state.
     buildroute      Build a route from a list of hop pubkeys.


#### Peers
|command|description|
| --- | --- |
|connect |Connect to a remote lnd peer.|
|disconnect |Disconnect a remote lnd peer identified by public key.|
|listpeers |List all active, currently connected peers.|
     peers       Interacts with the other nodes of the newtwork

#### Profiles
profile  Create and manage lncli profiles.


#### Startup
|command|description|
| --- | --- |
|create |Initialize a wallet when starting lnd for the first time.|
     createwatchonly  Initialize a watch-only wallet after starting lnd for the first time.
|unlock |Unlock an encrypted wallet at startup.|
|changepassword |Change an encrypted wallet's password at startup.|
     state            Get the current state of the wallet and RPC


#### Wallet
|command|description|
| --- | --- |
|newaddress |Generates a new address.|
|walletbalance |Compute and display the wallet's current balance.|
|signmessage |Sign a message with the node's private key.|
|verifymessage |Verify a message signed with the signature.|
     wallet         Interact with the wallet.


#### Watchtower
|command|description|
| --- | --- |
     tower     Interact with the watchtower.
|wtclient |Interact with the watchtower client.|

## GLOBAL OPTIONS
|option|description|
| --- | --- |
|--rpcserver value        |host:port of ln daemon (default: "localhost:10009")|
|--lnddir value           |path to lnd's base directory (default: "/home/tomosaigon/.lnd")|
   --socksproxy value         The host:port of a SOCKS proxy through which all connections to the LN daemon will be established over.
|--tlscertpath value      |path to TLS certificate (default: "/home/tomosaigon/.lnd/tls.cert")|
|--chain value, -c value  |the chain lnd is running on e.g. bitcoin (default: "bitcoin")|
|--network value, -n value|the network lnd is running on e.g. mainnet, testnet, etc. (default: "mainnet")|
|--no-macaroons           |disable macaroon authentication|
|--macaroonpath value     |path to macaroon file|
|--macaroontimeout value  |anti-replay macaroon validity time in seconds (default: 60)|
|--macaroonip value       |if set, lock macaroon to specific IP address|
|--profile value, -p value |Instead of reading settings from command line parameters or using the default profile, use a specific profile. If a default profile is set, this flag can be set to an empty string to disable reading values from the profiles file.|
|--macfromjar value       |Use this macaroon from the profile's macaroon jar instead of the default one. Can only be used if profiles are defined.|
|--help, -h               |show help|
|--version, -v            |print the version|
   
