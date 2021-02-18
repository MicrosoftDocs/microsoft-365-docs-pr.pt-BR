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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre mensagens em quarentena no Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8496ae4f1702bb63328be0c494d8829c9ddd8cf2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289396"
---
# <a name="quarantined-messages-faq"></a>Perguntas frequentes sobre mensagens em quarentena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

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

Os usuários podem acessar spam, email em massa e (a partir de abril de 2020) mensagens de phishing em que são destinatários. Os usuários finais não podem acessar malware em quarentena, phishing de  alta confiança ou mensagens que foram colocadas em quarentena devido à ação Entregar a mensagem para a quarentena hospedada em regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações sobre os usuários que acessam mensagens em quarentena, consulte Encontrar e liberar mensagens [em quarentena como um usuário.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Por quanto tempo as mensagens são mantidas em quarentena?

Você configura por quanto tempo as mensagens de spam, phishing e email em massa são mantidas em quarentena usando políticas anti-spam. O padrão é 30 dias, que também é o máximo. Para obter mais informações, [consulte Configurar políticas anti-spam no EOP](configure-your-spam-filter-policies.md)

Para mensagens que foram colocadas em quarentena pela ação de regra de fluxo de emails Entregar a mensagem para a quarentena hospedada, as mensagens são mantidas em quarentena por 30 dias. Não é possível configurar essa duração.

Depois que o período expirar, as mensagens serão excluídas e não serão recuperáveis.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Posso liberar ou relatar mais de uma mensagem em quarentena por vez?

No Centro de Conformidade & segurança, você pode selecionar e liberar até 100 mensagens por vez.

Os administradores podem usar os cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) no PowerShell do Exchange Online ou no PowerShell do EOP autônomo para encontrar e liberar mensagens em quarentena em massa e para relatar falsos positivos em massa.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Há suporte para curingas ao procurar mensagens em quarentena? Posso procurar mensagens em quarentena para um domínio específico?

Caracteres curinga não são suportados no Centro de Conformidade & segurança. Por exemplo, ao pesquisar um remetente, você precisa especificar o endereço de email completo. Porém, você pode usar curingas no PowerShell do Exchange Online ou no EOP PowerShell autônomo.

Por exemplo, copie o seguinte código do PowerShell para o Bloco de Notas e salve o arquivo como .ps1 em um local fácil de encontrar (por exemplo, C:\Data\QuarantineRelease.ps1).

Em seguida, depois de se conectar [ao PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online ou ao PowerShell da Proteção do [Exchange Online,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)execute o seguinte comando para executar o script:

```powershell
& C:\Data\QuarantineRelease.ps1
```

O script faz as seguintes ações:

- Encontre mensagens não enviadas que foram colocadas em quarentena como spam de todos os remetentes no domínio fabrikam. O número máximo de resultados é 50.000 (50 páginas de 1.000 resultados).
- Salve os resultados em um arquivo CSV.
- Liberar as mensagens em quarentena correspondentes para todos os destinatários originais.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

Depois de liberar uma mensagem, você não poderá liberá-la novamente.
