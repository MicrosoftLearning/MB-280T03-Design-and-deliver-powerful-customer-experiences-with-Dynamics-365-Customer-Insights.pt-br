---
lab:
  title: 'Laboratório 3.1: Fazer upload de ativos'
---

# Módulo 3: Gerenciar clientes e ativos no Dynamics 365 Customer Insights - Journeys

## Laboratório 3.1: Fazer upload de ativos

### Visão geral do laboratório

#### Cenário
A Contoso Coffee vende máquinas de café industriais e domésticas para proprietários de empresas de café que usam máquinas de café da Contoso em suas lojas individuais, empresas que têm máquinas de café da Contoso em seus escritórios corporativos e clientes individuais que usam máquinas de café da Contoso em suas casas. Este ano, a empresa está lançando um novo produto chamado Máquina de Café Airpot XL Smart. Eles planejam comercializar este novo produto para empresas e indivíduos.

A equipe de marketing decide montar uma campanha de venda cruzada para incentivar os clientes atuais a considerar a atualização para a nova máquina de café inteligente. Eles planejam enviar uma série de emails com uma chamada para ação para o cliente clicar em um link que acionará um telefonema de um representante de vendas. Eles planejam executar esta campanha por dois meses.


Para esta campanha, o Coordenador de Marketing precisará:
- Fazer upload de ativos de marketing para usar nas campanhas de email.
- Criar os emails de marketing para enviar aos clientes.
- Criar a jornada que automatizará a entrega do conteúdo da campanha.

Para começar, o Coordenador de Marketing precisa fazer o upload dos ativos digitais que serão usados na campanha. Também será necessário fazer upload de todos os novos contatos de vendas que a empresa adquiriu recentemente e atualizar os detalhes dos contatos e contas existentes.

## Visão geral do laboratório
Este laboratório é composto por quatro tarefas:
1. Na primeira tarefa, você fará upload de arquivos de imagem para serem usados em emails de marketing. Esses arquivos serão carregados na biblioteca de ativos em tempo real.
2. Na segunda tarefa, você atualizará os detalhes dos contatos existentes no Dynamics 365 Customer Insights - Journeys.
3. Na terceira tarefa, você criará um modelo de tarefa que será usado na jornada.
4. Na quarta tarefa, você configurará o perfil de marca padrão a ser usado em seus ativos de marketing (como emails).

### Será necessário:
- Um computador ou VM com um ambiente do Dynamics 365 Customer Insights - Journeys
- Os arquivos de imagem a serem usados no conteúdo de marketing. Eles podem ser encontrados no host do laboratório autorizado ou no arquivo **MB-280T03-Assets.zip** na pasta Instructions/Labs/Media no repositório GitHub. Pergunte ao instrutor se você tiver problemas para encontrá-los.

### Exercício 1: Preparar os ativos de marketing 
## Tarefa 1: Carregar as imagens na biblioteca de ativos
1. Faça o download dos arquivos de imagem dos documentos de recurso. Extraia os arquivos em uma pasta em sua área de trabalho.
2. Faça logon no Dynamics 365 Customer Insights - Journeys com suas credenciais de administrador.
3. Por padrão, abrirá a área Jornadas em tempo real. Confirme se você está na área Jornadas em tempo real abrindo o seletor de área no canto inferior esquerdo da tela.
4. No menu à esquerda, navegue até a seção Ativos. Selecione **Biblioteca**. Clique no botão **+ Novo** para abrir a janela de upload de arquivos.
5. Selecione **+ Adicionar arquivos**, localize os arquivos de imagem no computador local e selecione-os.
6. Enquanto a janela de upload estiver aberta, adicione uma marca do logotipo a contosologo.png. (Comece digitando logo na caixa de texto abaixo do nome do arquivo de imagem. Depois de digitar o *logotipo*, selecione o que você acabou de digitar. Uma marca será adicionada abaixo do nome do arquivo).
7. Escolha **Carregar**. Certifique-se de que os arquivos de imagem foram carregados– uma marca de seleção verde com Concluído aparecerá para cada arquivo. (Pode levar alguns minutos para que os arquivos carreguem.) Clique em **Fechar**.
8. Usando a caixa de pesquisa Filtrar por palavra-chave, digite *con* e pressione enter. Por padrão, esse filtro pesquisa pelo nome do arquivo. Verifique se contosologo.png aparece nos resultados da pesquisa.

Esses arquivos agora ficarão disponíveis para os usuários incorporarem em suas operações de marketing.

