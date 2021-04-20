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




