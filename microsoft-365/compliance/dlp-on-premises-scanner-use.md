---
title: Use o verificador local de prevenção contra perda de dados do Microsoft 365 (pré-visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Aprenda a usar o verificador local de prevenção contra perda de dados do  Microsoft 365 para examinar dados inativos e implementar ações de proteção para compartilhamentos de arquivos locais e pastas e bibliotecas de documentos locais do SharePoint.
ms.openlocfilehash: c46b67ca392732616329bad138166c892cd06640
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917817"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Use o verificador local de prevenção contra perda de dados do Microsoft 365 (pré-visualização)

Para ajudar a se familiarizar com os recursos locais do DLP e como eles aparecem nas políticas DLP, reunimos alguns cenários para você seguir.

> [!IMPORTANT]
> Esses cenários locais de DLP não são os procedimentos oficiais para criar e ajustar políticas DLP. Confira os tópicos a seguir quando você precisar trabalhar com políticas de DLP em situações gerais:
>- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
>- [Introdução à política DLP padrão](get-started-with-the-default-dlp-policy.md)
>- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
>- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Cenário: descobra arquivos que correspondem às regras de DLP

Dados de superfícies de verificação local DLP em várias áreas

#### <a name="activity-explorer"></a>Explorador de atividade 

 O DLP local da Microsoft detecta correspondências de regras de DLP e as relata ao [Explorador de Atividade](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer). 
 
#### <a name="microsoft-365-audit-log"></a>Log de auditoria do Microsoft 365

Durante a visualização pública, as correspondências de regras de DLP estão disponíveis na UI, consulte [Pesquisar o log de auditoria no centro de conformidade](search-the-audit-log-in-security-and-compliance.md)  ou acessíveis por [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) Windows PowerShell.

#### <a name="aip"></a>AIP

Os dados de descoberta estão disponíveis em um relatório local no formato csv, que é armazenado em:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Procure as seguintes colunas:
- Modo DLP
- Status DLP
- Comentário DLP
- Nome da regra DLP Ações DLP
- Proprietário
- Permissões NTFS atuais (SDDL)
- Permissões NTFS aplicadas (SDDL)
- Tipo de permissões NTFS
 
### <a name="scenario-enforce-dlp-rule"></a>Cenário: impor regra DLP 

Se você deseja impor regras DLP nos arquivos verificados, a imposição deve ser habilitada tanto no trabalho de verificação de conteúdo no AIP e no nível de política no DLP.


#### <a name="configure-dlp-to-enforce-policy-actions"></a>Configure o DLP para impor ações de política

1. Abra a [página de prevenção contra perda de dadose](https://compliance.microsoft.com/datalossprevention?viewid=policies) e selecione a política DLP que é direcionada aos repositórios locais que você configurou no AIP. 
2. Edite a política.
3. Na página **Testar ou ativar a política**, selecione **Sim, ativá-la imediatamente**. 

## <a name="see-also"></a>Confira também

- [Saiba mais sobre o verificador local DLP (visualização)](dlp-on-premises-scanner-learn.md)
- [Começar com a verificação DLP local (visualização)](dlp-on-premises-scanner-get-started.md)
- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)