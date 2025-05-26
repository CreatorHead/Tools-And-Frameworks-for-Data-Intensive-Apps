# Tools-And-Frameworks-for-Data-Intensive-Apps
List of Tools and Frameworks for Data Intensive applications


### Percentil Estimations Libs
Open source percentile estimation libraries include **HdrHistogram**, **t-digest**, **OpenHistogram**, and **DDSketch** 

### Schemas Used for Analytics

| Feature              | Star Schema     | Snowflake Schema | OBT (One Big Table)     |
|----------------------|-----------------|------------------|-------------------------|
| Normalization        | Denormalized    | Normalized       | Fully Denormalized      |
| Query Performance    | High            | Moderate         | High (simple queries)   |
| Data Redundancy      | Medium          | Low              | High                    |
| Complexity           | Low             | Medium           | Low                     |
| Best For             | BI dashboards   | Data consistency | Prototyping, fast access|


## 📍 Data Locality for Reads and Writes

- **Document Storage**:  
  Documents are stored as continuous strings (e.g., JSON, XML, BSON). This offers **performance benefits** when the entire document is accessed at once, due to reduced disk seeks.

- **Trade-offs**:
  - Advantageous when large parts of the document are read together.
  - Inefficient if only small parts are needed frequently, since the whole document is loaded or rewritten on updates.
  - ✅ **Best Practice**: Keep documents **small** and avoid **frequent small updates**.

- **Locality Beyond Documents**:
  - **Google Spanner** supports locality through **interleaved (nested) tables**.
  - **Oracle** supports it using **multi-table index cluster tables**.
  - **Wide-column stores** like **Bigtable**, **HBase**, and **Accumulo** use **column families** to manage related data locality.

> **Key Point**: Locality improves performance when related data is accessed together, regardless of the data model.
