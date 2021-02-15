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
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba mais sobre as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para colaboração de tarefas, conversas e documentação com convidados no Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233069"
---
# <a name="collaborate-with-guests-in-a-team"></a>Colaborar com convidados em uma equipe

Se você precisar colaborar com convidados em documentos, tarefas e conversas, recomendamos usar o Microsoft Teams. O Teams fornece todos os recursos de colaboração disponíveis no Office e no SharePoint com chat persistente e um conjunto personalizável e extensível de ferramentas de colaboração em uma experiência unificada do usuário.

Neste artigo, vamos ver as etapas de configuração do Microsoft 365 necessárias para configurar uma equipe para colaboração com convidados. Depois de configurar o acesso de convidados, você poderá convidar convidados para as equipes seguindo as etapas em Adicionar [convidados a uma equipe no Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra as etapas de configuração descritas neste documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configurações de colaboração externa do Azure

O compartilhamento no Microsoft 365 é regido em seu nível mais alto pelas configurações de colaboração [externa B2B no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Se o compartilhamento de convidados estiver desabilitado ou restrito no Azure AD, essa configuração substituirá as configurações de compartilhamento que você definir no Microsoft 365.

Verifique as configurações de colaboração externa B2B para garantir que o compartilhamento com convidados não seja bloqueado.

![Captura de tela da página de configurações das Relações Organizacionais do Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para definir configurações de colaboração externa

1. Entre no Azure Active Directory em [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. No painel de navegação esquerdo, clique no **Azure Active Directory.**
3. Clique **em Identidades externas.**
4. Na tela **De início,** no painel de navegação esquerdo, clique em **Configurações de colaboração externa.**
5. Certifique-se de que os administradores e  usuários na função de convidado convidado possam convidar e que os membros possam convidar estão **definidos** como **Sim.**
6. Caso tenha feito alterações, clique em **Salvar**.

Observe as configurações na seção **Restrições de** colaboração. Certifique-se de que os domínios dos convidados com os que você deseja colaborar não sejam bloqueados.

Se você trabalha com convidados de várias organizações, talvez queira restringir sua capacidade de acessar dados de diretório. Isso impedirá que eles veja quem mais é um convidado no diretório. Para fazer isso, sob restrições de acesso de usuário **convidado,** selecione **Usuários** convidados têm acesso limitado a propriedades e associação de configurações de objetos de diretório ou acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de **diretório.**

## <a name="teams-guest-access-settings"></a>Configurações de acesso de convidados do Teams

O Teams tem um botão ligar/desligar mestre para acesso de convidados e uma variedade de configurações disponíveis para controlar o que os convidados podem fazer em uma equipe. A opção mestre, **Permitir o acesso de convidados no Teams** deve estar **1.0** para que o acesso de convidados funcione no Teams.

Verifique se o acesso de convidados está habilitado no Teams e faça qualquer ajuste nas configurações dos convidados com base nas suas necessidades comerciais. Lembre-se de que essas configurações afetam todas as equipes.

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

Para definir as configurações de acesso de convidado do Teams

1. Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).
2. No painel de navegação esquerdo, clique em **Mostrar tudo.**
3. Em **Centros de administração**, clique em **Teams**.
4. No centro de administração do Teams, no painel de navegação esquerdo, expanda as **configurações** de toda a organização e clique em **Acesso de convidado.**
5. Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.
6. Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.

Depois que o acesso de convidados do Teams está ligado, você pode controlar opcionalmente o acesso de convidados a equipes individuais e seus sites associados do SharePoint usando rótulos de sensibilidade. Para mais informações, veja [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Pode levar até 24 horas para que as configurações de convidado do Teams se tornem ativas depois que você a ativa.

## <a name="microsoft-365-groups-guest-settings"></a>Configurações de convidado dos Grupos do Microsoft 365

O Teams usa grupos do Microsoft 365 para associação de equipe. As configurações de convidado dos Grupos do Microsoft 365 devem ser tivas para que o acesso de convidados no Teams funcione.

![Captura de tela das configurações de convidado dos Grupos do Microsoft 365 no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings.png)

Para definir as configurações de convidado dos Grupos do Microsoft 365

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, **expanda Configurações.**
2. Clique **em Configurações da Organização.**
3. Na lista, clique em **Grupos do Microsoft 365.**
4. Verifique se os proprietários do grupo Permitem que os proprietários adicionem pessoas de fora da sua organização aos Grupos do **Microsoft 365** como convidados e deixe que os membros do grupo convidado acessem as caixas de seleção de conteúdo do grupo. 
5. Se você fez alterações, clique em **Salvar alterações.**


## <a name="sharepoint-organization-level-sharing-settings"></a>Configurações de compartilhamento no nível da organização do SharePoint

O conteúdo do Teams, como arquivos, pastas e listas, é armazenado no SharePoint. Para que os convidados tenham acesso a esses itens no Teams, as configurações de compartilhamento no nível da organização do SharePoint devem permitir o compartilhamento com convidados.

As configurações no nível da organização determinam quais configurações estão disponíveis para sites individuais, incluindo sites associados a equipes. As configurações de site não podem ser mais permissivas do que as configurações no nível da organização.

Se você quiser permitir o compartilhamento de arquivos e pastas com pessoas não autenticadas, escolha **Qualquer pessoa.** Se você quiser garantir que todos os convidados tenham que se autenticar, escolha **Convidados novos e existentes.** Escolha a configuração mais permissiva que será necessária para qualquer site em sua organização.

![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para definir as configurações de compartilhamento no nível da organização do SharePoint

1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, em **Centros** de administração, clique **em SharePoint**.
2. No centro de administração do SharePoint, no painel de navegação esquerdo, expanda **Políticas** e clique em **Compartilhamento.**
3. Certifique-se de que o compartilhamento externo do SharePoint está definido **como Qualquer pessoa** ou convidados novos e **existentes.**
4. Caso tenha feito alterações, clique em **Salvar**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Configurações de link padrão no nível da organização do SharePoint

As configurações padrão de link de arquivo e pasta determinam a opção de link que será mostrada aos usuários por padrão quando eles compartilharem um arquivo ou pasta. Os usuários podem alterar o tipo de link para uma das outras opções antes de compartilhar, se desejado.

Lembre-se de que essa configuração afeta todas as equipes e sites do SharePoint em sua organização.

Escolha qualquer um dos seguintes tipos de link que serão selecionados por padrão quando os usuários compartilharem arquivos e pastas:

- **Qualquer pessoa com o link** - Escolha essa opção se você espera fazer muitos compartilhamentos não autenticados de arquivos e pastas. Se você quiser permitir links *para* Qualquer pessoa, mas estiver preocupado com o compartilhamento acidental não autenticado, considere uma das outras opções como padrão. Esse tipo de link só estará disponível se você tiver habilitado o compartilhamento **de Qualquer** pessoa.
- **Somente pessoas em sua organização** - Escolha essa opção se você espera que a maioria dos compartilhamentos de arquivos e pastas seja com pessoas dentro da sua organização.
- **Pessoas específicas** - Considere essa opção se você espera fazer muito compartilhamento de arquivos e pastas com convidados. Esse tipo de link funciona com convidados e exige que eles se autententem.
 
![Captura de tela das configurações de compartilhamento de pastas e arquivos no nível da organização do SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para definir as configurações de link padrão no nível da organização do SharePoint

1. Navegue até a página Compartilhamento no centro de administração do SharePoint.
2. Em **Links de arquivo e pasta,** selecione o link de compartilhamento padrão que você deseja usar.
3. Caso tenha feito alterações, clique em **Salvar**.

## <a name="create-a-team"></a>Criar uma equipe

A próxima etapa é criar a equipe que você planeja usar para colaborar com convidados.

Para criar uma equipe
1. No Teams, na guia **Teams,** clique **em Ingressar** ou criar uma equipe na parte inferior do painel esquerdo.
2. Clique **em Criar uma equipe.**
3. Clique **em Criar uma equipe do zero.**
4. Escolha **Particular** ou **Público.**
5. Digite um nome e uma descrição para a equipe e clique em **Criar.**
6. Clique **em Ignorar**.

Convidaremos os usuários mais tarde. Em seguida, é importante verificar as configurações de compartilhamento no nível do site do SharePoint que está associado à equipe.

## <a name="sharepoint-site-level-sharing-settings"></a>Configurações de compartilhamento no nível do site do SharePoint

Verifique as configurações de compartilhamento no nível do site para garantir que elas permitam o tipo de acesso que você deseja para essa equipe. Por exemplo, se você definir as configurações no nível da organização como Qualquer **pessoa,** mas quiser que todos os convidados se autententem nessa equipe, certifique-se de que as configurações de compartilhamento no nível do site estão definidas como convidados novos e existentes. 

![Captura de tela das configurações de compartilhamento de site externo do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para definir configurações de compartilhamento no nível do site
1. No centro de administração do SharePoint, no painel de navegação esquerdo, **expanda Sites** e clique em **Sites ativos.**
2. Selecione o site da equipe que você acabou de criar.
3. Clique em ... e escolha **Compartilhamento**.
4. Certifique-se de que o compartilhamento está definido **como Qualquer** pessoa ou convidados novos **e existentes.**
5. Caso tenha feito alterações, clique em **Salvar**.

## <a name="invite-users"></a>Convidar usuários

As configurações de compartilhamento de convidados agora estão configuradas, para que você possa começar a adicionar usuários internos e convidados à sua equipe. 

Para convidar usuários internos para uma equipe
1. Na equipe, clique em **Mais opções** ( **\*\*\*** ) e, em seguida, clique **em Adicionar membro**.
2. Digite o nome da pessoa que você deseja convidar.
3. Clique **em Adicionar** e em **Fechar.**

Para convidar convidados para uma equipe
1. Na equipe, clique em **Mais opções** ( **\*\*\*** ) e, em seguida, clique **em Adicionar membro**.
2. Digite o endereço de email do convidado que você deseja convidar.
3. Clique **em Editar informações de convidado.**
4. Digite o nome completo do convidado e clique na marca de seleção.
5. Clique **em Adicionar** e em **Fechar.**

## <a name="see-also"></a>Confira também

[Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)

[Limitar a exposição acidental dos arquivos ao compartilhar com convidados](share-limit-accidental-exposure.md)

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)

[Crie uma extranet B2B com convidados gerenciados](b2b-extranet.md)

[Integração do SharePoint e OneDrive com o Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[As opções de compartilhamento ficam acinzentas ao compartilhar do SharePoint ou do OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
