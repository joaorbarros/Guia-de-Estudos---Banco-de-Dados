# Banco de Dados: guia de estudo interativo

Guia de estudo da disciplina de **Banco de Dados**, criado a partir das minhas anotações e dos registros que fiz sobre o material didático da **Gran Faculdade**, no Curso Superior de Tecnologia em **Inteligência Artificial**.

É uma página única em HTML que roda no navegador, sem instalação e sem servidor. As quatro unidades da disciplina viram tópicos curtos, com diagramas, exercícios corrigidos na hora e um SQLite de verdade embutido para praticar.

> **[▶ Abrir o guia](https://joaorbarros.github.io/Guia-de-Estudos---Banco-de-Dados/)**

---

## O que tem no guia

| Aba | Conteúdo |
|---|---|
| **Unidade 1 · Modelo conceitual** | Fundamentos, MER, entidades e atributos, relacionamentos e multiplicidade, EER |
| **Unidade 2 · Modelo relacional** | Regras de Codd, esquemas e chaves, restrições, mapeamento do conceitual para o lógico, modelo físico |
| **Unidade 3 · Álgebra e SQL** | Álgebra relacional, operações de conjunto, SGBDs, DDL (CREATE, ALTER, DROP), DML (INSERT, UPDATE, DELETE) |
| **Unidade 4 · Consultas SQL** | SELECT, WHERE, ORDER BY, junções, funções de agregação, GROUP BY e HAVING, subconsultas, UNION/INTERSECT/EXCEPT, visões |
| **Além do material** | Diagnóstico do módulo, 8 lições complementares, curadoria de fontes abertas, simulado final e 3 projetos práticos |
| **Referências** | Material da instituição, bibliografia citada, materiais complementares e créditos |

Cada unidade traz:

- **Aulas em tópicos de 10 a 15 minutos**, na ordem das videoaulas, com teste rápido de resposta oculta e botão “marcar como revisado”. O progresso fica salvo no navegador.
- **Pegadinhas de prova** e caixas **“O material, com precisão”**, que registram onde apostila, slides, resumos e questionários se contradizem ou têm erros, e qual versão seguir.
- **Quiz de revisão** com as questões oficiais da unidade marcadas com ★.
- **Avaliação de nivelamento** de 10 questões: com 7 acertos ou mais, a unidade está consolidada; abaixo disso, o guia lista os tópicos exatos para revisar.
- **Conferência das fontes**: tabela com todas as divergências encontradas no material.

### Recursos interativos

- **Console SQL no navegador:** SQLite completo (via sql.js / WebAssembly) com os bancos de exemplo já carregados e corrigidos, exemplos prontos por aula e mensagens de erro traduzidas.
- **Exercícios com correção automática:** o verificador roda a sua consulta num banco limpo e compara o resultado com o esperado, sem exigir que a escrita seja idêntica à do gabarito.
- **Visualizador de junções:** INNER, LEFT, RIGHT e FULL JOIN linha a linha, com cores para quem tem par e quem sobrou.
- **Ordem de execução:** FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY, etapa por etapa.
- **Laboratório de álgebra relacional, leitor de cardinalidade, mapeador de relacionamentos, simulador de restrições** e outros, distribuídos pelas unidades.
- **Demonstração de injeção de SQL:** a mesma busca feita concatenando texto e com parâmetro.

### Lições complementares (“Além do material”)

Temas essenciais que o material base não aborda ou trata de forma superficial:

1. Normalização (dependência funcional, 1FN, 2FN, 3FN, FNBC)
2. NULL e lógica de três valores
3. Índices e desempenho (com `EXPLAIN QUERY PLAN` no console)
4. Transações, níveis de isolamento e backup
5. SQL além do básico: CASE, CTE e funções de janela
6. Restrições completas, gatilhos e procedimentos
7. Segurança, injeção de SQL e LGPD
8. Banco de dados na aplicação e na IA (Python, NoSQL, bancos vetoriais e RAG)

### Projetos práticos

| Projeto | O que pratica |
|---|---|
| **1 · O sebo, do diagrama ao SQL** | Modelo lógico, script DDL, carga, DML e 8 consultas verificadas |
| **2 · Relatórios do sebo** | CASE, CTE e funções de janela em 5 relatórios verificados |
| **3 · Mini-sistema em Python** | sqlite3, consultas parametrizadas, pandas e gráfico, no Google Colab |

---

## Como usar

**No navegador:** baixe o `index.html` e abra com dois cliques. Tudo funciona offline, inclusive o console SQL. Só as fontes tipográficas vêm da internet; sem conexão, o navegador usa as fontes do sistema.

**Sugestão de rotina:** um tópico por sessão de cerca de 25 minutos. Ao fim de cada unidade, faça o quiz e a avaliação de nivelamento antes de avançar.

---

## Como publicar (GitHub Pages)

1. Crie um repositório público e envie `index.html` e `README.md` para a raiz.
2. Em **Settings → Pages**, em *Build and deployment*, escolha **Deploy from a branch**, branch `main` e pasta `/ (root)`.
3. Depois de um ou dois minutos, o guia fica disponível em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

---

## Estrutura do repositório

```
.
├── index.html   # o guia completo (HTML, CSS, JS e o SQLite em WebAssembly embutidos)
├── README.md
└── LICENSE      # opcional, veja “Licença”
```

O arquivo tem cerca de 1,5 MB porque o motor do SQLite (WebAssembly) vai embutido nele, para o console funcionar sem rede.

---

## Tecnologias

- HTML, CSS e JavaScript puros, em um único arquivo, sem frameworks nem etapa de build
- [sql.js](https://github.com/sql-js/sql.js) 1.12.0 (SQLite compilado para WebAssembly), licença MIT
- [SQLite](https://www.sqlite.org/), domínio público
- Fontes Atkinson Hyperlegible e Bricolage Grotesque, do Google Fonts (SIL Open Font License)
- `localStorage` para salvar progresso, resultados das avaliações e exercícios resolvidos
- Tema claro e escuro automáticos, layout responsivo para celular

---

## Fontes e créditos

- **Material base:** apostilas, slides, resumos de videoaulas e questionários da disciplina de Banco de Dados da Gran Faculdade (Prof. Anderson Nascimento; videoaulas da aula 5 da Unidade 2 do Prof. José Reginaldo de Sousa Mendes Junior).
- **Bibliografia de referência do curso:** Heuser, *Projeto de Banco de Dados*; Elmasri e Navathe, *Sistemas de Banco de Dados*; Silberschatz, Korth e Sudarshan, *Sistema de Banco de Dados*; Cardoso, *Linguagem SQL*; Damas, *SQL*.
- **Fontes abertas** usadas para conferir divergências e para as lições complementares: SQLBolt, SQL Murder Mystery, Curso em Vídeo, CMU 15-445, documentação do PostgreSQL e do SQLite, IMD/UFRN, Use The Index, Luke, OWASP e documentação do Python.

A lista completa, em formato ABNT e com links, está na aba **Referências** do guia.

A organização do conteúdo, a revisão técnica e as ferramentas interativas foram feitas com apoio de assistente de inteligência artificial (Claude, da Anthropic), a partir das minhas anotações e dos arquivos do curso.

---

## Aviso sobre o material didático

Este é um **guia de estudo pessoal e não oficial**. Ele não tem vínculo com a Gran Faculdade e não substitui o material da disciplina.

O material didático da instituição é licenciado para uso individual do aluno e **não está incluído neste repositório**. O guia traz apenas resumos e explicações próprias; as poucas definições citadas literalmente indicam a fonte. As observações sobre erros e divergências do material são notas de estudo, conferidas com a bibliografia do próprio curso.

Os bancos de exemplo (locadora e sebo) são fictícios.

---

## Licença

Sugestão para quem quiser reutilizar:

- **Textos e conteúdo didático do guia:** [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.pt-br), com atribuição e sem uso comercial.
- **Código (HTML, CSS e JavaScript próprios):** [MIT](https://opensource.org/license/mit).
- O **sql.js** embutido mantém a própria licença MIT.

---

## Autor

**João Antonio Ramos de Barros**<br>
Estudante do Curso Superior de Tecnologia em Inteligência Artificial, Gran Faculdade

[GitHub](https://github.com/joaorbarros) · [LinkedIn](https://www.linkedin.com/in/jo%C3%A3o-rbarros/)
