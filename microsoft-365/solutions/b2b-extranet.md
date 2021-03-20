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
description: Saiba como criar um site de extranet B2B ou uma equipe com convidados gerenciados de uma organização parceira.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904751"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Crie uma extranet B2B com convidados gerenciados

Você pode usar o [Azure Active Directory Gerenciamento](/azure/active-directory/governance/entitlement-management-overview) de Direitos para criar uma extranet B2B para colaborar com uma organização parceira que usa o Azure Active Directory. Isso permite que os usuários se inscrevam no site ou equipe da extranet e recebam acesso por meio de um fluxo de trabalho de aprovação.

Com esse método de compartilhamento de recursos para colaboração, a organização do parceiro pode ajudar a manter e aprovar os convidados em suas extremidades, reduzindo a carga em seu departamento de IT e permitindo que os mais familiarizados com o contrato de colaboração gerenciem o acesso do usuário.

Este artigo percorre as etapas para criar um pacote de recursos (nesse caso, um site ou uma equipe) que você pode compartilhar com uma organização parceira por meio de um modelo de registro de acesso autoatendido. 

Antes de começar, crie o site ou a equipe que você deseja compartilhar com a organização do parceiro e habilita-o para compartilhamento de convidados. Confira [Colaborar com convidados em um site ou](collaborate-in-site.md) Colaborar com convidados em uma [equipe](collaborate-as-team.md) para obter mais informações. Também recomendamos que você revise Criar um ambiente de compartilhamento de convidados seguro para obter informações sobre recursos de segurança e conformidade que você pode usar para ajudar [a](create-secure-guest-sharing-environment.md) manter suas políticas de governança ao colaborar com convidados.

## <a name="license-requirements"></a>Requisitos de licença

Usar esse recurso requer uma licença do Azure AD Premium P2. 

Nuvens especializadas, como o Azure Germany e o Azure China 21Vianet, não estão disponíveis no momento para uso.

## <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo demonstra os procedimentos abordados neste artigo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>Conectar a organização do parceiro

Para convidar convidados de uma organização parceira, você precisa adicionar o domínio do parceiro como uma organização conectada no Azure Active Directory.

Para adicionar uma organização conectada
1. No [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**
2. Clique **em Organizações Conectadas**.
4. Clique **em Adicionar organização conectada.**
5. Digite um nome e uma descrição para a organização e clique em **Next: Directory + domain**.
6. Clique **em Adicionar diretório + domínio.**
7. Digite o domínio da organização que você deseja conectar e clique em **Adicionar**.
8. Clique **em Conectar** e clique em **Próximo: Patrocinadores**.
9. Adicione pessoas da sua organização ou da organização que você está conectando a quem deseja aprovar o acesso aos convidados.
10. Clique em **Avançar: Analisar + Criar**.
11. Revise as configurações escolhidas e clique em **Criar**.

    ![Captura de tela da página organizações conectadas no Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Escolha os recursos a compartilhar

A primeira etapa na seleção de recursos para compartilhar com uma organização parceira é criar um catálogo para contê-los.

Para criar um catálogo
1. No [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**
2. Clique **em Catálogos**.
3. Clique **em Novo catálogo**.
4. Digite um nome e uma descrição para  o catálogo e verifique se **Habilitado** e Habilitado para usuários externos estão definidos como **Sim**.
5. Clique em **Criar**.

   ![Captura de tela da página catálogos no Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

Depois que o catálogo tiver sido criado, você adicionará o site ou a equipe do SharePoint que deseja compartilhar com a organização do parceiro.

Para adicionar recursos a um catálogo
1. No Azure AD Identity Governance, clique em **Catálogos** e clique no catálogo onde você deseja adicionar recursos.
2. Clique **em Recursos** e clique em Adicionar **recursos.**
3. Selecione as equipes ou sites do SharePoint que você deseja incluir em sua extranet e clique em **Adicionar**.

   ![Captura de tela da página de recursos do catálogo no Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

Depois de definir os recursos que você deseja compartilhar, a próxima etapa é criar um pacote de acesso, que define o tipo de acesso que os usuários parceiros são concedidos e o processo de aprovação para novos usuários parceiros solicitando acesso.

Para criar um pacote de acesso
1. No Azure AD Identity Governance, clique em **Catálogos** e, em seguida, clique no catálogo onde você deseja criar um pacote de acesso.
2. Clique **em Acessar pacotes** e clique em Novo pacote de **acesso.**
3. Digite um nome e uma descrição para o pacote de acesso e clique em **Next: Resource roles**.
4. Escolha os recursos do catálogo que você deseja usar para sua extranet.
5. Para cada recurso, na coluna **Função,** escolha a função de usuário que você deseja conceder aos convidados que usam a extranet.
6. Clique **em Próximo: Solicitações**.
7. Em **Usuários que podem solicitar acesso,** escolha Para usuários que não estão em seu **diretório**.
8. Verifique se a **opção Organizações Conectadas** Específicas está selecionada e clique em **Adicionar diretórios**.
9. Escolha a organização conectada que você adicionar anteriormente e clique em **Selecionar**
10. Em **Aprovação**, escolha **Sim** para **Exigir aprovação**.
11. Em **Primeiro aprovador,** escolha um dos patrocinadores que você adicionou anteriormente ou escolha um usuário específico.
12. Clique **em Adicionar fallback** e selecione um aprovador de fallback.
13. Em **Habilitar**, escolha **Sim**.
14. Clique **em Próximo: Ciclo de Vida**.
15. Escolha as configurações de revisão de expiração e acesso que você deseja usar e clique em **Next: Review + Create**.
16. Revise suas configurações e clique em **Criar**.

    ![Captura de tela da tela de pacotes de acesso no Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

Se você estiver fazendo parceria com uma organização grande, talvez queira ocultar o pacote de acesso. Se o pacote estiver oculto, os usuários da organização parceira não verão o pacote em seu portal *do Meu* Acesso. Em vez disso, eles devem ser enviados um link direto para se inscrever no pacote. Ocultar o pacote de acesso pode reduzir o número de solicitações de acesso inadequadas e também pode ajudar a manter pacotes de acesso disponíveis organizados no portal da organização do parceiro.

Para definir um pacote de acesso como oculto
1. Em Governança de Identidade do Azure AD, clique em **Pacotes de Acesso** e clique em seu pacote de acesso.
2. Na página **Visão** Geral, clique em **Editar**.
3. Em **Propriedades,** escolha **Sim** para **Oculto** e clique em **Salvar**.

   ![Captura de tela de uma tela editar propriedades do pacote de acesso](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>Convidar usuários parceiros

Se você definir o pacote de acesso como oculto, precisará enviar um link direto para a organização do parceiro para que ele possa solicitar acesso ao seu site ou equipe.

Para encontrar o link do portal de acesso
1. Em Governança de Identidade do Azure AD, clique em **Pacotes de Acesso** e clique em seu pacote de acesso.
2. Na página **Visão** Geral, clique em **Copiar para** o link da área de transferência para o link do portal **Meu Acesso.**

   ![Captura de tela das propriedades do pacote de acesso com link do portal de acesso](../media/identity-governance-access-portal-link.png)

Depois de copiar o link, você pode compartilhá-lo com seu contato na organização do parceiro e eles podem enviá-lo para os usuários em sua equipe de colaboração.

## <a name="see-also"></a>Confira também

[Criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md)