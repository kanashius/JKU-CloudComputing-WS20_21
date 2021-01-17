# Project Proposal Group 3 - GitOps

The project is dedicated to exploration of GitOps - a developer-centric way of operating infrastructure. GitOps is an operational framework that is inspired by DevOps best practices used for application development (version control, collaboration, CI/CD) and applies them to infrastructure automation. While the software development lifecycle has been automated, infrastructure has remained a largely manual process that requires specialized teams. The core idea of GitOps is having a Git repository that always contains declarative descriptions of the desired infrastructure in the respective environment and an automated process to make the environment match the described state in the repository. The benefits of this approach are following:
- Easy and fast error recovery
  - If an error occurs in the infrastructure, the recovery is as easy as issuing a `git revert` command where you can rollback to the previous configuration
- Improved access control and easier credential management
  - There’s no need to give credentials to all infrastructure components since changes are automated (only CI/CD needs access)
  - The environment only needs access to the repository and image registry - no need for developers to have a direct access to the environment
- Collaboration
  - The changes can go through merge request/review/approval process so that everyone is involved
  - Using Git to store descriptions of the deployed infrastructure allows everybody in the team to check out its evolution over time.
- Self-documenting deployments
  - Every change to any environment must happen through the repository. The master branch is a complete description of what is deployed where and the complete history of every changed ever made to the system (audit trail)  
- increased productivity through the enablement of continuous delivery and deployment  
- enables an organization to use a single set of tools - so the developer only needs  knowledge about git

## Team members

Patrick Nolte (k01618097)  
Phung-Dong Kulcsar (k11937199)  
Stefan Paukner (k11808822)  

## Objectives - Goal of the Project

Demo: Implement a demo using Flux for versioning your applied configuration
Comparision between Flux and ArgoCD 
Implementing a Review Process for the PullRequests in GitHub 

## Tech stack

* [Kubernetes](https://kubernetes.io/)
* [Flux - GitOps toolkit](https://toolkit.fluxcd.io/)
* [GitHub](https://github.com/)
* [Git](https://git-scm.com/)

## Deliverables

1. Documentation of the project in a report format
2. Presentation of the demo application

## General steps

1. Set up an github account
1. Set up 2 different kubernetes clusters to represent 2 different stages like stage and production environment
1. Install the flux 
1. To enable the GitFlow we will try to use the existing repository (or maybe create a new one with the new github account) to manage the clusters
1. Then we will configure the clusters to synchronise with a directory in the repository
1. Register app sources that contain plain Kubernetes manifests or Kustomize overlays
1. Configure app deployments on both clusters (staging and production)
1. To test if our configuration works we would like to change the number of replicas of an pod to see, if these changes are applied correctly
1. Configure the review process with a test tool to verify the syntax of the configuration yaml files

## Responsibilities
Patrik Nolte: Comparison, github review process  
Phung-Dong Kulcsar : Flux setup on googlecloud, setup fleet-repo   
Stefan Paukner: Flux setup on azure cluster, setup fleet-repo with 2nd stage 





