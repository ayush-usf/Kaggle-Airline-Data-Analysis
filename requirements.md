### Obtaining the Data & Preprocessing
---
- #### Obtaining the Data: 
Each CSV file was downloaded individually and kept in local storage unless uploaded to the cloud.
- #### Preprocessing:
As the sourced data was already cleaned and formatted, no preprocessing was involved.

### Storage :
---
Each CSV file is nearly 700 MB in size. Such large size CSVs cannot be uploaded directly to BigQuery. So, GCS was involved as an intermediate data storage. The GCS bucket that was used : `gs://personal-pr.` 
The following command has been used:
```
gsutil cp <source_to_CSV_dir>/*.csv gs://personal-pr
```

The data points for the two datasets have been stored in two separate tables in BigQuery with the table’s schema being autogenerated. 
For the main dataset, CSVs were appended to the same table to form the final table.


#### Software Specifications:

- Choosing BigQuery : With such large data, obtaining results for even a small query takes nearly a minute or two in other database management systems. For complex queries, it might result in consuming 2-5 minutes. Such a huge latency might act as hurdles in business operations.
While viewing real-time dashboards, It may jeopardize user experience and as a result, reduce user retention overall. While querying data for APIs, such long time will lead in losing customers.

<div class="parent" style="display: inline-block;width: 100%;">
    <div class="header3" style="display: inline;float: left;width: 50%;">
        <a href="about"><img src="images/prev-page.png" style="max-width: 50px"></a>
    </div>
    <div style="text-align: right;display: inline;cursor:pointer;float: right;right: -6px;" align="right"> 
        <a href="analysis"><img src="images/next-page.png" style="max-width: 50px"></a>
    </div>
</div>