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
description: Agora você pode aplicar políticas de DLP a chats e canais do Microsoft Teams. Leia este artigo para saber mais sobre como ele funciona.
ms.openlocfilehash: bd6fa1c04a57f64997d5646374007641afa0f958
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632233"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenção contra perda de dados e Microsoft Teams

> [!NOTE]
> Os recursos de prevenção contra perda de dados foram adicionados recentemente às mensagens de chat e canal do Microsoft Teams para usuários licenciados para Office 365 E5/A5, Microsoft 365 E5/A5, Proteção de Informações e Governança do Microsoft 365 ou Conformidade Avançada do Office 365. O Office 365 e o Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online. Isso também inclui arquivos compartilhados pelo Teams porque o Teams usa o SharePoint Online e o OneDrive para compartilhar arquivos.
O suporte para proteção DLP no Teams Chat requer E5.
Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Visão geral da DLP para o Microsoft Teams

Recentemente, [os recursos de](data-loss-prevention-policies.md) prevenção contra perda de dados (DLP) foram estendidos para incluir mensagens de chat e canal do Microsoft Teams, incluindo mensagens de canal **privado**. 

> [!IMPORTANT]
> A DLP atualmente só se aplica às mensagens reais no thread de chat ou canal. As notificações de atividade - que incluem uma visualização de mensagem  curta e aparecem com base nas configurações de notificação de um usuário - não estão incluídas na DLP do Teams no momento. Quaisquer informações confidenciais presentes na parte da mensagem exibida na visualização permanecerão visíveis na notificação mesmo depois que a política DLP tiver sido aplicada e removida informações confidenciais da própria mensagem.

Se sua organização tiver DLP, agora você pode definir políticas que impedem que as pessoas compartilhem informações confidenciais em um canal do Microsoft Teams ou sessão de chat. Aqui estão alguns exemplos de como essa proteção funciona:

