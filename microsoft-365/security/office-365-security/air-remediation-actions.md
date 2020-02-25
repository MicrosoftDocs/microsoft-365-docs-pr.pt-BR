---
title: Ações de correção no Office 365 investigação e resposta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Saiba mais sobre as ações de correção em recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261048"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Ações de correção após uma investigação automatizada no Office 365

## <a name="remediation-actions"></a>Ações de correção

Os [recursos de investigação e resposta automatizados](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) na proteção avançada contra ameaças do Office 365 incluem determinadas ações de correção. Sempre que uma investigação automatizada estiver em execução ou concluída, você verá, em geral, uma ou mais ações de correção que exigem aprovação da equipe de operações de segurança para continuar. A tabela a seguir resume as ações de correção disponíveis atualmente na proteção avançada contra ameaças do Office 365. 

|Ação | Descrição |
|-----|-----|
|Bloquear URL (hora do clique) |Proteger contra emails e documentos que contenham URLs mal-intencionadas. Isso permite o bloqueio de links mal-intencionados e quaisquer páginas da Web relacionadas por meio de [links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando o usuário clica em um link em um arquivo do Office existente ou em uma mensagem de email mais antiga. |
|Email de exclusão reversível  |Exclusão reversível de mensagens de email específicas da caixa de correio de um usuário|
|Clusters de emails de exclusão reversível  |Exclusão reversível de mensagens de email mal-intencionadas que correspondem a uma consulta de todas as caixas de correio dos usuários|
|Desativar o encaminhamento de emails externo |Remove a regra de encaminhamento de uma caixa de correio de usuário final específica|

## <a name="approve-or-reject-pending-actions"></a>Aprovar (ou rejeitar) ações pendentes

![Página de ação de investigações aéreas](../../media/air-investigationactionspage.png)

Ao exibir os [detalhes de uma investigação](air-view-investigation-results.md), você pode aprovar ou rejeitar qualquer ação de correção pendente. É recomendável fazer isso assim que possível para que suas investigações automatizadas sejam concluídas.

> [!IMPORTANT]
> As permissões apropriadas são necessárias para aprovar ou rejeitar ações de correção. Confira [as permissões necessárias para usar os recursos de ar](office-365-air.md#required-permissions-to-use-air-capabilities).

1. Selecione a guia **ações** .

2. Selecione um item na lista. (Isso ativa os botões aprovar e rejeitar).

3. Revise as informações disponíveis para o (s) item (ns) que você selecionou e, em seguida, aprove ou rejeite a (s) ação (ões). 
 - **Aprovar** permite que a correção seja iniciada.
 - **Rejeitar** não realiza mais nenhuma ação

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre o guia de segurança de usuário comprometido](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [Exibir seus relatórios de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)