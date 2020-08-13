---
title: Detecção de vírus no SharePoint Online
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
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653504"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Detecção de vírus no SharePoint Online, no OneDrive e no Microsoft Teams

O Microsoft 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams. Os arquivos podem ser verificados em busca de vírus após serem carregados. Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.

> [!IMPORTANT]
> Esses recursos de antivírus no SharePoint Online são uma maneira de conter vírus. Eles não se destinam a um único ponto de defesa contra malware para seu ambiente. Incentivamos todos os clientes a avaliar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa. Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>O que acontece quando um arquivo infectado é carregado no SharePoint Online?

O Microsoft 365 usa um mecanismo de detecção de vírus comum. O mecanismo é executado de forma assíncrona no SharePoint Online e examina alguns arquivos após serem carregados. Heurísticas são usadas para determinar quais arquivos são verificados. Quando um arquivo é encontrado para conter um vírus, ele é sinalizado para que ele não possa ser baixado novamente. Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.

Veja o que acontece:

1. Um usuário carrega um arquivo para o SharePoint Online.

2. O SharePoint Online determina se o arquivo atende aos critérios de uma verificação.

3. O mecanismo de detecção de vírus examina o arquivo.

4. Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?

Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint online usando o navegador.

Veja o que acontece:

1. Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.

2. O usuário recebe um aviso de que um vírus foi detectado. O usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando seu próprio software antivírus.

> [!NOTE]
>
> Você pode usar o parâmetro *DisallowInfectedFileDownload* no cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem um arquivo infectado, mesmo na janela de aviso de antivírus.
>
> Além disso, tenha em mente que, assim que você habilitar o parâmetro *DisallowInfectedFileDownload* , o acesso aos arquivos detectados/bloqueados é completamente bloqueado para usuários e administradores.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?

Se os usuários sincronizam arquivos com o novo cliente de sincronização do OneDrive (OneDrive.exe) ou com o cliente de sincronização anterior do OneDrive for Business (Groove.exe), se um arquivo contiver um vírus, o cliente de sincronização não o baixará. O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.

## <a name="extended-capabilities-with-office-365-atp"></a>Recursos estendidos com o Office 365 ATP

Os clientes que habilitaram o Office 365 ATP para SharePoint, OneDrive e Microsoft Teams ativam a [ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) podem usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena para detecções AV e ATP. [Somente ATP: Use o centro de conformidade de & de segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="more-information"></a>Mais informações

Confira [proteção contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) e [ative a ATP para SharePoint, onedrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) para obter mais informações sobre como configurar o antivírus do SharePoint Online.


