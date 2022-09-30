

# Deployment-001

### Name

Endorsement policies - Deployment Considerations

### Status

proposed

### Last Update

2020-01-27

### Subject Area



### Topic



### Issue or Problem Statement

Endorsement policy deployment considerations (chaincode or key-level)


Key architecture topics to analyze when selecting a type of endorsement policy (chaincode- or key-level) and determining the endorsement policy that fits best to the given use case:

<ul><li><b>Bounded execution time </b>(termination): the more organizations are involved in endorsement, the more probable it becomes that the transaction will time out due to connection delays between distinct organizations and the application client.
</li><li><b>Determinism</b>: participation of numerous endorsers assures against non-deterministic output of executed transaction proposals.</li><li><b>Performance</b>: endorsement requires computing power and network throughput to allow for execution of the chaincode and transmission of the output to the application client.</li><li><b>Security guarantees</b>: layered endorsement policies involving a random subset of organizations minimize the appearance of malicious actors in the business network</li><li><b>Privacy and confidentiality</b>: endorsers are generally aware of the transaction input, unless transient data transmission or PDCs are in use.</li></ul>


### Assumptions



### Motivation



### Notes



[Expand all](#){ .md-button .same-line }

### Alternatives


    

<details markdown=1>
<summary markdown="span">Use of Chaincode endorsement policies
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
        <td>Use of Chaincode endorsement policies
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>Decision: The formulation of an endorsement policy across the entire namespace (chaincode within a channel) using basic logic expressions such as AND and OR.</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>
Recommendation: Use OR expression across a vast subset of endorsers for redundancy and randomization.

</td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>Risks: excessive use of AND expression in the absence of a stable connection between application clients and endorsers, or temporary unavailability of essential endorsers may cause a transaction to fail due to connection timeout or insufficient endorsement collections.</td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Use of Key-level endorsement policies
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
        <td>Use of Key-level endorsement policies
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>Decision: The formulation of an endorsement policy for individual keys using chaincode functions.


</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>Recommendation: Use deterministic and simple key-level endorsement policies such as organization identities extracted from the certificate, organization roles embedded in the certificate etc.
</td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>Risks: usage of non-deterministic policies may cause inability to collect enough endorsement collections.

</td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Use of custom endorsement policies
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
        <td>Use of custom endorsement policies
</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>Decision: The use custom endorsement policies in specific scenarios which require non-standard endorsement methods.</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>


Recommendation: Use chaincode-level or key-level endorsement policies instead.</td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>Risks: usage of non-standard endorsement policy plugins generates a potential operational overhead as the plugin has to be tested against security and stability for each new release of Hyperledger Fabric. 3rd party and custom development may also be affected by vulnerabilities which may be exploited by malicious parties within or outside the network.


</td>
    </tr>
</table>


</details>


    



### Decision



### Justification



### Implications



### Derived Requirements



### Related Decisions



