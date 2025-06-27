# ctrl-charts
helm charts of dolphin-operator

## execcution command
helm repo add dolphin-operator https://ccfish2.github.io/charts/dolphin-operator/
helm repo update
helm install dolphin-operator dolphin-operator/dolphin-operator --namespace dolphin --create-namespace
helm upgrade --install dolphin-operator dolphin-operator/dolphin-operator -f values.yaml --namespace dolphin --create-namespace

helm upgrade dolphin-operator ./dolphin-operator \
  --set enableGatewayApi=false \
  --set logController.enabled=false \
  --set logController.s3bucket="s3://new-bucket" \
  --namespace dolphin

