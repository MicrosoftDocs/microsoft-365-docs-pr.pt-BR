---
title: Remover um ex-funcionário
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Siga esta lista de verificação para remover um funcionário do Microsoft 365 e proteger dados. '
ms.openlocfilehash: ec2dd37a38c2509c2aa6a904326b74c8d3b8d7fb
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023996"
---
# <a name="remove-or-delete-a-former-employee"></a>Remover ou excluir um ex-funcionário

## <a name="sign-out-now"></a>Sair agora!

::: moniker range="o365-worldwide"

Assista a um breve vídeo sobre como remover um funcionário. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](../../business-video/index.yml).

Para impedir que um funcionário entre em log:

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.
3. Insira uma nova senha e selecione **Redefinir**. (Não envie para eles.)
4. Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o usuário e selecione **Redefinir senha**.

3. Insira uma nova senha e selecione **Redefinir**. (Não envie para eles.)

4. Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o usuário e selecione **Redefinir senha**.

3. Insira uma nova senha e selecione **Redefinir**. (Não envie para eles.)

4. Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.

::: moniker-end

> [!NOTE]
> Você precisa ser um administrador global para iniciar a saída.

Dentro de uma hora - ou depois de sair da página atual do Microsoft 365 em que estão - eles são solicitados a entrar novamente. Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.
  
> [!IMPORTANT]
> Se o usuário estiver no Outlook na Web, apenas clicando em sua caixa de correio, ele pode não ser colocado para fora imediatamente. Assim que eles selecionam um azulejo diferente, como o OneDrive, ou atualizem o navegador, a saída é iniciada.
  
Para usar o PowerShell para desconectar um usuário imediatamente, confira o cmdlet [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken).
  
