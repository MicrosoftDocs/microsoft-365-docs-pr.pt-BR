---
title: Pré-requisitos & permissões - Gerenciamento de Ameaças e Vulnerabilidades
description: Antes de começar a Gerenciamento de Ameaças e Vulnerabilidades, certifique-se de ter as configurações e permissões relevantes.
keywords: pré-& Gerenciamento de Vulnerabilidades permissões de ameaça, pré-requisitos de permissões Gerenciamento de Ameaças e Vulnerabilidades, pré-requisitos de permissões do Microsoft Defender para TVM de ponto de extremidade, Gerenciamento de Vulnerabilidades
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
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843945"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Pré-requisitos & permissões - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Ameaça e Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
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

- São integradas [para](/mem/intune/fundamentals/what-is-intune) Microsoft Intune e [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) ajudar a correção de ameaças encontradas por Gerenciamento de Ameaças e Vulnerabilidades. Se você estiver usando o Configuration Manager, atualize seu console para a versão mais recente.
    - **Observação**: se você tiver a conexão do Intune habilitada, você terá uma opção para criar uma tarefa de segurança do Intune ao criar uma solicitação de correção. Essa opção não será exibida se a conexão não estiver definida.
- Ter pelo menos uma recomendação de segurança que pode ser exibida na página do dispositivo
- São marcados ou marcados como co-gerenciados

## <a name="relevant-permission-options"></a>Opções de permissão relevantes

1. Faça logoff Central de Segurança do Microsoft Defender conta usando com um administrador de segurança ou função de administrador global atribuída.
2. No painel de navegação, selecione Configurações > **Funções**.

Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md)

### <a name="view-data"></a>Exibir dados

- **Operações de segurança** - Exibir todos os dados de operações de segurança no portal
- **Ameaça e Gerenciamento de Vulnerabilidades** - Exibir Gerenciamento de Ameaças e Vulnerabilidades dados no portal

### <a name="active-remediation-actions"></a>Ações de correção ativas

- **Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores
- **Ameaça e Gerenciamento de Vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas
- **Ameaças e Gerenciamento de Vulnerabilidades - Tratamento de** correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes

Para obter mais informações, consulte [opções de permissão RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Sistemas operacionais e plataformas com suporte](tvm-supported-os.md)
- [Atribuir valor ao dispositivo](tvm-assign-device-value.md)
- [Painel de ameaças e Gerenciamento de Vulnerabilidades de segurança](tvm-dashboard-insights.md)

