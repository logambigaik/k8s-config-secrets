# SECRETS:

Specify type= Opaque if you do not want validation, which means the secret does not claim to conform to any convention for key names or values.

# secret.yml
![image](https://user-images.githubusercontent.com/54719289/115090059-c2683d00-9f0b-11eb-99ed-b48280aa2c0a.png)

# in deploy.yml
![image](https://user-images.githubusercontent.com/54719289/115089229-b8ddd580-9f09-11eb-956a-5b43ac7c8ebf.png)

# kubectl to run:

      kubectl apply -f config.yml
      kubectl apply -f secret.yml
      kubectl apply -f deploy.yml
      
![image](https://user-images.githubusercontent.com/54719289/115089991-89c86380-9f0b-11eb-9a9e-d322b2a65be4.png)

![image](https://user-images.githubusercontent.com/54719289/115090024-a5cc0500-9f0b-11eb-89b8-8993dcb0bba2.png)
