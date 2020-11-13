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
description: Saiba mais sobre as etapas de configuração do 365 da Microsoft necessárias para configurar um site do SharePoint para colaboração com convidados.
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029988"
---
# <a name="collaborate-with-guests-in-a-site"></a>Colaborar com convidados em um site

Se você precisar colaborar com convidados entre documentos, dados e listas, poderá usar um site do SharePoint. Os sites modernos do SharePoint estão conectados a grupos do Microsoft 365 e podem gerenciar a associação do site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio compartilhada e um calendário.

Neste artigo, veremos as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

O compartilhamento no Microsoft 365 é regido no seu nível mais alto pelas [configurações de relações organizacionais no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você configurar no Microsoft 365.

Verifique as configurações de colaboração externa para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página de configurações de colaboração externa do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para definir configurações de colaboração externa

1. Faça logon no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. No painel de navegação esquerdo, clique em **Azure Active Directory**.
3. Clique em **identidades externas**.
4. Na tela **introdução** , no painel de navegação esquerdo, clique em **configurações de colaboração externa**.
5. Certifique-se de que **Administradores e usuários na função de convite de convidado podem convidar** e **os membros podem convidar** estão definidos como **Sim**.
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **restrições de colaboração** . Certifique-se de que os domínios dos convidados com os quais você deseja colaborar não estão bloqueados.

Se você trabalha com convidados de várias organizações, convém restringir sua capacidade de acessar dados de diretório. Isso impedirá que você veja quem mais é um convidado no diretório. Para fazer isso, em **restrições de acesso de usuário convidado** , selecione **os usuários convidados têm acesso limitado às propriedades e à associação de configurações de objetos de diretório** ou **o acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório**.

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado de grupos do Microsoft 365

Os sites modernos do SharePoint usam os grupos do Microsoft 365 para controlar o acesso ao site. As configurações de convidado do Microsoft 365 groups devem ser ativadas para que o acesso de convidados nos sites do SharePoint funcione.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidados de grupos do Microsoft 365

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, expanda **configurações**.
2. Clique em **configurações da organização**.
3. Na lista, clique em **Microsoft 365 grupos**.
4. Certifique-se de que os **proprietários de grupo permitem que as pessoas de fora da sua organização para o Microsoft 365 grupos de** convidados e **permitir que os membros do grupo convidado acessem o conteúdo do grupo de acesso** sejam verificados.
5. Se você tiver feito alterações, clique em **salvar alterações**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento no nível da organização do SharePoint

Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.

As configurações de nível de organização determinam as configurações que estarão disponíveis para sites individuais. As configurações do site não podem ser mais permissivas do que as configurações no nível da organização.

Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **qualquer pessoa**. Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha **novos e existentes convidados**. Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do SharePoint

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **centros de administração** , clique em **SharePoint**.
2. No centro de administração do SharePoint, no painel de navegação esquerdo, em **políticas** , clique em **compartilhamento**.
3. Verifique se o compartilhamento externo do SharePoint está definido como **qualquer pessoa** ou **novo convidado existente**.
4. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-site"></a>Criar um site

A próxima etapa é criar o site que você planeja usar para colaborar com convidados.

Para criar um site
1. No centro de administração do SharePoint, em **sites** , clique **sites ativos**.
2. Clique em **Criar**.
3. Clique em **site de equipe**.
4. Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).
5. Em **Configurações avançadas** , escolha se você deseja que esse site seja público ou privado.
6. Clique em **Avançar**.
7. Clique em **Concluir**.

Vamos convidar os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento no nível do site do SharePoint

Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para este site. Por exemplo, se você definir as configurações de nível de organização como **qualquer pessoa** , mas quiser que todos os convidados autentiquem esse site, verifique se as configurações de compartilhamento no nível do site estão definidas para **convidados novos e existentes**.

Observe que o site não pode ser compartilhado com pessoas não autenticadas (configuração de **qualquer pessoa** ), mas arquivos e pastas individuais podem.

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para definir configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.
2. Selecione o site que você deseja compartilhar.
3. Clique em... e em **compartilhamento**.
4. Verifique se o compartilhamento está definido como **qualquer pessoa** ou **convidado novo e existente**.
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas para que você possa começar a adicionar usuários internos e convidados ao seu site. O acesso ao site é controlado através do grupo associado da Microsoft 365, portanto, vamos adicionar usuários lá.

Para convidar usuários internos para um grupo
1. Navegue até o site em que você deseja adicionar usuários.
2. Clique no link **Membros** no canto superior direito que denota a contagem de membros.
3. Clique em **Adicionar membros**.
4. Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **salvar**.

Os usuários convidados não podem ser adicionados do site. Você precisa adicioná-los usando o Outlook na Web. Portanto, como pré-requisito para adicionar e convidar convidados para um grupo, clique na URL do site na coluna **URL**  para navegar até a página específica do site. Nessa página, clique no ícone do **inicializador de aplicativos** e selecione **Outlook**. Esta é a tela na qual você pode convidar convidados para um grupo, para o qual o procedimento descrito abaixo.

Para convidar convidados para um grupo
1. Em **grupos** , clique no grupo para o qual você deseja convidar convidados.
2. Abra o cartão de visita do grupo, clique no link **Membros** no canto superior direito (o link que denota a contagem de membros).
3. clique em **adicionar membros**.
4. Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar**.
5. Clique em **Fechar**.
Observe que você precisa clicar em **fechar** somente se não for o proprietário do grupo e, como resultado, você não tem permissão para adicionar o convidado ao grupo. Nesses casos, a solicitação para adicionar o convidado ao grupo é transferida para o proprietário do grupo para aprovação.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)

[Integração do SharePoint e do OneDrive com o B2B do Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
