---
title: Anexos seguros para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Saiba mais sobre o Microsoft Defender para Office 365 para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175722"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Anexos seguros para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Os Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams no [Microsoft Defender para Office 365](office-365-atp.md) fornece uma camada adicional de proteção para arquivos que já foram verificados no momento do carregamento pelo mecanismo de detecção de vírus comum no Microsoft [365.](virus-detection-in-spo.md) Os Anexos Seguros do SharePoint, oneDrive e Microsoft Teams ajudam a detectar e bloquear arquivos existentes identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.

Os Anexos Seguros do SharePoint, oneDrive e Microsoft Teams não estão habilitados por padrão. Para aproxá-lo, [confira Ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Como funcionam os Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams

Quando o recurso Anexos Seguros para SharePoint, OneDrive e Microsoft Teams está habilitado e identifica um arquivo como mal-intencionado, o arquivo é bloqueado usando a integração direta com os armazenamentos de arquivos. A imagem a seguir mostra um exemplo de um arquivo mal-intencionado detectado em uma biblioteca.

![Arquivos no OneDrive for Business com um detectado como mal-intencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Embora o arquivo bloqueado ainda esteja listado na biblioteca de documentos e em aplicativos web, móveis ou da área de trabalho, as pessoas não podem abrir, copiar, mover ou compartilhar o arquivo. Mas eles podem excluir o arquivo bloqueado.

Veja um exemplo da aparência de um arquivo bloqueado em um dispositivo móvel:

![Excluir um arquivo bloqueado do OneDrive for Business do aplicativo móvel do OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Por padrão, as pessoas podem baixar um arquivo bloqueado. Veja a aparência de download de um arquivo bloqueado em um dispositivo móvel:

![Baixando um arquivo bloqueado no OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Os administradores do SharePoint Online podem impedir que as pessoas baixem arquivos mal-intencionados. Para obter instruções, confira Usar o PowerShell do [SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Para saber mais sobre a experiência do usuário quando um arquivo foi detectado como mal-intencionado, confira O que fazer quando um arquivo mal-intencionado for encontrado no [SharePoint Online, no OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)ou no Microsoft Teams.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Exibir informações sobre arquivos mal-intencionados detectados pelos Anexos Seguros do SharePoint, OneDrive e Microsoft Teams

Os arquivos identificados como mal-intencionados pelo Microsoft Defender para Office 365 aparecerão nos relatórios do [Microsoft Defender para Office 365](view-reports-for-atp.md) e no Explorer [(e detecções](threat-explorer.md)em tempo real).

A partir de maio de 2018, quando um arquivo é identificado como mal-intencionado pelo Microsoft Defender para Office 365, o arquivo também está disponível em quarentena. Para obter mais informações, [consulte Usar o Centro de Conformidade & segurança para gerenciar arquivos em quarentena.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Tenha esses pontos em mente

- O Defender para Office 365 não verificará todos os arquivos no SharePoint Online, no OneDrive for Business ou no Microsoft Teams. Este é o comportamento padrão do produto. Os arquivos são verificados de forma assíncrona. O processo usa eventos de compartilhamento e atividades de convidados, juntamente com heurística inteligente e sinais de ameaça para identificar arquivos mal-intencionados.

- Certifique-se de que seus sites do SharePoint estão configurados para usar a [experiência moderna.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) A proteção do Defender para Office 365 se aplica se a experiência moderna ou a exibição Clássica é usada; No entanto, indicadores visuais de que um arquivo está bloqueado estão disponíveis somente na experiência moderna.

- Os Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams fazem parte da estratégia geral de proteção contra ameaças da sua organização, que inclui proteção anti-spam e anti-malware no Exchange Online Protection (EOP), bem como links seguros e anexos seguros no Microsoft Defender para Office 365. Para saber mais, confira [Proteger contra ameaças no Office 365.](protect-against-threats.md)
