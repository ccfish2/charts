# ctrl-charts
helm charts of dolphin-operator
## execcution command
helm install dolphin-operator ./dolphin-operator --namespace dolphin --create-namespace

helm upgrade dolphin-operator ./dolphin-operator \
  --set enableGatewayApi=false \
  --set logController.enabled=false \
  --set logController.s3bucket="s3://new-bucket" \
  --namespace dolphin

