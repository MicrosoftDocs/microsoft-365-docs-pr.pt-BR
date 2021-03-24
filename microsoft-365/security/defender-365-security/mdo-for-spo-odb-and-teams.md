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
description: Saiba mais sobre o Microsoft Defender para Office 365 para arquivos no SharePoint Online, No OneDrive for Business e no Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053155"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Anexos seguros para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Anexos seguros para SharePoint, OneDrive e Microsoft Teams no [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) fornece uma camada adicional de proteção para arquivos que já foram verificados no momento do carregamento pelo mecanismo de detecção de vírus comum no Microsoft [365](virus-detection-in-spo.md). Os Anexos Seguros para SharePoint, OneDrive e Microsoft Teams ajudam a detectar e bloquear arquivos existentes identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.

Anexos seguros para SharePoint, OneDrive e Microsoft Teams não estão habilitados por padrão. Para a ativar, consulte Ativar Anexos Seguros [para SharePoint, OneDrive e Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Como funcionam os anexos seguros do SharePoint, do OneDrive e do Microsoft Teams

Quando anexos seguros para SharePoint, OneDrive e Microsoft Teams estão habilitados e identificam um arquivo como mal-intencionado, o arquivo é bloqueado usando a integração direta com os armazenamentos de arquivos. A imagem a seguir mostra um exemplo de um arquivo mal-intencionado detectado em uma biblioteca.

![Arquivos no OneDrive for Business com um detectado como mal-intencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Embora o arquivo bloqueado ainda esteja listado na biblioteca de documentos e em aplicativos web, móveis ou desktop, as pessoas não podem abrir, copiar, mover ou compartilhar o arquivo. Mas eles podem excluir o arquivo bloqueado.

Veja um exemplo da aparência de um arquivo bloqueado em um dispositivo móvel:

![Excluir um arquivo bloqueado do OneDrive for Business do aplicativo móvel do OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Por padrão, as pessoas podem baixar um arquivo bloqueado. Veja a aparência de baixar um arquivo bloqueado em um dispositivo móvel:

![Baixar um arquivo bloqueado no OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Os administradores do SharePoint Online podem impedir que as pessoas baixem arquivos mal-intencionados. Para obter instruções, consulte Usar o PowerShell do [SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Para saber mais sobre a experiência do usuário quando um arquivo foi detectado como mal-intencionado, consulte O que fazer quando um arquivo mal-intencionado é encontrado no [SharePoint Online, no OneDrive ou no Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Exibir informações sobre arquivos mal-intencionados detectados por Anexos Seguros para SharePoint, OneDrive e Microsoft Teams

Arquivos identificados como mal-intencionados pelo Microsoft Defender para Office 365 aparecerão em relatórios para [o Microsoft Defender para Office 365](view-reports-for-mdo.md) e no Explorer (e detecções em tempo [real)](threat-explorer.md).

A partir de maio de 2018, quando um arquivo é identificado como mal-intencionado pelo Microsoft Defender para Office 365, o arquivo também está disponível em quarentena. Para obter mais informações, [consulte Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Lembre-se desses pontos

- O Defender para Office 365 não examinará todos os arquivos no SharePoint Online, no OneDrive for Business ou no Microsoft Teams. Este é o comportamento padrão do produto. Os arquivos são verificados de forma assíncrona. O processo usa eventos de compartilhamento e atividades de convidados, juntamente com heurísticas inteligentes e sinais de ameaça para identificar arquivos mal-intencionados.

- Certifique-se de que seus sites do SharePoint estão configurados para usar a [experiência moderna](/sharepoint/guide-to-sharepoint-modern-experience). A proteção do Defender para o Office 365 se aplica se a experiência moderna ou a exibição clássica é usada; no entanto, os indicadores visuais de que um arquivo está bloqueado estão disponíveis apenas na experiência moderna.

- Os Anexos Seguros para SharePoint, OneDrive e Microsoft Teams fazem parte da estratégia geral de proteção contra ameaças da sua organização, que inclui proteção anti-spam e anti-malware no Exchange Online Protection (EOP), bem como Links Seguros e Anexos Seguros no Microsoft Defender para Office 365. Para saber mais, confira [Proteger contra ameaças no Office 365](protect-against-threats.md).