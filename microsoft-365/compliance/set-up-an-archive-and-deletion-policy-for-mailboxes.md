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
ms.openlocfilehash: ae48335203968b25a00fda61bfe65ffde85649ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919527"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização

No Microsoft 365, os administradores podem criar uma política de arquivamento e exclusão que move automaticamente itens para a caixa de correio de arquivo morto de um usuário e exclui automaticamente itens da caixa de correio. O administrador faz isso criando uma política de retenção atribuída a caixas de correio e move itens para a caixa de correio de arquivo morto de um usuário após um determinado período de tempo e que também exclui itens da caixa de correio após atingir um determinado limite de idade. As regras reais que determinam quais itens são movidos ou excluídos e quando isso acontece são chamadas de marcas de retenção. As marcas de retenção são vinculadas a uma política de retenção, que, por sua vez, é atribuída à caixa de correio de um usuário. Uma marca de retenção aplica configurações de retenção a mensagens e pastas individuais na caixa de correio de um usuário. Ele define por quanto tempo uma mensagem permanece na caixa de correio e qual ação é tomada quando a mensagem atinge a idade de retenção especificada. Quando uma mensagem atinge sua idade de retenção, ela é movida para a caixa de correio de arquivo morto do usuário ou é excluída.
  
As etapas deste artigo configurarão uma política de arquivamento e retenção para uma organização fictícia chamada Alpine House. A configuração dessa política inclui as seguintes tarefas:
  
- Habilitando uma caixa de correio de arquivo morto para todos os usuários da organização. Isso oferece aos usuários armazenamento de caixa de correio adicional e é necessário para que uma política de retenção possa mover itens para a caixa de correio de arquivo morto. Ele também permite que um usuário armazene informações de arquivamento movendo itens para sua caixa de correio de arquivo morto.

