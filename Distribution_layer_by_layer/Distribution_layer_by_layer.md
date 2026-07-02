# Data Pipeline Pattern Map

```mermaid
flowchart TD
    subgraph Ingestion & Movement
        A1[ELT] --> A2[Batch Processing]
        A2 --> A3[Change Data Capture]
        A3 --> A4[ETL]
        A4 --> A5[Streaming / Kappa]
        A5 --> A6[Event-Driven]
        A6 --> A7[Reverse ETL]
        A7 --> A8[Lambda]
    end

    subgraph Storage & Processing
        B1[Medallion] --> B2[Lakehouse]
        B2 --> B3[Raw Data Lake]
        B3 --> B4[Data Fabric]
        B4 --> B5[Data Mesh]
    end

    subgraph Data Modeling
        C1[Kimball] --> C2[OBT]
        C2 --> C3[Data Vault 2.0]
        C3 --> C4[Snowflake Schema]
        C4 --> C5[Galaxy Schema]
        C5 --> C6[Inmon 3NF]
    end

    subgraph Orchestration
        D1[Workflow DAG] --> D2[Event/Trigger-based]
    end

    subgraph Governance & Quality
        E1[SCD 1/2/3] --> E2[Data Observability]
        E2 --> E3[Data Contracts]
        E3 --> E4[Master Data Management]
    end
