

# Infra-002

### Name

Environment Setup Considerations

### Status

proposed

### Last Update

2019-11-22

### Subject Area



### Topic



### Issue or Problem Statement

<div>Hyperledger Fabric is based on Docker images and thus, relies heavily on resource scheduling capabilities of an underlying containerization engine.&nbsp;</div><div>&nbsp;</div><div>A Hyperledger Fabric environment have to include one of the possible options as below&nbsp;</div><div>&nbsp;</div><ul><li>Use of Hyperledger Fabric native components vs external components (Operations APIs, CA, HSM etc.)&nbsp;</li><li>Availability of Hyperledger Fabric community images, IBM Blockchain Docker images, client application SDKs and Hyperledger Fabric CLI binaries for a particular computing platform&nbsp;</li><li>Container orchestration engine&nbsp;</li><li>Choice of preferred Cloud environment&nbsp;</li><li>Own IT security standards &nbsp;</li><li>Own IT operational capabilities&nbsp;</li></ul><div><br></div>

### Assumptions



### Motivation



### Notes



[Expand all](#){ .md-button .same-line }

### Alternatives


    

<details markdown=1>
<summary markdown="span">Use of BaaS
</summary>

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
        <td>Use of BaaS
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td><div>IBM Blockchain Docker images or BaaS&nbsp;</div><div><br></div><div>Pros: enterprise support&nbsp;</div></td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td><div><br></div><div>Cons: always a release behind community images and not available without paid subscription&nbsp;</div><div>&nbsp;</div><div><br></div></td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td><div>When to choose: &nbsp;</div><div>Enterprise support is needed to decrease operational and compliance risk &nbsp;</div><div>Optimization for Mainframe platforms is needed &nbsp;</div><div>Compatibility with IBM Blockchain Platform v2 needs to be assured. &nbsp;</div><div>Expectation to use IBM Blockchain Platform offering</div></td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Use of Hyperledger Fabric native components
</summary>

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
        <td>Use of Hyperledger Fabric native components
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td><div><b>Fabric-CA&nbsp;</b></div><ul><li>Pros: optimized for a communication with Hyperledger Fabric components to generate and manage identities&nbsp;</li><li>Cons: Can be chosen as a self-contained service.&nbsp;</li></ul><div><br></div><ul><li>When to choose:&nbsp;</li></ul><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; No particular requirements for an integration with an existing organization CA&nbsp;</div><div>Need to integrate Hyperledger Fabric with HSM&nbsp;</div><div><br></div><div><b>Fabric operations APIs</b>&nbsp;</div><div><br></div><ul><li>Pros: off-the-shelf 80+ metrics optimized for Prometheus or StatsD&nbsp;</li></ul><div><br></div><ul><li>Cons: Can only be used with Hyperledger Fabric 1.4.x.&nbsp;</li></ul><div><br></div><ul><li>When to choose:&nbsp;</li></ul><div>Usage of monitoring calling RESTful APIs for healthchecks&nbsp;</div><div>Need for Fabric-specific healthchecks&nbsp;</div><div><br></div><div><br></div><div><b>Fabric SDK</b>&nbsp;</div><div><br></div><ul><li>Pros: community support for off-the-shelf interaction with Hyperledger Fabric network, business logic and components.&nbsp;</li></ul><div><br></div><ul><li>Cons: Currently only Node SDK and Java SDK are mature. Some functionalities exist only in one of the two SDKs (example: Idemix is only implemented in Java SDK).&nbsp;</li><li><br></li><li>When to choose:&nbsp;</li></ul><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Quick development of the application business logic with an underlying Hyperledger Fabric chaincode.&nbsp;</div><div>Extensive use of new chaincode development methods&nbsp;</div><div>&nbsp;</div><div><br></div></td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td></td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td></td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Use of Kubernetes as an underlying containerization platform for Hyperledger Fabric
</summary>

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
        <td>Use of Kubernetes as an underlying containerization platform for Hyperledger Fabric
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td><div><b>Kubernetes</b>&nbsp;</div><div><br></div><ul><li>Pros: industry standard for large-scale orchestrated and automated deployments of containerized applications&nbsp;</li></ul><div><br></div><div><br></div><div><br></div></td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td><div>When to choose: &nbsp;</div><div>Blockchain-as-a-service offerings (massive deployments) &nbsp;</div><div>Dynamic, expandable environments (new client onboarding to an existing network) &nbsp;</div><div>Cloud- and platform-native requirements, abstracting the deployment layer from an underlying infrastructure layer &nbsp;</div><div>&nbsp;</div></td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td><div>Cons: &nbsp;</div><div><br></div><ul><li>Hyperledger Fabric requires security-lenient tweaking to work on top of Kubernetes &nbsp;<br></li><li>Kubernetes may be an &nbsp; &nbsp; &nbsp; overkill for smaller &nbsp; &nbsp;&nbsp; deployments &nbsp;<br></li></ul><ul><li>Lack of operational readiness and skills in organizations to maintain the deployment&nbsp;</li></ul></td>
    </tr>
</table>


</details>


    



### Decision



### Justification



### Implications



### Derived Requirements



### Related Decisions



