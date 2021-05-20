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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Saiba mais sobre as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para tarefas, conversas e colaboração de documentação com convidados no Teams.
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539258"
---
# <a name="collaborate-with-guests-in-a-team"></a>Colaborar com convidados em uma equipe

Se você precisar colaborar com convidados em documentos, tarefas e conversas, recomendamos o uso do Microsoft Teams. O Teams fornece todos os recursos de colaboração disponíveis no Office e no Microsoft Office SharePoint Online com chat persistente e um conjunto personalizável e extensível de ferramentas de colaboração em uma experiência de usuário unificada.

Neste artigo, vamos percorrer as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para colaboração com convidados. Depois de configurar o acesso de convidado, você pode convidar pessoas para equipes seguindo as etapas em [Adicionar convidados a uma equipe no Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

Compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [Configurações de colaboração externa B2B no Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá todas as configurações de compartilhamento que você definir no Microsoft 365.

Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para conjunto de configurações de colaboração externa

1. Faça log no Azure Active Directory em[https://aad.portal.azure.com](https://aad.portal.azure.com).
2. No painel de navegação esquerdo, clique em **Azure Active Directory**.
3. Clique em **Identidades externas**.
4. Na tela **Introdução**, no painel de navegação esquerdo, clique em **Configurações de colaboração externa**.
5. Certifique-se de que **Administradores e usuários na função de convidador podem convidar** e **Membros podem convidar** estão ambos no conjunto como **Sim**.
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **Restrições de colaboração**. Certifique-se de que os domínios dos convidados com os quais deseja colaborar não estão bloqueados.

Se você trabalha com convidados de várias organizações, pode restringir sua capacidade de acessar os dados do diretório. Isso os impedirá de ver quem mais é um convidado no diretório. Para fazer isso, em **Restrições de acesso do usuário convidado**, selecione **Usuários convidados têm acesso limitado às propriedades e configurações de associação de objetos de diretório** ou **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.

## <a name="teams-guest-access-settings"></a>Configurações de acesso de convidado das equipes

O Teams tem um interruptor mestre liga/desliga para acesso dos convidados e uma variedade de configurações disponíveis para controlar o que os convidados podem fazer em uma equipe. O switch mestre, **Permitir acesso de convidado no Teams** deve ser **No** para o acesso do convidado funcionar no Teams.

Verifique se o acesso de convidado está habilitado no Teams e faça qualquer ajuste nas configurações de convidado com base em suas necessidades de negócios. Lembre-se de que essas configurações afetam todas as equipes.

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

Para definir as configurações de acesso de convidado do Teams

1. Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).
2. No painel de navegação esquerdo, clique em **Mostrar todos**.
3. Em **Centros de administração**, clique em **Teams**.
4. No Centro de administração de equipes, no painel de navegação esquerdo, expanda **Configurações em toda a organização** e clique em **Acesso de convidado**.
5. Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.
6. Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.

Depois que o acesso de convidado do Teams está ativado, você pode opcionalmente controlar o acesso de convidado a equipes individuais e seus sites do Microsoft Office SharePoint Online associados usando rótulos de sensibilidade. Para mais informações, veja [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!NOTE]
> Pode levar até vinte e quatro horas para que as configurações de convidados do Teams se tornem ativas depois de ativadas.

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado do Microsoft 365 Groups

O Teams utiliza os Grupos Microsoft 365 para a associação à equipe. As configurações dos Grupos Microsoft 365 devem ser ativadas para que o acesso de convidados em Equipes trabalhe.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidado do Grupos do Microsoft 365

1. No Centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **Configurações**.
2. Clique em **Configurações da organização**.
3. Na lista, clique em **Grupos do Microsoft 365**.
4. Certifique-se de que as caixas de seleção **Permitir que proprietários de grupos adicionem pessoas fora de sua organização aos Grupos do Microsoft 365 como convidados** e **Permitir que membros de grupos convidados acessem o conteúdo do grupo** estejam marcadas.
5. Se você fez alterações, clique em **Salvar alterações**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento de nível de organização do Microsoft Office SharePoint Online

Conteúdo do Teams, como arquivos, pastas e listas, é armazenado no Microsoft Office SharePoint Online. Na ordem para os convidados tenham acesso a esses itens no Teams, as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online devem permitir o compartilhamento com convidados.

As configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes. Como configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes.

Se você deseja permitir o compartilhamento de arquivos e pastas com pessoas não autenticadas, escolha **Qualquer pessoa**. Se você quiser garantir que todos os convidados precisem ser autenticados, escolha **Convidados novos e existentes**. Escolher a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online

1. No Centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros de administração**, clique em **SharePoint**.
2. No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Políticas** e clique em **Compartilhamento**.
3. Certifique-se de que o compartilhamento externo para o Microsoft Office SharePoint Online esteja definido como **Qualquer Pessoa** ou **Convidados novos e existentes**.
4. Caso tenha feito alterações, clique em **Salvar**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Configurações de link padrão no nível da organização do Microsoft Office SharePoint Online

As configurações de link de arquivo e pasta padrão determinam a opção de link que será mostrada aos usuários por padrão quando eles compartilharem um arquivo ou pasta. Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.

Lembre-se de que essa configuração afeta todas as equipes e sites do Microsoft Office SharePoint Online em sua organização.

Escolher qualquer um dos seguintes tipos de link, que será selecionado por padrão quando os usuários compartilharem arquivos e pastas:

- **Qualquer pessoa com o link** - Escolher esta opção se você espera fazer muitos compartilhamentos não autenticados de arquivos e pastas. Se você deseja permitir links *Qualquer Pessoa*, mas está preocupado com o compartilhamento não autenticado acidental, considere uma das outras opções como padrão. Este tipo de link só estará disponível se você tiver ativado o compartilhamento **Qualquer Pessoa**.
- **Somente pessoas em sua organização** - Escolher esta opção se você espera que a maior parte do compartilhamento de arquivos e pastas seja com pessoas de dentro de sua organização.
- **Pessoas específicas** - Considerar esta opção se você pretende fazer muitos compartilhamentos de arquivos e pastas com convidados. Esse tipo de link funciona com os convidados e exige que eles se autentiquem.
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para conjunto de configurações de link padrão no nível da organização do Microsoft Office SharePoint Online

1. Navegue até a página Compartilhamento no Centro de administração do SharePoint.
2. Em **Links de arquivos e pastas**, selecione o link de compartilhamento padrão que deseja usar.
3. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-team"></a>Criar uma equipe

A próxima etapa é criar a equipe que você planeja usar para colaborar com os convidados.

Para criar uma equipe
1. No Teams, na guia **Teams**, clique em **Participar ou criar uma equipe** na parte inferior do painel esquerdo.
2. Clique em **Criar uma equipe**.
3. Clique **Build uma equipe do zero**.
4. Escolher **Privado** ou **Público**.
5. Digite um nome e uma descrição para a equipe e clique em **Criar**.
6. Clique **Ignorar**.

Convidaremos os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site para o site do Microsoft Office SharePoint Online que está associado à equipe.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento de nível de site do Microsoft Office SharePoint Online

Verificar as configurações de compartilhamento no nível do site para certificar-se de que permitem o tipo de acesso que você deseja para esta equipe. Por exemplo, se você definir as configurações no nível da organização como **Qualquer Pessoa**, mas quiser que todos os convidados se autentiquem para esta equipe, certifique-se de que as configurações de compartilhamento no nível do site estejam definidas como **Convidados novos e existentes**.

![Captura de tela das configurações de compartilhamento externo do site do Microsoft Office SharePoint Online](../media/sharepoint-site-external-sharing-settings.png)

Para conjunto de configurações de compartilhamento no nível do site
1. No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Sites** e clique em **Sites ativos**.
2. Selecione o site para a equipe que você acabou de criar.
3. Clique em ... e escolha **Compartilhamento**.
4. Certifique-se de que o compartilhamento esteja no conjunto como **Qualquer pessoa** ou **Convidados novos e existentes**.
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

Configurações de compartilhamento de convidados agora estão definidas, para que você possa começar a adicionar usuários internos e convidados à sua equipe. 

Para convidar usuários internos para uma equipe
1. Na equipe, clique em **Mais opções** (**\*\*\***) e, em seguida, clique em **Adicionar membro**.
2. Toque no nome da pessoa que você quer convidar.
3. Clique em **Adicionar** e, em seguida, clique em **Fechar**.

Para convidar pessoas para uma equipe
1. Na equipe, clique em **Mais opções** (**\*\*\***) e, em seguida, clique em **Adicionar membro**.
2. Digite o endereço de email do convidado que deseja convidar.
3. Clique em **Editar informações do convidado**.
4. Digite o nome completo do convidadi e clique na marca de verificação.
5. Clique em **Adicionar** e, em seguida, clique em **Fechar**.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)

[Integração do Microsoft Office SharePoint Online e OneDrive com Microsoft Azure Active Directory B2B](/sharepoint/sharepoint-azureb2b-integration-preview)

[Opções de compartilhamento ficam esmaecidas ao compartilhar do Microsoft Office SharePoint Online ou OneDrive](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)