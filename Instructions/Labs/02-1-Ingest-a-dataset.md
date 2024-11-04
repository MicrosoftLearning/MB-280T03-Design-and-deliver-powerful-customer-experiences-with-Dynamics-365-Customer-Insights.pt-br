---
lab:
  title: 'Laboratório 2.1: Ingerir um conjunto de dados'
---

# Módulo 2: Ingerir dados no Dynamics 365 Customer Insights - Data

## Cenário do laboratório: Contoso Coffee
A Contoso Coffees produz café e máquinas de café de alta qualidade, vendidas por meio de canais que incluem as novas lojas da Contoso Retail em locais privilegiados, revendedores de alimentos de luxo e no site da Contoso Coffee. A Contoso planeja ampliar suas ofertas com cafés da Contoso e uma nova máquina de café conectada, que pode disparar ordens de reabastecimento e alertar o serviço da Contoso sobre problemas. Essa nova oferta ajudará a empresa a construir relacionamentos diretos com seus clientes e aprender mais sobre como os clientes consomem seus produtos.

### Desafios da Contoso Coffee
- **Relacionamento transacional:** o modelo de negócios atual da empresa significa que eles não têm um relacionamento direto com os clientes.
- **Silos de dados:** eles não conseguem oferecer experiências do cliente personalizadas.

### Cenário de dados existente da Contoso
- **Dados de clientes fragmentados:** com vários sistemas, a Contoso tem vários registros para a mesma pessoa. Isso causa uma experiência desconexa para o cliente, que espera ser tratado como uma pessoa, independentemente do canal em que a transação ocorra.
- **Várias plataformas:** a arquitetura da Contoso evoluiu por meio de aquisição e sistemas herdados, o que significa que os dados podem residir não apenas em sistemas diferentes, mas em plataformas diferentes em várias nuvens e no local.
- **Dados que não são do cliente:** a Contoso está traçando correlações entre dados que não são do cliente e o impacto que eles têm nas experiências do cliente, incluindo dados de terceiros, como dados meteorológicos.

### Projeto do Customer Insights da Contoso Coffee
Escolheram você para ser gerente de projeto da implementação do Dynamics 365 Customer Insights na Contoso Coffees. Como gerente de projeto experiente, você elabora o seguinte plano:
1. Criar um ambiente do Customer Insights
2. Ingerir os dados das fontes de dados de maior prioridade da empresa:
   - Ponto de venda (PDV)
   - Dados de fidelidade
   - Clientes de comércio eletrônico
   - Compras na Web
3. Criar um perfil unificado do cliente com base nos dados ingeridos

## Introdução do módulo

### Pré-requisitos do laboratório:
Antes de iniciar este exercício, você deve ter concluído o Laboratório 0 para configurar seu ambiente.

### Ingestão e unificação de dados
Como Gerente de Projeto da Contoso Retail, você criará um perfil de cliente unificado ingerindo as principais fontes de dados do cliente e seguindo o processo de Mapeamento, Correspondência e Mesclagem. Neste laboratório, vamos ingerir dados. No próximo laboratório, unificaremos os dados.

**Tempo estimado para conclusão:** 45 minutos

### Familiarize-se com o Customer Insights - Data
Nesta tarefa, você explorará o ambiente de demonstração pré-configurado para se familiarizar com a movimentação no aplicativo Customer Insights – Data.
1. Entre no Customer Insights - Data em https://home.ci.ai.dynamics.com se ainda não tiver entrado.
2. No seletor Ambiente no canto superior direito, confirme se **Avaliação de Marketing** está selecionado.
3. Explore as opções do menu à esquerda para se familiarizar com a navegação:
   - **Página inicial:** Home Page
   - **Clientes:** visualize cartões para perfis de clientes unificados (você ainda não conseguirá ver isso; primeiro precisamos ingerir e unificar os dados)
   - **Dados > Fontes de dados:** ingerir dados demográficos, transacionais ou comportamentais em silos. Mapeie, combine e mescle em um Perfil do Cliente Unificado. Visualize suas entidades e defina os tipos de atividade e seus relacionamentos com seus clientes.
   - **Dados > Enriquecimento:** vá além do seu perfil unificado e enriqueça os perfis de clientes com dados proprietários da Microsoft. Desbloqueia dados de acordo com as afinidades de centenas de marcas e dezenas de categorias de interesse. Essas afinidades são extraídas para perfis que podem ser semelhantes aos dos seus clientes.
   - **Insights > Segmentos, Medidas e Previsões:** visualize segmentos, configure medidas e use modelos de previsão prontos para uso (ou crie seus próprios). (Você ainda não conseguirá visualizar esta seção.)
   - **Configurações**: administre funções, permissões, APIs e destinos de exportação para segmentos de clientes.

## Exercício 1 – Ingestão de dados
Neste laboratório, você se familiarizará com a ingestão de dados a partir de várias fontes. Como gerente de projeto da Contoso Retail, você já identificou fontes de dados importantes, como clientes de comércio eletrônico, compras online, compras de pontos de vendas na loja e dados do esquema do cartão-fidelidade da Contoso Retail.

