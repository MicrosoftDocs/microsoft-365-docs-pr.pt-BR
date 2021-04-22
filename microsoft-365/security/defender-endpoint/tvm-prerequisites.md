---
title: Pré-requisitos & permissões - gerenciamento de ameaças e vulnerabilidades
description: Antes de começar a usar o gerenciamento de ameaças e vulnerabilidades, certifique-se de ter as configurações e permissões relevantes.
keywords: pré-& permissões de gerenciamento de vulnerabilidades, pré-requisitos de permissões de gerenciamento de ameaças e vulnerabilidades, pré-requisitos de permissões de TVM do Microsoft Defender para Endpoint, gerenciamento de vulnerabilidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935180"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Pré-requisitos & permissões - gerenciamento de ameaças e vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Certifique-se de que seus dispositivos:

- Estão integradas ao Microsoft Defender para Ponto de Extremidade
- Executar [sistemas operacionais e plataformas com suporte](tvm-supported-os.md)
- Tenha as seguintes atualizações obrigatórias instaladas e implantadas em sua rede para aumentar suas taxas de detecção de avaliação de vulnerabilidade:

> Lançar | Número e link do KB de atualização de segurança
> :---|:---
> Windows 10 Versão 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) e [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Versão 1803 | [KB4493464](https://support.microsoft.com/help/4493464) e [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Versão 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Versão 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Estão integradas ao [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e ao  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) para ajudar a correção de ameaças encontradas pelo gerenciamento de ameaças e vulnerabilidades. Se você estiver usando o Configuration Manager, atualize seu console para a versão mais recente.
    - **Observação**: se você tiver a conexão do Intune habilitada, você terá uma opção para criar uma tarefa de segurança do Intune ao criar uma solicitação de correção. Essa opção não será exibida se a conexão não estiver definida.
- Ter pelo menos uma recomendação de segurança que pode ser exibida na página do dispositivo
- São marcados ou marcados como co-gerenciados

## <a name="relevant-permission-options"></a>Opções de permissão relevantes

1. Faça logoff no Centro de Segurança do Microsoft Defender usando conta com um administrador de segurança ou função de administrador global atribuída.
2. No painel de navegação, selecione **Configurações > Funções**.

Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md)

### <a name="view-data"></a>Exibir dados

- **Operações de segurança** - Exibir todos os dados de operações de segurança no portal
- **Gerenciamento de ameaças e vulnerabilidades** - Exibir dados de gerenciamento de ameaças e vulnerabilidades no portal

### <a name="active-remediation-actions"></a>Ações de correção ativas

- **Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores
- **Gerenciamento de ameaças e vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas
- **Gerenciamento de ameaças e vulnerabilidades - Tratamento** de correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes

Para obter mais informações, consulte [opções de permissão RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral do gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Sistemas operacionais e plataformas com suporte](tvm-supported-os.md)
- [Atribuir valor ao dispositivo](tvm-assign-device-value.md)
- [Painel de gerenciamento de ameaças e vulnerabilidades](tvm-dashboard-insights.md)

