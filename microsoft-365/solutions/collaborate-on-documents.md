---
title: Colaborar com convidados em um documento
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
localization_priority: Normal
f1.keywords: NOCSH
description: Neste artigo, você aprenderá a colaborar com convidados em um documento no SharePoint e no OneDrive.
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920223"
---
# <a name="collaborate-with-guests-on-a-document"></a>Colaborar com convidados em um documento

Se você precisar colaborar com pessoas de fora da sua organização em documentos no SharePoint ou no OneDrive, você pode enviar um link de compartilhamento para o documento. Neste artigo, vamos passar pelas etapas de configuração do Microsoft 365 necessárias para configurar links de compartilhamento para SharePoint e OneDrive para as necessidades da sua organização.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

Compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [Configurações de colaboração externa B2B no Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.

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

## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento no nível da organização do SharePoint

Para que pessoas de fora da sua organização tenham acesso a um documento no SharePoint ou no OneDrive, as configurações de compartilhamento no nível da organização do SharePoint e do OneDrive devem permitir o compartilhamento com pessoas de fora da sua organização.

As configurações no nível da organização do SharePoint determinam as configurações que estarão disponíveis para sites individuais do SharePoint. Como configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes. A configuração no nível da organização do OneDrive determina o nível de compartilhamento que estará disponível nas bibliotecas do OneDrive dos usuários.

Para SharePoint e OneDrive, se você quiser permitir compartilhamento de arquivos e pastas não autenticados, escolha **Qualquer Pessoa**. Se você quiser garantir que pessoas de fora da sua organização tenham que se autenticar, escolha Convidados novos **e existentes.** *Os* links de qualquer pessoa são a maneira mais fácil de compartilhar: pessoas de fora da sua organização podem abrir o link sem autenticação e podem passá-lo para outras pessoas.

Para o SharePoint, escolha a configuração mais permissiva que será necessária por qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online

1. No Centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros de administração**, clique em **SharePoint**.
2. No centro de administração do SharePoint, no painel de navegação esquerdo, em **Políticas,** clique em **Compartilhamento**.
3. Verifique se o compartilhamento externo do SharePoint ou do OneDrive está definido como **Qualquer pessoa** ou convidados novos **e existentes.** (Observe que a configuração do OneDrive não pode ser mais permissiva do que a configuração do SharePoint.)
4. Caso tenha feito alterações, clique em **Salvar**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Configurações de link padrão no nível da organização do Microsoft Office SharePoint Online

As configurações de link de arquivo e pasta padrão determinam a opção de link que será mostrada aos usuários por padrão quando eles compartilharem um arquivo ou pasta. Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.

Lembre-se de que essa configuração afeta sites do SharePoint em sua organização, bem como o OneDrive.

Escolha um link de qualquer um dos seguintes tipos selecionados por padrão quando os usuários compartilharem arquivos e pastas:

- **Qualquer pessoa com o link** - Escolha essa opção se você espera fazer um monte de compartilhamento de pastas e arquivos não autenticados. Se você deseja permitir links *Qualquer Pessoa*, mas está preocupado com o compartilhamento não autenticado acidental, considere uma das outras opções como padrão. Este tipo de link só estará disponível se você tiver ativado o compartilhamento **Qualquer Pessoa**.
- **Somente pessoas em sua organização** - Escolher esta opção se você espera que a maior parte do compartilhamento de arquivos e pastas seja com pessoas de dentro de sua organização.
- **Pessoas específicas** - Considerar esta opção se você pretende fazer muitos compartilhamentos de arquivos e pastas com convidados. Esse tipo de link funciona com os convidados e exige que eles se autentiquem.
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para definir as configurações de link padrão no nível da organização do SharePoint e do OneDrive

1. Navegue até a página Compartilhamento no Centro de administração do SharePoint.
2. Em **Links de arquivos e pastas**, selecione o link de compartilhamento padrão que deseja usar.
3. Caso tenha feito alterações, clique em **Salvar**.

Para definir a permissão para o link de compartilhamento, em Escolha a permissão selecionada **por padrão para compartilhar links.**

1. Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos e pastas.
2. Selecione **Editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos e pastas.

Observe que as duas opções de pré-emissão acima podem ser aplicadas não apenas para convidados/usuários externos, mas também para usuários internos. A opção de permissão escolhida é determinada por autodiscrição.

Para definir permissões para links que permitem o compartilhamento com qualquer pessoa

1. No **sub-painel Esses links podem dar essas permissões:** 
    1. Na lista **lista** listada de arquivos, 
        - Selecione **Exibir e editar** se quiser permitir que usuários não autenticados façam alterações nos arquivos.
        - Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nos arquivos.
    2. Na **lista** de pastas listadas,
        - Selecione **Exibir, editar e carregar** se quiser permitir que usuários não autenticados façam alterações nas pastas.
        - Selecione **Exibir** se você não quiser que usuários não autenticados façam alterações nas pastas.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento de nível de site do Microsoft Office SharePoint Online

Se você estiver compartilhando arquivos e pastas que estão em um site do SharePoint, você também precisa verificar as configurações de compartilhamento no nível do site para esse site.

![Captura de tela das configurações de compartilhamento externo do site do Microsoft Office SharePoint Online](../media/sharepoint-site-external-sharing-settings.png)

Para conjunto de configurações de compartilhamento no nível do site

1. No Centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Sites** e clique em **Sites ativos**.
2. Selecione o site no qual você deseja compartilhar arquivos e pastas com convidados.
3. Role diretamente pela linha (na qual o site selecionado está presente) e clique em qualquer lugar na **coluna Compartilhamento** externo.
4. Na página que aparece, clique na **guia Políticas.**
5. No painel **compartilhamento** externo, clique em **Editar**.
6. Certifique-se de que o compartilhamento esteja no conjunto como **Qualquer pessoa** ou **Convidados novos e existentes**.
7. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas; para que os usuários agora possam compartilhar arquivos e pastas com pessoas fora da sua organização. Confira [Compartilhar arquivos e pastas do OneDrive e](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) arquivos do [SharePoint ou pastas do SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obter mais informações.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Integração do Microsoft Office SharePoint Online e OneDrive com Microsoft Azure Active Directory B2B](/sharepoint/sharepoint-azureb2b-integration-preview)