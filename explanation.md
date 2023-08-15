IP4 Explanation

In this project, I chose to use Kubernetes Deployment objects for managing the deployment of my backend and client services. Deployments are suitable for stateless applications that require scaling and load balancing. However, for the database component, I opted to use StatefulSets. StatefulSets are beneficial for applications like databases where stable network identities and persistent storage are essential. Using StatefulSets ensures that each database pod has a unique identity and maintains its data even when rescheduled.

Method of Exposing Pods to Internet Traffic

To expose my pods to internet traffic, I used Kubernetes Services with the LoadBalancer type. This choice allowed me to expose my applications externally while the LoadBalancer handled traffic distribution across replicas. LoadBalancers provided a straightforward way to manage incoming internet traffic, especially for applications with fluctuating demand.

Use of Persistent Storage

For persistent storage, I employed PersistentVolumeClaims (PVCs) along with PersistentVolumes (PVs) in the case of the database. I created PVCs to request storage resources, and the PVs provided actual storage. This approach enabled data persistence across pod restarts and reschedules. By using PVCs and PVs, I ensured that the database data remained intact even if the underlying pods needed to be recreated.

Git Workflow

Throughout the development process, I followed a structured Git workflow. I used feature branches to work on specific features or fixes, ensuring a clean separation of changes. When a feature was complete, I created pull requests for review. This allowed for collaborative code review and discussions before merging changes into the main branch. Continuous integration was integrated to automatically test changes before merging, ensuring code quality and stability.
Running Applications from GitHub Repository

Initially, I faced some challenges when running the applications from the link provided in the GitHub repository's README.md. Some issues were related to networking and service discovery. To debug this, I used kubectl logs to check container logs and kubectl describe to inspect the status of different resources. I also ensured that the necessary environment variables and configurations were correctly set. After resolving these issues, the applications ran successfully.
Docker Image Tag Naming Standards

To maintain an organized and identifiable set of Docker images and containers, I followed a standard naming convention for tags. Each image had a clear version tag, following the format service-name:version. This made it easy to distinguish different versions of images and containers and simplified the process of deploying specific versions when needed.
