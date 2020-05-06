---
title: Perguntas Frequentes sobre a Quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Perguntas frequentes e respostas sobre a quarentena para caixas de correio do Office 365 no Exchange Online ou EOP autônomo sem caixas de correio do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5c5d7f426701ebc9a546a86a4fccbd7015fc0e49
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033849"
---
# <a name="quarantine-faq"></a>Perguntas Frequentes sobre a Quarentena

Este tópico fornece perguntas frequentes e respostas sobre a quarentena para clientes do Microsoft 365 com caixas de correio em Exchange Online ou clientes autônomos do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>P: como gerenciar mensagens em quarentena para malware?

Somente os administradores podem gerenciar mensagens em quarentena para malware. Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).

## <a name="q-how-do-i-quarantine-spam"></a>P: como colocar em quarentena spam?

R. Por padrão, as mensagens classificadas como spam ou email em massa por filtragem de spam são entregues na caixa de correio do usuário e são movidas para a pasta lixo eletrônico. Mas você pode criar e configurar políticas antispam para colocar em quarentena mensagens de email em massa ou spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>P: como permitir que os usuários acessem a quarentena?

R. Um usuário deve ter uma conta válida para acessar suas próprias mensagens em quarentena. O EOP autônomo exige que os usuários sejam representados como usuários de email no EOP (criado manualmente ou criado via sincronização de diretório). Para obter mais informações sobre como gerenciar usuários em ambientes autônomos do EOP, consulte [Manage mail users in EOP](manage-mail-users-in-eop.md).

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>P: quais mensagens podem acessar usuários finais em quarentena?

R. Os usuários podem acessar spam, emails em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários. Os usuários finais não podem acessar malware em quarentena, phishing de alta confiança ou mensagens que foram colocadas em quarentena devido à ação de **entrega da mensagem para a quarentena hospedada** em regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>P: quanto tempo as mensagens são mantidas na quarentena?

R. Você configura por quanto tempo spam, phishing e mensagens de email em massa são mantidos na quarentena usando políticas antispam. O padrão é 30 dias, que também é o máximo. Para obter mais informações, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md)

Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails **entregar a mensagem para a quarentena hospedada**, as mensagens são mantidas em quarentena por 30 dias. Você não pode configurar esta duração.

Depois que o período de tempo expira, as mensagens são excluídas e não são recuperáveis.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>P: posso liberar ou relatar mais de uma mensagem em quarentena por vez?

R. No centro de conformidade & segurança, você pode selecionar e liberar até 100 mensagens de cada vez.

Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) no PowerShell do Exchange Online ou do Exchange Online Protection PowerShell para localizar e liberar mensagens em quarentena em massa e para relatar falsos positivos em massa.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>P: há suporte para curingas durante a pesquisa de mensagens em quarentena? Posso pesquisar mensagens em quarentena para um domínio específico?

R. Não há suporte para curingas no centro de conformidade & segurança. Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo. No entanto, você pode usar caracteres curinga no PowerShell do Exchange Online ou do Exchange Online Protection.

Por exemplo, execute o seguinte comando para localizar mensagens de spam em quarentena de todos os remetentes no domínio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Em seguida, execute o seguinte comando para liberar essas mensagens a todos os destinatários originais:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Após liberar uma mensagem, você não poderá liberá-la novamente.
