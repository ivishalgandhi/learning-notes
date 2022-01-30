---
id: RngWwHFpftrWYJlCcH6mK
title: Doc
desc: ''
updated: 1643529294636
created: 1643529292927
---
## Create collection 


```shell
curl "http://typesense-1:7108/collections" \
       -X POST \
       -H "Content-Type: application/json" \
       -H "X-TYPESENSE-API-KEY: xyz" \
       -d '{
         "name": "companies",
         "fields": [
           {"name": "company_name", "type": "string" },
           {"name": "num_employees", "type": "int32" },
           {"name": "country", "type": "string", "facet": true }
         ],
         "default_sorting_field": "num_employees"
       }'



```

## Insert a document 

```shell

curl "http://typesense-1:7108/collections/companies/documents" -X POST \
        -H "Content-Type: application/json" \
        -H "X-TYPESENSE-API-KEY: xyz" \
        -d '{
          "id": "125",
          "company_name": "Stark Industries",
          "num_employees": 180000,
          "country": "USA"
        }'
```

## Retrieve a document

```shell

curl -s -H "X-TYPESENSE-API-KEY: xyz" -X GET \
      "http://typesense-1:7108/collections/companies/documents/126" | jq && \
curl -s -H "X-TYPESENSE-API-KEY: xyz" -X GET \
      "http://typesense-2:8108/collections/companies/documents/126" | jq && \
curl -s -H "X-TYPESENSE-API-KEY: xyz" -X GET \
      "http://typesense-3:9108/collections/companies/documents/126" | jq



```

