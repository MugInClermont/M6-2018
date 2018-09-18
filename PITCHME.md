---?image=assets/container-3118783_960_720.jpg

<span class="primary-title">
    <span>A Story </span>   
    <span> of containers</span>
</span> 

---

## Why a MUG?

* A cool team of experts |
* Nice conferences and nice subjects |
* A good time together |

Note: 
Présentation Mug / Sujet (Damien - 5min)

---

## Physical Deployment

Note: 
Déploiement Physique (Damien - 5min)

---

## Virtualization
+++

### Virtualization 
#### What is it?
> 	In computing, virtualization refers to the act of creating a virtual (rather than actual) version of something, including virtual computer hardware platforms, storage devices, and computer network resources.
note: Desktop virtualization

+++

### Virtualization 
#### Type-2 or hosted hypervisors
- VMware Workstation 
- Oracle VirtualBox
- Microsoft Windows Virtual PC

note: run on a conventional operating system.A guest operating system runs as a process on the host. Type-2 hypervisors abstract guest operating systems from the host operating system.

+++

### Virtualization 
#### Type-1 / native or bare-metal hypervisors
- VMware ESXi
- Microsoft Hyper-V
- Proxmox

note: run directly on the host's hardware to control the hardware and to manage guest operating systems. sometimes called bare metal hypervisors. The first hypervisors

+++

### Virtualization 
#### Cool features
- P2V |
- Shared resource |
- Snapshot |
- Migration |
- Failover |

Note: 
A snapshot is a state of a virtual machine, and generally its storage devices, at an exact point in time.
The snapshots described above can be moved to another host machine with its own hypervisor
Failover :Similar to the migration mechanism, failover allows the VM to continue operations if the host fails. However, in this case, the VM continues operation from the last-known coherent state, rather than the current state, based on whatever materials the backup server was last provided with.
Export, dupplication, backup, 
Greater IT efficiencies. Reduced operating costs.

+++

### Virtualization 
#### Pro
- can reduce IT costs |
- automates routine tasks |
- makes a business energy-efficient |
- promotes greater redundancy |
- greatly helps with development |
- allows for faster deployment

+++

### Virtualization 
#### Cons
- It requires high upfront expenditures. 
- comes with limitations.
- comes with the danger of server sprawl. 

note: Depense elevée au départ / tout n'est pas possible Hardware/Software

---

## Containers

Note: 
Containers (Jérôme ou Pierre - 20min)

+++

### Containers 
#### Transport before 1960

+++?image=assets/container-before-1960.jpg

+++

### Transport now

+++?image=assets/container-now.jpg
   
+++

#### Containers versus VitualMachine 

+++?image=assets/container-vs-vm.jpg

+++ 

### Container in IT

- Versionned artifact |
- Isolated deployable unit |
- Container image is bit by bit identical when deployed | 
- Abstraction of data center resources |
- Usage is "Castle business" |

+++

### definitions 

- Container |
- Images |

Note: 
- A container defines a software application and its dependencies wrapped in a complete filesystem, including code, runtime, system tools and libraries 
- An image is a read-only snapshot of a docker container 

+++

### Where are stored images?

- Docker Hub |
- Azure container registry |
- On premise registry |

+++

### Advantages of container 

- Bit by bit images |
- Fast deployment / Fast startup- - Simple scaling and partitioning |
- Isolated, versioned, reusable code |

+++

### Advantages of container 
#### Clear distinction between development and operations 

- Dev : takes care of the content of the container |
- Ops : takes care of the operations of the container |

+++

### Demo 

Note: 
    -> DockerFile
    -> Apache avec files

+++

### Docker Hub / Registry

---

## Orchestrator

+++

### Orchestrator 
#### What is it?

Core capabilities:
* Cluster Management |
* Scheduling |
* Orchestrator Updates and Host Maintenance |
* Service Discovery |
* Networking and Load Balancing |
* Multi-tenant, Multi-region |

Note: 
C'est tout le coeur de l'orchestration : Distribuer les services/application sur plusieurs hosts pour améliorer la performance, la disponibilité et la reprise d'activité
C'est la capacité d'un administrateur à charger un fichier de service sur un système hôte qui établit comment exécuter un conteneur spécifique. 
C'est la capacité de maintenir un cluser à jours et des hosts à jours sans interuption de service.
C'est la capacité d'un orchestrateur de faire communiquer des services entre eux en prenant en considération l'aspect changeant de la configuration des services qui sont exécutés à un instant T sur le cluster.
Si l'on veut que le ServiceDisovery fonctionne alors que les services sont exécutés avec plusieurs instances par exemple, nous aurons besoins : 
* Load balancing,
* Résolution de noms, 
* ...
Multi-tenant: C'est ce qui permet d'utiliser un cluster pour plusieurs besoins/equipes/projets (tenant). 
Multi-region: C'est ce qui permet d'orchestrer des containers dans plusieurs régions du monde en même temps dans un seul cluster.

+++

### Orchestrator 
#### What is it?

Additional capabilities
* Application Health Monitoring |
* Application Deployments |
* Application Performance Monitoring |

Note: 
C'est la capacité d'un cluster de monitorer le fonctionnement des hosts et d'en déduire des actions à effectuer sur le cluster.
C'est la capacité d'un cluster d'orchestration de choisir comment une application à partir d'un descripteur de comment est composé une applciation: 

* Sélection des hosts sur lesquels les containers vont être exécutés
* Réaliser la configuragtion des containers
C'est enfin la capacité de l'orchestrateur de monitorer le fonctionnement de l'application, d'en déduire des actions à effectuer pour que celle-ci continue de fonctionner correctement:

* Augmenter le nombre d'instance (Scaling)
* Déplacer les containers sur d'autres hosts

+++

### Orchestrator 
#### The products

+++

### Orchestrator
#### The products

Commonly used Orchestrators
* Docker Swarm | 
* Nomad |
* Empire |
* Mesosphere |
* Kubernetes |
* Rancher |

+++

### Orchestrator
#### The demo ?

+++

### Kubernetes
#### The concepts

* Node |
* Pod |
* Ingress |

+++

### Rancher Demo 
(And now let's playing...)

Note: 10min

+++

### And the Cloud? 

- Docker Cloud |
- Amazon Elastic Kubernetes Service (aka: Amazon EKS) |
- Alibaba Container Services for Kubernetes (aka: CSK) |
- Azure Kubernetes Service (aka: AKS) | 

---

## Question?

Note: 15 min