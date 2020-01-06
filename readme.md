# WordPress Development Environment

The goal of this repository is to provide a starter kit for WordPress development using containers. To do this, we need to be able to run WordPres in a container locally, in test environment, and in production. We should also be able to develop WordPress as a team using source control and use automated build, test, and deploy to quickly deliver changes.

## Docker Compose

Docker Compose created based on <https://pawelgrzybek.com/configure-a-local-wordpress-development-using-docker/>

To start the development environment, run `docker-compose up -d` from the path of the docker-compose file.

To access applications:

* WordPress - <http://localhost:88>
* phpMyAdmin - <http://localhost:8080>

To stop the development environment, run `docker-compose down` from the path of the docker-compose file.

Running the environment for the first time will create folders for plugins and themes and and index.php. This is where development is done and saved to source control.

### AWS Lightsail

We can deploy Docker to AWS Lightsail. If we use a static IP, we can deploy changes to a new instance and point the static IP to it. We can have a static IP and DNS for test and production. This would require seperating the database into a seperate instance or managing storage in a way that the database data is moved to the new instance.

https://www.youtube.com/watch?v=z525kfneC6E - provides an overview of how to deploy Docker to Lightsail.
https://github.com/mikegcoleman/todo - github repo for the above video overview.

## Kubernetes

To run the development environment in Kubernetes, start with <https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/>

To run a budget, cost effective Kubernetes cluster in the cloud, try

* <https://devonblog.com/containers/affordable-kubernetes-cluster/>
* <https://software.danielwatrous.com/kubernetes-on-the-cheap/>

## Challenges

* How to deploy changes.
* How to backup everything before deploying changes.
* How to automate backup and deploy.
