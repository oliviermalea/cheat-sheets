# Generic data architecture

## Overview

```mermaid
# Generic data architecture

  

## Overview

  

```mermaid

  

---

title: Conceptual diagram

---

  

%%{init: {'theme':'basic'}}%%

flowchart TB

    subgraph "d"[DataSources]

    direction TB

        d1(sources) --> d2[repository]

        d3{{apis}}

        d4[sftp]

        d5[erp]

    end    

    subgraph "i"[Ingest]

    direction TB

        i1[ingest service]

    end

    subgraph "s"[Store]

    direction LR

        s1[Temp data]

        s2[Lineage data]-->s3(sql repository)

    end

    subgraph "t"[Transform & Train]

        direction TB

        t1(Data-Warehouse)

    end

    subgraph "m"[Model & Serve]

        direction LR

        m1{{Generate models with power Query/Power BI}}

        m2(data storage)

        m3(other data storage)

    end

    subgraph "c"[Consume]

        direction LR

        c1{{read, extract, connect and virtualize with PBI}}

        c2{{APIsation}}

    end

    d --1--> i1

    d4--1-->i1

    d5--1-->i1

    i1--2-->s1

    s1<--3-->t1

    t1--4 : transform and feed DW-->s2

    s3--5-->m

    m--6-->c

  

```

  

---
```

---
