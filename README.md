# Scan-your-kubernetes-cluster-with-trivy

If you are looking for a comprehensive tool for the security of your Kubernetes cluster, container images, or filesystem, Trivy is the ideal solution. It's a single tool that covers all components.

## 1 - install Trivy in ubuntu
```
sudo apt-get install wget apt-transport-https gnupg lsb-release
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
```
## 2 - Trivy commands
```
1 - trivy k8s --report summary cluster # to scan your kubernetes cluster
2 - trivy k8s -n kube-system Deployment/metrics-server -s CRITICAL # to display critical vulnerability on a specific deployment
3 - trivy k8s cluster --compliance=k8s-cis --report summary # for cis compliance, you can also use nsa compliance
```
