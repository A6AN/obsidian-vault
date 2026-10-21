---
tags: [inbox, os]
---


2026-08-07 13:24

Status: #Teen 

Tags: [[OS]] [[CPU]] 

# Operating System Intro

##### what is a computer system?
A computer system is an integrated collection of hardware and software components that work together to process data and produce meaningful output

it has four fundamental systems

~~~
┌─────────────────────────────────────────────┐
│           COMPUTER SYSTEM                   │
├─────────────┬─────────────┬─────────────────┤
│   HARDWARE  │   SOFTWARE  │      DATA       │
│             │             │                 │
│ • CPU       │ • OS        │ • Files         │
│ • Memory    │ • Apps      │ • Databases     │
│ • Storage   │ • Drivers   │ • User Input    │
│ • I/O Dev   │ • Utilities │                 │
│ • Bus       │             │                 │
└─────────────┴─────────────┴─────────────────┘
~~~


```mermaid
graph TD
    CS[Computer System]
    CS --> HW[Hardware]
    CS --> SW[Software]
    CS --> D[Data]
    CS --> U[Users + Procedures]
    
    HW --> CPU[CPU]
    HW --> MEM[Main Memory]
    HW --> STOR[Secondary Storage]
    HW --> IO[I/O Devices]
    HW --> BUS[System Bus]
    
    SW --> OS[Operating System]
    SW --> APP[Applications]
    SW --> DRV[Device Drivers]
    
    style CS fill:#f9f,stroke:#333,stroke-width:4px
    style HW fill:#bbf,stroke:#333
    style SW fill:#bfb,stroke:#333
```


# References