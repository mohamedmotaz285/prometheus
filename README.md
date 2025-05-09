curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash


helm repo add prometheus-community https://prometheus-community.github.io/helm-charts


helm repo update


kubectl create namespace monitoring


helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring
ده هينزل: -Prometheus-Grafana-Alertmanager-Node Exporter-kube-state-metrics-cAdvisor كلهم بيشتغلوا مع بعض وبيكتشفوا الـ nodes والـ pods بشكل تلقائي


kubectl get all -n monitoring


kubectl port-forward -n monitoring svc/prometheus-stack-grafana 3000:80



http://localhost:3000
