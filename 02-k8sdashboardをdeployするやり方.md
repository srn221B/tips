- deploy
  - kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
- dashboardのsvcを以下に変更しreplace --force
```
apiVersion: v1
kind: Service
metadata:
  labels:
    k8s-app: kubernetes-dashboard
  name: kubernetes-dashboard
  namespace: kubernetes-dashboard
spec:
  ports:
  - port: 443
    protocol: TCP
    targetPort: 8443
  selector:
    k8s-app: kubernetes-dashboard
  type: NodePort
```
- dashboardにログインするためのtokenを作る
  - k create sa -n kubernetes-dashboard admin-user
  - k create clusterrolebinding kubernetes-dashboard-admin --serviceaccount=kubernetes-dashboard:admin-user --clusterrole=cluster-admin
  - k describe secret -n kubernetes-dashboard admin-user-token-xnsxq   | grep token: | awk '{print $2}'
- 
