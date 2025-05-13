### Apply all files in curr dir

k apply -f .

### Backend docker

docker buildx build --platform linux/amd64 -t vladstanciu/blogmates-backend:0.0.2 --push .

### Test via port forward
k port-forward blogmates-backend-597fbfbb7d-p7q6z 8080:8000

### Logs
k logs blogmates-backend-597fbfbb7d-p7q6z | cat

### Ingress
k get ingress

curl http://e7fe08b1-0bf7-4de8-aa42-87a3dbd3f3fe.nodes.k8s.pl-waw.scw.cloud

###
kubectl exec -it blogmates-backend-5dd5698cd-l54xx -- python3 manage.py migrate
kubectl exec -it blogmates-backend-5dd5698cd-22r4z -- python3 manage.py showmigrations            