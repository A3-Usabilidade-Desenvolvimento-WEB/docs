---
icon: house
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: false
  outline:
    visible: false
  pagination:
    visible: false
  metadata:
    visible: false
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: false
---

# Planejamento de Entregas A3

&#x20;

## 🗂️ Kanban de Entregas — Acompanhamento das Entregas

Quadro de acompanhamento das **tarefas do trabalho** (Unidade Curricular de Usabilidade e Desenvolvimento Web — A3), com cada card (`CF-XX`) representando uma atividade da equipe e seu(s) responsável(is). Este quadro é de **gestão do projeto/documentação** — os cards descrevem tarefas de construção do sistema ComprasFit, mas o quadro em si não é uma funcionalidade do sistema.

{% hint style="info" %}
Cards identificados por código (`CF-XX`), categoria, descrição e responsável(is), conforme divisão de tarefas definida pela equipe.
{% endhint %}

{% tabs %}
{% tab title="📥 Backlog (15)" %}
**CF-07 · Documentação** — Configurar o espaço do projeto no GitBook\
Seções: escopo, requisitos, protótipos, decisões técnicas, uso de IA, testes e...\
Responsável: Roni

***

**CF-08 · Pesquisa** — Roteiro e entrevistas exploratórias (5 a 10 pessoas)\
Lista, estimativa de gastos, retirada de itens no caixa e alimentos não...\
Responsável: Marco

***

**CF-09 · Pesquisa** — Levantamento de preços em supermercados\
Registrar estabelecimento, data, unidade de medida e tamanho da embalagem.\
Responsável: Roni

***

**CF-10 · UX / Protótipo** — Protótipo das telas do fluxo principal\
Parâmetros → geração da lista → resultado → lista de compras, aplicando...\
Responsável: Luiza

***

**CF-11 · Backend** — Modelagem do banco SQLite\
Produtos, preços (com data de atualização), receitas-base, ingredientes...\
Responsável: Lucas, Filipe, Davi Dilly

***

**CF-12 · Backend** — API FastAPI: parâmetros de planejamento\
Período, orçamento, preferência de compra e base de preços, com validaçã...\
Responsável: Lucas, Filipe, Davi Dilly

***

**CF-13 · Backend** — Regras de cálculo de ingredientes e orçamento\
Seleção de receitas-base, quantidades, subtotais, total e verificação do...\
Responsável: Lucas, Filipe, Davi Dilly

***

**CF-14 · Frontend** — Tela da lista de compras\
Preço unitário, subtotal, total estimado, marcar itens comprados e ver refeições...\
Responsável: Luiza

***

**CF-15 · Frontend** — Aviso de combinação inviável\
Explicar por que não coube no orçamento e permitir revisar os...\
Responsável: Luiza

***

**CF-16 · Frontend** — Registro de validade e ordem por vencimento\
Usuário informa a data da embalagem; itens ordenados pela proximidade do...\
Responsável: Luiza

***

**CF-17 · IA** — Sugestões culinárias com IA + validação\
Usar só ingredientes aprovados pelo sistema; resposta incompatível cai nas...\
Responsável: Erica

***

**CF-18 · Documentação** — Registro do uso de IA\
Finalidade, alterações feitas e revisão humana, na programação e na redação.\
Responsável: Roni

***

**CF-19 · Testes** — Testes automatizados das regras de cálculo\
Meta: toda lista aceita respeita o orçamento na base cadastrada.\
Responsável: Erica, Vinicius

***

**CF-20 · Testes** — Testes de usabilidade com o público-alvo\
Meta: pelo menos 4 de 5 participantes concluem o fluxo principal sem ajuda.\
Responsável: Davi Henrique

***

**CF-21 · Documentação** — Evidências das 8 heurísticas\
Para cada uma: tela, finalidade e tarefa de teste que demonstra o funcionamento.\
Responsável: Roni, Yasmin
{% endtab %}

{% tab title="📝 A Fazer (3)" %}
**CF-04 · Arquitetura** — Elaborar o diagrama de arquitetura\
Interface HTML/CSS/JS → API FastAPI → SQLite. Incluir módulo de IA com validação e fallback para receitas-base, onde ficam as regras de cálculo.\
Responsável: Lucas, Luiza

***

**CF-05 · Gestão** — Criar o repositório no GitHub\
README, pastas /frontend, /backend e /docs, .gitignore, branch main protegida e convite a todos os membros.\
Responsável: Roni

***

**CF-06 · Gestão** — Definir papéis da equipe (Scrum/Kanban simples)\
Preencher os papéis abaixo, combinar a reunião semanal e registrar tudo no GitBook.\
Responsável: Yasmin
{% endtab %}

{% tab title="🔧 Em Andamento (0)" %}
_Nenhum card em andamento no momento._
{% endtab %}

{% tab title="👀 Em Revisão (0)" %}
_Nenhum card em revisão no momento._

Quando um card for concluído e estiver aguardando validação do professor orientador ou do grupo, mova-o para esta coluna.
{% endtab %}

{% tab title="✅ Concluído (3)" %}
**CF-01 · Documentação** — Proposta do projeto ComprasFit\
Problema, público-alvo, solução, uso de IA, arquitetura preliminar e critérios de...\
Responsável: Lucas, Roni

***

**CF-02 · UX / Protótipo** — Seleção das 8 heurísticas de Nielsen\
Princípios definidos como base teórica da interface (NIELSEN, 1994, rev. 2024).\
Responsável: Lucas, Roni

***

**CF-03 · Pesquisa** — Análise de referência de mercado (Listonic)\
Categorias e compartilhamento de listas como exemplos para a prototipação.\
Responsável: Lucas, Roni
{% endtab %}
{% endtabs %}

&#x20;

### Legenda de status

| Status | Significado |
|---|---|
| 📥 Backlog | Entrega planejada, ainda sem trabalho iniciado |
| 📝 A Fazer | Priorizada para o próximo ciclo |
| 🔧 Em Andamento | Em desenvolvimento pela equipe |
| 👀 Em Revisão | Concluída pela equipe, aguardando validação |
| ✅ Concluído | Entregue e validada |

&#x20;

## &#x20;Registro Visual do Protótipo de Referência

{% hint style="info" icon="globe-www" %}
[https://claude.ai/artifact/TjC6sNDoErdu8fzMQKBvxZ](https://claude.ai/artifact/TjC6sNDoErdu8fzMQKBvxZ)&#x20;
{% endhint %}

&#x20;

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### REPOSITÓRIOS&#x20;

Back: [https://github.com/A3-Usabilidade-Desenvolvimento-WEB/backend-ComprasFit](https://github.com/A3-Usabilidade-Desenvolvimento-WEB/backend-ComprasFit)

Front: [https://github.com/A3-Usabilidade-Desenvolvimento-WEB/frontend-ComprasFit](https://github.com/A3-Usabilidade-Desenvolvimento-WEB/frontend-ComprasFit)
