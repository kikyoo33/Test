

# Multi-CPs-001

### Name

Coexistence of different Cloud Paks on the same infrastructure

### Status

proposed

### Last Update

2021-02-05

### Subject Area

IBM Cloud Paks installation

### Topic

A single OCP cluster, hosting two or more Cloud Paks instances vs. different OCP clusters.

### Issue or Problem Statement

The installation of two or more Cloud Paks requires (at least) the duplication of common-services layers, forcing to spend additional infrastructure resources.

### Assumptions



### Motivation

Optimize the infrastructure resources consumption to instantiate two or more Cloud Paks

### Notes



[Expand all](#){ .md-button .same-line }

### Alternatives


    

<details markdown=1>
<summary markdown="span">Dedicated clusters</summary>

<table>
    <caption></caption>
    <thead>
        <tr>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tr>
        <td> <strong>Name</strong> </td>
        <td>Dedicated clusters</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>Two or more OCP clusters; each Cloud Pak is instantiated on his-own OCP cluster.</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td></td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>
Managing different OCP clusters requires a significant overhead
Distinct common-services instances imposes a significant expense in computational resources 
Having OCP clusters involves a higher expense in terms of infrastructure
The interaction between the application running on different OCP clusters will  involve the ingress/routing layer of each cluster, with significant overhead in terms on configuration.
</td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Single Cluster</summary>

<table>
    <caption></caption>
    <thead>
        <tr>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tr>
        <td> <strong>Name</strong> </td>
        <td>Single Cluster</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>A single OCP cluster, hosting two or more Cloud Paks (e.g. CP4I and CP4D).</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>Resource optimization: a single OCP control plane, just one common-services instance, saving in infrastructure.</td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>At the date, this is a not tested configuration, especially related to CP4I and CP4D.</td>
    </tr>
</table>


</details>


    



### Decision

Dedicated clusters

### Justification



### Implications



### Derived Requirements



### Related Decisions



