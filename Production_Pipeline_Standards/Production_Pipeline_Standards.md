# Production-Grade Data Pipeline Rules

```mermaid
flowchart TD

    %% Extraction Stage
    subgraph Extraction ["Extraction Stage"]
        E1["Capture raw data exactly"]
        E2["Timestamp at extraction"]
        E3["Idempotent runs"]
        E4["Retry with backoff"]
        E5["Respect rate limits"]
    end

    %% Transformation Stage
    subgraph Transformation ["Transformation Stage"]
        T1["Schema standardization"]
        T2["Null/missing-value handling"]
        T3["Deduplication rules"]
        T4["Data validation & quality checks"]
        T5["Type casting & unit consistency"]
        T6["Slowly changing dimensions handling"]
    end

    %% Loading Stage
    subgraph Loading ["Loading Stage"]
        L1["Incremental loading with watermark"]
        L2["Upserts / merge logic"]
        L3["Partitioning for efficiency"]
    end

    %% Cross-Cutting Rules
    subgraph CrossCutting ["Cross-Cutting Rules"]
        C1["Logging & monitoring"]
        C2["Data lineage tracking"]
        C3["Config-driven design"]
        C4["Documentation of schema & logic"]
    end

    %% Flow connections
    Extraction --> Transformation --> Loading --> CrossCutting
