---
title: Métodos e propriedades de atividade de correção
description: A resposta à API contém & de gerenciamento de vulnerabilidades criadas em seu locatário. Você pode solicitar todas as atividades de correção, apenas uma atividade de correção ou informações sobre dispositivos expostos para uma tarefa de correção selecionada.
keywords: apis, correção, api de correção, obter, tarefas de correção,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f720d638ec469523a1d567dee9c01fa0974b0090
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061092"
---
# <a name="remediation-activity-methods-and-properties"></a>Métodos e propriedades de atividade de correção

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

A resposta à API contém [& atividades](next-gen-threat-and-vuln-mgt.md)de correção de gerenciamento de vulnerabilidades criadas em   seu locatário.  

## <a name="methods"></a>Métodos

Método | Tipo de dados | Descrição
:---|:---|:---
[Listar todas as atividades de correção](get-remediation-all-activities.md) | Coleção Investigation | Retorna informações sobre todas as atividades de correção.
[Listar dispositivos expostos de uma atividade de correção](get-remediation-exposed-devices-activities.md) | Entidade de investigação | Retorna informações sobre dispositivos expostos para a atividade de correção especificada.
[Obter uma atividade de correção por Id](get-remediation-one-activity.md) | Entidade de investigação | Retorna informações para a atividade de correção especificada.

Saiba mais sobre [atividades de correção.](tvm-remediation.md)

## <a name="properties"></a>Propriedades

ID da propriedade | Tipo de dados | Descrição
:---|:---|:---
category | Cadeia de caracteres | Categoria da atividade de correção (Configuração de software/segurança)
completerEmail | Cadeia de caracteres | Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails
completerId | Cadeia de caracteres | Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto
completionMethod | Cadeia de caracteres | Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída".
createdOn | DateTime | Hora em que essa atividade de correção foi criada
description | Cadeia de caracteres | Descrição dessa atividade de correção
dueOn | DateTime | Data de vencimento do conjunto de criadores para essa atividade de correção
fixedDevices |  | O número de dispositivos que foram corrigidos
id | Cadeia de caracteres | ID dessa atividade de correção
nameId | Cadeia de caracteres | Nome do produto relacionado
prioridade | Cadeia de caracteres | Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low)
productId | Cadeia de caracteres | ID do produto relacionado
productivityImpactRemediationType | Cadeia de caracteres | Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário. Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário".
rbacGroupNames | Cadeia de caracteres | Nomes de grupo de dispositivos relacionados
recommendedProgram | Cadeia de caracteres | Programa recomendado para atualizar para
recommendedVendor | Cadeia de caracteres | Fornecedor recomendado para atualizar para
recommendedVersion | Cadeia de caracteres | Versão recomendada para atualização/atualização para
relatedComponent | Cadeia de caracteres | Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança)
requesterEmail | Cadeia de caracteres | Endereço de email do criador
requesterId | Cadeia de caracteres | ID do objeto Creator
requesterNotes | Cadeia de caracteres | As anotações (texto livre) que o criador adicionou para essa atividade de correção
scid | Cadeia de caracteres | SCID da recomendação de segurança relacionada
status | Cadeia de caracteres | Status da atividade de correção (Ativo/Concluído)
statusLastModifiedOn | DateTime | Data em que o campo de status foi atualizado
targetDevices | Longo | Número de dispositivos expostos a que essa correção é aplicável
title | Cadeia de caracteres | Título dessa atividade de correção
tipo | Cadeia de caracteres | Tipo de correção
vendorId | Cadeia de caracteres | Nome do fornecedor relacionado

## <a name="see-also"></a>Confira também

- [Obter uma atividade de correção por Id](get-remediation-one-activity.md)

- [Listar todas as atividades de correção](get-remediation-all-activities.md)

- [Listar dispositivos expostos de uma atividade de correção](get-remediation-exposed-devices-activities.md)

- [Gerenciamento de vulnerabilidades baseadas em & risco](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
