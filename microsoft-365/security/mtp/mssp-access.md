---
title: Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365
description: Saiba mais sobre as alterações da Central de Segurança do Microsoft Defender para a central de segurança do Microsoft 365
keywords: Getting started with the Microsoft 365 security center, OATP, MDATP, MDO, MDE, single pane of glass, converged portal, security portal, defender security portal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242923"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Fornecer acesso ao provedor de serviços de segurança gerenciado (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Para implementar uma solução de acesso delegado de vários locatários, tome as seguintes etapas:

1. Habilita o controle de acesso baseado em função no Defender para o ponto de extremidade no centro de segurança do Microsoft 365 e [conecte-se](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) aos grupos do Azure Active Directory (Azure AD).

2. Configurar [Pacotes de Acesso de Governança](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para solicitação de acesso e provisionamento.

3. Gerenciar solicitações de acesso e auditorias [no Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Habilitar controles de acesso baseados em função no Microsoft Defender para o ponto de extremidade no centro de segurança do Microsoft 365

1. **Criar grupos de acesso para recursos MSSP no AAD do Cliente: Grupos**

    Esses grupos serão vinculados às Funções que você criar no Defender para o Ponto de Extremidade na central de segurança do Microsoft 365. Para fazer isso, no locatário do AD do cliente, crie três grupos. Na nossa abordagem de exemplo, criamos os seguintes grupos:

    - Analista de Nível 1 
    - Analista de Nível 2 
    - Aprovadores de analista do MSSP  


2. Crie funções do Defender para o Ponto de Extremidade para níveis de acesso apropriados no Customer Defender para o Ponto de Extremidade nas funções e grupos da central de segurança do Microsoft 365.

    Para habilitar o RBAC no centro de segurança do Microsoft 365 do cliente, acesse permissões > Funções de pontos de extremidade & grupos **> Funções** com uma conta de usuário com direitos de Administrador Global ou Administrador de Segurança.

    ![Imagem de acesso MSSP](../../media/mssp-access.png)

    Em seguida, crie funções do RBAC para atender às necessidades de camada SOC do MSSP. Vincule essas funções aos grupos de usuários criados por meio de "Grupos de usuários atribuídos".

    Duas funções possíveis:

    - **Nível 1 Analistas** <br>
      Execute todas as ações, exceto a resposta ao vivo e gerencie as configurações de segurança.

    - **Analistas de Nível 2** <br>
      Recursos do Nível 1 com a adição à [resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Para obter mais informações, [consulte Usar controle de acesso baseado em função.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)



## <a name="configure-governance-access-packages"></a>Configurar pacotes de acesso de governança

1.  **Adicionar MSSP como Organização Conectada no AAD do Cliente: Governança de Identidade**
    
    Adicionar o MSSP como uma organização conectada permitirá que o MSSP solicite e tenha acessos provisionados. 

    Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: organização conectada. Adicione uma nova organização e pesquise seu locatário de analista MSSP por meio da ID de locatário ou domínio. Sugerimos a criação de um locatário do AD separado para os analistas do MSSP.

2. **Criar um catálogo de recursos no AAD do Cliente: Governança de Identidade**

    Catálogos de recursos são uma coleção lógica de pacotes de acesso, criada no locatário do AD do cliente.

    Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Catálogos e adicione **Novo Catálogo.** No nosso exemplo, vamos chamá-lo **de MSSP Accesses**. 

    ![Imagem do novo catálogo](../../media/goverance-catalog.png)

    Mais informações, consulte [Criar um catálogo de recursos.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Criar pacotes de acesso para recursos MSSP Customer AAD: Identity Governance**

    Pacotes de acesso são o conjunto de direitos e acessos que um solicitante receberá mediante aprovação. 

    Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Pacotes do Access e adicione **Novo Pacote de Acesso.** Crie um pacote de acesso para os aprovadores do MSSP e para cada camada de analista. Por exemplo, a seguinte configuração de Analista de Nível 1 cria um pacote de acesso que:

    - Requer um membro do grupo AD **MSSP Analista Aprovadores** para autorizar novas solicitações
    - Tem revisões de acesso anual, onde os analistas do SOC podem solicitar uma extensão de acesso
    - Só pode ser solicitado por usuários no locatário SOC do MSSP
    - O Access expira automaticamente após 365 dias

    ![Imagem do novo pacote de acesso](../../media/new-access-package.png)

    Para obter mais informações, [consulte Criar um novo pacote de acesso.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Fornecer um link de solicitação de acesso aos recursos MSSP do AAD do Cliente: Governança de Identidade**

    O link do portal Meu Acesso é usado por analistas de SOC do MSSP para solicitar acesso por meio dos pacotes de acesso criados. O link é durável, o que significa que o mesmo link pode ser usado ao longo do tempo para novos analistas. A solicitação de analista entra em uma fila para aprovação dos aprovadores de **analista do MSSP.**


    ![Imagem das propriedades de acesso](../../media/access-properties.png)

    O link está localizado na página de visão geral de cada pacote de acesso.

## <a name="manage-access"></a>Gerenciar Acesso 

1. Revise e autorize solicitações de acesso no myaccess cliente e/ou MSSP.

    As solicitações de acesso são gerenciadas no cliente Meu Acesso, por membros do grupo Aprovadores de Analista do MSSP.

    Para fazer isso, acesse myaccess do cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Exemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aprovar ou negar solicitações na **seção Aprovações** da interface do usuário.

     Neste ponto, o acesso do analista foi provisionado, e cada analista deve poder acessar a Central de Segurança do Microsoft 365 do cliente: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` com as permissões e funções que foram atribuídas.

> [!IMPORTANT]
> O acesso delegado ao Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365 atualmente permite o acesso a um único locatário por janela do navegador. 