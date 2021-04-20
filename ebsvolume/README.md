# Create Volume  :

      aws ec2 create-volume --region eu-west-2 --availability-zone eu-west-2b --size 10 --volume-type gp2

![image](https://user-images.githubusercontent.com/54719289/115390891-b5cb3980-a1d6-11eb-83ae-d913180e66fe.png)
![image](https://user-images.githubusercontent.com/54719289/115390848-a6e48700-a1d6-11eb-86b4-70cbd1b924fe.png)

       kubectl apply -f pv.yml
       kubectl apply -f pvc.yml
       kubectl apply -f deploy.yml
       kubectl get pods
       
  ![image](https://user-images.githubusercontent.com/54719289/115418674-94c41200-a1f1-11eb-8a4d-6c0bbc638d68.png)


