# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Para que serve na Helo! |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores usando como base para melhorar o olhar financeiro. |
| `perfil_investidor.json` | JSON | Personalizar recomendações de forma que fique claro o entendimento do que precisa ser feito. |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil para uso no dia a dia para melhorar seu avanço. |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente olhando para onde deve focar para que seja sempre melhorado. |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

O fundo imobiliario foi alterado para o Fundo Multimercado, pois este eu já tive experiência Profissional e fico mais a vontade para utilizar e acompanhar este produto da forma que possa me ajudar e avançar de forma mais ativa. Assim ainda posso entender de forma mais clara os direcionamentos que poosso receber.
---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

[ex: Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt]

### Como os dados são usados no prompt?
Podemos ter a possibilidade de injetar de forma direta (Ctrl + C, Crtl + V) para carregar a base.

```python
import pandas as pd
import json

#CSVs
historico - pd.read_csv('data/historico_atendimento.csv')
transacoes = pd.read_csv('data/transacoes.csv')

#JSONs
with open('data/perfil_investidor.json', 'r', encoding'utf-8') as f:
  perfil = json.load(f)

  with open('data/produtos_financeiros.json', 'r', encoding=utf-8') as f:
```


## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

O exemplo abaixo mostra uma base que usamos como parametros nos dados de conhecimento, para que tenha um direcionamento para usar no acompanhamento e como devemos olhar para que o valor seja melhor monitorado e avaliado.

```
{
  "nome": "Weberton Oliveira",
  "idade": 42,
  "profissao": "Analista de Produtos",
  "renda_mensal": 10000.00,
  "perfil_investidor": "moderado",
  "objetivo_principal": "Construir reserva de emergência",
  "patrimonio_total": 15000.00,
  "reserva_emergencia_atual": 10000.00,
  "aceita_risco": false,
  "metas": [
    {
      "meta": "Completar reserva de emergência",
      "valor_necessario": 15000.00,
      "prazo": "2026-06"
    },
    {
      "meta": "Entrada do apartamento",
      "valor_necessario": 50000.00,
      "prazo": "2027-12"
    }
  ]
}
```
