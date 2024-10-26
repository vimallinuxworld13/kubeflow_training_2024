# kubeflow_training_2024
eksctl.exe create cluster --name lwcluster2


kubectl describe  cm aws-auth -n kube-system

helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver/
helm repo update
helm install aws-ebs-csi-driver aws-ebs-csi-driver/aws-ebs-csi-driver \
    --namespace kube-system \
    --set enableVolumeScheduling=true \
    --set enableVolumeResizing=true \
    --set enableVolumeSnapshot=true

    
kubectl patch storageclass gp2 -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'



git clone https://github.com/kubeflow/manifests.git

while ! kustomize build example | kubectl apply -f -; do echo "Retrying to apply resources"; sleep 20; done

kubectl port-forward svc/istio-ingressgateway -n istio-system 8080:80

The default username is user@example.com and the password is 12341234