- **Exemplo 1: Protegendo informações confidenciais em mensagens**. Suponha que alguém tenta compartilhar informações confidenciais em um chat ou canal do Teams com convidados (usuários externos). Se você tiver uma política de DLP definida para evitar isso, as mensagens com informações confidenciais enviadas a usuários externos serão excluídas. Isso acontece automaticamente e em segundos, de acordo com a configuração da política de DLP.

    > [!NOTE]
    > A DLP do Microsoft Teams bloqueia conteúdos confidenciais quando compartilhados com usuários do Microsoft Teams que têm:<br/>- [acesso de convidados](/MicrosoftTeams/guest-access) em equipes e canais; ou<br/>- [acesso externo](/MicrosoftTeams/manage-external-access) em reuniões e sessões de chat. <p>A DLP para sessões de chat externo só funcionará se o remetente e o receptor estão no modo Teams Only e usando a federação nativa [do Microsoft Teams.](/microsoftteams/manage-external-access) A DLP para o Teams não bloqueia mensagens [em interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com o Skype for Business ou sessões de chat federadas não nativas.

- **Exemplo 2: Protegendo informações confidenciais em documentos**. Suponha que alguém tenta compartilhar um documento com convidados em um canal ou chat do Microsoft Teams e o documento contém informações confidenciais. Se você tiver uma política de DLP definida para evitar isso, o documento não abrirá para esses usuários. Observe que, nesse caso, sua política de DLP deve incluir o SharePoint e o OneDrive para que a proteção seja realizada. (Este é um exemplo de DLP para SharePoint que aparece no Microsoft Teams e, portanto, exige que os usuários sejam licenciados para a DLP do Office 365 (incluído no Office 365 E3), mas não exige que os usuários sejam licenciados para a Conformidade Avançada do Office 365.)

## <a name="policy-tips-help-educate-users"></a>Dicas de política ajudam a instruir os usuários

Semelhante a como a DLP funciona no [Exchange, Outlook, Outlook na Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)Sites do [SharePoint Online, OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e clientes da área de trabalho do [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)as dicas de política aparecem quando uma ação entra em conflito com uma política de DLP. Veja um exemplo de uma dica de política:

![Notificação de mensagem bloqueada no Teams](../media/dlp-teams-blockedmessage-notification.png)

Nesse caso, o remetente tentou compartilhar um número de segurança social em um canal do Microsoft Teams. O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema. Observe que, nesse caso, o remetente pode optar por substituir a política ou notificar um administrador para revisá-la e resolvê-la.

![Opções para resolver mensagens bloqueadas](../media/dlp-teams-blockedmessage-possibleactions.png)

Em sua organização, você pode optar por permitir que os usuários substituam uma política de DLP. E, ao configurar suas políticas de DLP, você pode usar as dicas de política padrão ou [personalizar dicas](#to-customize-policy-tips) de política para sua organização.

Retornando ao nosso exemplo, onde um remetente compartilhou um número de segurança social em um canal do Teams, veja o que o destinatário viu:

> [!div class="mx-imgBorder"]
> ![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)

O **link O que é isso?** abre um [artigo](data-loss-prevention-policies.md) sobre políticas DLP, que ajuda a explicar por que a mensagem foi bloqueada.

### <a name="to-customize-policy-tips"></a>Para personalizar dicas de política

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Escolha **Política de prevenção contra perda de**  >  **dados**.

3. Selecione uma política e, ao lado de **Configurações de Política,** escolha **Editar**.

4. Crie uma nova regra ou edite uma regra existente para a política.

    > [!div class="mx-imgBorder"]
    > ![Editar uma regra para uma política](../media/dlp-teams-editrule.png)

5. Na guia **Notificações do usuário,** selecione **Personalizar o texto de email** e/ou Personalizar as opções de texto da dica **de** política.

    > [!div class="mx-imgBorder"]
    > ![Personalizar notificações do usuário e dicas de política](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique o texto que você deseja usar para notificações por email e/ou dicas de política e escolha **Salvar**.

7. Na guia **Configurações de Política,** escolha **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Adicionar o Microsoft Teams como local às políticas de DLP existentes

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Escolha **Política de prevenção contra perda de**  >  **dados**.

3. Selecione uma política e veja os valores em **Locais.** Se você vir mensagens **de chat e canal do Teams,** você está definido. Se não, clique em **Editar**.

    > [!div class="mx-imgBorder"]
    > ![Locais para política existente](../media/dlp-teams-editexistingpolicy.png)

4. Na coluna **Status,** a política é a ativas para mensagens de chat e **canal do Teams.**

    > [!div class="mx-imgBorder"]
    > ![DLP para chats e canais do Teams](../media/dlp-teams-addteamschatschannels.png)

5. Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**. É possível especificar:

    1. até 1000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. **Esse é um recurso de visualização pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Depois clique em **Próximo**.

7. Clique em **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir uma nova política de DLP para o Microsoft Teams

Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.

2. Escolha **Política de prevenção contra perda**  >  **de** dados + Criar uma  >  **política**.

3. Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **Next**.

    No nosso exemplo, escolhemos o modelo de Dados de Informações de Identificação Pessoal dos EUA.

    > [!div class="mx-imgBorder"]
    > ![Modelo de privacidade para política de DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Na guia **Nomear sua política,** especifique um nome e uma descrição para a política e escolha **Next**.

5. Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**. É possível especificar:

    1. até 1000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. **Esse é um recurso de visualização pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Locais de política DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Se você quiser garantir que documentos que contenham informações confidenciais não sejam compartilhados de forma inadequada no Teams, certifique-se de que sites do **SharePoint** e contas do **OneDrive** estão ativas, juntamente com mensagens de chat e canal do **Teams.**

6. Na guia **Configurações de** Política, em Personalizar o tipo de conteúdo que você deseja **proteger,** mantenha as configurações simples padrão ou escolha Usar configurações **avançadas** e escolha **Avançar**. Se você escolher configurações avançadas, poderá criar ou editar regras para sua política. (Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  Na guia **Configurações de** Política, em O que você deseja fazer se detectarmos informações **confidenciais?**, revise as configurações. (Aqui é onde você pode optar por manter dicas de política padrão e [notificações de email](use-notifications-and-policy-tips.md)ou personalizá-las.)

    > [!div class="mx-imgBorder"]
    > ![Configurações de política de DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)

    Quando terminar de revisar ou editar configurações, escolha **Next**.

8. Na  guia Configurações de Política, em Deseja ativar a política ou testar as coisas **primeiro?**, escolha se deseja ativar a [política,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)testá-la primeiro ou mantê-la desligada por enquanto e, em seguida, escolher **Next**.

    > [!div class="mx-imgBorder"]
    > ![Especificar se a política deve ser a a ativar](../media/dlp-teams-policysettings-turnonnow.png)

9. Na guia **Revisar suas configurações,** revise as configurações da nova política. Escolha **Editar** para fazer alterações. Quando terminar, escolha **Criar**.

Permita aproximadamente uma hora para que sua nova política funcione por meio do data center e sincronize com contas de usuário.

## <a name="prevent-external-access-to-sensitive-documents"></a>Impedir o acesso externo a documentos confidenciais

Para garantir que documentos do SharePoint que contenham informações confidenciais não podem ser acessados por convidados externos do SharePoint ou do Teams por padrão, selecione o seguinte:

- Você pode garantir que os documentos sejam protegidos até que a DLP os verifique e os marque como seguros para compartilhar marcando novos arquivos como confidenciais [por padrão.](/sharepoint/sensitive-by-default)

- Estrutura de política de DLP recomendada

    - **Condições**
        - O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]
        
        - O conteúdo é compartilhado do Microsoft 365 com pessoas de fora da minha organização
        
          > [!div class="mx-imgBorder"]
          > ![Condições de DLP para detectar o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-condition.png)

    - **Actions**
        - Restringir o acesso ao conteúdo para usuários externos
        
        - Notificar os usuários com dicas de política e email
        
        - Enviar relatórios de incidentes ao Administrador
        
        > [!div class="mx-imgBorder"]
        > ![Ação DLP para bloquear o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-action.png)

Política de DLP em ação ao tentar compartilhar um documento no SharePoint que contém informações confidenciais com um convidado externo:

> [!div class="mx-imgBorder"]
> ![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Política de DLP em ação quando o convidado tenta abrir um documento no Teams com bloqueio externo:

> [!div class="mx-imgBorder"]
> ![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Artigos relacionados

[Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

[Enviar notificações por email e mostrar dicas para políticas de DLP](use-notifications-and-policy-tips.md)
