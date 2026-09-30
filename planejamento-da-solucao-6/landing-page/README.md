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

# Planejamento da Solução

<h2 align="center"> Diagrama de arquitetura</h2>

<h2 align="center"> Arquitetura e Stack Tecnológica</h2>

<p align="center"> Proposta técnica para o MVP acadêmico </p>

<p align="center"></p>

O ComprasFit será desenvolvido como uma aplicação web full-stack responsiva, utilizando Next.js e TypeScript como tecnologias principais. A proposta prioriza uma arquitetura simples, moderna e adequada ao desenvolvimento assistido por IA, mantendo frontend, backend e regras de negócio em um único projeto.&#x20;

### 1. Visão Geral da Arquitetura&#x20;

A escolha de uma arquitetura full-stack em Next.js reduz a quantidade de tecnologias diferentes que a equipe precisa manter e facilita o desenvolvimento colaborativo. A interface, as APIs e as regras de negócio ficam no mesmo repositório, enquanto o banco de dados e o serviço de inteligência artificial são acessados pelo servidor.&#x20;

USUÁRIO (Computador / Smartphone) \
&#x20;             \| \
&#x20;             v \
NEXT.JS - React + TypeScript + Tailwind CSS \
&#x20;             \| \
&#x20;             v \
CAMADA DE SERVIDOR \
Server Actions / Route Handlers \
Validação + Regras + Cálculos + Planejamento \
&#x20;         \|                 | \
&#x20;         v                 v \
PostgreSQL / Supabase    API de LLM \
Prisma ORM               Sugestões culinárias

&#x20;

### &#x20;2. Stack Tecnológica&#x20;

| Área            | Tecnologia                       | Finalidade                             |
| --------------- | -------------------------------- | -------------------------------------- |
| Framework       | Next.js                          | Aplicação full-stack                   |
| Linguagem       | TypeScript                       | Frontend, backend e regras de negócio  |
| Interface       | React                            | Construção da interface                |
| Estilização     | Tailwind CSS                     | Responsividade e estilização           |
| Componentes     | shadcn/ui                        | Componentes reutilizáveis              |
| Ícones          | Lucide React                     | Ícones da interface                    |
| Formulários     | React Hook Form                  | Gerenciamento de formulários           |
| Validação       | Zod                              | Validação e tipagem de entradas        |
| Backend         | Server Actions / Route Handlers  | Operações de servidor e APIs           |
| Banco           | PostgreSQL                       | Persistência dos dados                 |
| Banco em nuvem  | Supabase                         | PostgreSQL compartilhado pela equipe   |
| ORM             | Prisma                           | Acesso tipado ao banco                 |
| IA              | API de LLM                       | Sugestões culinárias e preparo         |
| Testes          | Vitest                           | Testes das regras críticas             |
| Deploy          | Vercel                           | Publicação da aplicação                |
| Versionamento   | Git + GitHub                     | Colaboração e histórico                |
| Documentação    | GitBook                          | Documentação acadêmica e técnica       |

### &#x20;3. Frontend&#x20;

Next.js + React + TypeScript&#x20;

A interface será construída com React através do Next.js, utilizando o App Router. As principais telas previstas são: página inicial, dashboard, novo planejamento, resultado do planejamento, lista de compras, refeições, controle de validade e histórico.&#x20;

src/app/ \
├── page.tsx \
├── dashboard/page.tsx \
├── planejamento/ \
│   ├── page.tsx \
│   └── novo/page.tsx \
├── compras/page.tsx \
├── refeicoes/page.tsx \
└── validade/page.tsx&#x20;

### 4. Interface e Design&#x20;

Tailwind CSS: Será utilizado para estilização e responsividade, com abordagem mobile-first.&#x20;

shadcn/ui: Fornecerá componentes como Button, Card, Dialog, Input, Select, Checkbox, Progress, Tabs, Table, Badge, Alert, Toast e Skeleton.&#x20;

Lucide React: Será utilizado para ícones como carrinho, carteira, calendário, refeições, alertas e confirmações.&#x20;

### 5. Responsividade&#x20;

A aplicação seguirá o conceito mobile-first. Em casa, o usuário poderá planejar as compras no computador ou celular; no supermercado, poderá consultar e marcar itens diretamente pelo celular.&#x20;

### 6. Backend&#x20;

O próprio Next.js será utilizado como backend, evitando um projeto separado em Python/FastAPI. Server Actions serão utilizadas em operações internas e Route Handlers quando endpoints HTTP forem necessários.&#x20;

src/app/api/ \
├── produtos/route.ts \
├── receitas/route.ts \
├── planejamento/route.ts \
└── ia/ \
&#x20;   └── sugestao/route.ts&#x20;

