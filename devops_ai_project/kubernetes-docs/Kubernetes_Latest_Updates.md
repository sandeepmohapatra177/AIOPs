# Kubernetes Latest Updates
## Executive Summary
The latest release of Kubernetes includes significant updates to networking, API server functionality, controller manager performance, and scheduler configuration. Key highlights include new network policies for private clusters with no internet access and enhanced network management.
## Latest Stable Version:v1.24
## Release Date: March 17, 2023
## Release Highlights:
* [Networking]
	+ New network policies for private clusters with no internet access
	+ Enhanced network management for clusters with multiple hosts
* [API Server]
	+ Support for JSON encoded query parameters in API requests
	+ Enhanced API request logging
* [Controller Manager]
	+ Support for Windows server as the underlying OS for container runtime
	+ Enhanced controller manager performance improvement
* [Scheduler]
	+ New --allocatable-resource-preempt option
	+ Performance improvements
## New Features:
* [API Server]
	+ Support for JSON encoded query parameters in API requests
	+ Enhanced API request logging
* [Controller Manager]
	+ Support for Windows server as the underlying OS for container runtime
	+ Enhanced controller manager performance improvement
* [Scheduler]
	+ New --allocatable-resource-preempt option
	+ Performance improvements
## Deprecated APIs:
* [Node] - This API has been deprecated since version 1.23.
## Security Updates:
* Vulnerability fixed in etcd v3.17.2 for key-value store buffer overflow vulnerabilities. Only for users of Kubernetes as etcd is no longer present in the control plane.
## Bug Fixes:
* Bug fixes in Kubernetes, including various improvements for stability and performance
## Upgrade Recommendations: See Kubernetes Upgrade Guide.
## Official Documentation
See [official documentation](https://kubernetes.io/docs/concepts/configuration/map-configuration/#kubernetes-default-location-v1/) and more resources at https://kubernetes.io/