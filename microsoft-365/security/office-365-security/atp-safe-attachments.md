---
title: Anexos Seguros da ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre o recurso de anexos seguros de ATP para o Office 365 e como obter o recurso para sua assinatura.
ms.openlocfilehash: e6cbd5cb494e765bdb849da93114ea4168ab3c93
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034847"
---
# <a name="atp-safe-attachments"></a>Anexos Seguros da ATP

## <a name="overview-of-office-365-atp-safe-attachments"></a>Visão geral dos anexos seguros de ATP do Office 365

Os anexos seguros de ATP (juntamente com [links seguros de ATP](atp-safe-links.md)) fazem parte da [proteção avançada contra ameaças](office-365-atp.md) (atp) do Office 365. O recurso de anexos seguros de ATP verifica se os anexos de email são mal-intencionados e, em seguida, executa a ação de proteger sua organização. O recurso de anexos seguros de ATP protege sua organização de acordo com [as políticas de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md) definidas por seus administradores globais ou de segurança.

A proteção ATP também pode ser estendida para arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams. Para saber mais, confira [Office 365 Advanced Threat Protection for SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Como obter anexos seguros de ATP

Primeiro, certifique-se de que sua assinatura inclua [proteção avançada contra ameaças](office-365-atp.md). A ATP está incluída em inscrições, como [o microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [o Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), o Office 365 e5, o Office 365 a5, etc. Se sua organização tiver uma assinatura do Microsoft 365 que não inclua o Office 365 ATP, você poderá comprar ATP como um complemento. Confira mais informações em [planos e preços avançados de proteção contra ameaças do office 365](https://products.office.com/exchange/advance-threat-protection) e a [Descrição do serviço de proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Em seguida, verifique se as políticas de anexos seguros de ATP estão definidas. (Consulte [Configurar políticas de anexos seguros de ATP do Office 365](set-up-atp-safe-attachments-policies.md)) Os recursos de anexos seguros de ATP estão ativos quando:

- As políticas de anexos seguros de ATP estão configuradas. (Confira [Configurar políticas de anexos seguros de ATP no Office 365](set-up-atp-safe-attachments-policies.md).)

- Os usuários entraram usando sua conta corporativa ou de estudante. (Consulte [entrar no Office ou no office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída. Alguns exemplos são descritos na tabela a seguir:

|Role|Onde/como a atribuição|
|---------|---------|
|administrador global|Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global. (Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)|
|Administrador de Segurança|Centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()|
|Gerenciamento de Organização do Exchange Online|Centro de administração do[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Como saber se a proteção de anexos seguros de ATP está em vigor

Após [definir (ou revisar) suas políticas de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md), uma boa maneira de ver como o serviço está funcionando é [exibindo relatórios para proteção avançada contra ameaças](view-reports-for-atp.md).

A tabela a seguir descreve alguns exemplos de cenários. Em todos esses casos, assumimos que a organização tem uma assinatura do Microsoft 365 que inclui proteção avançada contra ameaças.

|**Cenário de exemplo**|**A proteção de anexos seguros ATP se aplica nesse caso?**|
|:-----|:-----|
|A organização do Luigi tem o Office 365 e5, mas nenhuma política de anexos seguros de ATP ainda foi definida.|Não. Embora o recurso esteja disponível, pelo menos uma política de anexos seguros de ATP deve ser definida para que a proteção de anexos seguros de ATP esteja em vigor.|
|Lee é um funcionário no departamento de vendas da contoso. A organização de Lee tem uma política de anexos seguros de ATP em vigor que se aplica apenas aos funcionários de finanças.|Não. Nesse caso, os funcionários de finanças teriam proteção de anexos seguros de ATP, mas outros funcionários, incluindo o departamento de vendas, não até as políticas que incluem esses grupos são definidas.|
|Ontem, um administrador na organização de Jean configurou uma política de anexos seguros de ATP que se aplica a todos os funcionários. Hoje em dia, Jean recebeu uma mensagem de email que inclui um anexo.|Sim. Neste exemplo, Jean tem uma licença para proteção avançada contra ameaças e uma política de anexos seguros de ATP que inclui Jean foi definida. Geralmente, leva cerca de 30 minutos para uma nova política entrar em vigor nos data centers; como um dia passou nesse caso, a política deve estar em vigor.|
|A organização de Carla tem o Office 365 E5 com políticas de anexos seguros de ATP in-loco para todos na organização. Chris recebe um email que tem um anexo e encaminha a mensagem para outras pessoas que estão fora da organização.|A proteção de anexos seguros de ATP está em vigor para mensagens que Carla receber. Se as organizações dos destinatários também tiverem diretivas de anexos seguros de ATP em vigor, a mensagem informando que Carla estaria sujeita às políticas quando a mensagem encaminhada chegar.|
|A organização de Jaime tem políticas de anexos seguros de ATP no local e [a ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) foi ativada. Jaime supõe que cada arquivo no SharePoint Online foi verificado e é seguro para ser aberto ou baixado.|A proteção de anexos seguros de ATP está no local de acordo com as políticas definidas; no entanto, isso não significa que cada arquivo único no SharePoint Online, no OneDrive for Business ou no Microsoft Teams seja verificado. (Para saber mais, confira [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).)|

## <a name="submitting-files-for-malware-analysis"></a>Enviando arquivos para análise de malware

- Se você receber um arquivo que deseja solicitar à Microsoft para analisar, visite [enviar um arquivo para análise de malware](https://aka.ms/wdsi/submit).

- Se você receber uma mensagem de email (com ou sem um anexo) que deseja enviar para a Microsoft para análise, confira [mensagens de relatório e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).
