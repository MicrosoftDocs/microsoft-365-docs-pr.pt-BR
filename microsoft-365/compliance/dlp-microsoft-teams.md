---
title: Prevenção de perda de dados e Microsoft Teams
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Agora, você pode aplicar políticas de DLP a chats e canais do Microsoft Teams. Leia este artigo para saber mais sobre como ele funciona.
ms.openlocfilehash: 55a13d44ab3cff777ee8ed4610d746c3649bf558
ms.sourcegitcommit: 3401f90721e6f7c65152a31c5be1bb91bfe641c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2020
ms.locfileid: "41022356"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenção de perda de dados e Microsoft Teams

> [!NOTE]
> Os recursos de prevenção contra perda de dados foram recentemente adicionados às mensagens de chat e de canal do Microsoft Teams para usuários licenciados para a Conformidade Avançada do Office 365, disponível como uma opção independente e está incluso na Conformidade do Office 365 E5 e no Microsoft 365 E5. O Office 365 e o Microsoft 365 E3 incluem o DLP Protection para SharePoint Online, OneDrive e Exchange Online. Isso também inclui arquivos compartilhados por meio do teams porque o Teams usa o SharePoint Online e o OneDrive para compartilhar arquivos.
O suporte para proteção DLP no Teams chat requer e5.
Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Visão geral da DLP para o Microsoft Teams

Recentemente, os recursos de DLP ( [prevenção contra perda de dados](data-loss-prevention-policies.md) ) foram estendidos para incluir mensagens de chat e de canal do Microsoft Teams. Se sua organização tem DLP, agora você pode definir políticas que impedem que as pessoas compartilhem informações confidenciais em um canal do Microsoft Teams ou em uma sessão de chat. Estes são alguns exemplos de como essa proteção funciona:

