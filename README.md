Overview

Goal/motivation
Technology stack
How it works
Results/achivements/future plans

Goal/Motivation

Full Hadoop stack provisioning - everywhere
Automate and unify the process
Zero-configuration approach
Same process through a cluster lifecycle (Dev, QA, UAT, Prod)
Provide tooling - UI, REST API and CLI/shell
Secure and multi-tenant
SLA policy based autoscaling

Technology stack

Docker
Swarm
Consul
Apache Ambari

Docker

Container based virtualization
Lightweight and portable
Build once, run anywhere
Ease of packaging applications
Automated and scripted
Isolated

Docker - How it works

Containers are isolated, but share OS and, where appropriate, bins/libraries
No need to emulate hardware
Image

Swarm

Native clustering for Docker
Distributed container orchestration
Same API as Docker

Swarm - How it works

Swarm manager/agents
Discovery services
Advanced scheduling


Consul

Service discovery/registry
Health checking
Key/Value store
Multi datacenter aware

Consul - How it works

Consul servers/agents
Consistency through a quorum (RAFT)
Scalability dud to gossip based protocol (SWIM)
Decentralized and fault tolerant
Highly available
Consistency over availability (CP)
Multiple interfaces - HTTP and DNS
Support watches



Apache Ambari

Easy Hadoop cluster provisioning
Management and monitoring
Key feature - Blueprints
REST API, CLI shell

Apache Ambari - How it works

Ambari server/agents
Define a blueprint (blueprint.json)
Define a host mapping (hostmapping.json)
Post the cluster create

Cloudbreak

Image

Cloudbreak

Benefits
  Zero configuration
  Elastic
  Secure
  Infrastructure agnostic
  Heterogenous clusters
  Auto-scaling

Main REST resources

  /template – specify an instance group infrastructure
  /stack – creates an infrastructure based on a template
  /blueprint – describes a Hadoop cluster
  /cluster – creates a Hadoop cluster

Cloudbreak - How it works

  Start VMs - with a running Docker daemon
  Cloudbreak Bootstrap
    Start Consul Cluster
    Start Swarm Cluster  (Consul for discovery)
  Start Ambari servers/agents - Swarm API
  Ambari service gets registered in Consul (Registrator)
  Post Blueprint

Cloudbreak - Features

  Support Kerberized clusters
  Cloudbreak recipes
    - Host configuration
    - Pre/post Ambari lifecycle hooks
    - Services reconfiguration
    - Automate/execute custom actions

Cloudbreak - Hadoop as a Service API

Public tech preview
  Amazon AWS
  Microsoft Azure
  Google Cloud Platform
  OpenStack

Private tech preview
  Bare metal
  Rackspace Managed Cloud
  HP Helion Public Cloud

*integration SPI is available


Periscope

Image

Periscope

Benefits
  Zero configuration
  Metric and time based alarms
  SLA policy based autoscaling
  Secure
  Hostgroup specific


Periscope - How it works

  Configures/monitors alarms in Ambari
  Manages alarm, cooldown periods
  Manages cluster sizes
  Allow to associate SLA scaling policies to alarms
  Instructs Cloudbreak to up/downscale the cluster

Future plans

  Leverage YARN as a datacenter scheduler
  Apache Slider - run any app on YARN
  
