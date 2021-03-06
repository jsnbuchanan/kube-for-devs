# ConfigMaps

## Commands

#### From file
Loading variables from a file with `--from-file=[path]`
```
kubectl create configmap [config-map-name]  --from-file=[path-to-file]
```

---

#### From an *"environment"* variable file
Loading variables from an *"environment"* variable file with `--from-env-file=[path]`

File `alien.properties`:
```
enemies=aliens
lives=3
enemies.cheat=true
enemies.cheat.level=noGoodRotten
```

Command:
```
kubectl create configmap [config-map-name] --from-env-file=alien.properties
```

---

#### Directly from the comman-line with --from-literal
An example of loading variables directly from the `kubectl create` command with `--from-literal`

```
kubectl create configmap [config-map-name] --from-literal=keyName1=someValue --from-literal=anyKeyName=anyValue
```

---

#### Directly in the ConfigMap.yml

File `config-map.yml`:
```
apiVersion: v1
kind: ConfigMap
data:
    enemies=aliens
    lives=3
    enemies.cheat=true
    enemies.cheat.level=noGoodRotten
```

