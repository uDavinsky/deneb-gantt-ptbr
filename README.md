![Capa do Gráfico de Gantt Deneb](Gantt%20Davd%20Thumbnail.png)

# Gráfico de Gantt Avançado para Power BI (Deneb / Vega) - PT-BR

## 📖 Sobre o Projeto
Como Analista de Projetos, uma das minhas maiores dificuldades sempre foi encontrar um gráfico de Gantt no Power BI que realmente atendesse às necessidades de gestão: visualização clara de múltiplos projetos, fases, dependências e marcos (milestones). 

Os visuais padrão de mercado são frequentemente "engessados" e limitados. Cheguei a tentar desenvolver uma solução própria via HTML puro, mas a complexidade técnica era inviável para a manutenção diária. Foi então que descobri o **Deneb (Vega)** e o incrível trabalho de **Davide Bacci**. 

Este repositório é um *fork* (código independente) da versão 2.1 do Gantt criado por ele, com diversas adaptações, correções estruturais e tradução completa para o Português (PT-BR) visando o mercado brasileiro.

---

## 🚀 O que foi modificado e melhorado?

Partindo do código original (v2.1), implementei as seguintes melhorias:

1. **Tradução Completa:** Todos os rótulos, dicas de ferramenta (tooltips), menus de botões e eixos de datas foram traduzidos e formatados para o padrão brasileiro (DD/MM/AAAA).
2. **Nova Hierarquia de Projetos:** O visual original trabalhava com "Fase > Tarefa". Adicionei um nível superior, permitindo a estrutura **Projeto > Fase > Tarefa**.
3. **Responsividade Automática:** Remoção das amarras estáticas de `width` e `height`, permitindo que o gráfico preencha 100% do contêiner do Power BI de forma dinâmica.
4. **Correção de Altura Dinâmica:** O comportamento das barras (`phaseSymbolHeight` e `yPaddingInner`) foi alterado de `init` para `update`, corrigindo o bug onde as barras ficavam grossas ou distorcidas ao redimensionar a tela.
5. **Correção de Estado (Expandir/Recolher):** Ajuste nos sinais do Vega e no redesenho dos SVGs (`summaryPaths`) para evitar que o visual "se perdesse" ao expandir ou recolher todas as linhas simultaneamente.
6. **Suporte a Fases Homônimas:** Correção de um bug crítico onde fases com o mesmo nome (ex: "Iniciação") em projetos diferentes quebravam o eixo Y e as setas de dependência. Foi implementada uma lógica de IDs compostos e únicos (`phase_Projeto_Fase`).
7. **Ajuste de Eixos Temporais:** Correção na sobreposição (`labelOverlap`) de textos no eixo superior para evitar que Meses e Anos ficassem encavalados sobre os dias.

---

## 🛠️ Como Utilizar

1. Faça o download do arquivo `Gantt_Deneb_PTBR.json` disponível neste repositório.
2. No Power BI, adicione o visual **Deneb** (baixe no marketplace de visuais da Microsoft, se não tiver).
3. Insira seus dados no visual Deneb (veja a planilha `Sample Data.xlsx` para entender a estrutura esperada de colunas).
4. Clique em "Edit" no visual do Deneb, escolha a opção de importar template (Vega, não Vega-Lite) e carregue o arquivo JSON.
5. Mapeie as colunas do seu modelo de dados com as variáveis do código.

> **Dica:** O repositório contém um arquivo `.pbix` de exemplo funcional já com dados fictícios para você explorar.

---

## 👏 Créditos

* **Código Original (v2.1):** [Davide Bacci](https://github.com/PBI-David/Deneb-Showcase) - O verdadeiro gênio por trás da estrutura Vega deste Gantt.
* **Adaptação, Correções de Bug e PT-BR:** David Junior da Silva