### &#x20;7. Validação&#x20;

O Zod será utilizado para validar orçamento, período, quantidade de pessoas, preferências e demais entradas. Valores inválidos, como orçamento negativo, zero pessoas ou período inválido, serão rejeitados antes do processamento.&#x20;

### 8. Banco de Dados&#x20;

PostgreSQL + Supabase + Prisma&#x20;

O PostgreSQL será o banco principal. O Supabase poderá hospedar o banco compartilhado pela equipe, enquanto o Prisma será utilizado como ORM para consultas e relacionamentos tipados.&#x20;

Next.js \
&#x20;  \| \
&#x20;  v \
Prisma ORM \
&#x20;  \| \
&#x20;  v \
PostgreSQL (Supabase)&#x20;

Entidades iniciais sugeridas: User, Product, Price, Recipe, RecipeIngredient, Planning, PlanningMeal, ShoppingList, ShoppingItem e FoodExpiration.&#x20;

### 9. Regras de Negócio&#x20;

As regras críticas serão implementadas em TypeScript e não delegadas à IA. O sistema calculará quantidades, embalagens, subtotais, custo total, agrupamento de ingredientes, compatibilidade com o orçamento e ordenação por validade.&#x20;

Orçamento disponível \
&#x20;       \| \
&#x20;       v \
Receitas selecionadas \
&#x20;       \| \
&#x20;       v \
Ingredientes necessários \
&#x20;       \| \
&#x20;       v \
Agrupamento + preços + embalagens \
&#x20;       \| \
&#x20;       v \
Cálculo do custo total \
&#x20;       \| \
&#x20;       v \
Total <= orçamento? \
&#x20;  SIM          NÃO \
&#x20;   \|            | \
Planejamento   Ajustar opções&#x20;

src/lib/ \
├── budget/ \
│   ├── calculate-budget.ts \
│   ├── calculate-packages.ts \
│   └── validate-budget.ts \
├── planning/ \
│   ├── generate-planning.ts \
│   └── group-ingredients.ts \
└── expiration/ \
&#x20;   └── sort-by-expiration.ts&#x20;

### 10. Inteligência Artificial&#x20;

A IA funcionará como camada auxiliar para gerar instruções de preparo, sugerir receitas, aproveitar ingredientes e oferecer alternativas de refeições. Ela não será responsável por cálculos financeiros. A chave da API ficará exclusivamente no servidor.&#x20;

Dados aprovados pelo sistema \
&#x20;       \| \
&#x20;       v \
Ingredientes disponíveis \
&#x20;       \| \
&#x20;       v \
Backend valida contexto \
&#x20;       \| \
&#x20;       v \
API de IA \
&#x20;       \| \
&#x20;       v \
Resposta validada \
&#x20;       \| \
&#x20;       v \
Exibição ao usuário / fallback de receita-base&#x20;

### 11. Estrutura Recomendada do Projeto&#x20;

comprasfit/ \
├── prisma/ \
│   ├── schema.prisma \
│   └── seed.ts \
├── public/ \
├── src/ \
│   ├── app/ \
│   │   ├── dashboard/ \
│   │   ├── planejamento/ \
│   │   ├── compras/ \
│   │   ├── refeicoes/ \
│   │   ├── validade/ \
│   │   └── api/ \
│   ├── components/ \
│   │   ├── ui/ \
│   │   ├── layout/ \
│   │   ├── planning/ \
│   │   ├── shopping/ \
│   │   └── recipes/ \
│   ├── lib/ \
│   │   ├── prisma.ts \
│   │   ├── ai.ts \
│   │   ├── budget/ \
│   │   ├── planning/ \
│   │   └── expiration/ \
│   ├── actions/ \
│   ├── schemas/ \
│   └── types/ \
├── tests/ \
├── .env.example \
├── package.json \
├── tsconfig.json \
└── README.md&#x20;

### 12. Fluxo Principal da Aplicação&#x20;

Novo planejamento \
&#x20;      \| \
&#x20;      v \
Orçamento + período + preferências \
&#x20;      \| \
&#x20;      v \
Refeições disponíveis \
&#x20;      \| \
&#x20;      v \
Ingredientes necessários \
&#x20;      \| \
&#x20;      v \
Consulta de preços \
&#x20;      \| \
&#x20;      v \
Cálculo do orçamento \
&#x20;  /              \ \
Cabe             Não cabe \
\|                  | \
v                  v \
Salvar          Ajustar opções \
\| \
+--> Refeições \
\| \
+--> Lista de compras \
&#x20;       \| \
&#x20;       v \
&#x20;  Marcar produtos \
&#x20;       \| \
&#x20;       v \
Registrar validade&#x20;

