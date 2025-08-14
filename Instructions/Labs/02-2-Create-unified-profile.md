---
lab:
  title: 'Laboratório 2.2: Criar um perfil do cliente unificado'
---

# Laboratório 2.2: Criar um perfil do cliente unificado

## Roteiro de aprendizagem 2: Trabalhar com perfis do cliente unificados no Dynamics 365 Customer Insights - Data

Depois de ingerir os dados brutos das fontes de dados nas entidades, você iniciará o processo de mapear, corresponder e mesclar para criar um Perfil unificado do cliente mesclando os dados de cada fonte de perfil do cliente. Para concluir esse processo, primeiro mapeie as entidades ingeridas em relação a um modelo padrão e selecione Chave primária para cada uma das entidades incluídas no perfil. Feito isso, você criará sua Regra de correspondência que será usada para corresponder contatos de todas as entidades do cliente. Por fim, execute o processo Mesclar para criar um único conjunto de clientes exclusivos que têm perfis correspondentes de todas as entidades de clientes que usam suas regras de correspondência. O objetivo é descobrir quantos perfis de clientes exclusivos a Contoso Retail tem em várias fontes de dados.

## Exercício 1 – Unificar os dados

### Tarefa 1 – Mapear contatos para tipos de dados comuns
1. Entre no Customer Insights - Data em https://home.ci.ai.dynamics.com.
2. No painel de navegação à esquerda, expanda **Dados** e selecione **Unificar**.
3. Na seção Dados do cliente, selecione **Introdução**.
4. Na tela **Descrever os dados do cliente a serem unificados**, selecione **+ Introdução**.
5. Selecione as tabelas que representarão o perfil do cliente. As tabelas são:
   - Contatos (Comércio Eletrônico)
   - Clientes (Lealdade)
6. Escolha **Aplicar**.
7. Agora você verá os mapeamentos da tabela de origem referentes aos tipos de modelo padrão. É possível examinar os tipos na tabela.
8. Escolha uma "Chave primária" para cada entidade que foi ingerida. A chave primária deve ser uma referência exclusiva. Para Contatos de comércio eletrônico, selecione **ContactId** como a chave primária.
9. Os dados dos Contatos de comércio eletrônico contêm uma coluna chamada **Assinante de email** que será mapeada para um tipo incorreto, Identity.Service.Email, devido ao nome. Abra o menu suspenso desta coluna e selecione a opção vazia (nada/em branco). Se não fizermos isso, o comportamento padrão do sistema é mesclar esse campo com o campo Email, o que não queremos.
10. Selecione **Lealdade do clientes** em Tabelas e defina **LoyaltyId** como a chave primária.
11. Selecione **Salvar colunas de origem** no canto superior esquerdo.
12. Clique no botão **Avançar** e, em seguida, em **Avançar** novamente para ignorar a verificação de duplicatas e passar para a etapa Regras de correspondência.

### Tarefa 2 – Especificar ordem de correspondência
No próximo estágio, você deve selecionar a ordem na qual mesclar os perfis. Você poderá mesclar atributos para garantir que os perfis unificados estejam completos e definir a prioridade das fontes que serão usadas para esses atributos.
1. Você deve selecionar a fonte de perfil mais completa ou precisa como a fonte primária (primeira). Verifique se **Contatos: comércio eletrônico** é a fonte primária (primeira) (ou mova-a se ainda não for).
2. Selecione a marca de seleção para **Incluir todos os registros**.
3. Verifique se **Clientes: Fidelidade** é a segunda fonte na lista. Escolha **Incluir todos** os registros.

### Tarefa 3 – Criar uma regra de correspondência
Nesta tarefa, você criará uma regra simples que será usada para fazer a correspondência dos registros em conjunto. As regras podem ter uma condição (por exemplo, com base na ID) ou várias condições (por exemplo, nome completo, código postal, data de nascimento). Para mais detalhes sobre as Regras de correspondência, consulte a documentação do Customer Insights.
1. Há um indicador de aviso na **linha Clientes: Fidelidade**. Clique em **+ Adicionar regra** ou clique no ícone **+** à direita.
2. Adicione sua primeira condição usando FullName:
   - Para a tabela Contatos: comércio eletrônico, selecione o campo **FullName**.
   - Para a tabela Clientes: Fidelidade, selecione o campo **FullName**.
   - Deixe o menu suspenso Normalizar em branco.
   - Defina o Nível de Precisão como **Básico** usando o campo suspenso.
   - Defina o Valor de Precisão como **Alto** usando o controle deslizante.
3. Insira **FullName, Email** para a regra.
4. Adicione uma segunda condição para o endereço de email clicando em **+ Adicionar** e escolhendo **Adicionar condição**.
   - Para a tabela Contatos: comércio eletrônico, selecione o campo **Email**.
   - Para a tabela Clientes: Fidelidade, selecione o campo **Email**.
   - Deixe o menu suspenso Normalizar em branco.
   - Defina o Nível de Precisão como **Básico**.
   - Defina o valor de Precisão como **Alto**.
5. Selecione **Concluído**.
6. Clique em **Avançar,** **Avançar** e selecione **Criar perfis do cliente**.

Agora, o Customer Insights está fazendo a correspondência dos dados dos clientes com base em todas as fontes de informações dos clientes para identificar quantos perfis de clientes exclusivos você tem com base nas suas regras. Converse com a turma: quantos clientes exclusivos você tem ao combinar os conjuntos de dados?

### Tarefa 4 – Precisão
Na Tarefa 3, usamos Alta Precisão na regra de correspondência para Nome Completo. Nesta tarefa, você ajustará o nível de precisão para criar um número maior de correspondências incluindo correspondências de menor confiança (resultando em um número menor de perfis exclusivos).

