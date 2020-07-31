---
title: Colaborar com convidados em uma equipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba mais sobre as etapas de configuração do 365 da Microsoft necessárias para configurar uma equipe para colaboração com convidados no Microsoft Teams.
ms.openlocfilehash: 73f9a7a1c52c8c237cccabafd8fca24abe038ff7
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528213"
---
# <a name="collaborate-with-guests-in-a-team"></a>Colaborar com convidados em uma equipe

Se você precisar colaborar com convidados entre documentos, tarefas e conversas, recomendamos o uso do Microsoft Teams. O Microsoft Teams fornece todos os recursos de colaboração disponíveis no Office e no SharePoint com chat persistente e um conjunto personalizável e extensível de ferramentas de colaboração em uma experiência de usuário unificada.

Neste artigo, veremos as etapas de configuração do 365 da Microsoft necessárias para configurar uma equipe para colaboração com convidados.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Configurações de relações organizacionais do Azure

O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas configurações de relações organizacionais no Azure Active Directory. Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, isso substituirá as configurações de compartilhamento que você configurar no Microsoft 365.

Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para definir as configurações de relação organizacional

1. Faça logon no Microsoft Azure em [https://portal.azure.com](https://portal.azure.com) .
2. Na navegação à esquerda, clique em **Azure Active Directory**.
3. No painel **visão geral** , clique em **identidades externas**.
4. No painel **identidades organizacionais** , clique em **configurações de colaboração externa**.
5. Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **restrições de colaboração** . Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.

## <a name="teams-guest-access-settings"></a>Configurações de acesso de convidados do teams

O Microsoft Teams tem uma opção de ativar/desativar mestre para acesso de convidados e uma variedade de configurações disponíveis para controlar o que os convidados podem fazer em uma equipe. A opção mestre **permite que o acesso de convidados no Microsoft Teams** seja **ativado** para que o acesso de convidados funcione no Microsoft Teams.

Verifique se o acesso de convidados está habilitado no Teams e faça qualquer ajuste nas configurações de convidado com base nas suas necessidades de negócios. Tenha em mente que essas configurações afetam todas as equipes.

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

Para definir as configurações de acesso de convidado do Teams

1. Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).
2. Na barra de navegação esquerda, clique em **Mostrar tudo**.
3. Em **Centros de administração**, clique em **Teams**.
4. No Centro de administração do Teams, na navegação à esquerda, expanda **Configurações para toda a organização** e clique em **Acesso de convidado**.
5. Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.
6. Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.

> [!NOTE]
> Depois de habilitá-la, pode levar até 24 horas para que a configuração de convidado do Teams se torne ativa.

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado de grupos do Microsoft 365

O Teams usa os grupos do Microsoft 365 para associação da equipe. As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados no Teams funcione.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidados de grupos do Microsoft 365

1. No centro de administração do Microsoft 365, no painel de navegação à esquerda, expanda **configurações**.
2. Clique em **configurações da organização**.
3. Na lista, clique em **Microsoft 365 grupos**.
4. Certifique-se de que o **grupo permitir Membros fora do seu conteúdo de grupo de acesso à organização** e **que os proprietários do grupo adicionem pessoas fora da sua organização a grupos de** seleção.
5. Se você tiver feito alterações, clique em **salvar alterações**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento de nível da organização do SharePoint

O conteúdo de equipes, como arquivos, pastas e listas, é armazenado no SharePoint. Para que os convidados tenham acesso a esses itens no Teams, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.

As configurações de nível de organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados ao Teams. As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.

Se você quiser permitir o compartilhamento de arquivos e pastas com pessoas não autenticadas, escolha **qualquer pessoa**. Se você quiser garantir que todos os convidados devem se autenticar, escolha **novos e existentes convidados**. Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento de nível da organização do SharePoint

1. No centro de administração do Microsoft 365, na navegação à esquerda, em **centros de administração**, clique em **SharePoint**.
2. No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.
3. Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.
4. Caso tenha feito alterações, clique em **Salvar**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Configurações de link padrão de nível de organização do SharePoint

As configurações padrão de link de arquivo e pasta determinam qual opção de link é mostrada para o usuário por padrão ao compartilhar um arquivo ou uma pasta. Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.

Tenha em mente que essa configuração afeta todas as equipes e sites do SharePoint em sua organização.

Escolha o tipo de link selecionado por padrão quando os usuários compartilham arquivos e pastas:

- **Qualquer pessoa com o link** -escolha essa opção se você quiser fazer muito do compartilhamento não autenticado de arquivos e pastas. Se você quiser permitir links de *qualquer pessoa* , mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão. Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento de **qualquer pessoa** .
- **Somente as pessoas da sua organização** -escolha esta opção se você espera que a maioria dos compartilhamento de arquivos e pastas seja com pessoas dentro da sua organização.
- **Pessoas específicas** -considere essa opção se você espera que um grande volume de compartilhamento de arquivos e pastas com convidados. Esse tipo de link funciona com convidados e exige a autenticação.
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para definir as configurações de link padrão de nível de organização do SharePoint

1. Navegue até a página de compartilhamento no centro de administração do SharePoint.
2. Em **links de arquivo e pasta**, selecione o link de compartilhamento padrão que você deseja usar.
3. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-team"></a>Criar uma equipe

A próxima etapa é criar a equipe que você planeja usar para colaborar com convidados.

Para criar uma equipe
1. No Teams, na guia **Teams** , clique em **ingressar ou criar uma equipe** na parte inferior do painel esquerdo.
2. Clique em **criar uma equipe**.
3. Clique em **criar uma equipe do zero**.
4. Escolha **privado** ou **público**.
5. Digite um nome e uma descrição para a equipe e, em seguida, clique em **criar**.
6. Clique em **ignorar**.

Vamos convidar os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site do SharePoint associado à equipe.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento no nível do site do SharePoint

Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para essa equipe. Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa**, mas quiser que todos os convidados autentiquem essa equipe, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)


Para definir configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.
2. Selecione o site da equipe que você acabou de criar.
3. Na faixa de opções, clique em **Compartilhamento**.
4. Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados à sua equipe. 

Para convidar usuários internos para uma equipe
1. Na equipe, clique em **mais opções** ( **\*\*\*** ) e, em seguida, clique em **Adicionar membro**.
2. Digite o nome da pessoa que você deseja convidar.
3. Clique em **Adicionar**e, em seguida, clique em **fechar**.

Para convidar convidados para uma equipe
1. Na equipe, clique em **mais opções** ( **\*\*\*** ) e, em seguida, clique em **Adicionar membro**.
2. Digite o endereço de email do convidado que você deseja convidar.
3. Clique em **Editar informações de convidado**.
4. Digite o nome completo do convidado e clique na marca de seleção.
5. Clique em **Adicionar**e, em seguida, clique em **fechar**.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)
