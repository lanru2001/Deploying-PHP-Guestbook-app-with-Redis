## Deploying PHP Guestbook application with Redis

## This project shows you how to build and deploy a simple (not production ready), multi-tier web application using Kubernetes and Docker. 

## This project consists of the following components:

A single-instance Redis to store guestbook entries
Multiple web frontend instances
Objectives
Start up a Redis leader.
Start up two Redis followers.
Start up the guestbook frontend.
Expose and view the Frontend Service.



## Creating the Redis Deployment 
The guestbook application uses Redis to store its data.

## Creating the Redis leader Service 
The guestbook application needs to communicate to the Redis to write its data. You need to apply a Service to proxy the traffic to the Redis Pod. A Service defines a policy to access the Pods.

## Creating the Redis leader Service 
The guestbook application needs to communicate to the Redis to write its data. You need to apply a Service to proxy the traffic to the Redis Pod. A Service defines a policy to access the Pods.

## Set up Redis followers 
Although the Redis leader is a single Pod, you can make it highly available and meet traffic demands by adding a few Redis followers, or replicas.

## Creating the Redis follower service 
The guestbook application needs to communicate with the Redis followers to read data. To make the Redis followers discoverable, you must set up another Service.

## Set up and Expose the Guestbook Frontend 
Now that you have the Redis storage of your guestbook up and running, start the guestbook web servers. Like the Redis followers, the frontend is deployed using a Kubernetes Deployment.

The guestbook app uses a PHP frontend. It is configured to communicate with either the Redis follower or leader Services, depending on whether the request is a read or a write. The frontend exposes a JSON interface, and serves a jQuery-Ajax-based UX.

