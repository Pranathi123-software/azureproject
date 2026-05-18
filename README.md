**Cloud-Based Data Engineering Platform**

📌 **Overview**

This project demonstrates an end-to-end data engineering pipeline built using Azure Databricks and Azure cloud services. The pipeline processes raw data from ADLS Gen2, applies transformations using PySpark, and stores curated data in Delta format following modern data engineering best practices.

**The project includes:**

Auto Loader ingestion
Structured Streaming
PySpark transformations
Delta Lake processing
Medallion Architecture (Bronze → Silver → Gold)
Checkpointing and schema evolution
Reusable utility functions
Unity Catalog integration
This project demonstrates an end-to-end data engineering pipeline built using Azure Databricks and Azure cloud services. The pipeline processes raw data from ADLS Gen2, applies transformations using PySpark, and stores curated data in Delta format following modern data engineering best practices.

**Architecture**

<img width="697" height="400" alt="image" src="https://github.com/user-attachments/assets/d283800b-20d8-414b-bdf3-a1131367f556" />

**⚙️ Technologies Used**

<img width="951" height="505" alt="image" src="https://github.com/user-attachments/assets/651e719a-ec63-4e72-9f1d-20059e57d385" />

**🔥 Features**

✅ Incremental file ingestion using Auto Loader
✅ Schema evolution support
✅ Rescued data handling
✅ Streaming and batch processing
✅ Delta Lake support
✅ Scalable PySpark transformations
✅ Reusable utility functions
✅ Cloud-native architecture
✅ Medallion architecture implementation

📥 **Data Ingestion**
The project uses Databricks Auto Loader for efficient incremental file ingestion from ADLS Gen2.

Example:
spark.readStream.format("cloudFiles") \
    .option("cloudFiles.format", "parquet") \
    .option("cloudFiles.schemaLocation", "<schema-path>") \
    .load("<source-path>")

🔄 **Transformations**

The pipeline performs transformations such as:

Column standardization
Upper/lower case conversion
Null handling
Data cleansing
Aggregations
Schema enforcement
Derived columns

Example:
df = df.withColumn(
    "user_name",
    upper(col("user_name"))
)

💾 **Delta Lake Processing**

Processed data is stored in Delta format for:

ACID transactions
Time travel
Scalable performance
Schema evolution
Reliable streaming

Example:
df.writeStream.format("delta") \
    .outputMode("append") \
    .option("checkpointLocation", "<checkpoint-path>") \
    .start("<target-path>")

📊 **Medallion Architecture**

**Bronze Layer**
Stores raw ingested data.

**Silver Layer**
Stores cleaned and transformed data.

**Gold Layer**
Stores business-ready aggregated data.

🔐 **Unity Catalog**

This project can integrate with Unity Catalog for:

Centralized governance
Fine-grained access control
Data lineage
Secure external locations

📈 **Future Enhancements**
CI/CD integration
Databricks Asset Bundles
Delta Live Tables (DLT)
Monitoring dashboards
Data quality framework
Workflow automation
CDC pipelines

👩‍💻 **Author**

Pranathi
Data Engineer | PySpark | Azure Databricks | Azure Data Factory | Delta Lake | Streaming ETL
