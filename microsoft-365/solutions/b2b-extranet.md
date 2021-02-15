---
title: Crie uma extranet B2B com convidados gerenciados
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba como criar um site ou uma equipe de extranet B2B com convidados gerenciados de uma organização parceira.
ms.openlocfilehash: cfb7cc4310cb83f9ce7761c95f021724b7d75faf
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613591"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Crie uma extranet B2B com convidados gerenciados

Você pode usar o Gerenciamento de Direitos do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) para criar uma extranet B2B para colaborar com uma organização parceira que usa o Azure Active Directory. Isso permite que os usuários se inscrevam no site ou na equipe da extranet e recebam acesso por meio de um fluxo de trabalho de aprovação.

Com esse método de compartilhamento de recursos para colaboração, a organização parceira pode ajudar a manter e aprovar os convidados da parte deles, reduzindo a carga sobre o departamento de IT e permitindo que os mais familiarizados com o contrato de colaboração gerenciem o acesso do usuário.

Este artigo explica as etapas para criar um pacote de recursos (neste caso, um site ou equipe) que você pode compartilhar com uma organização parceira por meio de um modelo de registro de acesso de autoatendido. 

Antes de começar, crie o site ou a equipe que você deseja compartilhar com a organização parceira e habilita-o para compartilhamento de convidados. Consulte [Colaborar com convidados em um site ou](collaborate-in-site.md) Colaborar com convidados em uma [equipe](collaborate-as-team.md) para obter mais informações. Também recomendamos que você revise Criar um ambiente de compartilhamento de convidados seguro para obter informações sobre recursos de segurança e conformidade que você pode usar para ajudar [a](create-secure-guest-sharing-environment.md) manter suas políticas de governança ao colaborar com convidados.

## <a name="license-requirements"></a>Requisitos de licença

Usar esse recurso requer uma licença do Azure AD Premium P2. 

Nuvens especializadas, como a Azure Alemanha e o Azure China 21Vianet, não estão disponíveis para uso no momento.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo demonstra os procedimentos abordados neste artigo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Conectar a organização parceira

Para convidar convidados de uma organização parceira, você precisa adicionar o domínio do parceiro como uma organização conectada no Azure Active Directory.

Para adicionar uma organização conectada
1. No [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**
2. Clique **em Organizações Conectadas.**
4. Clique **em Adicionar organização conectada.**
5. Digite um nome e uma descrição para a organização e clique em **Próximo: Diretório + domínio.**
6. Clique **em Adicionar diretório + domínio.**
7. Digite o domínio da organização que você deseja conectar e clique em **Adicionar.**
8. Clique **em Conectar** e clique em **Próximo: Patrocinadores.**
9. Adicione pessoas da sua organização ou da organização que você está se conectando a quem você deseja aprovar o acesso para convidados.
10. Clique **em Próximo: Revisão + Criar**.
11. Revise as configurações escolhidas e clique em **Criar.**

    ![Captura de tela da página de organizações conectadas no Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Escolher os recursos a compartilhar

A primeira etapa na seleção de recursos para compartilhar com uma organização parceira é criar um catálogo para contê-los.

Para criar um catálogo
1. No [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**
2. Clique **em Catálogos.**
3. Clique **em Novo catálogo.**
4. Digite um nome e uma descrição para  o catálogo e certifique-se de que **Habilitado** e Habilitado para usuários externos estão definidos como **Sim.**
5. Clique em **Criar**.

   ![Captura de tela da página de catálogos no Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Depois que o catálogo tiver sido criado, você adicionará o site ou a equipe do SharePoint que deseja compartilhar com a organização parceira.

Para adicionar recursos a um catálogo
1. No Azure AD Identity Governance, clique em **Catálogos** e, em seguida, clique no catálogo onde você deseja adicionar recursos.
2. Clique **em Recursos** e em Adicionar **recursos.**
3. Selecione as equipes ou sites do SharePoint que você deseja incluir em sua extranet e clique em **Adicionar**.

   ![Captura de tela da página de recursos de catálogo no Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Depois de definir os recursos que você deseja compartilhar, a próxima etapa é criar um pacote de acesso, que define o tipo de acesso que os usuários parceiros são concedidos e o processo de aprovação para novos usuários parceiros que solicitam acesso.

Para criar um pacote de acesso
1. No Azure AD Identity Governance, clique em **Catálogos** e, em seguida, clique no catálogo onde você deseja criar um pacote de acesso.
2. Clique **em Pacotes do Access** e em Novo pacote de **acesso.**
3. Digite um nome e uma descrição para o pacote de acesso e clique em **Próximo: Funções de recurso.**
4. Escolha os recursos do catálogo que você deseja usar para sua extranet.
5. Para cada recurso, na coluna **Função,** escolha a função de usuário que você deseja conceder aos convidados que usam a extranet.
6. Clique **em Próximo: Solicitações**.
7. Em **Usuários que podem solicitar acesso,** escolha Para usuários que não estão em seu **diretório.**
8. Verifique se a **opção Organizações conectadas** específicas está selecionada e clique em **Adicionar diretórios.**
9. Escolha a organização conectada que você adicionou anteriormente e clique em **Selecionar**
10. Em **Aprovação,** escolha **Sim** para **Exigir aprovação.**
11. Em **Primeiro aprovador,** escolha um dos patrocinadores que você adicionou anteriormente ou escolha um usuário específico.
12. Clique **em Adicionar fallback** e selecione um aprovador de fallback.
13. Em **Habilitar,** escolha **Sim**.
14. Clique **em Próximo: Ciclo de Vida.**
15. Escolha as configurações de revisão de expiração e acesso que você deseja usar e clique em **Next: Review + Create**.
16. Revise suas configurações e clique em **Criar.**

    ![Captura de tela da tela de pacotes de acesso no Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Se você estiver fazendo parceria com uma grande organização, talvez queira ocultar o pacote de acesso. Se o pacote estiver oculto, os usuários na organização parceira não verão o pacote no portal *meu Acesso.* Em vez disso, eles devem ser enviados um link direto para se inscrever no pacote. Ocultar o pacote de acesso pode reduzir o número de solicitações de acesso inadequado e também pode ajudar a manter os pacotes de acesso disponíveis organizados no portal da organização parceira.

Para definir um pacote de acesso como oculto
1. No Azure AD Identity Governance, clique em pacotes **do Access** e em seu pacote de acesso.
2. Na página **Visão** geral, clique em **Editar**.
3. Em **Propriedades,** escolha **Sim** para **Oculto** e clique em **Salvar.**

   ![Screenshot of an edit access package properties screen](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Convidar usuários parceiros

Se você definir o pacote de acesso como oculto, precisará enviar um link direto para a organização parceira para que eles possam solicitar acesso ao seu site ou equipe.

Para encontrar o link do portal de acesso
1. No Azure AD Identity Governance, clique em pacotes **do Access** e em seu pacote de acesso.
2. Na página **Visão geral,** clique no link Copiar **para área de** transferência para o link do portal meu **Acesso.**

   ![Captura de tela das propriedades do pacote de acesso com o link do portal de acesso](../media/identity-governance-access-portal-link.png)

Depois de copiar o link, você poderá compartilhá-lo com seu contato na organização do parceiro e eles poderão enviá-lo aos usuários em sua equipe de colaboração.

## <a name="see-also"></a>Confira também

[Criar um ambiente seguro de compartilhamento de convidados](create-secure-guest-sharing-environment.md)
