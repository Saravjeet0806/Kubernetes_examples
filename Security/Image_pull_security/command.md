kubectl create secret docker-registry my-registry-secret \
  --docker-server=registry.example.com \
  --docker-username=my-username \
  --docker-password=my-password \
  --docker-email=my-email@example.com