### Tarefa 2: Atualizar contatos existentes
1. Faça logon no Dynamics 365 Customer Insights - Journeys. Certifique-se de estar na área Jornadas em tempo real.
2. No painel de navegação à esquerda, selecione **Contatos** no grupo Público-alvo.
3. Abra o contato **Alva Tharaldsen.**
   - Em Nome da conta, selecione **Bellows College**. Em seguida, você navegará até o registro da conta Bellows College.
   - Role para baixo até a subgrade **Contatos**. Todos os contatos associados a Bellows College estão listados aqui. Clique na reticências vertical na parte superior da subgrade, clique em **Selecionar** e use as caixas de seleção para selecionar todos os contatos da lista de uma só vez.
   - Na parte superior da subgrade Contatos, clique na **reticências vertical**. Em seguida, selecione **Editar**.
   - Na guia Detalhes, localize o campo Anotações Pessoais. Digite "Proprietário da Airpot" no campo. Selecione **Salvar**.
   - Selecione um dos contatos que não seja Alva. Navegue até a guia **Detalhes**. Verifique se "Proprietário da Airpot" aparece no campo Notas pessoais.
4. Navegue de volta para a entidade **Contatos** no grupo Público-alvo. 
5. Defina um filtro em Nome da empresa:
   - Clique na **seta suspensa** ao lado de Nome da empresa. Selecione **Filtrar Por**. Escolha **Igual a** e, em seguida, selecione **Lucerne Publishing, Southridge Video** e **Wingtip Toys**. (Você pode selecionar as contas clicando no nome diretamente na lista ou começando a digitar o nome e selecionando o Nome da conta quando ele aparecer). Clique em **Aplicar**.
   - Selecione todos os contatos para essas três contas. (Você pode selecionar a marca de seleção ao lado de Nome completo no cabeçalho da exibição para selecionar todos os contatos de uma vez.)
   - Selecione **Editar** na barra de comandos. Insira o seguinte:
     - **Endereço 1: Cidade:** Bellevue
     - **Endereço 1: Estado/Província:** Washington
     - **Detalhes > Notas Pessoais:** Proprietário da Airpot
     - Selecione **Salvar**.
6. Altere o filtro no Nome da empresa:
   - Clique na **seta suspensa** ao lado de Nome da empresa. Selecione **Limpar filtro**.
   - Clique na **seta suspensa** novamente. Selecione **Filtrar por**. Selecione **Adatum Corporation** e **Northwind Traders**. Escolha **Aplicar**.
   - Selecione todos os contatos para essas duas contas.
   - Selecione **Editar** na barra de comandos. Insira o seguinte:
     - **Endereço 1: Cidade:** Redmond
     - **Endereço 1: Estado/Província:** Washington
     - **Detalhes > Notas Pessoais:** Proprietário da Airpot
     - Selecione **Salvar**.
7. Altere o filtro no Nome da empresa:
   - Clique na **seta suspensa** ao lado de Nome da empresa. Selecione **Limpar filtros**.
   - Selecione a seta suspensa novamente e selecione **Filtrar por**. Selecione **Trey Research**, **The Phone Company** e **Wide World Importers**. Escolha **Aplicar**.
   - Selecione todos os contatos para essas três contas.
   - Selecione Editar na barra de comandos. Insira o seguinte:
     - **Endereço 1: Cidade:** Seattle
     - **Endereço 1: Estado/Província:** Washington
     - **Detalhes > Notas Pessoais:** Proprietário da Airpot
     - Selecione **Salvar**.

### Tarefa 3: Criar um modelo de tarefa
1. Faça logon no Dynamics 365 Customer Insights - Journeys com suas credenciais de administrador.
2. No grupo **Ativos**, navegue até **Modelos de tarefa**.
3. Selecione **+ Novo**.
   - Nome: Verificar com o cliente
   - Assunto: Atualização da Airpot para Máquina de Café Airpot XL Smart
   - Tipo de agendamento: Atraso (em dias).
   - Atraso de início: 0.
4. Na seção Hora de início, selecione **01** para Hora. Deixe Minuto em branco.
4. Selecione **Salvar e Fechar**.

### Exercício 4: Configurar o perfil de marca padrão
1. Faça logon no Dynamics 365 Customer Insights - Journeys. Altere a área para **Configurações**.
2. No grupo **Participação do cliente**, navegue até **Perfis da marca**.
3. Selecione o **Perfil da marca padrão.**
4. Navegue até a guia **Remetentes**. Você verá o registro do remetente padrão na subgrade. 
5. Selecione a guia Links de redes sociais. Preencha o seguinte:
    - URL do LinkedIn: https://www.linkedin.com/company/contoso12345/about/
    - URL do Twitter: https://twitter.com/ContosoInc
    - URL do Facebook: https://www.facebook.com/Contoso-102137176602590/
6. Selecione **Salvar e Fechar**.

