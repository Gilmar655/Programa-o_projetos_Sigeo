# Programação projetos Sigeo

Site: https://gilmar655.github.io/Programa-o_projetos_Sigeo/

## Base atualizada em 12/10/2026

Fonte: `Programação_Sigeo_13_outubro_dezembro.xlsx`, aba `Dados`.

- **2.237 registros**, **1.952 projetos distintos**, 11 colunas e 41 contratadas.
- Período efetivo: **13/10/2026 a 25/12/2026**.
- Status: 1.034 liberados para execução, 554 liberados para documentação, 514 pendentes de aprovação, 87 cancelados, 46 rascunhos e 2 executados.
- Todas as linhas e colunas foram preservadas, incluindo duas linhas integralmente repetidas, 1.103 PowerON vazios e 17 registros com diferença entre a data de início e a data de programação. Não foram presumidas correções.
- A segunda coluna é **Descrição do Projeto**, conforme o arquivo recebido. A empresa consta em **Contratada**.

## Consultar

O `index.html` é autossuficiente: contém toda a base, a aparência, os cinco gráficos e as funções de consulta, importação e exportação. Os gráficos iniciais também estão desenhados no HTML. Os arquivos separados das versões anteriores não são carregados pela página atual.

Os gráficos de status, tipo de intervenção, contratada, região e período acompanham os filtros, assim como os indicadores e a tabela. Clique em uma barra para filtrar e novamente para remover o filtro. Os totais se referem a registros de programação, não a projetos distintos. A paginação não altera os gráficos nem o total exportado.

Use a barra horizontal da tabela para acessar todas as colunas. Os cabeçalhos permitem ordenar. Os filtros de data são inclusivos e usam Data Programacao. O relógio mostra a hora do dispositivo no fuso de Brasília.

## Importar e publicar uma nova base

1. Clique em **Importar Excel / CSV**, selecione um `.xlsx` sem senha ou um `.csv` de até 20 MB e escolha a aba.
2. Mantenha as 11 colunas da base atual; a ordem é livre e colunas extras são preservadas. Datas: DD/MM/AAAA, AAAA-MM-DD ou datas nativas do Excel. Recalcule e salve fórmulas no Excel antes da importação.
3. Informe a data de atualização, confira o total e confirme. Arquivos inválidos não substituem a base.
4. A importação vale apenas na sessão atual. Clique em **Baixar site atualizado** para salvar o `index.html` completo com a base importada.
5. Substitua o `index.html` na raiz do repositório e aguarde a publicação pelo GitHub Pages. Use Ctrl+F5 se a versão anterior permanecer em cache.

Atualizar somente `data.js` não atualiza o site atual: os dados estão incorporados ao `index.html`. `base_original.xlsx` contém a cópia integral da fonte usada na atualização do repositório. O `data.js` foi sincronizado para consistência com a base incorporada.

## Exportar

Escolha **Resultado dos filtros** ou **Base completa** e clique em Excel ou CSV. Todos os registros selecionados e todas as colunas são exportados, independentemente da paginação. O Excel mantém valores como texto para preservar códigos e datas apresentados. CSV usa UTF-8 com BOM e ponto e vírgula; conteúdo iniciado por =, +, - ou @ recebe apóstrofo de proteção.

Consulte também `LEIA-ME.txt`. Não existe sincronização automática com o sistema Sigeo.
