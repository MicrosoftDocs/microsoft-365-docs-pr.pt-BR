---
title: Colaborar com convidados em um documento
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Neste artigo, você aprenderá como colaborar com convidados em um documento no SharePoint e no OneDrive.
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357777"
---
# <a name="collaborate-with-guests-on-a-document"></a>Colaborar com convidados em um documento

Se você precisar colaborar com pessoas de fora da sua organização em documentos do SharePoint ou do OneDrive, você pode enviar um link de compartilhamento para o documento. Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar links de compartilhamento para o SharePoint e o OneDrive para as necessidades da sua organização.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Configurações de relações organizacionais do Azure

O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, isso substituirá as configurações de compartilhamento que você configurar no Microsoft 365.

Verifique as configurações de relações organizacionais para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para definir as configurações de relação organizacional

1. Faça logon no Microsoft Azure em [https://portal.azure.com](https://portal.azure.com) .
2. Na navegação à esquerda, clique em **Azure Active Directory**.
3. No painel **visão geral** , clique em **relações organizacionais**.
4. No painel **relações organizacionais** , clique em **configurações**.
5. Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **restrições de colaboração** . Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.

Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório. Isso impedirá que você veja quem mais é um convidado no diretório. Para fazer isso, em **restrições de acesso de usuário convidado**, selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento de nível da organização do SharePoint

Para que as pessoas de fora da sua organização tenham acesso a um documento no SharePoint ou no OneDrive, as configurações de compartilhamento no nível da organização do SharePoint e do OneDrive devem permitir o compartilhamento com pessoas de fora da sua organização.

As configurações de nível de organização para o SharePoint determinam as configurações disponíveis para sites individuais do SharePoint. As configurações do site não podem ser mais permissivas do que as configurações no nível da organização. A configuração de nível de organização para o OneDrive determina o nível de compartilhamento disponível nas bibliotecas do OneDrive dos usuários.

Para o SharePoint e o OneDrive, se você quiser permitir compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**. Se você quiser garantir que as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**. Os links de *qualquer pessoa* são a maneira mais fácil de compartilhar: as pessoas de fora da sua organização podem abrir o link sem autenticação e ficar livres para passá-lo para outros.

Para o SharePoint, escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento de nível da organização do SharePoint

1. No centro de administração do Microsoft 365, na navegação à esquerda, em **centros de administração**, clique em **SharePoint**.
2. No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.
3. Certifique-se de que o compartilhamento externo do SharePoint ou do OneDrive está definido como **qualquer pessoa** ou **convidado novo e existente**. (Observe que a configuração do OneDrive não pode ser mais permissiva do que a configuração do SharePoint.)
4. Caso tenha feito alterações, clique em **Salvar**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Configurações de link padrão de nível de organização do SharePoint

As configurações padrão de link de arquivo e pasta determinam qual opção de link é mostrada para o usuário por padrão ao compartilhar um arquivo ou uma pasta. Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.

Tenha em mente que essa configuração afeta os sites do SharePoint em sua organização, bem como o OneDrive.

Escolha o tipo de link selecionado por padrão quando os usuários compartilham arquivos e pastas:

- **Qualquer pessoa com o link** -escolha essa opção se você quiser fazer muito do compartilhamento de arquivos e pastas não autenticados. Se você quiser permitir links de *qualquer pessoa* , mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão. Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento de **qualquer pessoa** .
- **Somente as pessoas da sua organização** -escolha esta opção se você espera que a maioria dos compartilhamento de arquivos e pastas seja com pessoas dentro da sua organização.
- **Pessoas específicas** -considere essa opção se você espera que um grande volume de compartilhamento de arquivos e pastas com convidados. Esse tipo de link funciona com convidados e exige a autenticação.
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para definir as configurações de link padrão de nível de organização do OneDrive e SharePoint

1. Navegue até a página de compartilhamento no centro de administração do SharePoint.
2. Em **links de arquivo e pasta**, selecione o link de compartilhamento padrão que você deseja usar.
3. Caso tenha feito alterações, clique em **Salvar**.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento no nível do site do SharePoint

Se você estiver compartilhando arquivos e pastas que estão em um site do SharePoint, também precisará verificar as configurações de compartilhamento no nível do site.

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para definir configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.
2. Selecione o site que você acabou de criar.
3. Na faixa de opções, clique em **Compartilhamento**.
4. Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas, portanto, os usuários agora podem compartilhar arquivos e pastas com pessoas de fora da sua organização. Consulte [compartilhar arquivos e pastas do onedrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) e [compartilhar arquivos ou pastas do SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obter mais informações.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Integração do SharePoint e do OneDrive com o B2B do Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)