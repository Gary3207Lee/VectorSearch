# VectorSearch

## Azure Cosmos DB Vector Search

Reference Doc: [Use vector search on embeddings in Azure Cosmos DB for MongoDB vCore](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/vcore/vector-search) </br>

### Indexes

```
db.runCommand({
  createIndexes: 'C4_IVF_COS',
  indexes: [
    {
      name: 'IVF_COS_IDX',
      key: {
        "text_v": "cosmosSearch"
      },
      cosmosSearchOptions: {
        kind: 'vector-ivf',
        numLists: 365,
        similarity: 'COS',
        dimensions: 1536
      }
    }
  ]
});

db.runCommand({ 
    "createIndexes": "C4_HNSW_COS",
    "indexes": [
        {
            "name": "HNSW_COS_IDX",
            "key": {
                "text_v": "cosmosSearch"
            },
            "cosmosSearchOptions": { 
                "kind": "vector-hnsw", 
                "m": 16, 
                "efConstruction": 64, 
                "similarity": "COS", 
                "dimensions": 1536 
            } 
        } 
    ] 
});
```

</br>

## Azure SQL Database Vector Search

## Azure PostgreSQL Vector Search

## Azure AI Search Vector Search
