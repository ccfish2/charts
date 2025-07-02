# controller-charts
helm charts of dolphin-operator

# how to update
cd dolphin-operator

helm package .

mv dolphin-operator-0.1.0.tgz ../docs/dolphin-operator/

helm repo index ../docs/dolphin-operator --url https://ccfish2.github.io/charts/dolphin-operator

cd ..

git add docs/dolphin-operator/

git commit -m "Fix: add service.port to values.yaml"

git push origin

# often used command
helm repo add dolphin-operator https://ccfish2.github.io/charts/dolphin-operator/

helm repo update

helm install dolphin-operator dolphin-operator/dolphin-operator --namespace dolphin --create-namespace

helm upgrade --install dolphin-operator dolphin-operator/dolphin-operator -f values.yaml --namespace dolphin --create-namespace

helm uninstall dolphin-operator dolphin-operator/dolphin-operator -n dolphin

helm upgrade dolphin-operator ./dolphin-operator \
  --set enableGatewayApi=false \
  --set logController.enabled=false \
  --set logController.s3bucket="s3://new-bucket" \
  --namespace dolphin

