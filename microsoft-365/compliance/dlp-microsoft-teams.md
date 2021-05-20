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
description: Agora você pode aplicar políticas DLP para Microsoft Teams chats e canais. Leia este artigo para saber mais sobre como funciona.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572460"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Prevenção contra perda de dados e Microsoft Teams

> [!NOTE]
> Os recursos de prevenção de perda de dados foram recentemente adicionados a mensagens de chat e canal Microsoft Teams para usuários licenciados para Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Proteção e Governança de Informações ou Conformidade Avançada do Office 365. Office 365 e Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online. Isso também inclui arquivos que são compartilhados através de Teams porque Teams usa SharePoint Online e OneDrive para compartilhar arquivos.
O suporte para proteção DLP no Chat Teams requer E5.
Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Visão geral da DLP para o Microsoft Teams

Recentemente, os recursos de [prevenção de perda de dados](dlp-learn-about-dlp.md) foram estendidos para incluir Microsoft Teams mensagens de chat e canais, incluindo **mensagens de canais privados.** 

> [!IMPORTANT]
> Atualmente, o DLP se aplica apenas às mensagens reais no segmento de chat ou canal. As notificações de atividade - que incluem uma visualização de mensagem curta e aparecem com base nas configurações de notificação de um usuário - **não** estão incluídas em Teams DLP neste momento. Quaisquer informações confidenciais presentes na parte da mensagem que aparece na visualização permanecerão visíveis na notificação mesmo após a aplicação da política DLP e removida informações confidenciais da própria mensagem.

Se sua organização tiver DLP, agora você pode definir políticas que impeçam as pessoas de compartilhar informações confidenciais em um canal de Microsoft Teams ou sessão de bate-papo. Aqui estão alguns exemplos de como essa proteção funciona:

