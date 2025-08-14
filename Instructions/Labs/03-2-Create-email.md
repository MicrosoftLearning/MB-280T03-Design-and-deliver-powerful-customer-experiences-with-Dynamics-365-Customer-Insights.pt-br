---
lab:
  title: 'Laboratório 3.2: Criar um email'
---

# Roteiro de aprendizagem 3: Gerenciar clientes e ativos no Dynamics 365 Customer Insights - Journeys

## Laboratório prático 3.2: Criar um email

### Visão geral do laboratório

#### Cenário
Para esta campanha, a equipe de marketing planeja fazer uma grande campanho para a mais nova máquina de café inteligente. Eles planejam enviar uma série de três emails. O primeiro email promoverá a máquina de café inteligente da Contoso. O segundo email destina-se a incentivar os proprietários da Airpot regular a fazer upgade para a nova máquina inteligente. O terceiro email é um lembrete sobre o lançamento do novo produto. 

### Visão geral do laboratório
Este laboratório compreende três exercícios:
1. Neste exercício, você criará um email usando um modelo de email.
2. Neste exercício, você criará um email copiando outro email.
3. Neste exercício, você criará um email copiando outro email.

### Será necessário:
- Um computador com um ambiente do Dynamics 365 Customer Insights - Journeys

## Exercício 1: Criar um email de marketing
### Tarefa 1: Criar um email a partir de um modelo
1. Faça logon no Dynamics 365 Customer Insights - Journeys. Certifique-se de estar na **área Jornadas em tempo real**.
2. Navegue até **Emails** no grupo Canais.
3. Clique em **+ Novo** para criar um email.
4. Na galeria de modelos, role para baixo até a seção **Layouts**. Selecione **coluna 1-2** e **Selecionar**.
5. No canto superior à esquerda, altere o nome do email de *Email 1* para *Email da campanha da Smart Machine*. (Ao passar o mouse sobre **Email 1** no canto superior esquerdo, você poderá digitar nessa caixa de texto.)
6. Selecione a **caixa Nome do remetente/Assunto** no designer para exibir os detalhes do cabeçalho do Email.
   - Digite o seguinte no Assunto: "Finalmente, uma máquina de café que me entende."
   - Selecione **Contoso Coffee** como remetente (se ainda não estiver). O nome do remetente e o email do remetente serão preenchidos e serão somente leitura.
7. Localize o menu **Caixa de ferramentas** à direita, que aparecerá como uma série de ícones. Passar o mouse sobre os ícones mostrará o nome de cada guia. Selecione a guia **Tema**, que se parece com um pincel.
   - **Observação:** os detalhes nesta seção afetam todo o email. Se você adicionar novos elementos de texto ao email, o padrão será a fonte, o tamanho e a cor listados aqui. Em seguida, você pode atualizar esses elementos conforme necessário.
   - Altere a **Família de fontes** para: Segoe UI.
   - Altere a **cor do texto do corpo** para: #404040.
   - Altere o **plano de fundo do email** para: #CCCCCC.
8. No próprio e-mail, localize a primeira seção e selecione-a. Uma guia Editar layout será exibida. Altere a cor de fundo da seção para um tom de cinza.

## Tarefa 2: Atualizar imagens
Nesta tarefa, atualizaremos o logotipo.

1. Selecione a imagem na primeira seção do designer.
2. À direita, clique na imagem do espaço reservado. Selecione **Substituir imagem** e, em seguida, escolha **Procurar biblioteca**.
3. Selecione o **logotipo da Contoso** e clique em **Selecionar**.
4. Substitua o texto Alt pelo *logotipo da Contoso*.
5. Selecione o menu suspenso **Vincular para** e, em seguida, selecione **URL**. Digite *www.contoso.com*.
6. Na seção Tamanho e alinhamento, se a largura automática estiver ativada, use o botão de alternância para desativá-la. Insira *150px* para a largura. A outra dimensão será atualizada automaticamente.
7. Em seguida, atualizaremos a segunda imagem do email. Selecione a imagem na seção abaixo do logotipo.
8. Selecione **Substituir imagem** e **Procurar na biblioteca**.
9. Selecione a imagem **hero-page.jpg**. Clique em **Selecionar**.

## Tarefa 3: Atualizar um título usando a personalização
Nesta tarefa, atualizaremos um título para refletir o nome do contato do destinatário.
1. Navegue até a seção de texto abaixo do logotipo e selecione-o.
2. Coloque o cursor no início do texto do cabeçalho e clique em **Personalização** na barra de ferramentas na parte superior do email. Selecione **Nome** no menu suspenso. Certifique-se de que **Contato** esteja selecionado e selecione **Escolher**.
3. Adicione uma vírgula e um espaço após {{Firstname}}.
4. Altere o texto do espaço reservado para: "Deixe suas pausas para o café conosco".
5. Destaque o texto, coloque-o em negrito e altere o tamanho da fonte para *26*.
6. Altere a opção "Personalizar email..." para "Com a nova máquina de café inteligente Airpot XL é como se você tivesse seu próprio barista".
7. Realce o texto e altere o tamanho da fonte para *18*.

