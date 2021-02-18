---
title: Prevenção contra perda de dados e Microsoft Teams
f1.keywords:
- NOCSH
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
description: Agora você pode aplicar políticas DLP a canais e chats do Microsoft Teams. Leia este artigo para saber mais sobre como ele funciona.
ms.openlocfilehash: 13d5d73423cc6ad7db76076f6a53dde668b8fa5c
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279359"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenção contra perda de dados e Microsoft Teams

> [!NOTE]
> Os recursos de prevenção contra perda de dados foram adicionados recentemente às mensagens de chat e canal do Microsoft Teams para usuários licenciados para Office 365 E5/A5, Microsoft 365 E5/A5, Proteção e Governança de Informações do Microsoft 365 ou Office 365 Advanced Compliance. O Office 365 e o Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online. Isso também inclui arquivos compartilhados por meio do Teams porque o Teams usa o SharePoint Online e o OneDrive para compartilhar arquivos.
O suporte para proteção DLP no Chat do Teams requer o E5.
Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

> [!IMPORTANT]
> A DLP para o Teams só é suportada quando o usuário tem uma caixa de correio que está no Exchange Online

## <a name="overview-of-dlp-for-microsoft-teams"></a>Visão geral da DLP para o Microsoft Teams

Recentemente, os [recursos de prevenção](data-loss-prevention-policies.md) contra perda de dados (DLP) foram estendidos para incluir mensagens de canal e chat do Microsoft Teams, **incluindo mensagens de canal privado.**

Se sua organização tem DLP, agora você pode definir políticas que impedem que as pessoas compartilhem informações confidenciais em um canal ou sessão de chat do Microsoft Teams. Aqui estão alguns exemplos de como essa proteção funciona:

