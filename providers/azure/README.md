gcloud container clusters create lab-cluster --num-nodes=3

helm install crossplane \
--namespace crossplane-system \
--create-namespace crossplane-stable/crossplane

cat <<EOF | kubectl apply -f -
apiVersion: pkg.crossplane.io/v1
kind: Provider
metadata:
  name: upbound-provider-azure
spec:
  package: xpkg.upbound.io/upbound/provider-azure:v0.29.0
EOF

