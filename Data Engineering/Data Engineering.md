# Modern Data Stack — Layered Patterns

```mermaid
flowchart TD
    %% Pipeline spine
    SRC([Source]) --> ING[Ingestion & Movement]
    ING --> STOR[Storage & Processing]
    STOR --> MOD[Data Modeling]
    MOD --> CONS([Consumption])

    %% Ingestion Layer
    subgraph Ingestion & Movement
        ELT["1. ELT Pattern"]
        BATCH["2. Batch Processing"]
        CDC["3. Change Data Capture"]
        ETL["4. ETL Pattern"]
        STREAM["5. Streaming + Kappa Architecture"]
        EDA["6. Event-Driven Architecture"]
        REVETL["7. Reverse ETL"]
        LAMBDA["8. Lambda Architecture"]
    end

    %% Storage Layer
    subgraph Storage & Processing
        MEDALLION["1. Medallion Architecture"]
        LAKEHOUSE["2. Lakehouse Architecture"]
        DATALAKE["3. Data Lake (Raw Zone)"]
        FABRIC["4. Data Fabric"]
        MESH["5. Data Mesh"]
    end

    %% Modeling Layer
    subgraph Data Modeling
        KIMBALL["1. Kimball Dimensional Modeling"]
        OBT["2. One Big Table (OBT)"]
        VAULT["3. Data Vault 2.0"]
        SNOW["4. Snowflake Schema"]
        GALAXY["5. Galaxy Schema (Constellation)"]
        INMON["6. Inmon 3NF Enterprise DW"]
    end

    %% Cross-cutting Orchestration
    subgraph Orchestration
        DAG["1. Workflow DAG Pattern (Airflow, Dagster, Prefect)"]
        EVENTORCH["2. Event/Trigger-based Orchestration"]
    end

    %% Cross-cutting Governance
    subgraph Governance & Quality
        SCD["1. Slowly Changing Dimensions (SCD 1/2/3)"]
        OBS["2. Data Observability"]
        CONTRACTS["3. Data Contracts"]
        MDM["4. Master Data Management (MDM)"]
    end