- Criando três marcas de retenção personalizadas que fazem o seguinte:

  - Move automaticamente itens com 3 anos de idade para a caixa de correio de arquivo morto do usuário. Mover itens para a caixa de correio de arquivo morto libera espaço na caixa de correio principal de um usuário.

  - Exclui automaticamente itens com 5 anos de idade da pasta Itens Excluídos. Isso também libera espaço na caixa de correio principal do usuário. Os usuários terão a oportunidade de recuperar esses itens, se necessário. Consulte a nota de rodapé na [seção Mais informações](#more-information) para obter mais detalhes. 

  - Exclui automaticamente (e permanentemente) itens com 7 anos de idade da caixa de correio principal e de arquivo morto. Devido aos regulamentos de conformidade, algumas organizações são obrigadas a reter emails por um determinado período de tempo. Após esse período expirar, uma organização pode querer remover permanentemente esses itens caixas de correio de usuário.

- Criando uma nova política de retenção e adicionando as novas marcas de retenção personalizadas a ela. Além disso, você também adicionará marcas de retenção internas à nova política de retenção. Isso inclui marcas pessoais que os usuários podem atribuir a itens em suas caixas de correio. Você também adicionará uma marca de retenção que move itens da pasta Itens Recuperáveis na caixa de correio principal do usuário para a pasta Itens Recuperáveis em sua caixa de correio de arquivo morto. Isso ajuda a liberar espaço na pasta Itens Recuperáveis do usuário quando sua caixa de correio é colocada em espera.

Você pode seguir algumas ou todas as etapas deste artigo para configurar uma política de arquivamento e exclusão para caixas de correio em sua própria organização. Recomendamos que você teste esse processo em algumas caixas de correio antes de implementá-lo em todas as caixas de correio em sua organização.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Antes de configurar uma política de arquivamento e exclusão

- Você precisa ser um administrador global em sua organização para executar as etapas neste tópico. 

- Quando você cria uma nova conta de usuário e atribui ao usuário uma licença de Exchange Online, uma caixa de correio é criada automaticamente para o usuário. Quando a caixa de correio é criada, ela é atribuída automaticamente a uma política de retenção padrão, chamada Política mrm padrão. Neste artigo, você criará uma nova política de retenção e a atribuirá às caixas de correio de usuário, substituindo a política mrm padrão. Uma caixa de correio pode ter apenas uma política de retenção atribuída a ela a qualquer momento.

- Para saber mais sobre marcas de retenção e políticas de retenção em Exchange Online, consulte [Marcas de retenção e políticas de retenção.](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Etapa 1: Habilitar caixas de correio de arquivo morto para usuários

A primeira etapa é habilitar a caixa de correio de arquivo morto para cada usuário em sua organização. A caixa de correio de arquivo morto de um usuário precisa ser habilitada para que uma marca de retenção com uma ação de retenção "Mover para o Arquivo Morto" possa mover o item após a expiração da idade de retenção.
  
> [!NOTE]
> Você pode habilitar caixas de correio de arquivo morto a qualquer momento durante esse processo, contanto que elas estão habilitadas em algum momento antes de concluir o processo. Se uma caixa de correio de arquivo morto não estiver habilitada, nenhuma ação será tomada em todos os itens que tenham uma política de arquivamento ou exclusão atribuída a ela.
  
1. Acesse [https://protection.office.com](https://protection.office.com).

2. Entre usando sua conta de administrador global.
    
3. No Centro de Conformidade & segurança, vá para **Arquivo de governança de** \> **informações.**

    Uma lista das caixas de correio em sua organização é exibida e se a caixa de correio de arquivo morto correspondente está habilitada ou desabilitada.

4. Selecione todas as caixas de correio clicando na primeira da lista, segurando a tecla **Shift** e clicando na última da lista.

    > [!TIP]
    > Esta etapa supõe que nenhuma caixa de correio de arquivo morto está habilitada. Se você tiver caixas de correio com o arquivo morto habilitado, segure a tecla **Ctrl** e clique em cada caixa de correio que tenha uma caixa de correio de arquivo morto desabilitada. Ou você pode  clicar no header da coluna De caixa de correio de arquivo morto para classificar as linhas com base em se a caixa de correio de arquivo morto está habilitada ou desabilitada para facilitar a seleção de caixas de correio.
  
5. No painel de detalhes, em Edição em **Massa,** clique em **Habilitar**.

    Um aviso é exibido dizendo que itens com mais de dois anos serão movidos para a nova caixa de correio de arquivo morto. Isso acontece porque a política de retenção padrão atribuída a uma nova caixa de correio de usuário quando criada tem uma marca de política padrão de arquivo morto que tem uma idade de retenção de 2 anos. A marca de política padrão de arquivo morto personalizado que você criará na Etapa 2 tem uma idade de retenção de 3 anos. Isso significa que itens com 3 anos ou mais serão movidos para a caixa de correio de arquivo morto.

6. Clique **em Sim** para fechar a mensagem de aviso e iniciar o processo para habilitar a caixa de correio de arquivo morto para cada caixa de correio selecionada.

7. Quando o processo for concluído, clique em **Atualizar** ![ atualizar para atualizar a lista na página ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Arquivo** morto.

    A caixa de correio de arquivo morto está habilitada para todos os usuários da sua organização.

    ![A lista de caixas de correio com a caixa de correio de arquivo morto habilitada](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Etapa 2: Criar novas marcas de retenção para as políticas de arquivamento e exclusão

Nesta etapa, você criará as três marcas de retenção personalizadas descritas anteriormente.
  
- Alpine House 3 Year Move to Archive (custom archive policy)

- Alpine House 7 Year Permanently Delete (política de exclusão personalizada)

- Alpine House Excluídos Itens 5 Anos Excluir e Permitir Recuperação (marca personalizada para a pasta Itens Excluídos)

Para criar novas marcas de retenção, você usará o centro de administração Exchange (EAC) em sua Exchange Online organização. Certifique-se de usar a versão clássica do EAC.
  
1. Vá para [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) e entre usando suas credenciais.
  
2. No EAC, acesse Marcas de retenção de **gerenciamento**  >  **de conformidade**

    Uma lista das marcas de retenção da sua organização é exibida.

### <a name="create-a-custom-archive-default-policy-tag"></a>Criar uma marca de política padrão de arquivo morto personalizado
  
Primeiro, você criará uma marca de política padrão de arquivo morto (DPT) personalizada que moverá itens para a caixa de correio de arquivo morto após três anos.
  
1. Na página **Marcas de retenção,** clique em **Nova marca** Novo ícone e selecione aplicado automaticamente à caixa de correio ![ inteira ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(padrão)**.

2. Na página **Nova marca aplicada automaticamente à caixa de correio inteira (padrão),** conclua os seguintes campos: 

    ![Configurações criar uma nova marca de política padrão de arquivo morto](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Ação de retenção** Selecione **Mover para Arquivo Morto** para mover itens para a caixa de correio de arquivo morto quando o período de retenção expirar.

   3. **Período de retenção** Selecione Quando o item atingir a idade a seguir **(em dias)** e insira a duração do período de retenção. Nesse cenário, os itens serão movidos para a caixa de correio de arquivo morto após 1095 dias (3 anos).

   4. **Comentário** (Opcional) Digite um comentário que explica a finalidade da marca de retenção personalizada.

3. Clique **em Salvar** para criar o DPT de arquivo morto personalizado.

    O novo DPT de arquivo morto é exibido na lista de marcas de retenção.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Criar uma marca de política padrão de exclusão personalizada
  
Em seguida, você criará outro DPT personalizado, mas essa será uma política de exclusão que exclui permanentemente itens após 7 anos.
  
1. Na página **Marcas de retenção,** clique em **Nova marca** Novo ícone e selecione aplicado automaticamente à caixa de correio ![ inteira ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **(padrão)**.

2. Na página **Nova marca aplicada automaticamente à caixa de correio inteira (padrão),** conclua os seguintes campos: 

    ![Configurações criar uma nova marca de política padrão de exclusão](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Ação de retenção** Selecione **Excluir permanentemente** para limpar itens da caixa de correio quando o período de retenção expirar.

   3. **Período de retenção** Selecione Quando o item atingir a idade a seguir **(em dias)** e insira a duração do período de retenção. Para esse cenário, os itens serão limpos após 2555 dias (7 anos).

   4. **Comentário** (Opcional) Digite um comentário que explica a finalidade da marca de retenção personalizada. 

3. Clique **em Salvar** para criar o DPT de exclusão personalizado. 

    O novo DPT de exclusão é exibido na lista de marcas de retenção.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Criar uma marca de política de retenção personalizada para a pasta Itens Excluídos
  
A última marca de retenção que você criará é uma marca de política de retenção personalizada (RPT) para a pasta Itens Excluídos. Essa marca excluirá itens na pasta Itens Excluídos após 5 anos e fornece um período de recuperação quando os usuários podem usar a ferramenta Recuperar Itens Excluídos para recuperar um item.
  
1. Na página **Marcas de retenção,** clique em **Nova marca** Novo ícone e selecione aplicado ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **automaticamente a uma pasta padrão**.

2. Na nova **marca aplicada automaticamente a uma página de** pasta padrão, conclua os seguintes campos:

    ![Configurações criar uma nova marca de política de retenção para a pasta Itens Excluídos](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Nome** Digite um nome para a nova marca de retenção. 

   2. **Aplicar essa marca à seguinte pasta padrão** Na lista lista listada, selecione **Itens Excluídos**.

   3. **Ação de retenção** Selecione Excluir e Permitir **Recuperação** para excluir itens quando o período de retenção expirar, mas permitir que os usuários recuperem um item excluído dentro do período de retenção de item excluído (que por padrão é 14 dias).

   4. **Período de retenção** Selecione Quando o item atingir a idade a seguir **(em dias)** e insira a duração do período de retenção. Nesse cenário, os itens serão excluídos após 1825 dias (5 anos).

   5. **Comentário** (Opcional) Digite um comentário que explica a finalidade da marca de retenção personalizada. 

3. Clique **em Salvar** para criar o RPT personalizado para a pasta Itens Excluídos.

    O novo RPT é exibido na lista de marcas de retenção.

## <a name="step-3-create-a-new-retention-policy"></a>Etapa 3: Criar uma nova política de retenção

Depois de criar as marcas de retenção personalizadas, a próxima etapa é criar uma nova política de retenção e adicionar as marcas de retenção. Você adicionará as três marcas de retenção personalizadas criadas na Etapa 2 e as marcas criadas que foram mencionadas na primeira seção. Na Etapa 4, você atribuirá essa nova política de retenção às caixas de correio do usuário.
  
1. No EAC, vá para **Políticas de** retenção de gerenciamento de  >  **conformidade.**

2. Na página **Políticas de retenção,** clique em **Novo** ![ ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) Novo.

3. Na caixa **Nome,** digite um nome para a nova política de retenção; por exemplo, **Alpine House Archive and Deletion Policy**.

4. Em **Marcas de retenção,** clique **em Adicionar** novo ![ ícone ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

    Uma lista das marcas de retenção em sua organização é exibida. Observe que as marcas personalizadas criadas na Etapa 2 são exibidas.

5. Adicione as 9 marcas de retenção realçadas na captura de tela a seguir (essas marcas são descritas em mais detalhes na [seção Mais](#more-information) informações). Para adicionar uma marca de retenção, selecione-a e clique em **Adicionar**.

    ![Adicionar marcas de retenção à nova política de retenção](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Você pode selecionar várias marcas de retenção segurando a **tecla Ctrl** e clicando em cada marca. 
  
6. Depois de adicionar as marcas de retenção, clique em **OK**.

7. Na página **Nova política de retenção,** clique em **Salvar** para criar a nova política.

    A nova política de retenção é exibida na lista. Selecione-o para exibir as marcas de retenção vinculadas a ela no painel de detalhes.

    ![A nova política de retenção e a lista de marcas de retenção vinculadas](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Etapa 4: Atribuir a nova política de retenção a caixas de correio de usuário

Quando uma nova caixa de correio é criada, uma política de retenção chamada política MRM padrão é atribuída a ela por padrão. Nesta etapa, você substituirá essa política de retenção (porque uma caixa de correio pode ter apenas uma política de retenção atribuída a ela) atribuindo a nova política de retenção criada na Etapa 3 às caixas de correio do usuário em sua organização. Esta etapa supõe que você atribuirá a nova política a todas as caixas de correio em sua organização.
  
1. No EAC, vá para **Caixas de** Correio  >  **de Destinatários.**

    Uma lista de todas as caixas de correio de usuário em sua organização é exibida.

2. Selecione todas as caixas de correio clicando na primeira da lista, segurando a tecla **Shift** e clicando na última da lista. 

3. No painel de detalhes no lado direito do EAC, em **Editar** em Massa, clique **em Mais opções**.

4. Em **Política de Retenção**, clique em **Atualizar**.

5. Na página **Atribuir política de** retenção em massa, na lista drop-down **Selecionar** a política de retenção, selecione a política de retenção que você criou na Etapa 3; por exemplo, **Alpine House Archive and Retention Policy**.

6. Clique **em Salvar** para salvar a nova atribuição de política de retenção.

7. Para verificar se a nova política de retenção foi atribuída a caixas de correio, você pode fazer o seguinte:

   1. Selecione uma caixa de correio na página **Caixas de** Correio e clique em **Editar** ![ Editar ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) .

   2. Na página propriedades da caixa de correio do usuário selecionado, clique em **Recursos de Caixa de Correio**.

   O nome da nova política atribuída à caixa de correio é exibido na **lista** drop-down da política de retenção.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Opcional) Etapa 5: Executar o Assistente de Pasta Gerenciada para aplicar as novas configurações

Depois de aplicar a nova política de retenção às caixas de correio na Etapa 4, ela pode levar até 7 dias em Exchange Online para que as novas configurações de retenção sejam aplicadas às caixas de correio. Isso porque um processo chamado Assistente de Pasta *Gerenciada* processa caixas de correio pelo menos uma vez a cada 7 dias. Em vez de esperar que o Assistente de Pasta Gerenciada seja executado, você pode forçar isso a acontecer executando o cmdlet **Start-ManagedFolderAssistant** no Exchange Online PowerShell.

 **O que acontece quando você executar o Assistente de Pasta Gerenciada?** Ele aplica as configurações na política de retenção inspecionando itens na caixa de correio e determinando se eles estão sujeitos à retenção. Em seguida, ele carimba itens sujeitos à retenção com a marca de retenção apropriada e, em seguida, assume a ação de retenção especificada em itens além de sua idade de retenção.
  
Aqui estão as etapas para se conectar ao Exchange Online PowerShell e, em seguida, executar o Assistente de Pasta Gerenciada em todas as caixas de correio em sua organização.

1. [Conectar-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Execute os dois comandos a seguir para iniciar o Assistente de Pasta Gerenciada para todas as caixas de correio de usuário em sua organização.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Isso é tudo. Você definiu uma política de arquivamento e exclusão para a organização da Casa Alpine.

> [!NOTE]
> Conforme mencionado anteriormente, o Assistente de Pasta Gerenciada processa caixas de correio pelo menos uma vez a cada 7 dias. Portanto, é possível que uma caixa de correio possa ser processada pelo Assistente de Pasta Gerenciada com mais frequência. Além disso, os administradores não podem prever a próxima vez que uma caixa de correio é processada pelo Assistente de Pasta Gerenciada, que é um dos motivos pelos quais você pode querer executar manualmente. No entanto, se você quiser impedir temporariamente que o Assistente de Pasta Gerenciada aplicação das novas configurações de retenção a uma caixa de correio, execute o comando para desabilitar temporariamente o Assistente de Pasta Gerenciada do processamento de uma caixa de `Set-Mailbox -ElcProcessingDisabled $true` correio. Para habilitar o Assistente de Pasta Gerenciada para uma caixa de correio, execute o `Set-Mailbox -ElcProcessingDisabled $false` comando. Por fim, se um usuário de caixa de correio tiver uma conta desabilitada, não processaremos os itens de movimentação para arquivar a ação dessa caixa de correio.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(Opcional) Etapa 6: tornar a nova política de retenção o padrão para sua organização

Na Etapa 4, você precisa atribuir a nova política de retenção a caixas de correio existentes. Mas você pode configurar Exchange Online para que a nova política de retenção seja atribuída a novas caixas de correio criadas no futuro. Você faz isso usando o Exchange Online PowerShell para atualizar o plano de caixa de correio padrão da sua organização. Um *plano de caixa de* correio é um modelo que configura automaticamente as propriedades em novas caixas de correio.  Nesta etapa opcional, você pode substituir a política de retenção atual atribuída ao plano de caixa de correio (por padrão, a Política mrm padrão) pela política de retenção que você criou na Etapa 3. Depois de atualizar o plano de caixa de correio, a nova política de retenção será atribuída a novas caixas de correio.

1. [Conectar-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o seguinte comando para exibir informações sobre os planos de caixa de correio em sua organização.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Observe o plano de caixa de correio definido como padrão.

3. Execute o seguinte comando para atribuir a nova política de retenção que você criou na Etapa 3 (por exemplo, **Alpine House Archive and Retention Policy**) ao plano de caixa de correio padrão. Este exemplo pressuprime que o nome do plano de caixa de correio padrão **é ExchangeOnlineEnterprise**.

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Você pode reprisar o comando na etapa 2 para verificar se a política de retenção atribuída ao plano de caixa de correio padrão foi alterada.

## <a name="more-information"></a>Mais informações

- Como a idade de retenção é calculada? A idade de retenção dos itens de caixa de correio é calculada a partir da data de entrega ou da data de criação para itens como mensagens de rascunho que não são enviadas, mas são criadas pelo usuário. Quando o Assistente de Pasta Gerenciada processa itens em uma caixa de correio, ele insere uma data inicial e uma data de expiração para todos os itens com marcas de retenção com a ação de retenção Excluir e Permitir Recuperação ou Excluir Permanentemente. Os itens que têm uma marca de arquivo morto são carimbados com uma data de movimentação. 

- A tabela a seguir fornece mais informações sobre cada marca de retenção adicionada à política de retenção personalizada que foi criada seguindo as etapas deste tópico.

    | Marca de retenção | O que essa marca faz | Integrado ou personalizado? | Tipo |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Year Move to Archive  <br/> |Move itens que têm 1095 dias (3 anos) para a caixa de correio de arquivo morto.  <br/> |Personalizado (Consulte [a Etapa 2: Criar novas marcas de retenção para as políticas de arquivamento e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de Política Padrão (arquivo morto); essa marca é aplicada automaticamente a toda a caixa de correio.  <br/> |
    |Alpine House 7 Year Permanently Delete  <br/> |Exclui permanentemente itens na caixa de correio principal ou na caixa de correio de arquivo morto quando eles têm 7 anos.  <br/> |Personalizado (Consulte [a Etapa 2: Criar novas marcas de retenção para as políticas de arquivamento e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de Política Padrão (exclusão); essa marca é aplicada automaticamente a toda a caixa de correio.  <br/> |
    |Itens excluídos da Casa Alpine de 5 anos excluim e permitem recuperação  <br/> |Exclui itens da pasta Itens Excluídos que têm 5 anos. Os usuários podem recuperar esses itens por até 14 dias após a exclusão.<sup>\*</sup> <br/> |Personalizado (Consulte [a Etapa 2: Criar novas marcas de retenção para as políticas de arquivamento e exclusão](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Marca de Política de Retenção (Itens Excluídos); essa marca é aplicada automaticamente aos itens na pasta Itens Excluídos.  <br/> |
    |Itens recuperáveis 14 dias Mover para Arquivo Morto  <br/> |Move itens que estão na pasta Itens Recuperáveis há 14 dias para a pasta Itens Recuperáveis na caixa de correio de arquivo morto.  <br/> |Integrado  <br/> |Marca de Política de Retenção (Itens Recuperáveis); essa marca é aplicada automaticamente aos itens na pasta Itens Recuperáveis.  <br/> |
    |Lixo eletrônico  <br/> |Exclui permanentemente itens que estão na pasta Lixo Eletrônico há 30 dias. Os usuários podem recuperar esses itens por até 14 dias após a exclusão.<sup>\*</sup> <br/> |Integrado  <br/> |Marca de Política de Retenção (Lixo Eletrônico); essa marca é aplicada automaticamente aos itens na pasta Lixo Eletrônico.  <br/> |
    |Exclusão de 1 mês  <br/> |Exclui permanentemente itens com 30 dias de vida. Os usuários podem recuperar esses itens por até 14 dias após a exclusão.<sup>\*</sup> <br/> |Integrado  <br/> |Pessoal; essa marca pode ser aplicada pelos usuários.  <br/> |
    |Exclusão de 1 ano  <br/> |Exclui permanentemente itens com 365 dias. Os usuários podem recuperar esses itens por até 14 dias após a exclusão.<sup>\*</sup> <br/> |Integrado  <br/> |Pessoal; essa marca pode ser aplicada pelos usuários.  <br/> |
    |Nunca Excluir  <br/> |Essa marca impede que os itens são excluídos por uma política de retenção.  <br/> |Integrado  <br/> |Pessoal; essa marca pode ser aplicada pelos usuários.  <br/> |
    |Movimentação de 1 anos para arquivo pessoal  <br/> |Move itens para a caixa de correio de arquivo morto após 1 ano.  <br/> |Integrado  <br/> |Pessoal; essa marca pode ser aplicada pelos usuários.  <br/> |

    > <sup>\*</sup>Os usuários podem usar a ferramenta Recuperar Itens Excluídos no Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) para recuperar um item excluído dentro do período de retenção de item excluído, que por padrão é de 14 dias em Exchange Online. Um administrador pode usar Windows PowerShell para aumentar o período de retenção de item excluído para um máximo de 30 dias. Para obter mais informações, consulte: Recuperar itens [excluídos](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) no Outlook para Windows e Alterar o período de retenção de item excluído para uma caixa de correio em [Exchange Online](https://www.microsoft.com/?ref=go)
  
- Usar a marca de retenção **Itens Recuperáveis 14** dias Move to Archive ajuda a liberar espaço de armazenamento na pasta Itens Recuperáveis na caixa de correio principal do usuário. Isso é útil quando a caixa de correio de um usuário é colocada em espera, o que significa que nada é excluído permanentemente da caixa de correio do usuário. Sem mover itens para a caixa de correio de arquivo morto, é possível que a cota de armazenamento da pasta Itens Recuperáveis na caixa de correio principal seja atingida. Para obter mais informações sobre isso e como evitá-lo, consulte [Increase the Recoverable Items quota for mailboxes on hold](./increase-the-recoverable-quota-for-mailboxes-on-hold.md).