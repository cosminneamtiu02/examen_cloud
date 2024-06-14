## Debugging
🌵 Create a folder called ```debugging```. Add all the screenshots created in the steps below.

- create a namespace called ```awesome``` and another called ```tools```, ex:
```shell
kubectl create namespace awesome
```
- run: ```helm upgrade --install exam .```
- checkout the ```awesome``` namespace

1. 🌵 Count the pods in the exam environment (label ```env=exam```) → screenshot of the used command
2. 🌵 Count the pods in both the exam environment and of type frontend (label ```env=exam``` and ```tier=frontend```) →
   screenshot of the used command

- checkout the ```default``` namespace

3. 🌵 What is the current color of the web application, in the default namespace? (screenshot from the browser)

- Run the script named ```curl-test.sh``` to send multiple requests to test the web application. Take a note of the
  output. Use this script to test the solutions of the exercises below and take screenshots of the results.

4. 🌵 What container image is used to deploy the applications?
5. 🌵 Inspect the deployment and identify the current deployment strategy

- If you were to upgrade the pods now, what would happen?

  a.) All pods are taken down before upgrading any

  b.) pods are upgraded few at a time

6. 🌵 Let us try that. Upgrade the application by setting the image on the deployment to ```kodekloud/webapp-color:v2```.
   Run the script ```curl-test.sh``` again. Notice the requests now hit both the old and newer versions. However, none
   of them fail.

7. 🌵 Change the deployment strategy to ```Recreate```. Delete and re-create the deployment if necessary. Only update the
   strategy type for the existing deployment. Upgrade the application by setting the image on the deployment
   to ```kodekloud/webapp-color:v3```. Run the script ```curl-test.sh``` again. Notice the failures. Wait for the new
   application to be ready. Notice that the requests now do not hit both the versions

## Kubernetes

🌵 Create a folder called ```kubernetes```. Add all the YAML files created in the steps below.

- Create a Pod YAML file with two containers that use the image ```alpine:3.12.0```. Provide a command for both
  containers
  that keep them running forever.
- Define a Volume of type emptyDir for the Pod. ```Container 1``` should mount the Volume to path ```/etc/a```
  and ```container 2``` should mount the Volume to path ```/etc/b```
- Open an interactive shell for container 1 and create the directory ```data``` in the mounth path. Navigate to the
  directory and create the file ```hello.txt``` with the content "Hello World". Exit the container.
- Open an interactive shell for container 2 and navigate to the directory ```/etc/b/data```. Inspect the contents of
  file ```hello.txt```. 🌵 Take a screenshot, add it to the ```kubernetes``` folder. Exit out the container.
