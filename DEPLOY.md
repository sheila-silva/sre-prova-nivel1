# Guia de Deploy e Rollback

## Como fazer deploy

### 1. Construa e teste localmente:
```bash
docker build -t sre-app:1.0.1 app/
docker run -p 8080:8080 sre-app:1.0.1
```

### 2. Execute os testes:
```bash
cd tests && pytest -v
```

### 3. Execute o deploy:
```bash
./deploy.sh 1.0.1
```

### 4. Monitore a aplicação:
```bash
./scripts/monitor.sh
```

## Como fazer rollback

Se algo der errado após o deploy:

### 1. Execute o rollback:
```bash
./rollback.sh
```

### 2. Verifique se a versão anterior voltou:
```bash
curl http://localhost:8080/health
```

### 3. Investigue o problema antes de tentar novo deploy