## Tarefa 4: Criar o restante do email
1. Selecione a seção de duas colunas abaixo do texto. Altere a cor de fundo da seção para um tom de azul.
2. Na coluna à esquerda, selecione o espaço reservado Imagem e clique em **Substituir imagem**. Selecione **Procurar na biblioteca** e selecione **coffee-machine.jpg**. Clique em **Selecionar**.
3. Substitua o Texto alternativo por "Máquina de café". (Se o painel para editar a imagem não aparecer imediatamente, você poderá encontrar as propriedades da imagem como o ícone inferior no Menu **Caixa de ferramentas**.)
4. No campo **Vincular para**, selecione **URL**. Insira [https://dynamics.microsoft.com/].
5. Na seção Tamanho e alinhamento, **desative** a largura automática. Altere a largura para *150px* e deixe a outra dimensão definida automaticamente.
6. Na coluna da direita, no subtítulo, selecione o espaço reservado Imagem e clique em **Substituir imagem**. Selecione **Procurar na biblioteca** e selecione **barista.jpg**. Clique em **Selecionar**.
7. Substitua o texto alternativo por *Barista*.
8. No campo Vincular para, selecione URL. Insira [https://dynamics.microsoft.com/].
9.  Selecione a seção com os ícones de redes sociais. Altere a cor de fundo da seção para um tom de cinza.
10. Selecione a seção com as informações de direitos autorais. Atualize os direitos autorais de *2022 Company Inc.* para *2024 Contoso Coffee*.
11. Faça outras alterações conforme desejado. Sinta-se à vontade para explorar sua criatividade e usar qualquer experiência de design que você tenha. O que chama sua atenção ao receber um email de marketing?

## Tarefa 5: Salvar e testar o email
16. Clique em **Salvar** na barra de ferramentas.
17. Selecione **Visualizar e testar**.
18. Clique em **Editar dados de exemplo**. No painel Visualizar personalização, insira o nome de um contato que você criou. Selecione o contato para ver a alteração da personalização.
19. Retorne à tela **Visualizar e testar**. Visualize o email em todos os tamanhos de tela.
20. Clique na **seta** de avanço para Verificar o conteúdo. Execute o **Verificador de acessibilidade** para ver se há outros problemas no email. Mitigue quaisquer outros problemas como achar melhor.
21. Na barra de ferramentas, clique em **Pronto para enviar**.

### Exercício 2: Criar um email copiando um email

## Tarefa 1: Criar um email para clientes existentes
1. Faça logon no Dynamics 365 Customer Insights - Journeys. Certifique-se de estar na área Marketing em tempo real.
2. Navegue até **Emails** no grupo Canais.
3. Abra o email que você criou na Tarefa 1.
4. Na barra de comandos, clique na **seta suspensa** ao lado de Salvar. Escolha **Salvar como**.
5. No menu Criação rápida à direita, nomeie o email *Email de Upgrade da Airpot*.
6. No campo Assunto, digite "Está na hora de fazer upgrade?"
7. Clique em **Salvar e Fechar**. Aparecerá um pop-up informando que *Suas alterações foram salvas*. Clique em **Exibir registro** para abrir o novo email. (Você também pode navegar de volta para **Emails** e abrir **Email de Atualização da Airpot**).
8. No designer, altere o texto do cabeçalho para: "{{Nome}}, café do seu jeito, na ponta dos dedos".
9. Altere a cópia abaixo do cabeçalho para: "Seu pedido de café é tão único quanto você. Está na hora de experimentar nossa nova máquina de café inteligente Airpot."
10. Selecione a próxima seção de duas colunas. Altere o layout de 2 para 1:2.
    - Na coluna da esquerda, faça as seguintes atualizações:
      - Remova o texto.
      - Remova o botão.
    - Na coluna da direita, faça as seguintes atualizações:
      - Remova a imagem.
      - Altere o texto para: "Meio-cafeinado americano ou café duplo com leite? Seja qual for a sua escolha para abastecer o dia, a Contoso Coffee tem tudo o que você precisa." ‎
      - Altere o tamanho da fonte para 16 e coloque em itálico.
11. Atualize o botão.
    - Selecione o botão .
    - Altere Vincular para para URL.
    - Digite https://dynamics.microsoft.com/.
    - Altere o texto do botão para *EXPLORE A NOVA SMART MACHINE*.
    - Expanda **Tamanho e alinhamento**. Alterne Ajustar para texto para **Desativado**. Altere a largura para *200px*.
12. Clique em **Salvar** na barra de ferramentas.
13. Visualize o email.
14. Clique em **Verificar conteúdo**. Corrija os erros, se necessário.
15. Na barra de ferramentas, clique em **Pronto para enviar**.

### Tarefa 2: Criar um email de campanha de acompanhamento
1. Faça logon no Dynamics 365 Customer Insights - Journeys. Certifique-se de estar na área Marketing em tempo real.
2. Navegue até **Emails** no grupo Canais.
3. Abra o e-mail que você criou na Tarefa 2.
4. Na barra de comandos, clique na seta suspensa ao lado de **Salvar**. Escolha **Salvar como**.
5. No menu Criação rápida à direita, nomeie o email *Lembrete da campanha da Smart Machine*.
6. No campo Assunto, digite "Já ficou sabendo da novidade?"
7. Clique em **Salvar e Fechar**. Um pop-up aparecerá no canto superior direito que diz Suas alterações foram salvas. Clique em **Exibir registro** para abrir o novo email. (Você também pode navegar até a lista Emails e abrir **Lembrete da campanha da Smart Machine**.)
8. Altere o texto do cabeçalho para: "A nova Smart Machine Airpot: disponível neste outono!"
9. Altere a cópia abaixo do cabeçalho para: "Nossa nova Smart Machine Airpot oferece uma nova maneira de fazer café. Saiba mais sobre a primeira máquina de café desse tipo hoje mesmo."
10. Remova a seção de duas colunas.
11. Clique em **Salvar** na barra de ferramentas.
12. Visualize o email.
13. Clique em **Verificar conteúdo**. Corrija os erros, se necessário.
14. Na barra de ferramentas, clique em **Pronto para enviar**.

