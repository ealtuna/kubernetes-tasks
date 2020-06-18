ssh -i $(minikube ssh-key) docker@$(minikube ip) -R 9047:10.9.100.85:9047

netstat -an | grep 9047

a=$(ip route get 1 | sed -n 's/^.*src \([0-9.]*\) .*$/\1/p')

curl http://${a}:9047/
