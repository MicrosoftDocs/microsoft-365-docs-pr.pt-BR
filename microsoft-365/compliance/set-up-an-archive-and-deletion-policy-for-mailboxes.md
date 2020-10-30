---
title: Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: Saiba como criar uma política de arquivamento e exclusão no Microsoft 365 que move automaticamente itens para a caixa de correio de arquivo morto de um usuário.
ms.openlocfilehash: 093363b3c7c59f655a627d5f50e436c8f9f3c0dd
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804800"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização

No Microsoft 365, os administradores podem criar uma política de arquivamento e exclusão que move automaticamente os itens para a caixa de correio de arquivo morto de um usuário e exclui automaticamente os itens da caixa de correio. O administrador faz isso criando uma política de retenção que é atribuída às caixas de correio e move itens para a caixa de correio de arquivo morto de um usuário depois de um determinado período de tempo e que também exclui itens da caixa de correio depois que eles atingem um determinado limite de idade. As regras reais que determinam quais itens são movidos ou excluídos e quando isso acontece é chamado de marcas de retenção. As marcas de retenção são vinculadas a uma política de retenção, que, por sua vez, é atribuída à caixa de correio de um usuário. Uma marca de retenção aplica configurações de retenção a mensagens e pastas individuais na caixa de correio de um usuário. Define por quanto tempo uma mensagem permanece na caixa de correio e qual ação é executada quando a mensagem atinge a idade de retenção especificada. Quando uma mensagem atinge sua idade de retenção, ela é movida para a caixa de correio de arquivo morto do usuário ou ela é excluída.
  
As etapas deste artigo definirão uma política de arquivamento e de retenção para uma organização fictícia chamada Alpine House. A configuração dessa política inclui as seguintes tarefas:
  
- Habilitar uma caixa de correio de arquivo morto para cada usuário da organização. Isso fornece aos usuários a adição de armazenamento de caixa de correio e é necessário para que uma política de retenção possa mover itens para a caixa de correio de arquivo morto. Também permite que um usuário armazene informações de arquivamento movendo itens para a caixa de correio de arquivo morto.

