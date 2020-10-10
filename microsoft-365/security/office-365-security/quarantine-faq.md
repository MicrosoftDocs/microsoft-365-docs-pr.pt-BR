---
title: Perguntas frequentes sobre mensagens em quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
description: Os administradores podem exibir perguntas frequentes e respostas sobre mensagens em quarentena na proteção do Exchange Online (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00768b3584c854ef0648f75f1966a8fa331b2866
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413419"
---
# <a name="quarantined-messages-faq"></a>Perguntas frequentes sobre mensagens em quarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este tópico fornece perguntas frequentes e respostas sobre mensagens de email em quarentena para organizações do Microsoft 365 com caixas de correio no Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online.

Para perguntas e respostas sobre a proteção contra spam, confira [perguntas frequentes sobre proteção](anti-spam-protection-faq.md)contra spam.

Para perguntas e respostas sobre a proteção contra malware, consulte [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md).

Para perguntas e respostas sobre a proteção contra falsificação, confira [perguntas frequentes sobre proteção contra falsificação](anti-spoofing-protection-faq.md).

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Como gerenciar mensagens em quarentena para malware?

Somente os administradores podem gerenciar mensagens em quarentena para malware. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Como faço a quarentena de spam?

Por padrão, as mensagens classificadas como spam ou email em massa por filtragem de spam são entregues na caixa de correio do usuário e são movidas para a pasta lixo eletrônico. Mas você pode criar e configurar políticas antispam para colocar em quarentena mensagens de email em massa ou spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Como posso conceder aos usuários acesso à quarentena?

Um usuário deve ter uma conta válida para acessar suas próprias mensagens em quarentena. O EOP autônomo exige que os usuários sejam representados como usuários de email no EOP (criado manualmente ou criado via sincronização de diretório). Para obter mais informações sobre como gerenciar usuários em ambientes autônomos do EOP, consulte [Manage mail users in EOP](manage-mail-users-in-eop.md).

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Quais mensagens podem acessar usuários finais em quarentena?

Os usuários podem acessar spam, email em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários. Os usuários finais não podem acessar malware em quarentena, phishing de alta confiança ou mensagens que foram colocadas em quarentena devido à ação de **entrega da mensagem para a quarentena hospedada** em regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte [Localizar e liberar mensagens em quarentena como um usuário](find-and-release-quarantined-messages-as-a-user.md).

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Quanto tempo as mensagens são mantidas na quarentena?

Você configura por quanto tempo spam, phishing e mensagens de email em massa são mantidos na quarentena usando políticas antispam. O padrão é 30 dias, que também é o máximo. Para obter mais informações, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md)

Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails **entregar a mensagem para a quarentena hospedada**, as mensagens são mantidas em quarentena por 30 dias. Você não pode configurar esta duração.

Depois que o período de tempo expira, as mensagens são excluídas e não são recuperáveis.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Posso liberar ou relatar mais de uma mensagem em quarentena por vez?

No centro de conformidade & segurança, você pode selecionar e liberar até 100 mensagens de cada vez.

Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) no PowerShell do Exchange Online ou EOP PowerShell para encontrar e liberar mensagens em massa e para relatar falsos positivos em massa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Há suporte para curingas durante a pesquisa de mensagens em quarentena? Posso pesquisar mensagens em quarentena para um domínio específico?

Não há suporte para curingas no centro de conformidade & segurança. Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo. No entanto, você pode usar caracteres curinga no PowerShell do Exchange Online ou no PowerShell do EOP autônomo.

Por exemplo, execute o seguinte comando para localizar mensagens de spam em quarentena de todos os remetentes no domínio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Em seguida, execute o seguinte comando para liberar essas mensagens a todos os destinatários originais:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Após liberar uma mensagem, você não poderá liberá-la novamente.
