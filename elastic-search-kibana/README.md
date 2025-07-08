# 🐳 Elasticsearch + Kibana (Dev Setup)

A lightweight **Docker Compose** setup for running **Elasticsearch** and **Kibana** locally with **security disabled**.  
Perfect for learning, testing, and development environments.

---

## 📦 Services

### 🚀 Elasticsearch

- **Image**: `docker.elastic.co/elasticsearch/elasticsearch:9.0.2`
- **Port**: [`9200`](http://localhost:9200)
- **Configuration**:
  - Runs in **single-node mode**
  - **Security and TLS disabled**
  - Java heap size set to **1GB**
  - Memory locking enabled via `memlock` (Prevents the OS from swapping ES memory to disk. Improves performance)
  - Persistent data stored in a named volume `esdata`

### 📊 Kibana

- **Image**: `docker.elastic.co/kibana/kibana:9.0.2`
- **Port**: [`5601`](http://localhost:5601)
- **Configuration**:
  - Connects to local Elasticsearch
  - Security disabled (`XPACK_SECURITY_ENABLED=false`)
  - Uses `xpack.encryptedSavedObjects.encryptionKey` to support alerts and saved objects

---

## 🔧 Docker Volume

- **`esdata`**: Named Docker volume used to persist Elasticsearch data.

```yaml
volumes:
  esdata: