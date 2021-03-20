---
title: Fornecer acesso ao MSSP (provedor de serviços de segurança gerenciado)
description: Saiba mais sobre as alterações do Centro de Segurança do Microsoft Defender para o centro de segurança do Microsoft 365
keywords: Iniciando o centro de segurança do Microsoft 365, OATP, MDATP, MDO, MDE, painel único de vidro, portal convergido, portal de segurança, portal de segurança do defender
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
ms.openlocfilehash: db9279ba1bc5fe11f3a31884a05b4403f0cb67f3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906695"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Fornecer acesso ao MSSP (provedor de serviços de segurança gerenciado) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Para implementar uma solução de acesso delegado de vários locatários, tome as seguintes etapas:

1. Habilita o controle de acesso baseado em função no Defender for Endpoint no Centro de segurança do Microsoft 365 e [conecte-se](/windows/security/threat-protection/microsoft-defender-atp/rbac) aos grupos do Azure Active Directory (Azure AD).

2. Configurar [Pacotes de Acesso à Governança](/azure/active-directory/governance/identity-governance-overview) para solicitação e provisionamento de acesso.

3. Gerenciar solicitações e auditorias de acesso no [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Habilitar controles de acesso baseados em função no Microsoft Defender para Ponto de Extremidade no Centro de segurança do Microsoft 365

1. **Criar grupos de acesso para recursos MSSP no AAD do Cliente: Grupos**

    Esses grupos serão vinculados às funções que você criar no Defender for Endpoint no Centro de segurança do Microsoft 365. Para fazer isso, no locatário do AD do cliente, crie três grupos. Em nossa abordagem de exemplo, criamos os seguintes grupos:

    - Analista de Camada 1 
    - Analista de Camada 2 
    - Aprovadores do analista MSSP  


2. Crie funções do Defender para Ponto de Extremidade para níveis de acesso apropriados no Customer Defender for Endpoint em funções e grupos do Centro de Segurança do Microsoft 365.

    Para habilitar o RBAC no centro de segurança do Microsoft 365 do cliente, acesse Permissões > Funções de Pontos de Extremidade & **grupos > Funções** com uma conta de usuário com direitos de Administrador Global ou Administrador de Segurança.

    ![Imagem do acesso ao MSSP](../../media/mssp-access.png)

    Em seguida, crie funções RBAC para atender às necessidades de Camada SOC do MSSP. Vincule essas funções aos grupos de usuários criados por meio de "Grupos de usuários atribuídos".

    Duas funções possíveis:

    - **Analistas de Camada 1** <br>
      Execute todas as ações, exceto a resposta ao vivo e gerencie as configurações de segurança.

    - **Analistas de Camada 2** <br>
      Recursos de camada 1 com a adição à [resposta ao vivo](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Para obter mais informações, [consulte Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).



## <a name="configure-governance-access-packages"></a>Configurar pacotes de Acesso à Governança

1.  **Adicionar MSSP como Organização Conectada no AAD do Cliente: Governança de Identidade**
    
    Adicionar o MSSP como uma organização conectada permitirá que o MSSP solicite e tenha acessos provisionados. 

    Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Organização conectada. Adicione uma nova organização e pesquise seu locatário do Analista MSSP por meio da ID do Locatário ou domínio. Sugerimos a criação de um locatário AD separado para seus Analistas MSSP.

2. **Criar um catálogo de recursos no AAD do Cliente: Governança de Identidade**

    Catálogos de recursos são uma coleção lógica de pacotes de acesso, criada no locatário do AD do cliente.

    Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Catálogos e adicione **Novo Catálogo.** No nosso exemplo, vamos chamá-lo **de Acessos MSSP.** 

    ![Imagem do novo catálogo](../../media/goverance-catalog.png)

    Mais informações em [Criar um catálogo de recursos.](/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Criar pacotes de acesso para recursos MSSP Customer AAD: Identity Governance**

    Pacotes de acesso são a coleção de direitos e acessos que um solicitante será concedido mediante aprovação. 

    Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Pacotes de Acesso e **adicione Novo Pacote de Acesso.** Crie um pacote de acesso para os aprovadores do MSSP e cada camada de analista. Por exemplo, a seguinte configuração de Analista de Camada 1 cria um pacote de acesso que:

    - Requer um membro do grupo AD Aprovadores de **Analista MSSP** para autorizar novas solicitações
    - Tem avaliações de acesso anual, onde os analistas do SOC podem solicitar uma extensão de acesso
    - Só pode ser solicitado por usuários no Locatário SOC do MSSP
    - O access auto expira após 365 dias

    ![Imagem do novo pacote de acesso](../../media/new-access-package.png)

    Para obter mais informações, [consulte Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Fornecer link de solicitação de acesso aos recursos do MSSP do AAD do Cliente: Governança de Identidade**

    O link do portal Meu Acesso é usado pelos analistas soc do MSSP para solicitar acesso por meio dos pacotes de acesso criados. O link é durável, ou seja, o mesmo link pode ser usado ao longo do tempo para novos analistas. A solicitação de analista entra em fila para aprovação pelos Aprovadores do **Analista MSSP.**


    ![Imagem das propriedades de acesso](../../media/access-properties.png)

    O link está localizado na página de visão geral de cada pacote de acesso.

## <a name="manage-access"></a>Gerenciar Acesso 

1. Revisar e autorizar solicitações de acesso no myaccess cliente e/ou MSSP.

    As solicitações de acesso são gerenciadas no cliente Meu Acesso, por membros do grupo aprovadores de analistas do MSSP.

    Para fazer isso, acesse o myaccess do cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Exemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aprovar ou negar solicitações na seção **Aprovações** da interface do usuário.

     Neste ponto, o acesso de analistas foi provisionado e cada analista deve poder acessar o Centro de Segurança do Microsoft 365 do cliente: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` com as permissões e funções que foram atribuídas.

> [!IMPORTANT]
> O acesso delegado ao Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365 atualmente permite o acesso a um único locatário por janela do navegador.