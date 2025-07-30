# ARQV30 Enhanced v2.0 - Guia de Deploy Local

## 🚀 Deploy Rápido (Recomendado)

```bash
# 1. Execute o deploy automático
deploy_local.bat

# 2. Acesse http://localhost:5000
```

## 📋 Deploy Manual (Passo a Passo)

### 1. Preparação do Ambiente

```bash
# Instalar dependências
setup_complete.bat

# Verificar sistema
python check_system.py
```

### 2. Configuração

O arquivo `.env` já está configurado com suas chaves de API:
- ✅ Gemini API configurada
- ✅ Supabase configurado
- ✅ Google Search configurado
- ✅ Groq configurado
- ✅ HuggingFace configurado

### 3. Inicialização

#### Modo Síncrono (Simples)
```bash
run.bat
```

#### Modo Assíncrono (Avançado)
```bash
# Terminal 1: Inicia Redis + Celery
start_celery.bat

# Terminal 2: Inicia aplicação
run.bat
```

## 🔧 Solução de Problemas

### Erro: "No module named 'groq'"
```bash
pip install groq==0.4.1
```

### Erro: "No module named 'tasks'"
- Execute `setup_complete.bat` para corrigir paths do Celery

### Redis não encontrado
- A aplicação funciona sem Redis (modo síncrono)
- Para funcionalidades assíncronas, instale Redis

### Erro de encoding
- O sistema está configurado para UTF-8
- Execute `python check_system.py` para verificar

## 📊 Funcionalidades Disponíveis

### ✅ Funcionando Sempre
- Análise de mercado síncrona
- Pesquisa web profunda
- Geração de PDF
- Upload de anexos
- Avatar ultra-detalhado
- Análise de concorrência

### ⚡ Funcionando com Redis/Celery
- Análise assíncrona
- Dashboard interativo
- Monitoramento de progresso
- Múltiplos formatos de download

## 🌐 URLs Importantes

- **Aplicação**: http://localhost:5000
- **Flower (Celery)**: http://localhost:5555
- **Status da API**: http://localhost:5000/api/health

## 📞 Suporte

Se encontrar problemas:

1. Execute `python check_system.py`
2. Verifique logs em `src/logs/arqv30.log`
3. Execute `setup_complete.bat` novamente

## 🎯 Teste Rápido

```bash
# Teste básico
python test_simple.py

# Verificação completa
python check_system.py
```