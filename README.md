readme_content = """# Sistema de Filtragem e Triagem - Contadoria Judicial (JFPE)

Este repositório contém o código-fonte de uma aplicação web de página única (SPA), desenvolvida estritamente com tecnologias nativas (HTML5, CSS3 e JavaScript), destinada à otimização do fluxo de triagem e organização de processos no âmbito da Contadoria Judicial da Justiça Federal em Pernambuco.

## 🚀 Funcionalidades Principais

### 1. Gestão e Carga de Dados
* **Suporte a Múltiplos Formatos:** Permite a importação de ficheiros CSV nativos do sistema **PJE2 X** (extraídos com o auxílio da extensão **PJE+R**) e ficheiros de persistência personalizados em formato **JSON**.
* **Interface Drag & Drop:** Zona de arrastamento e largada de ficheiros para carregamento imediato e intuitivo no topo da página.

### 2. Triagem e Isolamento de Fluxos (Abas)
* **Processos com Etiquetas:** Centraliza os fluxos de trabalho regulares que já possuem marcações padronizadas vindas do PJe.
* **Processos Sem Etiqueta:** Identifica e isola automaticamente os processos que não possuem nenhuma etiqueta registada, atribuindo-lhes uma marcação temporária para que possam ser filtrados e tratados de forma autónoma sem afetar o fluxo principal.

### 3. Filtros Dinâmicos e Interativos
* Painel de filtragem multidimensional baseado nos dados carregados, permitindo a segmentação simultânea por:
  * **Mês** de distribuição/referência.
  * **Órgão** julgador.
  * **Servidor / Supervisão** (com contagem dinâmica de registos em tempo real).
  * **Outras etiquetas** acessórias.
  * **Polo Passivo / Réu** (Ordenado alfabeticamente).
  * **Assunto** processual (Ordenado alfabeticamente).
* Controlos rápidos para selecionar todos os elementos de um filtro (✓ Todos) ou limpar a seleção atual (🧹 Limpar).

### 4. Controlo Visual de Produtividade
* **Marcar Linha (Riscar):** Permite riscar visualmente os processos já analisados, reduzindo a opacidade da linha para focar no trabalho pendente.
* **A Concluir (Urgência):** Altera o tom da fonte da linha para um destaque laranja/vermelho (`#e65100`), ideal para categorizar processos que necessitam de uma validação ou retorno posterior.
* **Cópia Rápida:** Botão incorporado (📋) para copiar o número do processo para a área de transferência com um único clique.

### 5. Editor Avançado de Anotações (Rich Text)
* Janela modal integrada com suporte a edição de texto enriquecido (*Rich Text Interface*) através da API `contenteditable`.
* **Barra de ferramentas dedicada:**
  * Formatação em **Negrito**.
  * Ajuste de tamanho de fonte (Aumentar/Diminuir).
  * Aplicação de paleta de cores institucional e de alerta: **Azul**, **Vermelho** e **Verde Escuro**.
  * Limpeza rápida de formatação.

 #### Essa implementação com o contenteditable e a separação automática de páginas (page-break-inside: avoid) no PDF vai garantir que seus relatórios fiquem limpos, organizados e fáceis de ler, mesmo quando contiverem muitas anotações formatadas.

### 6. Exportação e Persistência de Trabalho
* **Salvamento de Progresso (JSON):** Exporta o estado atual completo da aplicação — incluindo a listagem de processos, os filtros aplicados, o estado de cada caixa de seleção (riscado/pendente) e todas as anotações ricas personalizadas — permitindo retomar o trabalho exatamente de onde parou.
* **Planilha Excel (.xlsx):** Gera um relatório em formato folha de cálculo através da biblioteca *SheetJS*, com ajuste automático de largura de colunas e inclusão de uma coluna dedicada com as anotações de texto limpo.
* **Relatório em PDF:** Gera uma versão de impressão otimizada. Possui uma caixa de seleção dinâmica **"Com anotações"** que, quando ativa, renderiza uma secção complementar detalhada abaixo da tabela principal, agrupando as anotações formatadas de cada processo (preservando cores, negritos e estilos) com quebras de página inteligentes (`page-break-inside: avoid`).

## 🛠️ Tecnologias e Bibliotecas Utilizadas

A aplicação foi desenhada para ser totalmente cliente (*client-side*), sem necessidade de base de dados externa ou servidores backend:
* **HTML5 & CSS3:** Estruturação semântica e estilização responsiva baseada em grelhas (*Filtros Grid*) e flexibilidade de componentes visuais.
* **JavaScript (Vanilla):** Lógica de filtragem, ordenação cronológica estrita de datas (particionamento de strings de tempo `DD/MM/AAAA HH:MM:SS`) e manipulação dinâmica do DOM.
* **SheetJS (xlsx.full.min.js):** Responsável pelo parsing estruturado do JSON interno para conversão e download em formato de folha de cálculo binária Excel.
* **Chart.js:** Declarado no cabeçalho para suporte a futuras expansões estatísticas ou painéis visuais (*Dashboards*).

## 📖 Como Executar

Por ser uma aplicação inteiramente *estática*, não requer qualquer instalação complexa:
1. Transfira ou copie o ficheiro `.html` completo fornecido.
2. Abra o ficheiro em qualquer navegador moderno de internet (Google Chrome, Microsoft Edge, Mozilla Firefox, etc.).
3. Arraste o seu ficheiro CSV extraído do PJe ou um JSON guardado anteriormente para começar a trabalhar.

## 🔒 Nota de Segurança e Uso Interno
Os dados são processados inteiramente na memória local do seu navegador. Nenhum dado processual, informação de autor/réu ou anotação confidencial é enviado para servidores externos ou armazenado na nuvem, respeitando integralmente as diretrizes de segurança da informação e sigilo processual da Justiça Federal.
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(readme_content)

print("README.md criado com sucesso.")