### 13. Testes&#x20;

Vitest será utilizado para testar cálculo de orçamento, cálculo de embalagens, agrupamento de ingredientes, subtotais, validação de orçamento, seleção de refeições e datas de validade.&#x20;

Exemplo: orçamento de R$ 300 e custo de R$ 285 deve produzir um planejamento válido. Orçamento de R$ 300 e custo de R$ 325 deve produzir um planejamento inválido.&#x20;

### 14. Deploy&#x20;

A aplicação Next.js poderá ser publicada na Vercel. O GitHub ficará conectado ao serviço de deploy, permitindo que alterações aprovadas na branch principal gerem novas versões automaticamente. O PostgreSQL permanecerá no Supabase.&#x20;

Desenvolvedor → Git → GitHub → Vercel → ComprasFit online&#x20;

### 15. Desenvolvimento Assistido por IA&#x20;

A arquitetura foi pensada para facilitar o desenvolvimento assistido por ferramentas como Codex. O projeto utilizará TypeScript em praticamente toda a aplicação, frontend e backend no mesmo repositório, componentes reutilizáveis, bibliotecas populares, estrutura previsível, schemas de validação e testes automatizados.&#x20;

* A IA poderá auxiliar na criação de componentes, rotas, schemas, testes, consultas e refatorações.&#x20;
* As regras críticas permanecerão separadas da interface.&#x20;
* O código gerado deverá passar por revisão e testes antes de ser incorporado à branch principal.&#x20;

### 16. Git e GitHub&#x20;

Para o MVP, será adotado um fluxo simples de branches, evitando complexidade desnecessária.&#x20;

main \
├── feature/interface \
├── feature/database \
├── feature/planning \
├── feature/shopping-list \
└── feature/ai&#x20;

### 17. Documentação no GitBook&#x20;

O GitBook deverá registrar definição do problema, entrevistas, requisitos, arquitetura, stack, banco de dados, protótipos, regras de negócio, decisões técnicas, uso de IA, heurísticas de Nielsen, testes, resultados, limitações e melhorias futuras.&#x20;

### 18. Arquitetura Resumida&#x20;

COMPRASFIT \
&#x20;   \| \
&#x20;   v \
NEXT.JS (React + TypeScript) \
&#x20;   \| \
&#x20;   +--> Interface: Tailwind CSS + shadcn/ui \
&#x20;   \| \
&#x20;   +--> Backend: Server Actions + Route Handlers \
&#x20;   \| \
&#x20;   +--> Regras: TypeScript + Zod \
&#x20;            \| \
&#x20;            v \
&#x20;        Prisma ORM \
&#x20;            \| \
&#x20;            v \
&#x20;    PostgreSQL / Supabase \
&#x20;            \| \
&#x20;            +--> Dados \
&#x20;            \| \
&#x20;            +--> API de IA (via servidor)&#x20;

### 19. Stack Final Recomendada&#x20;

* Framework: Next.js&#x20;
* Linguagem: TypeScript&#x20;
* Frontend: React&#x20;
* Estilização: Tailwind CSS&#x20;
* Componentes: shadcn/ui&#x20;
* Ícones: Lucide React&#x20;
* Formulários: React Hook Form&#x20;
* Validação: Zod&#x20;
* Backend: Next.js Server Actions + Route Handlers&#x20;
* Banco de dados: PostgreSQL&#x20;
* Banco em nuvem: Supabase&#x20;
* ORM: Prisma&#x20;
* IA: API de LLM acessada pelo servidor&#x20;
* Testes: Vitest&#x20;
* Deploy: Vercel&#x20;
* Versionamento: Git + GitHub&#x20;
* Documentação: GitBook&#x20;

### 20. Justificativa da Escolha&#x20;

A stack foi escolhida por permitir o desenvolvimento de praticamente toda a aplicação em TypeScript, diminuindo a quantidade de tecnologias que a equipe precisa manter. O Next.js concentra frontend e backend em uma única aplicação; Tailwind CSS e shadcn/ui aceleram a construção da interface; Prisma simplifica a comunicação com o PostgreSQL; e o Supabase disponibiliza um banco remoto compartilhado.&#x20;

A arquitetura favorece o desenvolvimento assistido por IA por utilizar tecnologias populares, amplamente documentadas e uma organização previsível. Ao mesmo tempo, as regras críticas do ComprasFit continuam separadas da interface e da IA, permitindo testes automatizados e validação objetiva dos resultados.&#x20;

A solução foi dimensionada para o MVP acadêmico, evitando complexidade desnecessária e mantendo espaço para evolução futura.
