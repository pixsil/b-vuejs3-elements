
# for local testing

Here:
```
npm link
```

In project:
```
trap 'npm unlink b-vuejs3-elements' EXIT; npm link b-vuejs3-elements; while true; do sleep 1; done
```

## Others commands

Link
```
npm link b-vuejs3-elements
```

Unlink
```
npm unlink b-vuejs3-elements
```