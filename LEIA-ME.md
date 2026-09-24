# Programação projetos Sigeo

Site estático pronto para GitHub Pages. Não exige instalação, conta, compilação ou serviços externos. Abra index.html no navegador para usar no computador; mantenha todos os arquivos juntos.

## Publicar no GitHub

1. Extraia o ZIP.
2. Crie um repositório, por exemplo `Programacao_projetos_Sigeo`.
3. Envie **o conteúdo da pasta**, incluindo `index.html`, `styles.css`, `app.js`, `excel.js`, `charts.js`, `data.js`, `.nojekyll` e a pasta `vendor`, para a raiz do repositório. O index.html deve estar diretamente na raiz, não dentro de outra pasta.
4. Em **Settings → Pages**, escolha **Deploy from a branch**, branch **main**, pasta **/(root)**, e clique em **Save**.
5. Aguarde a publicação. O endereço esperado para esse nome de repositório é `https://gilmar655.github.io/Programacao_projetos_Sigeo/`. Esse endereço depende da publicação feita no GitHub.

## Conteúdo da base inicial

- Fonte: `Programação_24_09_ ate dezembro.xlsx`, aba Dados.
- Data de atualização exibida: **24/09/2026**, conforme a identificação do arquivo fornecido.
- 460 programações, 423 projetos distintos, 11 colunas e 10 contratadas.
- Datas efetivamente presentes: **24/09/2026 a 31/10/2026**. A base não contém programações de novembro ou dezembro.
- 218 liberadas para execução; 194 liberadas para documentação; 38 pendentes de aprovação; 10 rascunhos.
- Não há linhas integralmente duplicadas. As repetições de projeto foram preservadas, pois podem representar programações diferentes.
- Campos vazios aparecem como “—” na tabela e permanecem vazios nos arquivos exportados.
- “Empresa Executante” contém descrições de serviços. O cabeçalho original foi preservado; a empresa é filtrada por “Contratada”.
- Todos os valores e 11 campos da base foram preservados, incluindo datas completas nos campos de início e fim. Não há ligação automática com o sistema Sigeo.

## Consultar e exportar

Os filtros atuam em conjunto. A busca pesquisa todas as colunas. Os filtros por coluna aceitam trechos de texto, sem diferenciar maiúsculas ou acentos. Os filtros de data são inclusivos e usam Data Programacao. Os indicadores e a tabela refletem o resultado.

Use a barra horizontal da tabela para ver todas as colunas. A primeira coluna e o cabeçalho ficam fixos. Clique em um cabeçalho para ordenar. “Linhas por página → Todas” exibe todos os resultados.

Em Exportar, escolha **Resultado dos filtros** ou **Base completa**, depois Excel ou CSV. A exportação inclui todas as linhas do resultado, independentemente da paginação, e todas as colunas. Excel gera um `.xlsx` real, com filtro e cabeçalho fixo. Os valores são exportados como texto para preservar códigos, datas apresentadas e zeros iniciais. CSV usa UTF-8 com BOM, separador ponto e vírgula e campos entre aspas. Conteúdo iniciado por =, +, - ou @ recebe apóstrofo de proteção no CSV.

## Gráficos interativos

A seção Gráficos das programações contém cinco gráficos:

- Status da programação: barras com quantidades e percentuais.
- Tipo de intervenção: distribuição por modalidade.
- Contratada: todas as contratadas do resultado, em ordem de quantidade.
- Região: todas as regiões informadas na base.
- Programações ao longo do tempo: linha com agrupamento por dia ou mês.

Todos usam o mesmo resultado dos filtros da tabela, antes da paginação. A unidade é **programação (registro)**, não projeto distinto. A base original possui 460 registros e 423 projetos distintos.

Clique em uma barra para aplicar o filtro correspondente; clique novamente para removê-lo. Os outros filtros são mantidos. Percentuais usam o total filtrado. As barras começam em zero e são proporcionais à maior quantidade do respectivo gráfico.

O gráfico temporal inclui dias ou meses sem programação registrada entre a primeira e a última data do resultado, com valor zero. Registros sem data válida são informados e excluídos apenas do gráfico temporal. Acima de 730 dias, o agrupamento passa automaticamente para mensal. Passe o mouse sobre um ponto para ver o valor ou abra “Consultar quantidades por período”.

Os gráficos são atualizados após novas importações e funcionam sem bibliotecas externas ou conexão com CDN. Use “Ver base de dados” para acessar a tabela abaixo dos gráficos.

## Importar e atualizar o site

1. Clique em **Importar Excel / CSV** e selecione um `.xlsx` sem senha ou `.csv` de até 20 MB. Arquivos `.xls` antigos devem ser salvos como `.xlsx` no Excel antes.
2. Escolha a aba, se houver mais de uma. Cabeçalhos podem estar nas primeiras 20 linhas.
3. Informe o dia real de atualização da base. O valor sugerido é a data atual de Brasília.
4. Confira a quantidade e confirme. A base é substituída apenas depois da validação; arquivos inválidos não apagam a base atual.
5. A importação vale **somente nesta sessão do navegador**. Recarregar a página volta à base publicada.
6. Para tornar a atualização permanente para todos, clique em **Baixar base para publicação**. Substitua o arquivo **data.js** na raiz do repositório pelo arquivo baixado e confirme a alteração no GitHub. O arquivo inclui toda a base e a data de atualização informada, mesmo com filtros ativos.
7. Aguarde o GitHub Pages atualizar e recarregue a página. Se necessário, pressione Ctrl+F5.

Cabeçalhos obrigatórios (ordem livre; acentos e maiúsculas são aceitos):

`Projeto; Empresa Executante; Data Programacao; Status Programacao; Tipo Intervencao; Numero PowerON; Equipamentos; Regiao; Horario Inicio; Horario Fim; Contratada`

Colunas extras são preservadas. Datas de programação devem ser datas Excel ou textos DD/MM/AAAA ou AAAA-MM-DD. Células de fórmulas usam o resultado salvo no arquivo: recalcule e salve no Excel antes de importar. A importação não executa macros ou fórmulas. Limites: 100.000 registros e 256 colunas; bases muito grandes podem ficar lentas no navegador.

## Arquivos

- `index.html`: página principal.
- `styles.css`: aparência responsiva.
- `app.js`: filtros, tabela, relógio, importação e exportação.
- `charts.js`: gráficos interativos sincronizados com os filtros.
- `excel.js`: leitura e escrita de tabelas Excel/CSV.
- `data.js`: base de dados inicial e data de atualização; é o arquivo substituído nas atualizações.
- `vendor/jszip.min.js`: biblioteca local para arquivos Excel, com licença incluída.
- `base_original.xlsx`: cópia integral da planilha recebida, para conferência.
- `.nojekyll`: compatibilidade com GitHub Pages.

O relógio usa a hora do dispositivo no fuso America/Sao_Paulo e é atualizado a cada segundo. Não depende de uma conexão com servidor de horário. O site funciona sem baixar bibliotecas de CDN.

Referência: [Carteira Start Sigeo](https://gilmar655.github.io/Carteira_Start_Sigeo/). O código do site de referência foi consultado no repositório para manter a lógica de filtros, indicadores e tabela. O novo painel apresenta cores claras, todas as colunas da nova base em destaque, relógio e atualização da base para publicação.
