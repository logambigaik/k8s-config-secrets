# kubectl apply -f config.yml
# kubectl apply -f deploy.yml

![image](https://user-images.githubusercontent.com/54719289/115082929-94c8c700-9efe-11eb-81b3-0123d67c7eb4.png)

# Error due to field name mismatch, specified user field as user in deploy and in config as username.

# kubectl describe pods
![image](https://user-images.githubusercontent.com/54719289/115083227-f852f480-9efe-11eb-80e4-366c44a2b578.png)

# CrashLoopBackoff error:

![image](https://user-images.githubusercontent.com/54719289/115083357-1fa9c180-9eff-11eb-872a-2421e95e36e0.png)

![image](https://user-images.githubusercontent.com/54719289/115083635-9a72dc80-9eff-11eb-8ca1-dfa1a331e26d.png)

# To check the logs : 
          kubectl logs mysql-6c68786968-99lts

![image](https://user-images.githubusercontent.com/54719289/115084752-34875480-9f01-11eb-8a79-7a577f0891a0.png)
# The problem is with MYSQL_ROOT_PASSWORD(missed in deploy.yml) hence its failed.

![image](https://user-images.githubusercontent.com/54719289/115085010-a19aea00-9f01-11eb-9453-46fcf6234e2b.png)

# kubectl exec -it mysql-85d684b559-c2cfl /bin/bash

