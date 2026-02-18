# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |
---

## Estratégia de Integração

### Como os dados são carregados?

Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt

```python
import json
import pandas as pd

perfil=json.loaD(open('./data/perfil_investidor.json'))
transacoes=pd.read_csv('./data/transacoes.csv')
```

### Como os dados são usados no prompt?

Para simplificar, podemos simplesmente "injetar" os dados em nosso prompt, garantindo que o agente tenha o melhor contexto possível.

---

## Exemplo de Contexto Montado

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
