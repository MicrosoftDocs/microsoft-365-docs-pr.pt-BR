---
title: Colaborar com convidados em um site
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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Saiba mais sobre as Microsoft 365 de configuração necessárias para configurar um site SharePoint para colaboração com convidados.
ms.openlocfilehash: f91b9c64dbdca8ed7e3ada3315cb57f1c728f838
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539246"
---
# <a name="collaborate-with-guests-in-a-site"></a>Colaborar com convidados em um site

Se você precisar colaborar com convidados em documentos, dados e listas, poderá usar um SharePoint site. Os SharePoint modernos são conectados a grupos Microsoft 365 e podem gerenciar a associação ao site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio compartilhada e um calendário.

Neste artigo, vamos passar pelas etapas de configuração Microsoft 365 necessárias para configurar um site SharePoint para colaboração com convidados.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

Compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas [Configurações de colaboração externa B2B no Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá todas as configurações de compartilhamento que você definir no Microsoft 365.

Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da Azure Active Directory de colaboração externa Configurações página](../media/azure-ad-organizational-relationships-settings.png)

Para conjunto de configurações de colaboração externa

1. Faça log no Azure Active Directory em[https://aad.portal.azure.com](https://aad.portal.azure.com).
2. No painel de navegação esquerdo, clique em **Azure Active Directory**.
3. Clique em **Identidades externas**.
4. Na tela **Introdução**, no painel de navegação esquerdo, clique em **Configurações de colaboração externa**.
5. Certifique-se de que **Administradores e usuários na função de convidador podem convidar** e **Membros podem convidar** estão ambos no conjunto como **Sim**.
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **Restrições de colaboração**. Certifique-se de que os domínios dos convidados com os quais deseja colaborar não estão bloqueados.

Se você trabalha com convidados de várias organizações, pode restringir sua capacidade de acessar os dados do diretório. Isso os impedirá de ver quem mais é um convidado no diretório. Para fazer isso, em **Restrições de acesso do usuário convidado**, selecione **Usuários convidados têm acesso limitado às propriedades e configurações de associação de objetos de diretório** ou **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado do Microsoft 365 Groups

Os SharePoint modernos usam Microsoft 365 grupos para controlar o acesso ao site. As Microsoft 365 de convidado grupos devem ser ativas para que o acesso de convidados SharePoint sites funcionem.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidado do Grupos do Microsoft 365

1. No Centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **Configurações**.
2. Clique em **Configurações da organização**.
3. Na lista, clique em **Grupos do Microsoft 365**.
4. Certifique-se de que as caixas de seleção **Permitir que proprietários de grupos adicionem pessoas fora de sua organização aos Grupos do Microsoft 365 como convidados** e **Permitir que membros de grupos convidados acessem o conteúdo do grupo** estejam marcadas.
5. Se você fez alterações, clique em **Salvar alterações**.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint configurações de compartilhamento no nível da organização

Para que os convidados tenham acesso SharePoint sites SharePoint, as configurações de compartilhamento no nível da organização devem permitir o compartilhamento com convidados.

As configurações no nível da organização determinam as configurações que estarão disponíveis para sites individuais. Como configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes.

Se você quiser permitir o compartilhamento de pastas e arquivos não autenticados, escolha **Qualquer Pessoa**. Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha Convidados novos **e existentes.** Escolher a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do Microsoft Office SharePoint Online

1. No Centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros de administração**, clique em **SharePoint**.
2. No centro SharePoint de administração, no painel de navegação esquerdo, em **Políticas,** clique em **Compartilhamento**.
3. Certifique-se de que o compartilhamento externo para o Microsoft Office SharePoint Online esteja definido como **Qualquer Pessoa** ou **Convidados novos e existentes**.
4. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-site"></a>Criar um site

A próxima etapa é criar o site que você planeja usar para colaborar com convidados.

Para criar um site
1. No centro de administração do SharePoint, em **sites**, clique **sites ativos**.
2. Clique em **Criar**.
3. Clique **em Site de Equipe**.
4. Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).
5. Em **Configurações avançadas,** escolha se deseja que esse site seja público ou privado.
6. Clique em **Avançar**.
7. Clique em **Concluir**.

Convidaremos os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento de nível de site do Microsoft Office SharePoint Online

Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para este site. Por exemplo, se você definir as configurações no nível da organização como Qualquer Pessoa **,** mas quiser que todos os convidados sejam autenticados para este site, certifique-se de que as configurações de compartilhamento no nível do site sejam definidas como Convidados novos e existentes. 

Observe que o site não pode ser compartilhado com pessoas não autenticadas **(** configuração de Qualquer pessoa), mas arquivos e pastas individuais podem.

Você também pode usar [rótulos de sensibilidade para controlar configurações de compartilhamento externo para SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).

![Captura de tela das configurações de compartilhamento externo do site do Microsoft Office SharePoint Online](../media/sharepoint-site-external-sharing-settings.png)

Para conjunto de configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.
2. Selecione o site que você deseja compartilhar.
3. Clique em ..., e clique em **Compartilhamento.**
4. Certifique-se de que o compartilhamento esteja no conjunto como **Qualquer pessoa** ou **Convidados novos e existentes**.
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas, para que você possa começar a adicionar usuários internos e convidados ao seu site. O acesso ao site é controlado por meio do grupo de Microsoft 365 associado, portanto, vamos adicionar usuários lá.

Para convidar usuários internos para um grupo
1. Navegue até o site onde você deseja adicionar usuários.
2. Clique **em** Link Membros no canto superior direito que indica a contagem de membros.
3. Clique em **Adicionar membros**.
4. Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **Salvar**.

Os convidados não podem ser adicionados do site. Você precisa adicioná-los usando Outlook na Web. Portanto, como pré-requisito para adicionar e convidar convidados a um grupo, clique na URL do site na coluna **URL**  para navegar até a página específica do site. Nesta página, clique no ícone do **iniciador de aplicativos** e selecione **Outlook**. Esta é a tela da qual você pode convidar convidados para um grupo, para o qual o procedimento é descrito abaixo.

Para convidar convidados para um grupo
1. Em **Grupos**, clique no grupo para o qual você deseja convidar convidados.
2. Abra o cartão de visita do grupo, **clique** em Link Membros no canto superior direito (o link que indica a contagem de membros).
3. clique **em Adicionar membros**.
4. Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar**.
5. Clique em **Fechar**.
Observe que você precisa clicar em **Fechar** somente se você não for o proprietário do grupo e, como resultado, não tiver permissão para adicionar o convidado ao grupo. Nesses casos, a solicitação para adicionar o convidado ao grupo é transferida para o proprietário do grupo para aprovação.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)

[Integração do Microsoft Office SharePoint Online e OneDrive com Microsoft Azure Active Directory B2B](/sharepoint/sharepoint-azureb2b-integration-preview)