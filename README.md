# Raspberry Pi 4 Cluster

## Purpose

The purpose of this project is to provide a devops like experience deploying
and managing a cluster of Raspberry Pis

This particular cluster will contain 4 Raspberry Pi 4's (2GB) connected to a
PoE enabled switch, allowing for easy deployment.

This project is mostly a learning experience and not meant to support any
specific end product, with a focus on covering the following topics:

1. Using standard DevOps software to help manage a series of servers. We could
   configure each Pi individually with only 4 nodes but the goal is to be able
   to scale this to an arbitrary size with minimal effort.  This will be done
   with Ansible but may include other deployment tools like Chef.
1. Be able to provide a service that is hosted across multiple devices,
   allowing for better performance as usage scales up.  Some services that will
   be desired are:
   - Gitlab CI Runners
   - A simple web service which requires some basic db functionality (likely a
     page view counter)

## Technologies to use

These are the technologies I wish to familiarize myself with throughout this
project.

- Ansible, perhaps Chef
- Kubernetes, Docker Swarm
- Docker Compose, Dockerfile
- Gitlab CI, perhaps Jenkins or Travis

## Technologies used so far

- Git! Hosted on Gitlab and Github
- Fusion360 for enclosure modeling, Meshmixer for basic edits/positioning
- FDM 3D Printer for creating the enclosure

## Project Overview

| Location | Description |
|-|-|
| [**./3dprint**](./3dprint) | Contains various models used to construct an enclosure for this project |
