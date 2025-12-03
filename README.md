**CleanStart Container for Helm**

Official Helm container image optimized for enterprise Kubernetes environments. Includes the Helm package manager for managing Kubernetes applications through charts. Features security-hardened base image, minimal attack surface, and runs as non-root user. Supports both production deployments and development workflows with separate tagged versions. Essential tool for deploying, managing, and upgrading Kubernetes applications.

**Key Features**
* Complete Helm 3 environment for Kubernetes package management
* Non-root user execution (clnstrt) for enhanced security
* Minimal base image with SSL certificate support
* Optimized for cloud-native and CI/CD workflows

**Common Use Cases**
* Managing Kubernetes application deployments
* Creating and packaging Helm charts
* Automating Kubernetes application releases in CI/CD pipelines
* Template rendering and chart validation

**Pull Commands**
Download the runtime container images

```bash
docker pull cleanstart/helm:latest
docker pull cleanstart/helm:latest-dev
```

**Quick Start**
Display Helm version and help

```bash
docker run --rm cleanstart/helm:latest-dev version
docker run --rm cleanstart/helm:latest-dev --help
```

**Create a New Chart**
Generate a new Helm chart

```bash
docker run --rm -v $(pwd)/my-chart:/workspace cleanstart/helm:latest-dev create /workspace/my-app
```

**Interactive Development**
Start interactive session for development

```bash
docker run --rm -it --entrypoint /bin/sh cleanstart/helm:latest-dev
```

**Kubernetes Integration**
Connect to Kubernetes cluster with kubeconfig

```bash
docker run --rm \
  -v ~/.kube:/home/clnstrt/.kube:ro \
  cleanstart/helm:latest-dev list
```

**Best Practices**
* Use specific image tags for production (avoid latest)
* Mount kubeconfig as read-only (:ro) for security
* Run with non-root user (default: clnstrt)
* Use volume mounts for persistent chart data
* Validate charts with lint before deployment

**Architecture Support**

**Multi-Platform Images**

```bash
docker pull --platform linux/amd64 cleanstart/helm:latest
docker pull --platform linux/arm64 cleanstart/helm:latest
```

**
### 
### Resources

- Official Documentation: https://helm.sh/docs/
- View Provenance, Specifications, SBOM, Signature at: https://images.cleanstart.com/images/helm
- Docker Hub: https://hub.docker.com/r/cleanstart/helm
- CleanStart All Images: https://images.cleanstart.com
- CleanStart All Community Images: https://hub.docker.com/u/cleanstart

---

### Vulnerability Disclaimer

CleanStart offers Docker images that include third-party open-source libraries and packages maintained by independent contributors. While CleanStart maintains these images and applies industry-standard security practices, it cannot guarantee the security or integrity of upstream components beyond its control.

Users acknowledge and agree that open-source software may contain undiscovered vulnerabilities or introduce new risks through updates. CleanStart shall not be liable for security issues originating from third-party libraries, including but not limited to zero-day exploits, supply chain attacks, or contributor-introduced risks.

Security remains a shared responsibility: CleanStart provides updated images and guidance where possible, while users are responsible for evaluating deployments and implementing appropriate controls.
