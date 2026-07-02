# Modern Data Stack — Layered Patterns

```mermaid
flowchart TD
    %% Pipeline spine
    SRC([Source]):::spine --> ING[Ingestion & Movement]:::ingestion
    ING --> STOR[Storage & Processing]:::storage
    STOR --> MOD[Data Modeling]:::modeling
    MOD --> CONS([Consumption]):::spine

    %% Ingestion Layer
    subgraph Ingestion & Movement
        ELT["1. ELT Pattern"]:::ingestion
        BATCH["2. Batch Processing"]:::ingestion
        CDC["3. Change Data Capture"]:::ingestion
        ETL["4. ETL Pattern"]:::ingestion
        STREAM["5. Streaming + Kappa Architecture"]:::ingestion
        EDA["6. Event-Driven Architecture"]:::ingestion
        REVETL["7. Reverse ETL"]:::ingestion
        LAMBDA["8. Lambda Architecture"]:::ingestion
    end

    %% Storage Layer
    subgraph Storage & Processing
        MEDALLION["1. Medallion Architecture"]:::storage
        LAKEHOUSE["2. Lakehouse Architecture"]:::storage
        DATALAKE["3. Data Lake (Raw Zone)"]:::storage
        FABRIC["4. Data Fabric"]:::storage
        MESH["5. Data Mesh"]:::storage
    end

    %% Modeling Layer
    subgraph Data Modeling
        KIMBALL["1. Kimball Dimensional Modeling"]:::modeling
        OBT["2. One Big Table (OBT)"]:::modeling
        VAULT["3. Data Vault 2.0"]:::modeling
        SNOW["4. Snowflake Schema"]:::modeling
        GALAXY["5. Galaxy Schema (Constellation)"]:::modeling
        INMON["6. Inmon 3NF Enterprise DW"]:::modeling
    end

    %% Cross-cutting Orchestration
    subgraph Orchestration
        DAG["1. Workflow DAG Pattern (Airflow, Dagster, Prefect)"]:::orchestration
        EVENTORCH["2. Event/Trigger-based Orchestration"]:::orchestration
    end

    %% Cross-cutting Governance
    subgraph Governance & Quality
        SCD["1. Slowly Changing Dimensions (SCD 1/2/3)"]:::governance
        OBS["2. Data Observability"]:::governance
        CONTRACTS["3. Data Contracts"]:::governance
        MDM["4. Master Data Management (MDM)"]:::governance
    end

    %% Styles
    classDef spine fill=#0B1220,stroke=#5EEAD4,stroke-width=2px,color=#E8EDF7;
    classDef ingestion fill=#121A2B,stroke=#5EEAD4,stroke-width=2px,color=#E8EDF7;
    classDef storage fill=#121A2B,stroke=#7C9EFF,stroke-width=2px,color=#E8EDF7;
    classDef modeling fill=#121A2B,stroke=#C792EA,stroke-width=2px,color=#E8EDF7;
    classDef orchestration fill=#0F1626,stroke=#F5A65B,stroke-dasharray: 5 5,stroke-width=2px,color=#E8EDF7;
    classDef governance fill=#0F1626,stroke=#F5A65B,stroke-dasharray: 5 5,stroke-width=2px,color=#E8EDF7;
