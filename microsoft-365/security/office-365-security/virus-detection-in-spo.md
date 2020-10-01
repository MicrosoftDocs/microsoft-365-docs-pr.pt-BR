---
title: Proteção de vírus interna no SharePoint Online, no OneDrive e no Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Saiba como o SharePoint Online detecta vírus em arquivos que os usuários carregam e impedem que os usuários baixem ou sincronizem os arquivos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327982"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Proteção de vírus interna no SharePoint Online, no OneDrive e no Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

O Microsoft 365 usa um mecanismo de detecção de vírus comum para verificar arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams. Essa proteção está incluída em todas as assinaturas que incluem o SharePoint Online, o OneDrive e o Microsoft Teams.

> [!IMPORTANT]
> Os recursos de antivírus internos são uma maneira de ajudar a conter vírus. Eles não se destinam a um único ponto de defesa contra malware para seu ambiente. Incentivamos todos os clientes a investigar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa. Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>O que acontece quando um arquivo infectado é carregado no SharePoint Online?

O mecanismo de detecção de vírus do Microsoft 365 é executado de forma assíncrona no SharePoint Online. **Todos os arquivos não são verificados automaticamente no carregamento**. Heurística determina os arquivos a serem verificados. Quando um arquivo é encontrado para conter um vírus, o arquivo é sinalizado para que ele não possa ser baixado novamente. Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.

Veja o que acontece:

1. Um usuário carrega um arquivo para o SharePoint Online.
2. O SharePoint Online determina se o arquivo atende aos critérios de uma verificação.
3. O mecanismo de detecção de vírus examina o arquivo.
4. Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?

Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint online usando um navegador.

Veja o que acontece:

1. Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.
2. O usuário recebe um aviso de que um vírus foi detectado. Por padrão, o usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando o software antivírus em seu próprio dispositivo.

> [!NOTE]
>
> Os administradores podem usar o parâmetro *DisallowInfectedFileDownload* no cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem arquivos infectados, mesmo na janela de aviso de antivírus. Para obter instruções, confira [usar o PowerShell do SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).
>
> Assim que você habilita o parâmetro *DisallowInfectedFileDownload* , o acesso aos arquivos detectados/bloqueados é completamente bloqueado para usuários e administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?

Os clientes de sincronização do OneDrive não baixarão arquivos que contenham vírus. O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a>Recursos estendidos com a proteção avançada contra ameaças do Office 365

As organizações 365 da Microsoft que têm a [proteção avançada contra ameaças do Office 365 (ATP)](office-365-atp.md) incluídas na assinatura ou compradas como um complemento podem habilitar a ATP para SharePoint, onedrive e Microsoft Teams para relatórios e proteção avançados. Para obter mais informações, consulte [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="more-information"></a>Mais informações

Para obter mais informações sobre anti-vírus no SharePoint Online, no OneDrive e no Microsoft Teams, consulte [proteger contra ameaças](protect-against-threats.md) e [ativar a ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
