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
description: Saiba mais sobre as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663519"
---
# <a name="collaborate-with-guests-in-a-site"></a>Colaborar com convidados em um site

Se você precisar colaborar com convidados em documentos, dados e listas, poderá usar um site do SharePoint. Os sites modernos do SharePoint estão conectados aos Grupos do Microsoft 365 e podem gerenciar a associação ao site e fornecer ferramentas de colaboração adicionais, como uma caixa de correio compartilhada e um calendário.

Neste artigo, vamos ver as etapas de configuração do Microsoft 365 necessárias para configurar um site do SharePoint para colaboração com convidados.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

O compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas configurações de colaboração [externa B2B no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você definir no Microsoft 365.

Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página Configurações de colaboração externa do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para definir configurações de colaboração externa

1. Entre no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. No painel de navegação esquerdo, clique no **Azure Active Directory.**
3. Clique **em Identidades externas.**
4. Na tela **De início,** no painel de navegação esquerdo, clique em **Configurações de colaboração externa.**
5. Certifique-se de que os administradores e  usuários na função de convidado convidado possam convidar e que os membros possam convidar estão **definidos** como **Sim.**
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **Restrições de** colaboração. Certifique-se de que os domínios dos convidados com os que você deseja colaborar não sejam bloqueados.

Se você trabalha com convidados de várias organizações, talvez queira restringir sua capacidade de acessar dados de diretório. Isso impedirá que eles veja quem mais é um convidado no diretório. Para fazer isso, em restrições de acesso de usuário **convidado,** selecione **Usuários** convidados têm acesso limitado a propriedades e associação de configurações de objetos de diretório ou acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de **diretório.**

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado dos Grupos do Microsoft 365

Os sites modernos do SharePoint usam grupos do Microsoft 365 para controlar o acesso ao site. As configurações de convidado dos Grupos do Microsoft 365 devem ser tivas para que o acesso de convidados nos sites do SharePoint funcione.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidado dos Grupos do Microsoft 365

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, **expanda Configurações.**
2. Clique **em Configurações da Organização.**
3. Na lista, clique em **Grupos do Microsoft 365.**
4. Verifique se os proprietários do grupo Permitem que os proprietários adicionem pessoas de fora da sua organização aos Grupos do **Microsoft 365** como convidados e deixe que os membros do grupo convidado acessem as caixas de seleção de conteúdo do grupo. 
5. Se você fez alterações, clique em **Salvar alterações.**

## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento no nível da organização do SharePoint

Para que os convidados tenham acesso aos sites do SharePoint, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.

As configurações no nível da organização determinam as configurações que estarão disponíveis para sites individuais. As configurações de site não podem ser mais permissivas do que as configurações no nível da organização.

Se você quiser permitir o compartilhamento de arquivos e pastas não autenticados, escolha **Qualquer Pessoa.** Se você quiser garantir que todas as pessoas de fora da sua organização tenham que se autenticar, escolha convidados **novos e existentes.** Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do SharePoint

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros** de administração, clique **em SharePoint**.
2. No centro de administração do SharePoint, no painel de navegação esquerdo, em **Políticas,** clique em **Compartilhamento.**
3. Certifique-se de que o compartilhamento externo do SharePoint está definido **como Qualquer pessoa** ou convidados novos e **existentes.**
4. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-site"></a>Criar um site

A próxima etapa é criar o site que você planeja usar para colaborar com convidados.

Para criar um site
1. No centro de administração do SharePoint, em **sites**, clique **sites ativos**.
2. Clique em **Criar**.
3. Clique **em Site de Equipe.**
4. Digite um nome de site e insira um nome para o proprietário do grupo (proprietário do site).
5. Em **Configurações Avançadas,** escolha se deseja que este site seja público ou privado.
6. Clique em **Avançar**.
7. Clique em **Concluir**.

Convidaremos os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site para este site.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento no nível do site do SharePoint

Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para esse site. Por exemplo, se você definir as configurações no nível da organização como Qualquer **Pessoa,** mas quiser que todos os convidados se autentiem nesse site, certifique-se de que as configurações de compartilhamento no nível do site estão definidas como Convidados novos e existentes. 

Observe que o site não pode ser compartilhado com pessoas não autenticadas **(** configuração de Qualquer pessoa), mas arquivos e pastas individuais podem.

Você também pode usar [rótulos de sensibilidade para controlar as configurações de compartilhamento externo para sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para definir configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.
2. Selecione o site que você deseja compartilhar.
3. Clique em ...e clique em **Compartilhamento.**
4. Certifique-se de que o compartilhamento está definido **como Qualquer** pessoa ou convidados novos **e existentes.**
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas, para que você possa começar a adicionar usuários internos e convidados ao seu site. O acesso ao site é controlado por meio do Grupo do Microsoft 365 associado, portanto, adicionaremos usuários lá.

Para convidar usuários internos para um grupo
1. Navegue até o site em que deseja adicionar usuários.
2. Clique **no** link Membros no canto superior direito que indica a contagem de membros.
3. Clique em **Adicionar membros**.
4. Digite os nomes ou endereços de email dos usuários que você deseja convidar para o site e clique em **Salvar.**

Os convidados não podem ser adicionados do site. Você precisa adicioná-los usando o Outlook na Web. Portanto, como pré-requisito para adicionar e convidar convidados a um grupo, clique na URL do site na coluna **url**  para navegar até a página específica do site. Nesta página, clique no ícone do **iniciador de aplicativos** e selecione **Outlook.** Esta é a tela da qual você pode convidar convidados para um grupo, para a qual o procedimento é descrito abaixo.

Para convidar convidados para um grupo
1. Em **Grupos,** clique no grupo para o qual você deseja convidar convidados.
2. Abra o cartão de visita do grupo, **clique** no link Membros no canto superior direito (o link que indica a contagem de membros).
3. clique **em Adicionar membros**.
4. Digite os endereços de email dos convidados que você deseja convidar e clique em **Adicionar.**
5. Clique em **Fechar**.
Observe que você precisará **clicar** em Fechar somente se não for o proprietário do grupo e, como resultado, não tiver permissão para adicionar o convidado ao grupo. Nesses casos, a solicitação para adicionar o convidado ao grupo é transferida para o proprietário do grupo para aprovação.

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)

[Integração do SharePoint e OneDrive com o Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
