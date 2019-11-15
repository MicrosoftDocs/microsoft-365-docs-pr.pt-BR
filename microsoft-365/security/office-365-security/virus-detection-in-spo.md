---
title: Detecção de vírus no SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: O Office 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online. Os arquivos são verificados em busca de vírus após serem carregados. Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639821"
---
# <a name="virus-detection-in-sharepoint-online"></a>Detecção de vírus no SharePoint Online

> [!IMPORTANT]
> Para usar esse recurso, a proteção avançada contra ameaças do Office 365 (ATP) é necessária. Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).

O Office 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online. Os arquivos são verificados em busca de vírus após serem carregados. Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.
  
> [!IMPORTANT]
> Esses recursos de antivírus no SharePoint Online são uma maneira de conter vírus. Eles não se destinam a um único ponto de defesa contra malware para seu ambiente. Incentivamos todos os clientes a avaliar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa. Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md). 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>O que acontece quando um arquivo infectado é carregado no SharePoint Online?

O Office 365 usa um mecanismo de detecção de vírus comum. O mecanismo é executado de forma assíncrona no SharePoint Online e verifica os arquivos após serem carregados. Quando um arquivo é encontrado para conter um vírus, ele é sinalizado para que ele não possa ser baixado novamente. Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.
  
Veja o que acontece:
  
1. Um usuário carrega um arquivo para o SharePoint Online.
    
2. O mecanismo de detecção de vírus examina o arquivo.
    
3. Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?

Se um arquivo estiver infectado por um vírus, os usuários não poderão baixar o arquivo do SharePoint online usando o navegador.
  
Veja o que acontece:
  
1. Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.
    
2. O usuário recebe um aviso de que um vírus foi detectado. O usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando seu próprio software de vírus.

> [!NOTE]
> Você pode usar o cmdlet Set-SPOTenant com o parâmetro **DisallowInfectedFileDownload** para não permitir que os usuários baixem um arquivo detectado, mesmo na janela de aviso de antivírus. Confira [DisallowInfectedFileDownload]https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)(.
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?

Se os usuários sincronizam arquivos com o novo cliente de sincronização do OneDrive (OneDrive. exe) ou o cliente de sincronização anterior do OneDrive for Business (Groove. exe), se um arquivo contiver um vírus, o cliente de sincronização não o baixará. O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.
  

