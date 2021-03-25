---
title: Conceder acesso ao provedor de serviços de segurança gerenciado (MSSP)
description: Tomar as etapas necessárias para configurar a integração do MSSP com o Microsoft Defender ATP
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1bb7bc3565bbb7c05f165c5649f3672ff33bb18b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165448"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Conceder acesso ao MSSP (provedor de serviços de segurança gerenciado) (visualização)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
>Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Para implementar uma solução de acesso delegado de vários locatários, tome as seguintes etapas:

1. Habilita o controle de acesso baseado em função no Defender para Ponto de Extremidade e [conecte-se](rbac.md) com grupos do Active Directory (AD).

2. Configurar [Pacotes de Acesso à Governança](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para solicitação e provisionamento de acesso.

3. Gerenciar solicitações e auditorias de acesso no [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Habilitar controles de acesso baseados em função no Microsoft Defender para Ponto de Extremidade

1. **Criar grupos de acesso para recursos MSSP no AAD do Cliente: Grupos**

    Esses grupos serão vinculados às Funções que você criar no Defender para Ponto de Extremidade. Para fazer isso, no locatário do AD do cliente, crie três grupos. Em nossa abordagem de exemplo, criamos os seguintes grupos:

    - Analista de Camada 1 
    - Analista de Camada 2 
    - Aprovadores do analista MSSP  


2. Crie funções do Defender para Ponto de Extremidade para níveis de acesso apropriados no Customer Defender for Endpoint.

    Para habilitar o RBAC no Centro de Segurança do Microsoft Defender do cliente, acesse Configurações > Permissões > **Funções** e "Ativar funções", de uma conta de usuário com direitos de Administrador Global ou Administrador de Segurança.

    ![Imagem do acesso ao MSSP](images/mssp-access.png)

    Em seguida, crie funções RBAC para atender às necessidades de Camada SOC do MSSP. Vincule essas funções aos grupos de usuários criados por meio de "Grupos de usuários atribuídos".

    Duas funções possíveis:

    - **Analistas de Camada 1** <br>
      Execute todas as ações, exceto a resposta ao vivo e gerencie as configurações de segurança.

    - **Analistas de Camada 2** <br>
      Recursos de camada 1 com a adição à [resposta ao vivo](live-response.md)

    Para obter mais informações, [consulte Use role-based access control](rbac.md).



## <a name="configure-governance-access-packages"></a>Configurar pacotes de Acesso à Governança

1.  **Adicionar MSSP como Organização Conectada no AAD do Cliente: Governança de Identidade**
    
    Adicionar o MSSP como uma organização conectada permitirá que o MSSP solicite e tenha acessos provisionados. 

    Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Organização conectada. Adicione uma nova organização e pesquise seu locatário do Analista MSSP por meio da ID do Locatário ou domínio. Sugerimos a criação de um locatário AD separado para seus Analistas MSSP.

2. **Criar um catálogo de recursos no AAD do Cliente: Governança de Identidade**

    Catálogos de recursos são uma coleção lógica de pacotes de acesso, criada no locatário do AD do cliente.

    Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Catálogos e adicione **Novo Catálogo.** No nosso exemplo, vamos chamá-lo **de Acessos MSSP.** 

    ![Imagem do novo catálogo](images/goverance-catalog.png)

    Mais informações em [Criar um catálogo de recursos.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Criar pacotes de acesso para recursos MSSP Customer AAD: Identity Governance**

    Pacotes de acesso são a coleção de direitos e acessos que um solicitante será concedido mediante aprovação. 

    Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Pacotes de Acesso e **adicione Novo Pacote de Acesso.** Crie um pacote de acesso para os aprovadores do MSSP e cada camada de analista. Por exemplo, a seguinte configuração de Analista de Camada 1 cria um pacote de acesso que:

    - Requer um membro do grupo AD Aprovadores de **Analista MSSP** para autorizar novas solicitações
    - Tem avaliações de acesso anual, onde os analistas do SOC podem solicitar uma extensão de acesso
    - Só pode ser solicitado por usuários no Locatário SOC do MSSP
    - O access auto expira após 365 dias

    > [!div class="mx-imgBorder"]
    > ![Imagem do novo pacote de acesso](images/new-access-package.png)

    Para obter mais informações, [consulte Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Fornecer link de solicitação de acesso aos recursos do MSSP do AAD do Cliente: Governança de Identidade**

    O link do portal Meu Acesso é usado pelos analistas soc do MSSP para solicitar acesso por meio dos pacotes de acesso criados. O link é durável, ou seja, o mesmo link pode ser usado ao longo do tempo para novos analistas. A solicitação de analista entra em fila para aprovação pelos Aprovadores do **Analista MSSP.**

    > [!div class="mx-imgBorder"]
    > ![Imagem das propriedades de acesso](images/access-properties.png)

    O link está localizado na página de visão geral de cada pacote de acesso.

## <a name="manage-access"></a>Gerenciar Acesso 

1. Revisar e autorizar solicitações de acesso no myaccess cliente e/ou MSSP.

    As solicitações de acesso são gerenciadas no cliente Meu Acesso, por membros do grupo aprovadores de analistas do MSSP.

    Para fazer isso, acesse o myaccess do cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Exemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aprovar ou negar solicitações na seção **Aprovações** da interface do usuário.

    Neste ponto, o acesso ao analista foi provisionado e cada analista deve poder acessar o Centro de Segurança do Microsoft Defender do cliente: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Tópicos relacionados
- [Acessar o portal do cliente MSSP](access-mssp-portal.md)
- [Configurar notificações de alerta](configure-mssp-notifications.md)
- [Buscar alertas do locatário do cliente](fetch-alerts-mssp.md)



 

