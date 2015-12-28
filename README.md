= spring-cloud-connector-kubernetes

The http://cloud.spring.io/spring-cloud-connectors/spring-cloud-connectors.html[Spring Cloud Connector project] provides an abstraction to discover services at runtime and register them as Spring beans.  

This project provides support to discover Redis and RabbitMQ servers running on Kubernetes. The mechanism by which it performs the discovery is to look for a Kubernetes service whose name is `redis` or `rabbitmq` along with a label that has a key named `spirng-cloud-service`.  Here is an example taken from the https://github.com/spring-cloud/spring-cloud-dataflow-admin-kubernetes/blob/master/src/etc/kubernetes/redis-service.yml[redis-service.yml] definition used in the Spring Cloud DataFlow Kubernetes getting started project.

----
metadata:
  name: redis
  labels:
    spring-cloud-service: redis
----

A standard https://github.com/kubernetes/kubernetes/blob/master/docs/user-guide/services.md#discovering-services[kubernetes style service discovery mechanism], that does not require the use of labels is an https://github.com/spring-cloud/spring-cloud-dataflow-admin-kubernetes/issues/17[open issue].