- **Exemplo 1: Proteção de informações confidenciais em mensagens**. Suponha que alguém tente compartilhar informações confidenciais em um chat ou canal Teams com convidados (usuários externos). Se você tiver uma política DLP definida para evitar isso, mensagens com informações confidenciais enviadas a usuários externos serão excluídas. Isso acontece automaticamente e em segundos, de acordo com a forma como sua política de DLP é configurada.

    > [!NOTE]
    > O DLP for Microsoft Teams bloqueia conteúdo sensível quando compartilhado com Microsoft Teams usuários que têm:<br/>- [acesso de hóspedes](/MicrosoftTeams/guest-access) em equipes e canais; ou<br/>- [acesso externo](/MicrosoftTeams/manage-external-access) em reuniões e sessões de bate-papo. <p>O DLP para sessões de bate-papo externo só funcionará se o remetente e o receptor estiverem no modo somente Teams e usando [Microsoft Teams federação nativa](/microsoftteams/manage-external-access). O DLP para Teams não bloqueia mensagens em [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com sessões de bate-papo federadas Skype for Business ou não nativas.

- **Exemplo 2: Proteção de informações confidenciais em documentos**. Suponha que alguém tente compartilhar um documento com convidados em um canal ou chat Microsoft Teams, e o documento contém informações confidenciais. Se você tiver uma política DLP definida para evitar isso, o documento não será aberto para esses usuários. Observe que, neste caso, sua política de DLP deve incluir SharePoint e OneDrive para que a proteção esteja em vigor. (Este é um exemplo de DLP para SharePoint que aparece em Microsoft Teams e, portanto, exige que os usuários sejam licenciados para Office 365 DLP (incluído em Office 365 E3), mas não exige que os usuários sejam licenciados por Conformidade Avançada do Office 365.)

## <a name="policy-tips-help-educate-users"></a>Dicas de políticas ajudam a educar os usuários

Semelhante à forma como o DLP funciona em [Exchange, Outlook, Outlook na web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, sites de OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e Office [clientes de desktop](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), as dicas de políticas aparecem quando uma ação entra em conflito com uma política de DLP. Aqui está um exemplo de uma dica de política:

![Notificação de mensagem bloqueada em Teams](../media/dlp-teams-blockedmessage-notification.png)

Neste caso, o remetente tentou compartilhar um número de segurança social em um canal Microsoft Teams. O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema. Observe que, neste caso, o remetente pode optar por substituir a apólice ou notificar um administrador para revisá-la e resolvê-la.

![Opções para resolver mensagem bloqueada](../media/dlp-teams-blockedmessage-possibleactions.png)

Em sua organização, você pode optar por permitir que os usuários substituam uma política DLP. E, ao configurar suas políticas DLP, você pode usar as dicas de política padrão ou [personalizar dicas de política](#to-customize-policy-tips) para sua organização.

Voltando ao nosso exemplo, onde um remetente compartilhou um número de segurança social em um canal de Teams, aqui está o que o destinatário viu:

> [!div class="mx-imgBorder"]
> ![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Dicas para personalizar a política

Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.

2. Clique em **Prevenção contra perda de dados** > **Política**.

3. Selecione uma política e, ao lado **das configurações de política,** escolha **Editar**.

4. Crie uma nova regra ou edite uma regra existente para a política.

    > [!div class="mx-imgBorder"]
    > ![Editando uma regra para uma política](../media/dlp-teams-editrule.png)

5. Na guia **Notificações do Usuário,** selecione **Personalizar o texto de e-mail** e/ou Personalizar as opções **de texto de ponta de política.**

    > [!div class="mx-imgBorder"]
    > ![Personalize notificações e dicas de políticas de usuários](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Especifique o texto que deseja usar para notificações de e-mail e/ou dicas de política e, em seguida, escolha **Salvar**.

7. Na guia **Configurações de políticas,** escolha **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem através do data center e sincronizem com as contas de usuários.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Adicionar o Microsoft Teams como um local para as políticas de DLP existentes

Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.

2. Clique em **Prevenção contra perda de dados** > **Política**.

3. Selecione uma política e veja os valores em **Locais**. Se você vir **Teams chat e mensagens de canal,** está tudo pronto. Se não o fizer, clique em **Editar**.

    > [!div class="mx-imgBorder"]
    > ![Locais para a política existente](../media/dlp-teams-editexistingpolicy.png)

4. Na coluna **Status,** ligue a política para **Teams mensagens de chat e canal**.

    > [!div class="mx-imgBorder"]
    > ![DLP para Teams chats e canais](../media/dlp-teams-addteamschatschannels.png)

5. Na guia **Escolher locais,** manter a configuração padrão de todas as contas ou selecionar **Deixe-me escolher locais específicos**. É possível especificar:

    1. até 1000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Depois clique em **Próximo**.

7. Clique em **Salvar**.

Permita aproximadamente uma hora para que suas alterações funcionem através do data center e sincronizem com as contas de usuários.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definir uma nova política DLP para o Microsoft Teams

Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP. Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).

1. Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.

2. Escolha **Prevenção contra perda de dados** > **Política** > **+ Criar uma política**.

3. Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **o Next**.

    Em nosso exemplo, escolhemos o modelo de dados de informações pessoalmente identificáveis dos EUA.

    > [!div class="mx-imgBorder"]
    > ![Modelo de privacidade para a política DLP](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Na guia **Nomear sua política,** especifique um nome e descrição para a política e, em seguida, escolha **o Próximo**.

5. Na guia **Escolher locais,** manter a configuração padrão de todas as contas ou selecionar **Deixe-me escolher locais específicos**. É possível especificar:

    1. até 1000 contas individuais para incluir ou excluir
    1. listas de distribuição e grupos de segurança para incluir ou excluir. **Este é um recurso de pré-visualização pública.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Localizações de políticas DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Se você quiser garantir que documentos que contenham informações confidenciais não sejam compartilhados inapropriadamente em Teams, certifique-se **de que SharePoint sites** e contas **OneDrive** sejam ligados, juntamente com **Teams mensagens de chat e canal**.

6. Na guia **Configurações De políticas,** em **Personalizar o tipo de conteúdo que deseja proteger,** mantenha as configurações simples padrão ou escolha **Usar configurações avançadas** e, em seguida, escolha **o Próximo**. Se você escolher configurações avançadas, você pode criar ou editar regras para sua política. (Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  Na guia **Configurações De políticas,** em **que você deseja fazer se detectarmos informações confidenciais?** (Aqui é onde você pode optar por manter dicas de política padrão [e notificações de e-mail](use-notifications-and-policy-tips.md), ou personalizá-las.)

    > [!div class="mx-imgBorder"]
    > ![Configurações de políticas DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)

    Quando terminar de revisar ou editar configurações, escolha **o Next**.

8. Na guia **Configurações de políticas,** em **Você deseja ativar a política ou testar as coisas primeiro?**, escolha se ativar a política, [testá-la primeiro](dlp-overview-plan-for-dlp.md#policy-deployment)ou mantê-la desligada por enquanto e, em seguida, escolher o **Next**.

    > [!div class="mx-imgBorder"]
    > ![Especifique se ativar a política](../media/dlp-teams-policysettings-turnonnow.png)

9. Na guia **Analisar suas configurações,** revise as configurações da sua nova política. Escolha **Editar** para fazer alterações. Quando terminar, escolha **Criar**.

Permita que aproximadamente uma hora para sua nova política funcione através do seu data center e sincronize com as contas de usuários.

## <a name="prevent-external-access-to-sensitive-documents"></a>Impedir o acesso externo a documentos confidenciais

Para garantir que SharePoint documentos que contenham informações confidenciais não possam ser acessados por hóspedes externos SharePoint ou Teams por padrão, selecione o seguinte:

- Você pode garantir que os documentos estejam protegidos até que o DLP os digitaliza e os marque como seguros de compartilhar [marcando novos arquivos como sensíveis por padrão](/sharepoint/sensitive-by-default).

- Estrutura de política DLP recomendada

    - **Condições**
        - O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]
        
        - O conteúdo é compartilhado de Microsoft 365 com pessoas de fora da minha organização
        
          > [!div class="mx-imgBorder"]
          > ![Condições de DLP para detectar compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-condition.png)

    - **Actions**
        - Restringir acesso de usuários externos ao conteúdo
        
        - Notificar usuários com dicas de política e email
        
        - Enviar relatórios de incidentes para o administrador
        
        > [!div class="mx-imgBorder"]
        > ![Ação do DLP para bloquear o compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-action.png)

Política DLP em ação ao tentar compartilhar um documento em SharePoint que contenha informações confidenciais com um convidado externo:

> [!div class="mx-imgBorder"]
> ![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


Política DLP em ação quando o hóspede tenta abrir um documento em Teams com bloco externo:

> [!div class="mx-imgBorder"]
> ![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Artigos relacionados

[Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

[Enviar notificações por email e mostrar dicas para políticas de DLP](use-notifications-and-policy-tips.md)
