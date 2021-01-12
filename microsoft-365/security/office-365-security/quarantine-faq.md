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
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre mensagens em quarentena no Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794407"
---
# <a name="quarantined-messages-faq"></a>Perguntas frequentes sobre mensagens em quarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este tópico fornece perguntas frequentes e respostas sobre mensagens de email em quarentena para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.

Para perguntas e respostas sobre a proteção anti-spam, consulte Perguntas frequentes sobre [a proteção anti-spam.](anti-spam-protection-faq.md)

Para perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre [a proteção anti-malware.](anti-malware-protection-faq-eop.md)

Para perguntas e respostas sobre a proteção anti-spoofing, consulte Perguntas frequentes sobre a proteção [anti-spoofing.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Como faço para gerenciar mensagens que foram colocadas em quarentena para malware?

Somente administradores podem gerenciar mensagens que foram colocadas em quarentena para malware. Para obter mais informações, [consulte Gerenciar mensagens e arquivos em quarentena como administrador.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Como colocar o spam em quarentena?

Por padrão, as mensagens classificadas como spam ou email em massa pela filtragem de spam são entregues na caixa de correio do usuário e movidas para a pasta Lixo Eletrônico. Mas você pode criar e configurar políticas anti-spam para colocar mensagens de spam ou emails em massa em quarentena. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Como posso dar aos usuários acesso à quarentena?

Um usuário deve ter uma conta válida para acessar suas próprias mensagens em quarentena. O EOP autônomo exige que os usuários sejam representados como usuários de email no EOP (criado manualmente ou criado por meio da sincronização de diretórios). Para obter mais informações sobre como gerenciar usuários em ambientes EOP autônomos, consulte [Gerenciar usuários de email no EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Quais mensagens os usuários finais podem acessar em quarentena?

Os usuários podem acessar spam, email em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários. Os usuários finais não podem acessar malware em quarentena, phishing de  alta confiança ou mensagens que foram colocadas em quarentena devido à ação Entregar a mensagem para a quarentena hospedada em regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte Encontrar e liberar mensagens em quarentena [como um usuário.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Por quanto tempo as mensagens são mantidas em quarentena?

Você configura por quanto tempo as mensagens de spam, phishing e email em massa são mantidas em quarentena usando políticas anti-spam. O padrão é 30 dias, que também é o máximo. Para obter mais informações, [consulte Configurar políticas anti-spam no EOP](configure-your-spam-filter-policies.md)

Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails Entregar a mensagem para a quarentena hospedada, as mensagens são mantidas em quarentena por 30 dias. Não é possível configurar essa duração.

Após o período de tempo expirar, as mensagens serão excluídas e não serão recuperáveis.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Posso liberar ou relatar mais de uma mensagem em quarentena por vez?

No Centro de Conformidade & segurança, você pode selecionar e liberar até 100 mensagens por vez.

Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) no PowerShell do Exchange Online ou no PowerShell do EOP autônomo para encontrar e liberar mensagens em quarentena em massa e para relatar falsos positivos em massa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Há suporte para curingas ao procurar mensagens em quarentena? Posso procurar mensagens em quarentena para um domínio específico?

Caracteres curinga não são suportados no Centro de Conformidade & segurança. Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo. Porém, você pode usar curingas no PowerShell do Exchange Online ou no EOP PowerShell autônomo.

Por exemplo, execute o seguinte comando para encontrar mensagens em quarentena de spam de todos os remetentes no domínio contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Em seguida, execute o seguinte comando para liberar essas mensagens para todos os destinatários originais:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Depois de liberar uma mensagem, você não poderá liberá-la novamente.
