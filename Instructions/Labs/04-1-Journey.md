---
lab:
  title: 'Laboratório 4.1: Criar uma jornada baseada em gatilho'
---

# Roteiro de aprendizagem 4: Criar jornadas

## Laboratório prático 4.1: Criar uma jornada baseada em gatilho 

### Visão geral do laboratório

#### Cenário
Agora que criamos nossos três emails, é hora de criar uma jornada para enviar os emails para os clientes. Enviaremos o primeiro email para os clientes para informá-los sobre a próxima cafeteira Airpot Smart Machine.

Os clientes que interagirem com este email serão divididos em duas seções: clientes que já possuem um modelo Airpot antigo e clientes que não possuem. Para quem já tiver uma Airpot, enviaremos um email incentivando o upgrade. Se eles interagirem com um link neste email, um vendedor entrará em contato diretamente com eles.

Quem já tiver uma Airpot e não clicar em um link receberá outro email anunciando o produto. Este email também será enviado para quem tiver máquinas de café que não são Airpot.


### Será necessário:
- Um computador com um ambiente do Dynamics 365 Customer Insights - Journeys

## Exercício 1: Criar uma jornada em tempo real

### Tarefa 1: Criar uma jornada
1.  Faça logon no Dynamics 365 Customer Insights - Journeys.
2.  Navegue até a área de trabalho **Jornadas em tempo real**.
3.  Em **Participação**, selecione **Jornadas**.
4.  Clique em **+ Nova jornada** na barra de comandos. Se for solicitado usar o Copilot para criar a jornada, selecione **Ignorar e criar do zero**.
5.  Em **Nome da jornada**, insira *Campanha de lançamento da Airpot Smart Machine*.
6.  Em **Escolher tipo de jornada**, selecione **Baseada em gatilho.**
7.  Em **Escolher um gatilho**, pesquise e selecione **Link de email clicado**.
8.  Em **Escolher email**, pesquise e selecione seu **Email da campanha da Smart Machine**.
9.  Clique em **Criar**.

### Tarefa 2: Configurar a entrada da jornada
1. Navegue até a seção de **configurações da jornada**, que será expandida no lado direito da tela. A seção **Entrada** abrirá.
2. Deixe **Excluir por segmentos** em branco.
3. Na seção **Repetir**, selecione Imediatamente.
4. Na seção **Fuso horário**, escolha seu fuso horário.
5. Em **Iniciar**, selecione hoje. Defina o tempo para 15 minutos a partir de agora. (Você pode digitar diretamente nesse campo.)
6. Em **Encerrar**, selecione amanhã.

### Tarefa 3: Configurar a meta da jornada
1.  Navegue até as configurações da jornada à direita, que se parecerão com uma lista de ícones. Passe o mouse sobre cada ícone para ver o nome de cada guia. Selecione a seção **Meta**.
2.  Em *O objetivo desta jornada é*, selecione **Enviar uma notificação geral.**
3.  Em *A meta é atingida quando,* selecione **Uma pessoa clicou em pelo menos um link.**
4.  Insira *50* em *Número de pessoas necessárias*. Deixe a porcentagem selecionada.

### Tarefa 4: Adicionar uma ramificação de atributo
1. No designer da jornada, clique no **ícone de adição (+)** no bloco **Link por email clicado**.
2. Selecione **Atribuir ramificação** na seção *Condições*.
3. Em **Nome de exibição** à direita, insira *Já possui uma Airpot*
4. Selecione **Ramificação 1**. Em Nome de exibição, insira *Possui uma Airpot*.
5. Selecione **Adicionar condições**.
6. Em **Escolher um atributo**, pesquise **Descrição (descrição)** em Contato.
7. Altere o valor de Igual para Contém.
8. Em **Valor**, insira *Airpot*.
9. Retorne ao designer de jornada. Clique no **ícone de adição (+)** em Ramificação 1.
  - Selecione **Email**.
  - Em **Selecionar email**, escolha **Email de Atualização da Airpot**.
10.  Clique no **ícone de adição (+)** no bloco Enviar um email.
  - Selecione **Aguardar gatilho**.
  - Em **Escolher um tipo de condição de ramificação**, selecione **A mensagem anterior obtém uma interação**.
  - Em **Escolher uma interação**, selecione **Link por email clicado**.
  - Em **Qual é o limite de tempo?**, insira 10 minutos.
11. No caminho **Sim**, clique no **ícone de adição (+)**.
  - Selecione **Tarefa** na seção Atividades.
  - Em Escolher um modelo, selecione **Acompanhar com o cliente**.
  - Assunto e Atribuir a serão preenchidos automaticamente.
  - Mude **Vencimento após** para *2 semanas*.
12. No caminho correspondente **Não** (abaixo da ramificação Link por email clicado se/então), clique no **ícone de adição (+)**.
  - Selecione **Enviar um email**.
  - Em **Selecionar email**, escolha **Lembrete da campanha da Smart Machine**.
13. Retorne ao designer de jornada. Localize o bloco **Atributo**. Agora vamos configurar a ramificação **Não**. Para clientes que ainda não possuem uma Airpot, enviaremos o terceiro email.
  - Selecione o sinal **+** em **Outro**.
  - Selecione **Email**.
  - Em Selecionar email, selecione **Lembrete da campanha da Smart Machine**.
14. **Salve** a jornada.
15. Revise a jornada. Faça as alterações finais.
16. Clique em **Publicar**. Aguarde a publicação da jornada.
