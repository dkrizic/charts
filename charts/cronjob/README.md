# Create a cronjob

Example usage. Create a yaml file like this:

```
fullnameOverride: yasm-neo4j-restart
cronjob:
  schedule: '0 0 * * *'
  successfulJobsHistoryLimit: 1
  deployment: yasm-neo4j-core
  command:
    - 'kubectl'
    - 'rollout'
    - 'restart'
    - 'statefulset/yasm-neo4j-core'
```

and install using 

```
helm upgrade --install yasm-neo4j-restart -f yasm-neo4j-restart.yaml dkrizic/cronjob
```

