Please practice on : https://containerjournal.com/topics/container-networking/using-ebs-and-efs-as-persistent-volume-in-kubernetes/

# First Install kubectl dashboard and run gp2-storageclass.yml

[k8s-Dashboard](https://github.com/logambigaik/kubernetes-dashboard.git)


Before creating storageclass in k8s dashboard,

![image](https://user-images.githubusercontent.com/54719289/116599342-e2422c80-a91f-11eb-8e70-3cee2cc6c3cd.png)

            kubectl create ns ns-awsebs

            kubectl apply -f gps-storageclass.yml
            
            kubectl get storageclasses --all-namespaces
            
![image](https://user-images.githubusercontent.com/54719289/116598217-790de980-a91e-11eb-9f1e-51877ff78838.png)


            kubectl get storageclass -n ns-awsebs
            
 ![image](https://user-images.githubusercontent.com/54719289/116599593-35b47a80-a920-11eb-8eae-9037976d74e9.png)


# After adding storageclass in k8s UI:

![image](https://user-images.githubusercontent.com/54719289/116598326-980c7b80-a91e-11eb-9817-313abf124dbd.png)


# Update gp2 as default storage class:

            kubectl patch storageclass gp2 -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}' --namespace=ns-awsebs
            
![image](https://user-images.githubusercontent.com/54719289/116599941-a065b600-a920-11eb-9803-59d49865b960.png)

# Change the standard storage class -not default :
            
             kubectl patch storageclass standard -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"false"}}}'

![image](https://user-images.githubusercontent.com/54719289/116601885-e58ae780-a922-11eb-9218-80973a016f84.png)


# Create persistent volume claim with gp2 storage class for mysql & wordpree:

            kubectl apply  -f pvc.yml -n ns-awsebs

![image](https://user-images.githubusercontent.com/54719289/116602025-0ce1b480-a923-11eb-85c0-0c0224ab2f6a.png)

            
            
            
            
            
            

# Create Volume  :


      aws ec2 create-volume --region eu-west-2 --availability-zone eu-west-2b --size 10 --volume-type gp2

![image](https://user-images.githubusercontent.com/54719289/115390891-b5cb3980-a1d6-11eb-83ae-d913180e66fe.png)
![image](https://user-images.githubusercontent.com/54719289/115390848-a6e48700-a1d6-11eb-86b4-70cbd1b924fe.png)

       kubectl apply -f pv.yml
       kubectl apply -f pvc.yml
       kubectl apply -f deploy.yml
       kubectl get pods
       
  ![image](https://user-images.githubusercontent.com/54719289/115418674-94c41200-a1f1-11eb-8a4d-6c0bbc638d68.png)
  
      kubectl describe pods
      
  ![image](https://user-images.githubusercontent.com/54719289/115420078-c25d8b00-a1f2-11eb-96b6-9395f00fddd8.png)

      kubectl describe pv pvc -n mysql-template
      
  ![image](https://user-images.githubusercontent.com/54719289/115420379-ff298200-a1f2-11eb-9148-e3b35a792438.png)


      kubectl get svc
      
  ![image](https://user-images.githubusercontent.com/54719289/115420790-56c7ed80-a1f3-11eb-93de-26bb489910ab.png)
  
      kubectl get pv
      
   ![image](https://user-images.githubusercontent.com/54719289/115421125-9c84b600-a1f3-11eb-9116-1efed5269357.png)




