# c-lightning-REST
REST APIs for c-lightning written in Node.js

*IN EARLY STAGES OF DEVELOPMENT. NOT READY FOR PRIME TIME!*

## Pre-requisite
A full node running [c-lightning](https://github.com/ElementsProject/lightning)

APIs will be served over https (a self signed certificate and key will be generated in the certs folder with openssl)
Sample url:
`https://localhost:3001/v1/getinfo/`

## APIs available:
### General Node info
- getinfo (/v1/getinfo) - Get node information
- listfunds (/v1/listFunds) - Returns on-chain funds and channel funds information
- getbalance (/v1/getBalance) - Returns total, confirmed and unconfirmed on-chain balances
- getfees (/v1/getFees) - Returns the routing fee collected by the node
- localremotebal (/v1/localremotebal) - Summarizes local and remote channel balances on the node
### On-Chain fund management
- newaddr (/v1/newaddr) - Generate address for recieving on-chain funds
- withdraw (/v1/withdraw) - Withdraw on-chain funds to an address
### Peer management
- connect (/v1/peer) - Connect with a network peer
- listpeers (/v1/listPeers) - Returns the list of peers connected with the node
### Channel management
- fundchannel (/v1/openChannel) - Open channel with a connected peer node
- getchannels (/v1/getChannels) - Get the list of channels open on the node
- setchannelfee (/v1/setChannelFee) - Update the fee policy for a channel
- close (/v1/closeChannel) - Close channel

### Payments
- pay (/v1/pay) - Pay a bolt11 invoice
- listpays (/v1/pay/listPays) - List result of payment {bolt11}, or all
- listpayments (/v1/pay/listPayments) - List outgoing payments {bolt11}, or all. This api has more detailed output than listpays
- decodepay (/v1/pay/decodePay) - Decode the bolt11 invoice

### Invoice
- invoice (/v1/invoice/genInvoice) - Generates a bolt11 invoice provided amount in msat, label, description, expiry in seconds (optional)
- listinvoices (/v1/invoice/listInvoices) - Lists the invoice on the node, for a {label} or all.
- delexpiredinvoice (v1/invoice/delExpiredInvoice) - Delete expired invoices.

PRs are welcome! :-)