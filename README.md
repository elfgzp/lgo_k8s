# lgo k8s yaml

```bash
kubectl apply -f https://raw.githubusercontent.com/elfgzp/lgo_k8s/main/all.yaml
```

# Alias

## zsh
```bash
cat <<\EOF >>~/.zshrc 
alias lgo="kubectl exec -it -n lgo $(kubectl get po -n lgo -l app=lgo -o jsonpath="{.items[0].metadata.name}") -- jupyter console --kernel lgo"
alias lgoget='f() {echo lgo get "$@";kubectl exec -it -n lgo $(kubectl get po -n lgo -l app=lgo -o jsonpath="{.items[0].metadata.name}") -- /usr/local/go/bin/go get -u "$@"};f'
EOF
. ~/.zshrc
```


## bash
```bash
cat <<\EOF >>~/.bashrc 
alias lgo="kubectl exec -it -n lgo $(kubectl get po -n lgo -l app=lgo -o jsonpath="{.items[0].metadata.name}") -- jupyter console --kernel lgo"
alias lgoget='f() {echo lgo get "$@";kubectl exec -it -n lgo $(kubectl get po -n lgo -l app=lgo -o jsonpath="{.items[0].metadata.name}") -- /usr/local/go/bin/go get -u "$@"};f'
EOF
. ~/.bashrc
```
