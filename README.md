In Kubernetes, admission controllers are components that intercept and potentially modify requests to the Kubernetes API server before they are persisted as objects in the cluster. Admission controllers are crucial for enforcing policies, validating requests, and performing various operations on resources as they are being created, updated, or deleted. 

 Here are some of the different admission controllers available in Kubernetes and their typical use cases:

NamespaceLifecycle:

Ensures that namespaces adhere to predefined lifecycle policies.
Use cases: Enforcing naming conventions, restricting the creation or deletion of namespaces.
LimitRanger:

Enforces resource usage limits for pods and containers.
Use cases: Enforcing CPU and memory limits, preventing resource overallocation.
ServiceAccount:

Automatically injects default service accounts into pods without explicitly defined service accounts.
Use cases: Providing default service accounts to pods for authentication and authorization.
ResourceQuota:

Enforces constraints on resource usage within namespaces.
Use cases: Enforcing resource quotas such as CPU, memory, and storage limits within namespaces.
PodSecurityPolicy:

Enforces security policies on pods, such as restricting privilege escalation and controlling access to host resources.
Use cases: Enforcing security best practices, preventing container breakout.
DefaultStorageClass:

Automatically assigns a default storage class to persistent volume claims (PVCs) that do not specify one.
Use cases: Simplifying PVC creation by automatically selecting a storage class.
MutatingAdmissionWebhook:

Allows external services to modify pod requests before they are persisted.
Use cases: Automatically injecting sidecar containers, applying default annotations.
ValidatingAdmissionWebhook:

Allows external services to validate and potentially reject pod requests based on custom criteria.
Use cases: Enforcing custom validation policies, integrating with external validation services.
CertificateApproval:

Allows external services to approve or deny Certificate Signing Requests (CSRs) for TLS certificates.
Use cases: Automating certificate issuance and approval workflows.

we have Static controllers which are are built into the Kubernetes API server binary and provide general-purpose functionality, while dynamic controllers are external components that offer flexibility and customization through custom logic and external integrations.

Kyverno works in conjunction with Kubernetes' admission control mechanism to enforce policies by intercepting resource requests, evaluating them against policy rules, and taking appropriate actions to ensure compliance before admitting resources into the cluster
