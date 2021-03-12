---
title: Proteção contra vírus integrado no SharePoint Online, OneDrive e Microsoft Teams
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
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727494"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Proteção contra vírus integrado no SharePoint Online, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)

O Microsoft 365 usa um mecanismo de detecção de vírus comum para a verificação de arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams. Essa proteção está incluída em todas as assinaturas que incluem o SharePoint Online, o OneDrive e o Microsoft Teams.

> [!IMPORTANT]
> Os recursos antivírus integrados são uma maneira de ajudar a conter vírus. Eles não são destinados como um único ponto de defesa contra malware para seu ambiente. Incentivamos todos os clientes a investigar e implementar a proteção anti-malware em várias camadas e aplicar práticas recomendadas para proteger sua infraestrutura corporativa. Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Roteiro de segurança.](security-roadmap.md)

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>O que acontece se um arquivo infectado for carregado no SharePoint Online?

O mecanismo de detecção de vírus do Microsoft 365 é executado de forma assíncrona (independente dos carregamentos de arquivos) no SharePoint Online. **Todos os arquivos não são verificados automaticamente.** A heurística determina os arquivos a examinar. Quando um arquivo é encontrado para conter um vírus, o arquivo é sinalizado. Em abril de 2018, removemos o limite de 25 MB para arquivos verificados.

Veja o que acontece:

1. Um usuário carrega um arquivo no SharePoint Online.
2. O SharePoint Online, como parte de seus processos de verificação de vírus, determina mais tarde se o arquivo atende aos critérios de uma verificação.
3. Se o arquivo atender aos critérios de uma verificação, o mecanismo de detecção de vírus examinará o arquivo.
4. Se um vírus for encontrado no arquivo verificado, o mecanismo de vírus define uma propriedade no arquivo indicando que ele está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?

Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint Online usando um navegador.

Veja o que acontece:

1. Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.
2. O usuário recebe um aviso de que um vírus foi detectado. Por padrão, o usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando o software antivírus em seu próprio dispositivo.

> [!NOTE]
>
> Os administradores podem usar o *parâmetro DisallowInfectedFileDownload* no cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem arquivos infectados, mesmo na janela de aviso anti-vírus. Para obter instruções, consulte Usar o PowerShell do [SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)
>
> Assim que você habilitar o *parâmetro DisallowInfectedFileDownload,* o acesso aos arquivos detectados/bloqueados será completamente bloqueado para usuários e administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?

Os clientes de sincronização do OneDrive não baixarão arquivos que contêm vírus. O cliente de sincronização exibirá uma notificação de que o arquivo não pode ser sincronizado.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Recursos estendidos com o Microsoft Defender para Office 365

As organizações do Microsoft 365 que têm o [Microsoft Defender para Office 365](office-365-atp.md) incluído em sua assinatura ou comprados como complemento podem habilitar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams para relatórios e proteção aprimorados. Para obter mais informações, consulte [Anexos Seguros para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>Artigos relacionados

[Proteção contra malware e ransomware no Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Para obter mais informações sobre antivírus no SharePoint Online, OneDrive e Microsoft Teams, consulte [Protect against](protect-against-threats.md) threats and Turn on [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