**Observações sobre Precisão:**
- Exata no lado direito da escala corresponderá aos registros em que sua condição tem uma correspondência exata. Selecione um dos outros níveis para corresponder aos registros que não são 100% idênticos.
- Alto é para os casos em que a precisão é mais importante do que o alcance, como um serviço financeiro para um cliente específico.
- Baixo é para casos em que o oposto é verdadeiro, como uma campanha de marketing.
- O nível Médio serve como uma opção intermediária.

1. No Customer Insights, expanda **Dados** no menu de navegação à esquerda. Selecione **Unificar.**
2. Em Regras de correspondência, selecione **Editar**.
3. Expanda a regra **Clientes: Fidelidade** e clique no botão **Editar** para abrir o painel de condições **FullName, Email**.
4. Em Condição 1, selecione **Visualizar** e anote os valores. Mude o controle deslizante Precisão para a Condição 1 de **Alto** para **Baixo**. Selecione **Concluído**.
5. Selecione **Avançar**, **Avançar** e **Criar perfis de cliente**.
6. Aguarde o processo de correspondência ser concluído.
7. Depois que o processo de correspondência for concluído, clique em **Editar** nas regras de correspondência. Selecione o **menu de pontos verticais** ao lado da regra **FullName, Email** e selecione **Visualização** para ver os resultados da correspondência e a pontuação. Isso mostra como o Customer Insights correspondeu às tabelas de dados com base nas regras que você definiu. Alguns perfis foram criados com uma menor confiança de correspondência.
8. Feche a visualização e clique em Editar. Clique no botão Visualização abaixo da Condição 1. Aqui você pode visualizar o número de registros que Não correspondem e Correspondem para a condição FullName.
9. Selecione **Visualizar dados** em Não correspondem ou Correspondem para visualizar as correspondências. Observe como as pontuações mais altas têm ortografia exata, mas podem corresponder mesmo que o formato do nome (Nome, Sobrenome / Sobrenome, Nome) seja diferente. Com as pontuações baixas, observe como as correspondências são feitas mesmo quando os nomes não são escritos de forma idêntica.
10. Feche o painel de visualização Critérios e selecione **Cancelar**.

Converse com a turma: quantos perfis exclusivos de clientes vocês têm agora?

### Tarefa 5 – Unificar campos de cliente
Esta é a última fase do processo de unificação de dados. A finalidade é reconciliar os dados conflitantes e definir os atributos que serão usados no perfil unificado do cliente. Um atributo mesclado existe em mais de uma fonte de dados e representa os mesmos dados. Por exemplo, você pode ter um "Endereço de Email" nas fontes de dados de Clientes de comércio eletrônico e de Clientes de Fidelidade. O Customer Insights tentará identificar os atributos a serem mesclados com os tipos de dados padrão que definimos na etapa Campos de origem.

1. No Customer Insights, expanda **Dados** no menu de navegação à esquerda. Selecione **Unificar.**
2. Na exibição Dados unificados, clique em **Editar**.
3. Em Colunas do cliente, observe como os atributos de diferentes fontes de dados do mesmo tipo (por exemplo, Nome) mesclaram.
4. Expanda o atributo mesclado **FirstName**. Você verá que o atributo FirstName em eCommerce: Contacts está classificado como número 1. Isso indica que, quando você tem um perfil do cliente correspondente tanto para LoyaltyScheme quanto para eCommerce, o nome obtido de eCommerce: Contacts é o principal.
9. Clique em **Avançar** e selecione **Criar perfis de cliente**.
10. Aguarde a conclusão do processo.

Parabéns! Você ingeriu, mapeou, fez a correspondência e mesclou os dados de várias fontes no Customer Insights para criar um Perfil unificado do cliente que pode ser usado para obter insights de toda a sua base de clientes.

## Exercício 2 – Pesquisar clientes
Neste exercício, configuraremos os critérios de Pesquisa e Filtro para permitir que os usuários do Customer Insights pesquisem perfis unificados do cliente para que você possa extrair informações sobre um cliente ou grupo de clientes específico de forma rápida.

### Tarefa 1 – Configurar colunas de pesquisa e índices de filtro
1. No Customer Insights, selecione **Clientes** no menu de navegação à esquerda.
2. Selecione **Pesquisar e filtrar índice.**
3. Alguns campos específicos de pesquisa de clientes já são adicionados por padrão e você pode adicionar mais clicando em **+ Adicionar** na barra de ferramentas.
4. Certifique-se de que **CustomerId, FirstName, LastName, FullName, DateOfBirth, EMail, PostCode, ContactId (eCommerce_Contacts)** e **LoyaltyId** estejam selecionados. Desmarque todos os outros campos marcados. Escolha **Aplicar**.
5. Selecione **Salvar**.

### Tarefa 2 – Pesquisar um registro de cliente
1. No Customer Insights, selecione **Clientes** no menu de navegação à esquerda. Você verá um conjunto de cartões de cliente, representando os Perfis Unificados. Você pode expandir os cartões para ver mais sobre o cliente ou classificá-los por vários campos. Tente isso clicando em **Expandir cartões** e **Classificar por** na barra de ferramentas.
2. Você pode usar Pesquisar clientes para pesquisar atributos de texto relacionados a perfis unificados de cliente. Por exemplo, A pesquisa "24502" pesquisará todos os atributos de texto e retornará correspondências e correspondências parciais.)

Use a barra de pesquisa para responder às seguintes perguntas:
- Qual é a data de nascimento de Brian Gobble? (Pesquise Brian Gobble)
- Qual cliente tem o ID do cartão-fidelidade LOYID_5707? (Pesquise LOYID_5707)
- Qual cliente tem um código postal de 24502? (Pesquise 24502)