Para saber mais sobre quanto tempo é preciso para excluir alguém do email, confira [O que você precisa saber sobre o encerramento da sessão de email de um funcionário](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Visão geral de todas as etapas para remover um funcionário e proteger dados

Uma pergunta que recebemos frequentemente é: o que posso fazer para proteger os dados quando um funcionário deixa a organização? Este artigo explica como bloquear o acesso ao Microsoft 365 e as etapas que você deve seguir para proteger seus dados.
  
> [!NOTE]
> Se você for um administrador global, poderá excluir o funcionário, encaminhar seus emails, escolher o que fazer com o conteúdo do OneDrive usando a nova experiência guiada. Para obter mais informações, consulte [Administrador global: Excluir um usuário](remove-former-employee.md). No entanto, recomendamos concluir todas as etapas adicionais listadas aqui para garantir que o funcionário não tenha acesso aos dados da sua empresa. 
  
A seguir está uma breve visão geral. Cada etapa é explicada em detalhes neste artigo.
  
|||
|:-----|:-----|
|**Etapa** <br/> |**Por que fazer isso** <br/> |
|1. [Salvar o conteúdo da caixa de correio de um ex-funcionário](#save-the-contents-of-a-former-employees-mailbox) <br/> |Isso é útil para a pessoa que assumirá o trabalho do funcionário ou se houver litígio.  <br/> |
|2. [Encaminhar o email do ex-funcionário a outro funcionário ou convertê-lo em uma caixa de correio compartilhada](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |Isso permite manter o endereço de email do ex-funcionário ativo. Se clientes ou parceiros ainda enviarem emails ao endereço de email do ex-funcionário, isso os encaminhará para a pessoa que assumir o trabalho.  <br/> |
|3. [Apagar e bloquear o dispositivo móvel de um ex-funcionário](#wipe-and-block-a-former-employees-mobile-device) <br/> |Remove seus dados comerciais do telefone ou tablet.  <br/> |
|4. [Bloquear o acesso de um ex-funcionário aos dados do Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Isso impede que a pessoa acesse sua caixa de correio e dados antigos do Microsoft 365.  <br/><br/> **Dica:** ao bloquear o acesso de um usuário, você ainda está pagando pela licença. Para parar de pagar por ela, exclua a licença de sua assinatura (etapa 5).  |
|5. [Mover o conteúdo do OneDrive do funcionário](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Quando você remove apenas a licença e não exclui a conta do usuário, o conteúdo do OneDrive permanece acessível para você mesmo após os 30 dias.  <br/><br/> Antes de excluir a conta, você deve migrar o conteúdo do OneDrive desse usuário para outro local de fácil acesso. Depois que você excluir a conta de um funcionário, o conteúdo no OneDrive será retido por **30** dias. No entanto, durante esses 30 dias você pode restaurar a conta do usuário e ter acesso ao conteúdo dele no OneDrive. Se você restaurar a conta do usuário, o conteúdo do OneDrive permanecerá acessível para você mesmo após os 30 dias.  <br/> |
|5a. E se a pessoa usou o computador pessoal para acessar o OneDrive e o SharePoint?  <br/> |Se ela usou um computador pessoal em vez de um computador corporativo para baixar arquivos do OneDrive e do SharePoint, não há nenhuma maneira de apagar os arquivos armazenados por ela.  <br/><br/> Eles continuam a ter acesso a todos os arquivos que foram sincronizados com o computador.  <br/> |
|6. Remover e excluir a licença do [Microsoft 365 de um ex-funcionário](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |Ao remover uma licença, você pode atribuí-la a outra pessoa. Ou pode excluir a licença para não pagar por ela até contratar outra pessoa.  <br/><br/> Quando você remove ou exclui uma licença, o antigo email, contatos e calendário do usuário são mantidos por **30 dias** e, em seguida, excluídos permanentemente. Se você remover ou excluir a licença, mas não excluir a conta do usuário, o conteúdo do OneDrive permanecerá acessível para você mesmo após os 30 dias.  <br/> |
|7. [Excluir a conta de usuário de um ex-funcionário](#delete-a-former-employees-user-account)<br/> |Isso remove a conta do centro de administração. Mantenha as coisas organizadas.  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Salvar o conteúdo da caixa de correio de um ex-funcionário

Há duas maneiras de salvar o conteúdo da caixa de correio do ex-funcionário:
  
1. Adicionar o endereço de email do ex-funcionário à sua versão do Outlook 2013 ou 2016 e exportar os dados para um arquivo .pst. É possível importar os dados para outra conta de email conforme necessário. Para saber como fazer isso, confira [Obter acesso e fazer back up dos dados de um ex-usuário](get-access-to-and-back-up-a-former-user-s-data.md).

    OU

2. Coloque uma retenção de litígio ou bloqueio in-loco na caixa de correio antes de excluir a conta do usuário. Isso é muito mais complicado do que a primeira opção, mas vale a pena se o seu plano empresarial inclui arquivamento e retenção jurídica, se o litígio é uma possibilidade e se você tem um departamento de TI com excelente experiência técnica.

    Depois de converter a caixa de correio em uma "caixa de correio inativa", os administradores, responsáveis pela conformidade ou gerentes de registros podem usar In-Place ferramentas de Descoberta Eletrônico no Exchange Online para acessar e pesquisar o conteúdo.

    As caixas de correio inativas não podem receber emails e não são exibidas no catálogo de endereços compartilhados da sua organização ou em outras listas.

    Para saber como colocar uma espera em uma caixa de correio, consulte [Gerenciar caixas de correio inativas no Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Encaminhar o email do ex-funcionário a outro funcionário ou convertê-lo em uma caixa de correio compartilhada

Nesta etapa, você atribui o endereço de email do ex-funcionário para outro funcionário ou [converte a caixa de correio do usuário em uma caixa de correio compartilhada](../email/convert-user-mailbox-to-shared-mailbox.md) que você tenha criado.
  
- Criar uma caixa de correio compartilhada é a maneira mais econômica, pois assim não é necessário pagar por uma licença, **desde que a caixa de correio tenha menos de 50 GB**. Para caixas de correio acima de 50 GB, é necessário atribuir uma licença.
- Se você converter a caixa de correio em uma caixa de correio compartilhada, todos os emails antigos ficarão disponíveis também. Isso pode ocupar muito espaço.
- Quando você configura o encaminhamento de email, apenas os  *novos*  emails enviados ao ex-funcionário são enviados para o funcionário atual.

 > [!IMPORTANT]
 > Se você estiver configurando o encaminhamento de email ou uma caixa de correio compartilhada, no final, não exclua a conta do ex-funcionário. Ela deve existir para ancorar o encaminhamento de email ou a caixa de correio compartilhada.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja bloquear e selecione a **guia Email.**
3. Em **Encaminhamento de Email,** selecione **Gerenciar encaminhamento de email.**
4. Ative **Encaminhar todos os emails enviados para esta caixa de correio**. Na caixa **Endereço de encaminhamento,** digite o endereço de email do funcionário atual que vai receber o email.
5. Selecione **Salvar**.
6. Lembre-se de não excluir a conta do ex-funcionário.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e expandir **Configurações de Email.**

3. Ao lado de **Encaminhamento de Email,** selecione **Editar**.

4. Ative **Encaminhar todos os emails enviados para esta caixa de correio**. Na caixa **Endereço de encaminhamento**, digite o endereço de email do funcionário atual (ou da caixa de correio compartilhada) que vai receber os emails.
  
5. Selecione **Salvar**.

6. Lembre-se de não excluir a conta do ex-funcionário.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e expandir **Configurações de Email.**

3. Ao lado de **Encaminhamento de Email,** selecione **Editar**.

4. Ative **Encaminhar todos os emails enviados para esta caixa de correio**. Na caixa **Endereço de encaminhamento**, digite o endereço de email do funcionário atual (ou da caixa de correio compartilhada) que vai receber os emails.
  
5. Selecione **Salvar**.

6. Lembre-se de não excluir a conta do ex-funcionário.

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Apagar e bloquear o dispositivo móvel de um ex-funcionário

Se seu ex-funcionário tinha um telefone de organização, você pode usar o Centro de administração do Exchange para apagar e bloquear esse dispositivo para que todos os dados da organização seja removidos do dispositivo e ele não possa mais se conectar ao Office 365.

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
2. No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.
3. Selecione o usuário e, em **Dispositivos Móveis,** selecione **Exibir detalhes**.
4. Na página **Detalhes do Dispositivo** Móvel, em **Dispositivos** Móveis, selecione o dispositivo móvel, selecione **Apagar Dispositivo** de Apagar Dados e selecione ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Bloquear**.
5. Selecione **Salvar**.
   > [!TIP]
   > Certifique-se de remover ou desabilitar o usuário do Serviço Empresarial blackberry local. Você também deve desabilitar todos os dispositivos Blackberry desse usuário. Veja o Guia de Administração do Blackberry Business Cloud Services se precisar de etapas específicas para desabilitar o usuário.

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Bloquear o acesso de um ex-funcionário aos dados do Microsoft 365

 > [!IMPORTANT]
 > O bloqueio de uma conta pode levar até 24 horas para ter efeito. Se você precisar impedir imediatamente o acesso de entrada [](reset-passwords.md) de um usuário, você deve redefinir a senha e iniciar um evento único que as desajuste das sessões do Microsoft 365 em todos os dispositivos. Confira [Sair agora!](#sign-out-now)

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja bloquear e, sob o nome do usuário, selecione o símbolo para **Bloquear este usuário**.
3. Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, selecione **Bloquear a assinatura**.

3. Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, selecione **Bloquear a assinatura**.

3. Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear o acesso de um ex-funcionário ao email (Exchange Online)

Se você tiver emails como parte da sua assinatura do Microsoft 365, você precisará entrar no Centro de administração do Exchange para seguir estas etapas para impedir que seu ex-funcionário acesse seus emails.
  
1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
2. No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.
3. Clique duas vezes no usuário e vá para a página **Recursos de Caixa de** Correio. Em **Dispositivos Móveis,** selecione **Desabilitar Exchange ActiveSync** e **Desabilitar o OWA para** Dispositivos e responda **Sim** a ambos quando solicitado.
4. Em **Conectividade de Email,** selecione **Desabilitar** e responder **Sim** quando solicitado.

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Remover e excluir a licença do Microsoft 365 de um ex-funcionário

Para que você não continue pagando por uma licença depois que alguém sair da sua organização, você precisa remover sua licença do Microsoft 365 e excluí-la da sua assinatura. Se preferir não excluir a licença da assinatura, é possível atribuí-la a outro usuário.
  
Quando você remove a licença, todos os dados do usuário são mantidos por 30 dias. Você pode [acessar](get-access-to-and-back-up-a-former-user-s-data.md) os dados ou [restaurar](restore-user.md) a conta se o usuário retornar. Após 30 dias, todos os dados do usuário (exceto os documentos armazenados no SharePoint Online) são excluídos permanentemente do Microsoft 365 e não podem ser recuperados.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja bloquear e selecione a guia **Licenças e Aplicativos.**
3. Des limpar as caixas de seleção para as licenças que você deseja remover e selecione **Salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, ao lado de **Licenças de produto,** selecione **Editar**.

3. Na página **Licenças de** produto, alterne as licenças que você deseja remover e selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, ao lado de **Licenças de produto,** selecione **Editar**.

3. Na página **Licenças de** produto, alterne as licenças que você deseja remover e selecione **Salvar**.

::: moniker-end

**Para reduzir o número de licenças** que você está pagando até contratar outra pessoa, faça as seguintes etapas:

::: moniker range="o365-worldwide"
1. No centro de administração, vá até a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus</a> produtos e selecione **a guia** Produtos.
2. Selecione a assinatura da qual você deseja remover licenças.
3. Na página detalhes, selecione **Remover licenças**.
4. No painel **Remover licenças,** em Nova quantidade, na caixa Total de **licenças,** insira o número total de licenças que você deseja para essa assinatura. Por exemplo, se você tiver 25 licenças e quiser remover uma delas, insira 24.
5. Selecione **Salvar**.
::: moniker-end

::: moniker range="o365-germany"
1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.
2. Selecione **Adicionar/Remover licenças** para excluir a licença para que você não pague por ela até contratar outra pessoa.
::: moniker-end

::: moniker range="o365-21vianet"
1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.
2. Selecione **Adicionar/Remover licenças** para excluir a licença para que você não pague por ela até contratar outra pessoa.
::: moniker-end

Ao [adicionar outra pessoa](add-users.md) à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

Para obter mais informações sobre como gerenciar licenças de usuário para o Microsoft 365 para empresas, consulte [Assign licenses to users in Microsoft 365 for business](../manage/assign-licenses-to-users.md)e [Unassign licenses from users in Microsoft 365 for business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Como a conta de funcionário excluída afeta o Skype for Business

Quando você remove uma licença de usuário do Office 365, o número de chamada PSTN associado ao usuário será lançado. Você pode atribuí-la a outro usuário.
  
Se o usuário pertencer a um grupo de espera, ele não será mais um alvo viável de agentes da fila a chamada. Portanto, recomendamos remover o usuário também de grupos associados à fila de chamadas.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configurar o encaminhamento de chamada para pessoas em sua organização

Se você precisar configurar o encaminhamento de chamadas para o número de telefone do funcionário encerrado, a configuração de encaminhamento de chamada em políticas de chamada pode configurar o encaminhamento para onde as chamadas de entrada podem ser encaminhadas para outros usuários ou podem tocar em outra pessoa ao mesmo tempo. Para obter mais informações, consulte [Políticas de chamada no Microsoft Teams](/microsoftteams/teams-calling-policy).
  
## <a name="delete-a-former-employees-user-account"></a>Excluir a conta de usuário de um ex-funcionário

Depois de salvar e acessar todos os dados de usuário do ex-funcionário, você pode excluir a conta do ex-funcionário.
  
Não exclua a conta se tiver configurado o encaminhamento de email ou se tiver convertido essa conta em uma caixa de correio compartilhada. Ambos precisam da conta para ancorar o encaminhamento ou a caixa de correio compartilhada.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja excluir.
3. Em nome do usuário, selecione o símbolo para **Excluir usuário**. Escolha as opções que você deseja para esse usuário e selecione **Excluir usuário**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja excluir.

3. Na parte superior da página, selecione **Excluir usuário**. Escolha as opções que você deseja para esse usuário e selecione **Excluir usuário**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja excluir.

3. Na parte superior da página, selecione **Excluir usuário**. Escolha as opções que você deseja para esse usuário e selecione **Excluir usuário**.

::: moniker-end

Quando você exclui um usuário, a conta se torna inativa por aproximadamente 30 dias. Você tem até esse prazo para restaurar a conta antes de ela ser permanentemente excluída.
  
### <a name="does-your-organization-use-active-directory"></a>Sua organização usa o Active Directory?

Se sua organização sincroniza contas de usuário com o Microsoft 365 de um ambiente local do Active Directory, você deve excluir e restaurar essas contas de usuário em seu serviço local do Active Directory. Não é possível excluí-las ou restaurá-las no Office 365.
  
Para saber como excluir e restaurar a conta de usuário no Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Se você estiver usando o Azure Active Directory, consulte o cmdlet [Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>O que você precisa saber sobre o encerramento da sessão de email de um funcionário

Aqui estão as informações sobre como excluir um funcionário do email (Exchange).
  
|||
|:-----|:-----|
|**O que você pode fazer** <br/> |**Como fazer isso** <br/> |
|Encerrar uma sessão (como o Outlook na Web, Outlook, Exchange Active Sync, etc.) e forçar a abertura de uma nova sessão  <br/> |Redefina a senha  <br/> |
|Encerrar uma sessão e bloquear o acesso a sessões futuras (para todos os protocolos)  <br/> |Desabilite a conta. Por exemplo, (no Centro de administração do Exchange ou usando o PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Encerrar a sessão de um protocolo específico (como ActiveSync)  <br/> |Desabilite o protocolo. Por exemplo, (no Centro de administração do Exchange ou usando o PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

As operações acima podem ser feitas em três locais:
  
|||
|:-----|:-----|
|**Se você encerrar a sessão aqui** <br/> |**Quanto tempo demora** <br/> |
|No centro de administração do Exchange ou usando o PowerShell  <br/> |O atraso esperado é de 30 minutos  <br/> |
|No centro de administração do Azure Active Directory  <br/> |O atraso esperado é de 60 minutos  <br/> |
|Em um ambiente local  <br/> |O atraso esperado é de três horas ou mais  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Como obter a resposta mais rapidamente para o encerramento da conta

 **Mais rápido**: use o centro de administração do Exchange (use o PowerShell) ou o centro de administração do Azure Active Directory. Em um ambiente local, pode demorar várias horas para sincronizar a alteração por meio do DirSync.
  
 **O mais rápido para um usuário com presença local e no Datacenter do Exchange**: Encerre a sessão usando o centro de administração do Azure Active Directory/centro de administração do Exchange e altere TAMBÉM no ambiente local. Caso contrário, a alteração no centro de administração do Azure Active Directory/centro de administração do Exchange será substituída pelo DirSync.
  
## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)