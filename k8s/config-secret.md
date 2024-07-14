kubectl create secret docker-registry gcr-json-key --docker-server=europe-west9-docker.pkg.dev --docker-username=_json_key --docker-password="$(cat /Users/youneskabiri/Desktop/Nest/products-launcher/k8s/microservices-shop-nestjs-53a989cc6293.json)" --docker-email=kabiriyounes76@gmail.com 



kubectl patch serviceaccount default -p '{"imagePullSecrets":[{"name":"gcr-json-key"}]}'

kubectl rollout restart deployment


kubectl get pods


kubectl describe pod client-gateway-765f8bb965-q27kn


kubectl logs client-gateway-765f8bb965-q27kn