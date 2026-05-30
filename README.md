# Proyecto de RAG con Agente

## Levantar

sudo docker-compose up -d

### Activar Posgres

sudo docker compose exec -it postgres psql -U n8n_user -d n8n_db -c "CREATE EXTENSION IF NOT EXISTS vector;"

### Descargar Ollama

# Descargar modelo de lenguaje (puedes cambiar llama3 por mistral, phi3, etc.)
sudo docker compose exec -it ollama ollama run llama3

Servidor con 16gb de ram
sudo docker compose exec -it ollama ollama pull qwen3:14b

Version ligera server con 8gb de ram
<!-- sudo docker compose exec -it ollama ollama pull qwen3:8b -->
sudo docker compose exec -it ollama ollama pull qwen2.5:7b
sudo docker compose exec -it ollama ollama pull qwen2.5:1.5b
sudo docker compose exec -it ollama ollama pull qwen2.5:0.5b
sudo docker compose exec -it ollama ollama pull smollm2
<!-- sudo docker compose exec -it ollama ollama pull tinyllama -->

# Descargar modelo de embeddings (esencial para la BD Vectorial)
sudo docker compose exec -it ollama ollama run nomic-embed-text
sudo docker compose exec -it ollama ollama pull mxbai-embed-large

### Verificar modelos instalados
sudo docker compose exec -it ollama ollama list