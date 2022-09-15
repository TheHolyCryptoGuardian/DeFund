# Commands to install [DeFund node](https://github.com/TheHolyCryptoGuardian/DeFund/blob/main/Node)

`wget -q -O defund.sh https://raw.githubusercontent.com/TheHolyCryptoGuardian/DeFund/main/Node && chmod +x defund.sh && sudo /bin/bash defund.sh` to start installing

`source $HOME/.bash_profile` to set a name

`defundd keys add wallet` to create a wallet

`defundd q bank balances YOUR_WALLET_ADDRESS` to check your balance

`defundd tx staking create-validator \`  
`--amount=1000000ufetf \`      
`--pubkey=$(defundd tendermint show-validator) \`    
`--moniker="$DEFUND_NODENAME" \`    
`--chain-id=defund-private-1 \`  
`--commission-rate="0.10" \`  
`--commission-max-rate="0.20" \`  
`--commission-max-change-rate="0.01" \`  
`--min-self-delegation="1000000" \`  
`--gas="auto" \`  
`--from=wallet  ` to create a validator

`journalctl -u defund -f` to check node logs

`systemctl restart defund` to restart your node

`curl localhost:26657/status` to check your node status

`curl -s localhost:26657/status | jq .result.sync_info.catching_up` to check node synchronization

# DeFund

DeFund allows for the creation of decentralized exchange-traded funds (formally called dETF’s) with underlying assets from dozens and dozens of blockchains (and growing rapidly). Once a dETF is created, any DeFund user can invest in any of the created dETF’s offered.
