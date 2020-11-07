# solana_exporter

solana_exporter exports basic monitoring data from a Solana node.

<img src="https://i.imgur.com/Ue36pLd.png" width="595px" alt="" />

Docker images are available on [Docker Hub](https://hub.docker.com/r/certusone/solana_exporter). \

Run the exporter: `sudo docker run -d -e SOLANA_RPC_ADDR=http://127.0.0.1:8899 -e LISTEN_ADDR=:9101 --net host --name solana_exporter certusone/solana_exporter` \
You can change `SOLANA_RPC_ADDR` and `LISTEN_ADDR` to values you want.

## Metrics

- **solana_validator_root_slot** - Latest root seen by each validator.
- **solana_validator_last_vote** - Latest vote by each validator (not necessarily on the majority fork!)
- **solana_validator_delinquent** - Whether node considers each validator to be delinquent.
- **solana_validator_activated_stake**  - Active stake for each validator. 
- **solana_active_validators** - Total number of active/delinquent validators.

## Environment variables

| Variable          | Description             |
|-------------------|-------------------------|
| `SOLANA_RPC_ADDR` | Your node's RPC URL     | 
| `LISTEN_ADDR`     | Exporter's Listen Addr  |