### Tarefa 1 – Ingerir dados do cliente a partir da plataforma de comércio eletrônico
1. Entre no Customer Insights em http://home.ci.ai.dynamics.com e verifique se **Avaliação de Marketing** está selecionado no menu suspenso no canto superior direito.
2. No Customer Insights, expanda **Dados** no menu de navegação esquerdo e selecione **Fontes de Dados**.
3. Selecione **+ Adicionar uma fonte de dados**. Veja os métodos disponíveis de ingestão de dados. Para este laboratório, escolha Microsoft Power Query, nomeie o *Comércio eletrônico* de origem e clique em **Avançar**.
4. Você verá uma tela com as fonte de dados do Power Query que o Customer Insights pode ingerir. Anote os tipos de conectores disponíveis. Selecione o conector **Texto/CSV**.
5. Insira https://aka.ms/CI-ILT/Contacts em Caminho do arquivo ou URL e clique em **Avançar**. Pode demorar um pouco para que os dados carreguem.
6. Agora você deve ver os dados da fonte tabulados. Selecione **Transformar dados** para configurar os tipos e formatos dos dados que serão ingeridos.
7. Você observará que o cabeçalho da coluna foi mostrado na primeira linha dos dados. Para corrigir isso, selecione **Transformar > Usar a primeira linha como cabeçalhos** na guia Página Inicial ou selecione a guia **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.
8. Como ingerimos os dados de uma fonte de Texto/CSV, todas as colunas são padronizadas como o tipo de dados "Texto". Para ingerir e modelar os dados com êxito, podemos definir o tipo de dados como colunas que não são de texto. Para alterar o tipo de dados, selecione o ícone ABC no título de cada coluna. Atualize o tipo de dados das colunas:
   - **DateOfBirth**: Data
   - **CreatedOn:** Data
   - **Income:** Moeda
9. Verifique se o campo Nome no painel Configurações de consulta está definido como Contatos. Selecione **Avançar**. Selecione **Salvar**.
   - Parabéns. Você criou sua primeira fonte de dados com um conjunto de dados. Continuaremos importando o próximo conjunto de dados na próxima tarefa.

## Tarefa 2 – Ingerir dados de compras online
Nesta tarefa, você vai ingerir os dados de compras online, que representam as compras feitas no site da Contoso Coffee.

1. No Customer Insights, expanda **Dados** no menu à esquerda e selecione **Fontes de dados**.
2. Em *Gerenciado por mim (1)*, selecione o conjunto de dados de **Comércio eletrônico** e selecione **Editar**. Selecione **Avançar**.
   - **Observação:** se seus dados ainda estiverem sendo atualizados, você precisará aguardar a conclusão antes de editar. Você pode pular direto para a Tarefa 3 e retornar à Tarefa 2 depois de concluir as Tarefas 3 a 5.
3. Você verá a tela do Power Query com os dados de Contatos de Comércio eletrônico ingeridos na Tarefa 1. Na guia **Página Inicial**, selecione **Obter dados**.
4. Você verá uma tela com os conectores de fonte de dados que o Customer Insights pode ingerir. Selecione o conector **Texto/CSV**.
5. Insira https://aka.ms/CI-ILT/OnlinePurchases em Caminho do arquivo ou URL e clique em **Avançar**. Selecione **Criar**.
6. Como antes, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.
7. Atualize os tipos de dados para as seguintes colunas:
   - **PurchasedOn:** Data
   - **TotalPrice**: Moeda
8. Nomeie essa consulta como *Compras* e clique em **Salvar**.

## Tarefa 3 – Ingerir dados do cliente do esquema de fidelidade
1. No Customer Insights, expanda **Dados** no menu à esquerda e selecione **Fontes de dados**.
2. Clique em **+Adicionar uma Fonte de Dados** e escolha **Microsoft Power Query** como o método de importação. Nomeie a fonte como *Lealdade* e clique em **Avançar**.
3. Selecione o conector **Texto/CSV**.
4. Insira https://aka.ms/CI-ILT/LoyaltySchemeCustomers em Caminho do arquivo ou URL, clique em **Avançar** e, em seguida, em **Transformar dados**.
5. Como antes, selecione Transformar e, em seguida, Usar a primeira linha como cabeçalhos.
6. Atualize o tipo de dados das colunas:
   - **DateOfBirth**: Data
   - **RewardPoints**: Número inteiro
   - **CreatedOn:** Data
7. Renomeie essa consulta para *Clientes* no painel Configurações de consulta e clique em **Avançar**.
8. Na tela de atualização, clique em **Salvar**.

## Tarefa 4 – Ingerir dados do cliente de compras no ponto de venda
1. No Customer Insights, expanda **Dados** no menu de navegação esquerdo e selecione **Fontes de Dados**.
2. Selecione **+ Adicionar uma fonte de dados**, escolha **Microsoft Power Query** e nomeie o *PoS* de origem e clique em **Avançar**.
3. Selecione o conector **Texto/CSV**.
4. Digite https://aka.ms/CI-ILT/POSPurchases em Caminho do arquivo ou URL. Clique em **Avançar** e **Transformar dados**.
5. Como antes, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.
6. Atualize o tipo de dados das colunas:
   - **PurchasedOn:** Data
   - **TotalPrice**: Moeda
   - **RewardPointsAdded:** Número inteiro
7. No campo **Nome** do painel Configurações da consulta, renomeie a consulta para *Compras*. Selecione **Avançar**.
8. Na tela de atualização de dados, clique em **Salvar**.

## Tarefa 5 – Ingerir os dados dos clientes a partir das avaliações do site
1. No Customer Insights, expanda **Dados** no menu de navegação esquerdo e selecione **Fontes de Dados**.
2. Selecione **+ Adicionar uma fonte de dados**. Escolha **Microsoft Power Query**, nomeie o *Site* de origem e clique em **Avançar**.
3. Selecione o conector **Texto/CSV**.
4. Digite https://aka.ms/CI-ILT/WebReviews em Caminho do arquivo ou URL. Clique em **Avançar** e **Transformar dados**.
5. Como antes, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.
6. Atualize o tipo de dados das colunas:
   - **ReviewRating**: Número inteiro
   - **ReviewDate**: Data
7. No campo **Nome** no painel Configurações da consulta, renomeie a consulta para *Revisões*. Selecione **Avançar**.
8. Na tela Configurações de atualização, selecione **Salvar**.
