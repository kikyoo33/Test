

# Copy of Data and AI Collect and Organize 001

### Name

Copy of Frequency of Data Transfer

### Status

proposed

### Last Update

2021-07-26

### Subject Area

Collect and Organize

### Topic

Frequency of data collection should not be smaller than when an action can be taken. 

### Issue or Problem Statement

Customers are often misled by competitors and sometime by IBM for getting insights from data on a frequency smaller than when an action can be taken.  This causes confusion and the outcome is not aligned with expectation.   

### Assumptions

1. Customers are not aware of frequency and action <div>2. Customers are sold on collecting data and insights in real time even when they cannot take action in real time. </div><div> </div>

### Motivation

Collect data that is needed and actionable and save on resources 

### Notes



[Expand all](#){ .md-button .same-line }

### Alternatives


    

<details markdown=1>
<summary markdown="span">Collect data in realtime </summary>

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
        <td>Collect data in realtime </td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>Collect data in realtime. </td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>In critical situation like monitoring a customers critical health, security threats, crime prevention etc.</td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>This alternative is not advisable in most situations when an action cannot be taken. For example : In situations like adjuster allocation for insurance companies, supply chain insights</td>
    </tr>
</table>


</details>


    

<details markdown=1>
<summary markdown="span">Frequency of data collection should be dependent on when action can be taken</summary>

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
        <td>Frequency of data collection should be dependent on when action can be taken</td>
    </tr>
    <tr>
        <td> <strong>Description</strong> </td>
        <td>It may not be practically possible to take action on data collected more frequently. So the frequency of data collected should be determined by when an action can b e tyaken.</td>
    </tr>
    <tr>
        <td> <strong>Best Applied</strong> </td>
        <td>In moist situations. </td>
    </tr>
    <tr>
        <td> <strong>Contraindications</strong> </td>
        <td>In situations that monitor health of an individual</td>
    </tr>
</table>


</details>


    



### Decision

Frequency of data collection should be dependent on when action can be taken

### Justification

If action cannot be taken in a timely manner the data collection does not provide value. 

### Implications

Data collected does not provide value and increases the need for higher compute resources.

### Derived Requirements

Design architectures that can help in improving the time of actions 

### Related Decisions

Data Volume, Data Variety, Data Veracity

