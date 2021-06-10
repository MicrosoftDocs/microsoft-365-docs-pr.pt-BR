---
title: Proteção contra vírus SharePoint online, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Saiba como o SharePoint Online detecta vírus em arquivos que os usuários carregam e impede que os usuários baixem ou sincronizem os arquivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202984"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Proteção contra vírus SharePoint online, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)

Microsoft 365 usa um mecanismo de detecção de vírus comum para a verificação de arquivos que os usuários carregam no SharePoint Online, OneDrive e Microsoft Teams. Essa proteção está incluída em todas as assinaturas que incluem SharePoint Online, OneDrive e Microsoft Teams.

> [!IMPORTANT]
> Os recursos antivírus integrados são uma maneira de ajudar a conter vírus. Eles não são destinados como um único ponto de defesa contra malware para seu ambiente. Incentivamos todos os clientes a investigar e implementar a proteção anti-malware em várias camadas e aplicar práticas recomendadas para proteger sua infraestrutura corporativa. Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Roteiro de segurança.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>O que acontece se um arquivo infectado for carregado no SharePoint Online?

O Microsoft 365 de detecção de vírus é executado de forma assíncrona (independente de carregamentos de arquivos) no SharePoint Online. **Todos os arquivos não são verificados automaticamente.** A heurística determina os arquivos a examinar. Quando um arquivo é encontrado para conter um vírus, o arquivo é sinalizado. Em abril de 2018, removemos o limite de 25 MB para arquivos verificados.

Veja o que acontece:

1. Um usuário carrega um arquivo para SharePoint Online.
2. SharePoint Online, como parte de seus processos de verificação de vírus, determina mais tarde se o arquivo atende aos critérios de uma verificação.
3. Se o arquivo atender aos critérios de uma verificação, o mecanismo de detecção de vírus examinará o arquivo.
4. Se um vírus for encontrado no arquivo verificado, o mecanismo de vírus define uma propriedade no arquivo indicando que ele está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?

Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint Online usando um navegador.

Veja o que acontece:

1. Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.
2. O usuário recebe um aviso de que um vírus foi detectado. Por padrão, o usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando o software antivírus em seu próprio dispositivo.

> [!NOTE]
>
> Os administradores podem usar o *parâmetro DisallowInfectedFileDownload* no cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem arquivos infectados, mesmo na janela de aviso anti-vírus. Para obter instruções, [consulte Use SharePoint Online PowerShell para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Assim que você habilitar o *parâmetro DisallowInfectedFileDownload,* o acesso aos arquivos detectados/bloqueados será completamente bloqueado para usuários e administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>O que acontece quando o OneDrive de sincronização tenta sincronizar um arquivo infectado?

OneDrive clientes de sincronização não baixarão arquivos que contenham vírus. O cliente de sincronização exibirá uma notificação de que o arquivo não pode ser sincronizado.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Recursos estendidos com o Microsoft Defender para Office 365

Microsoft 365 organizações que têm o [Microsoft Defender](defender-for-office-365.md) para Office 365 incluídos em sua assinatura ou comprados como complemento podem habilitar anexos do Cofre para SharePoint, OneDrive e Microsoft Teams para relatórios e proteção aprimorados. Para obter mais informações, [consulte Cofre Attachments for SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Artigos relacionados

[Proteção contra malware e ransomware Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obter mais informações sobre o antivírus no SharePoint Online, OneDrive e Microsoft Teams, consulte [Protect against threats](protect-against-threats.md) and Turn on Cofre [Attachments for SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).