- Criar três marcas de retenção personalizadas que fazem o seguinte:

  - Move automaticamente os itens que têm 3 anos de idade para a caixa de correio de arquivo morto do usuário. Mover itens para a caixa de correio de arquivo morto libera espaço na caixa de correio principal de um usuário.

  - Exclui automaticamente os itens que têm 5 anos de idade da pasta itens excluídos. Isso também libera espaço na caixa de correio principal do usuário. O usuário terá a oportunidade de recuperar esses itens, se necessário. Consulte a nota de rodapé na seção [mais informações](#more-information) para obter mais detalhes. 

  - Automaticamente (e permanentemente) exclui itens que têm 7 anos de idade da caixa de correio principal e de arquivo morto. Devido às normas de conformidade, algumas organizações precisam reter o email por um determinado período de tempo. Após expirar esse período de tempo, uma organização pode querer remover permanentemente essas caixas de correio de usuário dos itens.

- Criar uma nova política de retenção e adicionar novas marcas de retenção personalizadas a ela. Além disso, você também adicionará marcas de retenção internas à nova política de retenção. Isso inclui marcas pessoais que os usuários podem atribuir a itens em suas caixas de correio. Você também adicionará uma marca de retenção que move itens da pasta itens recuperáveis na caixa de correio principal do usuário para a pasta itens recuperáveis em suas caixas de correio de arquivo morto. Isso ajuda a liberar espaço na pasta itens recuperáveis de um usuário quando a caixa de correio é colocada em espera.

Você pode seguir algumas ou todas as etapas deste artigo para configurar uma política de arquivo morto e exclusão para caixas de correio em sua própria organização. Recomendamos que você teste esse processo em algumas caixas de correio antes de implementá-lo em todas as caixas de correio da sua organização.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Antes de configurar uma política de arquivo morto e exclusão

- Você deve ser um administrador global em sua organização para executar as etapas neste tópico. 

- Quando você cria uma nova conta de usuário e atribui ao usuário uma licença do Exchange Online, uma caixa de correio é automaticamente criada para o usuário. Quando a caixa de correio é criada, ela recebe automaticamente uma política de retenção padrão, denominada política de MRM padrão. Neste artigo, você criará uma nova política de retenção e a atribuirá às caixas de correio do usuário, substituindo a política padrão do MRM. Uma caixa de correio pode ter apenas uma política de retenção atribuída a ela a qualquer momento.

- Para saber mais sobre marcas de retenção e políticas de retenção no Exchange Online, confira [marcas de retenção e políticas de retenção](https://go.microsoft.com/fwlink/p/?LinkId=404424).

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Etapa 1: habilitar caixas de correio de arquivo morto para usuários

A primeira etapa é habilitar a caixa de correio de arquivo morto para cada usuário da sua organização. A caixa de correio de arquivo morto de um usuário deve ser habilitada para que uma marca de retenção com uma ação de retenção "mover para arquivo morto" possa mover o item após a expiração da idade da retenção.
  
> [!NOTE]
> Você pode habilitar as caixas de correio de arquivo em qualquer momento durante esse processo, desde que estejam habilitadas em algum momento antes de concluir o processo. Se uma caixa de correio de arquivo morto não estiver habilitada, nenhuma ação será tomada em qualquer item que tenha uma política de arquivo morto ou exclusão atribuída a ela.
  
1. Acesse [https://protection.office.com](https://protection.office.com).

2. Entre usando sua conta de administrador global.
    
3. No centro de conformidade & segurança, vá para o arquivo de **governança de informações** \> **Archive** .

    Uma lista das caixas de correio em sua organização é exibida e se a caixa de correio de arquivo morto correspondente está habilitada ou desabilitada.

4. Selecione todas as caixas de correio clicando no primeiro nome da lista, mantendo pressionada a tecla **Shift** e clicando no último da lista.

    > [!TIP]
    > Esta etapa pressupõe que nenhuma caixa de correio de arquivo morto esteja habilitada. Se você tiver caixas de correio com o arquivo morto habilitado, pressione a tecla **Ctrl** e clique em cada caixa de correio que possui uma caixa de correio de arquivo morto desabilitada. Ou você pode clicar no cabeçalho de coluna **caixa de correio de arquivo morto** para classificar as linhas com base em se a caixa de correio de arquivo morto está habilitada ou desabilitada para facilitar a seleção de caixas de correio.
  
5. No painel de detalhes, em **Editar em massa** , clique em **habilitar** .

    Um aviso é exibido dizendo que os itens com mais de dois anos serão movidos para a nova caixa de correio de arquivo morto. Isso ocorre porque a política de retenção padrão atribuída a uma nova caixa de correio de usuário quando criada tem uma marca de política padrão de arquivo morto com uma idade de retenção de dois anos. A marca de política padrão de arquivo morto personalizada que você criará na etapa 2 tem um tempo de retenção de 3 anos. Isso significa que os itens que são 3 anos ou mais antigos serão movidos para a caixa de correio de arquivo morto.

6. Clique em **Sim** para fechar a mensagem de aviso e iniciar o processo para habilitar a caixa de correio de arquivo morto para cada caixa de correio selecionada.

7. Quando o processo estiver concluído, clique em **Atualizar** ![ atualização ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) para atualizar a lista na página **arquivo morto** . 

    A caixa de correio de arquivo morto está habilitada para todos os usuários em sua organização.

    ![A lista de caixas de correio com a caixa de correio de arquivo morto habilitada](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. Deixe o centro de conformidade & segurança aberto. Você precisará usá-las na próxima etapa.

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Etapa 2: criar novas marcas de retenção para as políticas de arquivo morto e exclusão

Nesta etapa, você criará as três marcas de retenção personalizadas descritas anteriormente.
  
- Alpine House 3 anos mover para arquivo morto (política de arquivo morto personalizada)

- Alpine House 7 ano excluir permanentemente (política de exclusão personalizada)

- Alpine House itens excluídos 5 anos excluir e permitir a recuperação (marca personalizada para a pasta itens excluídos)

Para criar novas marcas de retenção, você usará o centro de administração do Exchange (Eat) em sua organização do Exchange Online.
  
1. No centro de conformidade & segurança, clique no inicializador de aplicativos no canto superior esquerdo e, em seguida, clique no bloco **administrador** .

2. No painel de navegação esquerdo do centro de administração do Microsoft 365, clique em **centros de administração** e, em seguida, clique em **Exchange** .

    ![A captura de tela mostra o centro de administração do Microsoft 365 com a opção centros de administração expandida e o Exchange selecionado.](../media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. No Eat, vá para **Compliance management** \> **marcas de retenção** de gerenciamento de conformidade

    É exibida uma lista das marcas de retenção da sua organização.

### <a name="create-a-custom-archive-default-policy-tag"></a>Criar uma marca de política padrão de arquivo morto personalizado
  
Primeiro, você criará uma marca de política padrão de arquivo morto personalizada (DPT) que moverá itens para a caixa de correio de arquivo morto após 3 anos.
  
1. Na página **marcas de retenção** , clique em Nova **marca** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) e selecione **aplicada automaticamente à caixa de correio inteira (padrão)** .

2. Na página **nova marca aplicada automaticamente à caixa de correio inteira (padrão)** , preencha os seguintes campos: 

    ![Configurações para criar uma nova marca de política padrão de arquivo morto](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Ação de retenção** Selecione **mover para o arquivo morto** para mover itens para a caixa de correio de arquivo morto quando o período de retenção expirar.

   3. **Período de retenção** Selecione **quando o item atinge a seguinte idade (em dias)** e, em seguida, insira a duração do período de retenção. Neste cenário, os itens serão movidos para a caixa de correio de arquivo morto após 1095 dias (3 anos).

   4. **Comentário** (opcional) digite um comentário que explique o objetivo da marca de retenção personalizada.

3. Clique em **salvar** para criar a DPT de arquivo morto personalizada.

    O novo arquivo morto DPT é exibido na lista de marcas de retenção.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Criar uma marca de política padrão de exclusão personalizada
  
Em seguida, você criará outro DPT personalizado, mas ele será uma política de exclusão que exclui permanentemente os itens após 7 anos.
  
1. Na página **marcas de retenção** , clique em Nova **marca** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) e selecione **aplicada automaticamente à caixa de correio inteira (padrão)** .

2. Na página **nova marca aplicada automaticamente à caixa de correio inteira (padrão)** , preencha os seguintes campos: 

    ![Configurações para criar uma nova marca de política padrão de exclusão](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Ação de retenção** Selecione **excluir permanentemente** para limpar itens da caixa de correio quando o período de retenção expirar.

   3. **Período de retenção** Selecione **quando o item atinge a seguinte idade (em dias)** e, em seguida, insira a duração do período de retenção. Para este cenário, os itens serão removidos após 2555 dias (sete anos).

   4. **Comentário** (opcional) digite um comentário que explique o objetivo da marca de retenção personalizada. 

3. Clique em **salvar** para criar a DPT de exclusão personalizada. 

    O novo DPT de exclusão é exibido na lista de marcas de retenção.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Criar uma marca de política de retenção personalizada para a pasta itens excluídos
  
A última marca de retenção que você criará é uma marca de política de retenção personalizada (RPT) para a pasta itens excluídos. Essa marca excluirá itens na pasta itens excluídos após 5 anos e fornecerá um período de recuperação quando os usuários puderem usar a ferramenta recuperar itens excluídos para recuperar um item.
  
1. Na página **marcas de retenção** , clique em Nova **marca** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) e selecione **aplicada automaticamente a uma pasta padrão** .

2. Na página **nova marca aplicada automaticamente a uma pasta padrão** , preencha os seguintes campos:

    ![Configurações para criar uma nova marca de política de retenção para a pasta itens excluídos](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Aplicar esta marca à seguinte pasta padrão** Na lista suspensa, selecione **itens excluídos** .

   3. **Ação de retenção** Selecione **excluir e permitir que a recuperação** exclua itens quando o período de retenção expirar, mas permitir que os usuários recuperem um item excluído dentro do período de retenção de itens excluídos (que por padrão é 14 dias).

   4. **Período de retenção** Selecione **quando o item atinge a seguinte idade (em dias)** e, em seguida, insira a duração do período de retenção. Para este cenário, os itens serão excluídos após 1825 dias (5 anos).

   5. **Comentário** (opcional) digite um comentário que explique o objetivo da marca de retenção personalizada. 

3. Clique em **salvar** para criar o relatório personalizado para a pasta itens excluídos.

    O novo relatório é exibido na lista de marcas de retenção.

## <a name="step-3-create-a-new-retention-policy"></a>Etapa 3: criar uma nova política de retenção

Após criar as marcas de retenção personalizadas, a próxima etapa é criar uma nova política de retenção e adicionar as marcas de retenção. Você adicionará as três marcas de retenção personalizadas que você criou na etapa 2 e as marcas internas que foram mencionadas na primeira seção. Na etapa 4, você atribuirá essa nova política de retenção a caixas de correio do usuário.
  
1. No Eat, vá para políticas de retenção de **Gerenciamento de conformidade** \> **Retention policies** .

2. Na página **políticas de retenção** , clique em **novo** ![ ícone novo ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

3. Na caixa **nome** , digite um nome para a nova política de retenção; por exemplo, **política de arquivo morto e exclusão da Alpine Ski** .

4. Em **marcas de retenção** , clique em **Adicionar** ![ novo ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

    É exibida uma lista das marcas de retenção em sua organização. Observação as marcas personalizadas que você criou na etapa 2 são exibidas.

5. Adicione as 9 marcas de retenção realçadas na captura de tela a seguir (essas marcas são descritas em mais detalhes na seção [mais informações](#more-information) ). Para adicionar uma marca de retenção, selecione-a e clique em **Adicionar** .

    ![Adicionar marcas de retenção à nova política de retenção](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Você pode selecionar várias marcas de retenção mantendo pressionada a tecla **Ctrl** e clicando em cada marca. 
  
6. Depois de adicionar as marcas de retenção, clique em **OK** .

7. Na página **nova política de retenção** , clique em **salvar** para criar a nova política.

    A nova política de retenção é exibida na lista. Selecione-o para exibir as marcas de retenção vinculadas a ela no painel de detalhes.

    ![A nova política de retenção e a lista de marcas de retenção vinculadas](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Etapa 4: atribuir a nova política de retenção a caixas de correio do usuário

Quando uma nova caixa de correio é criada, uma política de retenção chamada Default MRM Policy é atribuída por padrão. Nesta etapa, você substituirá essa política de retenção (porque uma caixa de correio pode ter apenas uma política de retenção atribuída a ela), atribuindo a nova política de retenção que você criou na etapa 3 às caixas de correio do usuário em sua organização. Esta etapa pressupõe que você atribuirá a nova política a todas as caixas de correio em sua organização.
  
1. No EAC, vá até **Destinatários** \> **Caixas de Correio** .

    É exibida uma lista de todas as caixas de correio de usuário em sua organização.

2. Selecione todas as caixas de correio clicando no primeiro nome da lista, mantendo pressionada a tecla **Shift** e clicando no último da lista. 

3. No painel de detalhes no lado direito do Eat, em **edição em massa** , clique em **mais opções** .

4. Em **Política de Retenção** , clique em **Atualizar** .

5. Na página **atribuir política de retenção em massa** , na lista suspensa **Selecione a política de retenção** , selecione a política de retenção que você criou na etapa 3; por exemplo, a **política de retenção e arquivo morto da Alpine Ski** .

6. Clique em **salvar** para salvar a nova atribuição de política de retenção.

7. Para verificar se a nova política de retenção foi atribuída às caixas de correio, você pode fazer o seguinte:

   1. Selecione uma caixa de correio na página **caixas de correio** e clique em **Editar** ![ Editar ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) .

   2. Na página de propriedades da caixa de correio do usuário selecionado, clique em **recursos da caixa de correio** .

   O nome da nova política atribuída à caixa de correio é exibida na lista suspensa **política de retenção** .

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>Opcion Etapa 5: executar o assistente de pasta gerenciada para aplicar as novas configurações

Após aplicar a nova política de retenção às caixas de correio na etapa 4, pode levar até 7 dias no Exchange Online para que as novas configurações de retenção sejam aplicadas às caixas de correio. Isso ocorre porque um processo chamado *Assistente de pasta gerenciada* processa caixas de correio pelo menos uma vez a cada 7 dias. Em vez de aguardar a execução do assistente de pasta gerenciada, você pode forçar isso a acontecer executando o cmdlet **Start-ManagedFolderAssistant** no PowerShell do Exchange Online.

 **O que acontece quando você executa o assistente de pasta gerenciada?** Aplica as configurações da política de retenção inspecionando itens na caixa de correio e determinando se estão sujeitos à retenção. Em seguida, ele carimba os itens sujeitos à retenção com a marca de retenção apropriada e, em seguida, executa a ação de retenção especificada em itens além da idade da retenção.
  
Aqui estão as etapas para se conectar ao PowerShell do Exchange Online e, em seguida, executar o assistente de pasta gerenciada em todas as caixas de correio em sua organização.

1. [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).
  
2. Execute os dois comandos a seguir para iniciar o assistente de pasta gerenciada para todas as caixas de correio de usuário em sua organização.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Isso é tudo. Você configurou uma política de arquivamento e exclusão para a organização Alpine House.

> [!NOTE]
> Conforme mencionado anteriormente, o assistente de pasta gerenciada processa caixas de correio pelo menos uma vez a cada 7 dias. Portanto, é possível que uma caixa de correio possa ser processada pelo assistente de pasta gerenciada com mais frequência. Além disso, os administradores não podem prever na próxima vez que uma caixa de correio é processada pelo assistente de pasta gerenciada, que é um dos motivos pelos quais você pode querer executá-la manualmente. No entanto, se você deseja impedir temporariamente que o assistente de pasta gerenciada aplique as novas configurações de retenção a uma caixa de correio, é possível executar o `Set-Mailbox -ElcProcessingDisabled $true` comando para desabilitar temporariamente o assistente de pasta gerenciada do processamento de uma caixa de correio. Para reabilitar o assistente de pasta gerenciada para uma caixa de correio, execute o `Set-Mailbox -ElcProcessingDisabled $false` comando.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>Opcion Etapa 6: tornar a nova política de retenção o padrão para sua organização

Na etapa 4, você precisa atribuir a nova política de retenção a caixas de correio existentes. Mas você pode configurar o Exchange Online para que a nova política de retenção seja atribuída a novas caixas de correio criadas no futuro. Faça isso usando o PowerShell do Exchange Online para atualizar o plano de caixa de correio padrão da sua organização. Um *plano de caixa de correio* é um modelo que configura automaticamente as propriedades em novas caixas de correio.  Nesta etapa opcional, você pode substituir a política de retenção atual atribuída ao plano de caixa de correio (por padrão, a política padrão do MRM) com a política de retenção que você criou na etapa 3. Depois de atualizar o plano de caixa de correio, a nova política de retenção será atribuída a novas caixas de correio.

1. [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).

2. Execute o comando a seguir para exibir informações sobre os planos de caixa de correio em sua organização.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Observe o plano de caixa de correio definido como o padrão.

3. Execute o comando a seguir para atribuir a nova política de retenção que você criou na etapa 3 (por exemplo, a **política de retenção e arquivo morto da Alpine Ski House** ) ao plano de caixa de correio padrão. Este exemplo assume que o nome do plano de caixa de correio padrão é **ExchangeOnlineEnterprise** .

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Você pode executar novamente o comando na etapa 2 para verificar se a política de retenção atribuída ao plano de caixa de correio padrão foi alterada.

## <a name="more-information"></a>Mais informações

- Como a idade de retenção é calculada? A idade de retenção de itens de caixa de correio é calculada a partir da data de entrega ou da data de criação de itens como mensagens de rascunho que não são enviadas, mas são criadas pelo usuário. Quando o Assistente de Pasta Gerenciada processa itens em uma caixa de correio, ele insere uma data inicial e uma data de expiração para todos os itens com marcas de retenção com a ação de retenção Excluir e Permitir Recuperação ou Excluir Permanentemente. Os itens que têm uma marca de arquivo morto são carimbados com uma data de movimentação. 

- A tabela a seguir fornece mais informações sobre cada marca de retenção que é adicionada à política de retenção personalizada que foi criada seguindo as etapas deste tópico.

    | Marca de retenção | O que essa marca faz | Interno ou personalizado? | Tipo |
    |:-----|:-----|:-----|:-----|
    |Mover para arquivo morto da Alpine House 3 anos  <br/> |Move itens que são 1095 dias (3 anos) de idade para a caixa de correio de arquivo morto.  <br/> |Personalizado (consulte [etapa 2: criar novas marcas de retenção para as políticas de arquivo morto e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de política padrão (arquivo morto); Essa marca é aplicada automaticamente à caixa de correio inteira.  <br/> |
    |Alpine House 7 ano excluir permanentemente  <br/> |Exclui permanentemente os itens na caixa de correio principal ou na caixa de correio de arquivo morto quando eles têm 7 anos de idade.  <br/> |Personalizado (consulte [etapa 2: criar novas marcas de retenção para as políticas de arquivo morto e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de política padrão (exclusão); Essa marca é aplicada automaticamente à caixa de correio inteira.  <br/> |
    |Alpine House itens excluídos 5 anos excluir e permitir recuperação  <br/> |Exclui itens da pasta itens excluídos que têm 5 anos de idade. Os usuários podem recuperar esses itens por até 14 dias após serem excluídos.<sup>\*</sup> <br/> |Personalizado (consulte [etapa 2: criar novas marcas de retenção para as políticas de arquivo morto e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de política de retenção (itens excluídos); Essa marca é aplicada automaticamente a itens na pasta itens excluídos.  <br/> |
    |Itens recuperáveis 14 dias mover para o arquivo morto  <br/> |Move itens que estão na pasta itens recuperáveis por 14 dias para a pasta itens recuperáveis na caixa de correio de arquivo morto.  <br/> |Interno  <br/> |Marca de política de retenção (itens recuperáveis); Essa marca é aplicada automaticamente a itens na pasta itens recuperáveis.  <br/> |
    |Lixo eletrônico  <br/> |Exclui permanentemente os itens que estão na pasta lixo eletrônico por 30 dias. Os usuários podem recuperar esses itens por até 14 dias após serem excluídos.<sup>\*</sup> <br/> |Interno  <br/> |Marca de política de retenção (lixo eletrônico); Essa marca é aplicada automaticamente a itens na pasta lixo eletrônico.  <br/> |
    |Exclusão de 1 mês  <br/> |Exclui permanentemente os itens que têm 30 dias de idade. Os usuários podem recuperar esses itens por até 14 dias após serem excluídos.<sup>\*</sup> <br/> |Interno  <br/> |PCs Essa marca pode ser aplicada pelos usuários.  <br/> |
    |Exclusão de 1 ano  <br/> |Exclui permanentemente os itens que têm 365 dias de idade. Os usuários podem recuperar esses itens por até 14 dias após serem excluídos.<sup>\*</sup> <br/> |Interno  <br/> |PCs Essa marca pode ser aplicada pelos usuários.  <br/> |
    |Nunca excluir  <br/> |Essa marca impede que itens sejam excluídos por uma política de retenção.  <br/> |Interno  <br/> |PCs Essa marca pode ser aplicada pelos usuários.  <br/> |
    |Movimentação de 1 anos para arquivo pessoal  <br/> |Move itens para a caixa de correio de arquivo morto após 1 ano.  <br/> |Interno  <br/> |PCs Essa marca pode ser aplicada pelos usuários.  <br/> |

    > <sup>\*</sup> Os usuários podem usar a ferramenta recuperar itens excluídos no Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App) para recuperar um item excluído dentro do período de retenção de itens excluídos, que por padrão é de 14 dias no Exchange Online. Um administrador pode usar o Windows PowerShell para aumentar o período de retenção de itens excluídos para no máximo 30 dias. Para obter mais informações, consulte: [recuperar itens excluídos no Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) e [alterar o período de retenção de itens excluídos para uma caixa de correio no Exchange Online](https://www.microsoft.com/?ref=go)
  
- Usando os **itens recuperáveis 14 dias mover para arquivo morto** a marca de retenção ajuda a liberar espaço de armazenamento na pasta itens recuperáveis na caixa de correio principal do usuário. Isso é útil quando a caixa de correio de um usuário é colocada em espera, o que significa que nada é permanentemente excluído da caixa de correio do usuário. Sem mover itens para a caixa de correio de arquivo morto, é possível que a cota de armazenamento da pasta itens recuperáveis na caixa de correio principal seja atingida. Para obter mais informações sobre isso e como evitá-la, consulte [aumentar a cota de itens recuperáveis para caixas de correio em espera](https://go.microsoft.com/fwlink/p/?LinkId=786479).
