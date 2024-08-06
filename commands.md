mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl apply -f deploy.yaml

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl scale deployment nginx-deployment --replicas=3

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl apply -f service.yaml

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl get pods

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl get pods -o wide
mo_gaber@LAPTOP-9FO64LDT:~/all$ curl 10.42.0.26:80
mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl get svc nginx-service
mo_gaber@LAPTOP-9FO64LDT:~/all$ curl 10.42.9.26:80

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl delete pods -l app=nginx
mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl get pods

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl exec -it nginx-deployment-576c6b7b6-4lfw5 -- /bin/bash
root@nginx-deployment-576c6b7b6-52gb7:/# cat /var/run/nginx.pid
root@nginx-deployment-576c6b7b6-4lfw5:/# kill -9 1
root@nginx-deployment-576c6b7b6-4lfw5:/# exit

mo_gaber@LAPTOP-9FO64LDT:~/all$ kubectl get pods