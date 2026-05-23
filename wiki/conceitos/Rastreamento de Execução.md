---
title: "Rastreamento de Execução"
tags: ["metodologia", "python", "debug", "rich"]
---

# Rastreamento de Execução (Execution Tracing)

O **Rastreamento de Execução** é uma técnica de monitoramento de runtime que captura a hierarquia, o tempo e o sucesso de chamadas de função dentro de um pipeline de bioinformática.

## 1. Arquitetura de Rastreamento
A implementação recomendada utiliza o **Padrão Decorator** e uma **Pilha de Contexto (Stack)** para evitar o acoplamento entre a lógica de negócio e a interface de visualização.

- **Fronteira**: O rastreador opera em uma camada isolada.
- **Hierarquia**: Funções que chamam outras funções são automaticamente aninhadas na visualização (Parent-Child relationship).

## 2. Implementação Técnica

### O Decorador `@trace_step`
```python
def trace_step(name: str):
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            node = tracer.push(name)  # Empilha contexto
            try:
                result = func(*args, **kwargs)
                tracer.pop(node, success=True) # Desempilha com sucesso
                return result
            except Exception as e:
                tracer.pop(node, success=False) # Desempilha com erro
                raise e
        return wrapper
    return decorator
```

## 3. Benefícios para a Tese
- **Auditabilidade**: Registro visual claro de quais etapas do pipeline (ex: filtragem de outliers, normalização) foram concluídas.
- **Profiling**: Identificação imediata de gargalos de tempo em funções específicas sem necessidade de ferramentas complexas de profiling.
- **Tratamento de Erros**: Visualização imediata de onde o pipeline falhou na hierarquia (ex: erro no carregamento de dados impede a transformação subsequente).

## 4. Referências
- [[Nova-conversa-2026-05-22]]
- [[Visualização de Dados com Rich]]