- **Exemplo 1: protegendo informações confidenciais em mensagens**. Suponha que alguém tente compartilhar informações confidenciais em um chat de equipes ou canal com convidados (usuários externos). Se você tiver uma política de DLP definida para evitar isso, as mensagens com informações confidenciais enviadas a usuários externos serão excluídas. Isso ocorre automaticamente e, em segundos, de acordo com o modo como sua política de DLP é configurada.

    > [!NOTE]
    > O DLP para o Microsoft Teams bloqueia conteúdo confidencial quando compartilhado com usuários do Microsoft Teams que têm:<br/>- [acesso de convidados](https://docs.microsoft.com/MicrosoftTeams/guest-access) em equipes e canais; ou<br/>- [acesso externo](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) em sessões de chat e reuniões. <p>A DLP para sessões de chat externas só funcionará se o remetente e o receptor estiverem no modo somente Teams e o uso da [Federação nativa do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access). O DLP para Teams não bloqueia mensagens em [interoperabilidade](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com o Skype for Business ou sessões de chat federadas não nativas.

- **Exemplo 2: protegendo informações confidenciais em documentos**. Suponha que alguém tente compartilhar um documento com convidados em um canal ou chat do Microsoft Teams, e o documento contém informações confidenciais. Se você tiver uma política de DLP definida para evitar isso, o documento não será aberto para esses usuários. Observe que, nesse caso, sua política de DLP deve incluir o SharePoint e o OneDrive para que a proteção esteja no local. (Este é um exemplo de DLP para SharePoint que aparece no Microsoft Teams e, portanto, requer que os usuários estejam licenciados para o Office 365 DLP (incluído no Office 365 E3), mas não exija que os usuários sejam licenciados para conformidade avançada do Office 365.)

## <a name="policy-tips-help-educate-users"></a>Dicas de política ajudam a ensinar usuários

Semelhante à forma como o DLP funciona no [Exchange, Outlook, Outlook na Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, sites do onedrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e [clientes de área de trabalho do Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), as dicas de política são exibidas quando uma ação entra em conflito com uma política de DLP. Veja um exemplo de uma dica de política:

![Notificação de mensagem bloqueada no Teams](media/dlp-teams-blockedmessage-notification.png)

Nesse caso, o remetente tentou compartilhar um número de segurança social em um canal do Microsoft Teams. O link o **que eu posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema. Observe que, nesse caso, o remetente pode optar por substituir a política ou notificar um administrador para revisá-la e resolvê-la.

![Opções para resolver mensagem bloqueada](media/dlp-teams-blockedmessage-possibleactions.png)

Em sua organização, você pode optar por permitir que os usuários substituam uma política de DLP. E, ao configurar suas políticas de DLP, você pode usar as dicas de política padrão ou [personalizar dicas de política](#to-customize-policy-tips) para sua organização. 

Retornando ao nosso exemplo, em que um remetente compartilhou um número de seguro social em um canal do Teams, aqui está o que o destinatário viu:

![Mensagem bloqueada](media/dlp-teams-blockedmessage-notification-to-user.png)

O link o **que é isto** abre um [artigo](data-loss-prevention-policies.md) sobre políticas de DLP, que ajuda a explicar por que a mensagem foi bloqueada.

### <a name="to-customize-policy-tips"></a>Para personalizar dicas de política

Para realizar essa tarefa, você deve receber uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o centro de conformidade & segurança do Office[https://protection.office.com](https://protection.office.com)365 () e entre.

2. Escolha > **política**de **prevenção contra perda de dados**. 

3. Selecione uma política e ao lado de **configurações de política**, escolha **Editar**.

4. Crie uma nova regra ou edite uma regra existente para a política.<br/>![Editando uma regra para uma política](media/dlp-teams-editrule.png)<br/>

5. Na guia **notificações do usuário** , selecione **Personalizar o texto do email** e/ou **Personalizar as opções de texto de dica de política** .<br/>![Personalizar notificações de usuário e dicas de política](media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique o texto que você deseja usar para notificações por email e/ou dicas de política e, em seguida, escolha **salvar**. 

7. Na guia **configurações de política** , escolha **salvar**.

Aguarde aproximadamente uma hora para que suas alterações funcionem de forma em seu data center e sincronize com as contas de usuário.
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Adicionar o Microsoft Teams como um local às políticas de DLP existentes

Para realizar essa tarefa, você deve receber uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o centro de conformidade & segurança do Office[https://protection.office.com](https://protection.office.com)365 () e entre.

2. Escolha > **política**de **prevenção contra perda de dados**. 

3. Selecione uma política e examine os valores em **locais**. Se você vir **chat de equipes e mensagens de canal**, tudo pronto. Caso contrário, clique em **Editar**.<br/>![Locais para política existente](media/dlp-teams-editexistingpolicy.png)<br/>

4. Na coluna **status** , ative a política para chat de **equipes e mensagens de canal**.<br/>![DLP para bate-papos e canais do teams](media/dlp-teams-addteamschatschannels.png)<br/>

5. Mantenha as configurações padrão de todas as contas ou especifique quais contas serão incluídas ou excluídas.

6. Clique em **Salvar**.

Aguarde aproximadamente uma hora para que suas alterações funcionem de forma em seu data center e sincronize com as contas de usuário.
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir uma nova política de DLP para o Microsoft Teams

Para realizar essa tarefa, você deve receber uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o centro de conformidade & segurança do Office[https://protection.office.com](https://protection.office.com)365 () e entre.

2. Escolha > **** política > de **prevenção contra perda de dados****+ criar uma política**. 

3. Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e, em seguida, escolha **Avançar**.<br/>No nosso exemplo, escolhemos o modelo de dados de informações de identificação pessoal dos EUA.<br/>![Modelo de privacidade para política de DLP](media/dlp-teams-createnewpolicy-template.png)<br/>

4. Na guia **nomear sua política** , especifique um nome e uma descrição para a política e, em seguida, escolha **Avançar**. 

5. Na guia **escolher locais** , mantenha a configuração padrão de todos os locais ou selecione **deixe-me escolher locais específicos**e, em seguida, escolha **Avançar**.<br/>Se você escolher locais específicos, selecione-os para a política de DLP e, em seguida, escolha **Avançar**.<br/>![Locais de política de DLP](media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > Se você quiser garantir que os documentos que contêm informações confidenciais não sejam compartilhados inadequadamente, verifique se os **sites do SharePoint** e as **contas do onedrive** estão ativados, junto com **as mensagens de chat e de canal do teams**.
    > Os canais no Microsoft Teams são fortemente dependentes da funcionalidade do Exchange Online. Verifique se o local de **email do Exchange** também está habilitado para as políticas que devem ser aplicadas ao conteúdo dos canais.  
<br/>

6. Na guia **configurações de política** , em **Personalizar o tipo de conteúdo que você deseja proteger**, mantenha as configurações simples padrão ou escolha **usar configurações avançadas**e, em seguida, escolha **Avançar**. Se você escolher configurações avançadas, você pode criar ou editar regras para sua política. (Para obter ajuda com isso, consulte [configurações simples vs. configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  Na guia **configurações de política** , em **o que você deseja fazer se detectarmos informações confidenciais?**, revise as configurações. (Aqui você pode optar por manter [dicas de política padrão e notificações por email](use-notifications-and-policy-tips.md)ou personalizá-las.)<br/>![Configurações de política de DLP com dicas e notificações](media/dlp-teams-policysettings-tipsemails.png)<br/>Quando terminar de revisar ou editar as configurações, escolha **Avançar**.

8. Na guia **configurações de política** , em **você deseja ativar a política ou testar as tarefas primeiro?**, escolha se deseja ativar a política, [testá-la primeiro](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)ou mantê-la desativada por enquanto e, em seguida, escolha **Avançar**.<br/>![Especificar se a política será ativada](media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Na guia **examinar suas configurações** , revise as configurações da nova política. Escolha **Editar** para fazer alterações. Quando tiver terminado, escolha **criar**. 

Aguarde aproximadamente uma hora para que sua nova política funcione de forma em seu data center e sincronize com as contas de usuário.

## <a name="related-articles"></a>Artigos relacionados

[Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

[Enviar notificações por email e mostrar dicas para políticas de DLP](use-notifications-and-policy-tips.md)