- **Exemplo 1: Proteger informações confidenciais em mensagens.** Suponha que alguém tenta compartilhar informações confidenciais em um chat ou canal do Teams com convidados (usuários externos). Se você tiver uma política de DLP definida para evitar isso, as mensagens com informações confidenciais enviadas a usuários externos serão excluídas. Isso acontece automaticamente e em segundos, de acordo com a configuração da política de DLP.

    > [!NOTE]
    > A DLP do Microsoft Teams bloqueia o conteúdo sensível quando compartilhado com usuários do Microsoft Teams que têm:<br/>- [acesso de convidados](https://docs.microsoft.com/MicrosoftTeams/guest-access) em equipes e canais; ou<br/>- [acesso externo](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) em reuniões e sessões de chat. <p>A DLP para sessões de chat externas só funcionará se o remetente e o destinatário estão no modo Teams Only e usando a [federação nativa do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access) A DLP do Teams não bloqueia mensagens na [interopção](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com o Skype for Business ou sessões de chat federadas não nativas.

- **Exemplo 2: Proteger informações confidenciais em documentos.** Suponha que alguém tenta compartilhar um documento com convidados em um canal ou chat do Microsoft Teams e o documento contém informações confidenciais. Se você tiver uma política DLP definida para evitar isso, o documento não será aberto para esses usuários. Observe que, nesse caso, sua política de DLP deve incluir o SharePoint e o OneDrive para que a proteção seja realizada. (Este é um exemplo de DLP para SharePoint que aparece no Microsoft Teams e, portanto, requer que os usuários sejam licenciados para a DLP do Office 365 (incluído no Office 365 E3), mas não exige que os usuários sejam licenciados para a Conformidade Avançada do Office 365.)

## <a name="policy-tips-help-educate-users"></a>Dicas de política ajudam a instruir os usuários

Semelhante a como a DLP funciona no [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)na [Web, SharePoint Online, sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)do OneDrive for Business e clientes da área de trabalho do [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)as dicas de política aparecem quando uma ação entra em conflito com uma política de DLP. Veja um exemplo de dica de política:

![Notificação de mensagem bloqueada no Teams](../media/dlp-teams-blockedmessage-notification.png)

Nesse caso, o remetente tentou compartilhar um número de seguro social em um canal do Microsoft Teams. O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema. Observe que, nesse caso, o remetente pode optar por substituir a política ou notificar um administrador para revisá-la e resolvê-la.

![Opções para resolver mensagens bloqueadas](../media/dlp-teams-blockedmessage-possibleactions.png)

Em sua organização, você pode optar por permitir que os usuários substituam uma política de DLP. E, ao configurar suas políticas de DLP, você pode usar as dicas de política padrão ou personalizar as dicas [de política](#to-customize-policy-tips) para sua organização.

Retornando ao nosso exemplo, em que um remetente compartilhou um número de seguro social em um canal do Teams, veja o que o destinatário viu:

![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)

O **link What's this?** abre um [artigo sobre](data-loss-prevention-policies.md) políticas de DLP, que ajuda a explicar por que a mensagem foi bloqueada.

### <a name="to-customize-policy-tips"></a>Para personalizar dicas de política

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Escolha **Política de prevenção contra perda de**  >  **dados.**

3. Selecione uma política e, ao lado das **configurações de política,** escolha **Editar.**

4. Crie uma nova regra ou edite uma regra existente para a política.<br/>![Editando uma regra para uma política](../media/dlp-teams-editrule.png)<br/>

5. Na guia **Notificações do usuário,** selecione **Personalizar o texto do email** e/ou Personalizar as opções de texto da dica **de** política.<br/>![Personalizar notificações do usuário e dicas de política](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique o texto que você deseja usar para notificações por email e/ou dicas de política e, em seguida, escolha **Salvar**.

7. Na guia **Configurações de política,** escolha **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem no data center e sincronizem com contas de usuário.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Adicionar o Microsoft Teams como um local para políticas de DLP existentes

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Escolha **Política de prevenção contra perda de**  >  **dados.**

3. Selecione uma política e veja os valores em **Locais.** Se você vir mensagens **de chat e canal do Teams,** você está pronto. Se você não o fez, clique em **Editar**.<br/>![Locais para política existente](../media/dlp-teams-editexistingpolicy.png)<br/>

4. Na coluna **Status,** a ativar a política para mensagens de canal e **chat do Teams.**<br/>![DLP para chats e canais do Teams](../media/dlp-teams-addteamschatschannels.png)<br/>

5. Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos.** É possível especificar:
    1. até 1.000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. **Esse é um recurso de visualização pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Depois clique em **Próximo**.



6. Clique em **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem no data center e sincronizem com contas de usuário.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir uma nova política DLP para o Microsoft Teams

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Choose **Data loss prevention**  >  **Policy**+ Create a  >  **policy**.

3. Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **Próximo.**<br/>No nosso exemplo, escolhemos o modelo dados de informações de identificação pessoal dos EUA.<br/>![Modelo de privacidade para política DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Na guia **Nomear sua política,** especifique um nome e uma descrição para a política e escolha **Próximo.**

5. Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos.** É possível especificar:
    1. até 1.000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. **Esse é um recurso de visualização pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![Locais de política de DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> Se você quiser garantir que os documentos que contêm informações confidenciais não sejam compartilhados inadequadamente no Teams, certifique-se de que os sites do **SharePoint** e as contas do **OneDrive** estão ativas, juntamente com mensagens de chat e canal do **Teams.**


6. Na guia **Configurações** de política, em Personalizar o tipo de conteúdo que você deseja **proteger,** mantenha as configurações simples padrão ou escolha Usar configurações **avançadas** e escolha **Avançar.** Se você escolher configurações avançadas, poderá criar ou editar regras para sua política. (Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas.)](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  Na guia **Configurações de** política, em O que você deseja fazer se detectarmos **informações confidenciais?**, revise as configurações. (Aqui você pode optar por manter as dicas de política padrão e as notificações [por email](use-notifications-and-policy-tips.md)ou personalizá-las.)<br/>![Configurações de política de DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)<br/>Quando terminar de revisar ou editar as configurações, escolha **Próximo.**

8. On the **Policy settings** tab, under Do you want to turn on **the policy or test things out first?**, choose whether to turn the policy on, [test](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)it first , or keep it turned off for now, and then choose **Next**.<br/>![Especifique se a política será turn on](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Na guia **Revisar suas configurações,** revise as configurações da nova política. Escolha **Editar** para fazer alterações. Quando terminar, escolha **Criar**.

Permita aproximadamente uma hora para que sua nova política funcione em seu data center e sincronize com contas de usuário.

## <a name="prevent-external-access-to-sensitive-documents"></a>Impedir o acesso externo a documentos confidenciais

Para garantir que os documentos do SharePoint que contenham informações confidenciais não podem ser acessados por convidados externos do SharePoint ou do Teams por padrão, selecione o seguinte:

- Você pode garantir que os documentos sejam protegidos até que a DLP os verifique e os marque como seguros para compartilhar marcando novos arquivos como confidenciais [por padrão](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- Estrutura de política DLP recomendada
    - **Condições**
        - O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]
        - O conteúdo é compartilhado do Microsoft 365 com pessoas de fora da minha organização
        <br/>![Condições de DLP para detectar o compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **Ações**
        - Restringir o acesso ao conteúdo para usuários externos
        - Notificar os usuários com dicas de política e email
        - Enviar relatórios de incidentes ao Administrador    
        <br/>![Ação DLP para bloquear o compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-action.png)<br/>

Política DLP em ação ao tentar compartilhar um documento no SharePoint que contém informações confidenciais com um convidado externo:
<br/>![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


Política DLP em ação quando convidado tenta abrir um documento no Teams com bloqueio externo:
<br/>![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>Artigos relacionados

[Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

[Enviar notificações por email e mostrar dicas para políticas de DLP](use-notifications-and-policy-tips.md)
