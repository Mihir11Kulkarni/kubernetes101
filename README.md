# kubernetes101
# Explanation of Kubernetes Definitions

## Service Definition (`service.yml`)

- `apiVersion` and `kind` indicate this is a Kubernetes Service resource named "tomcat2."
- Under `metadata`, you define metadata for the Service.
- `spec` defines the Service's specifications.
  - `type` is set to `LoadBalancer`, indicating a LoadBalancer service.
  - `selector` selects Pods with the label `app: tomcat`.
  - `ports` lists the ports to expose:
    - `port` is the external port (80).
    - `protocol` specifies the network protocol (TCP).
    - `targetPort` is the port on the backend Pods (8080).

## Deployment Definition (`deployment.yml`)

- `apiVersion` and `kind` specify a Kubernetes Deployment resource named "tomcat-deployment."
- Under `metadata`, you define metadata for the Deployment.
- `spec` defines the Deployment's specifications.
  - `replicas` is set to 2, creating two identical Pods.
  - `selector` matches Pods controlled by this Deployment based on labels.
  - `template` specifies the Pod template for the Deployment.
    - `metadata` in the template sets labels for the created Pods.
    - `spec` in the template defines the Pod's specification.
      - `containers` lists the containers within the Pod.
        - `name` is the container name.
        - `image` specifies the Docker image.
        - `ports` specifies the container's port (8080).

This Markdown file explains the key components of the provided Kubernetes definitions.

