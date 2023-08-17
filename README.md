# vectordb_milvus

## install Milvus & Attu in Docker
- https://milvus.io/docs/install_standalone-docker.md
- https://milvus.io/docs/attu_install-docker.md
1. Download the YAML file
   ```
   wget https://github.com/milvus-io/milvus/releases/download/v2.2.13/milvus-standalone-docker-compose.yml -O docker-compose.yml
   ```

2. Add attu code in the YAML file
   ```
     attu:
         container_name: attu
         image: zilliz/attu:v2.2.6
         environment:
           MILVUS_URL: standalone:19530
         ports:
           - "8000:3000"
         depends_on:
           - "standalone"
   ```
3. Upload 2 im Docker
   ```
   docker-compose up -d
   ```
4. Check port
   ```
   docker port milvus-standalone 19530/tcp
   ```

