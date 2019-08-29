# broker metrics explained

## brokers online

`count(kafka_server_replicamanager_leadercount)`

Set the thresholds depending on your cluster size

## active controller count

sum(kafka_controller_kafkacontroller_activecontrollercount)

## unclean leader election rate

Unclean leader elections are an extreme measure to ensure availability at the cost of data consistency. Any value >0 is risky.

`sum(kafka_controller_controllerstats_uncleanleaderelections_total)`

## underreplicated partitoins
