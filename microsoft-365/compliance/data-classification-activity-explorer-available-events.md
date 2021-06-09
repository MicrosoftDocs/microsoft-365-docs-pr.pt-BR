---
title: Rotular ações relatadas no gerenciador de Atividades
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: listagem de atividades de rotulagem que estão disponíveis no explorador de atividades.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532249"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Atividades de rotulagem que estão disponíveis no Explorador de Atividades

## <a name="sensitivity-label-applied"></a>Rótulo de sensibilidade aplicado

Esse evento é gerado sempre que um documento não rotulado é rotulado ou um email é enviado com um rótulo de sensibilidade. 

- Ele é capturado no momento da salvação em aplicativos Office nativos e aplicativos Web. 
- Ele é capturado no momento da ocorrência nos complementos da Proteção de Informações do Azure. 
- As ações de rótulos de atualização e downgrade também podem ser monitoradas por meio do *campo de* tipo de evento Label e filtro.   


|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------|
| Word, Excel, PowerPoint|sim |
|Outlook| sim |do Win 32 |
|SharePoint online, OneDrive|sim | |
|Exchange        |sim         | |
|Cliente unificado da Proteção de Informações do Azure (AIP) e scanner unificado do AIP |sim |a ação de *novo rótulo* da AIP é mapeada para o rótulo *aplicado no* explorador de atividades   |
|Microsoft information protection (MIP) SDK         |sim|a ação de *novo rótulo* da AIP é mapeada para o rótulo *aplicado no* explorador de atividades|
|Serviço de Gerenciamento de Direitos (RMS)         |não se aplica         | |
|Power BI desktop e web        | não| acessíveis nos logs Microsoft 365 de auditoria         |
|MCAS (Microsoft Cloud App Security)         |não|         |

## <a name="sensitivity-label-changed"></a>Rótulo de sensibilidade alterado

Esse evento é gerado sempre que um rótulo de sensibilidade é atualizado no documento ou no email.

- Para as fontes de SDK do AIP Unified Client, Unified Scanner e MIP, o rótulo de atualização do *AIP* e a ação de rótulo de *downgrade* são mapeados para o rótulo do explorador de *atividades alterado*

- Ele é capturado no ponto de salvar em aplicativos Office nativos e aplicativos Web. 
- Ele é capturado no momento da ocorrência em Azure Information protection unified client add-ins and scanner enforcements
- As ações de rótulos de atualização e downgrade também podem ser monitoradas por meio do *campo de* tipo de evento Label e filtro. O *texto de* justificativa também é capturado, exceto SharePoint Online e OneDrive.
- A rotulagem de confidencialidade feita Office aplicativos nativos no Outlook coleta a última ação gerada antes das ações de envio/envio de email de arquivo. Por exemplo, se o usuário mudar o rótulo em um email várias vezes antes de enviar, o último rótulo encontrado no email quando ele é enviado será capturado no log de auditoria e, em seguida, relatado no explorador de atividades. 


|Source  |Relatado no explorador de atividades|Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sim         |
|Outlook         |sim         |Ganhar 32|
|SharePoint Online, OneDrive         |sim         |
|Exchange         |sim         |
|Cliente unificado AIP         |sim         |
|Scanner unificado AIP         |sim         |
|MIP SDK         |sim         |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não         |acessíveis nos logs Microsoft 365 de auditoria |
|MCAS     |não         |         |

## <a name="sensitivity-label-removed"></a>Rótulo de sensibilidade removido

Esse evento é gerado sempre que um rótulo de confidencialidade é removido de um arquivo ou documento.

- Esse evento é capturado no momento da salvação em Office aplicativos web e aplicativos web nativos.
- Ele é capturado no momento da ocorrência nos complementos da Proteção de Informações do Azure. 
- A rotulagem de confidencialidade, com Office rótulo MIP nativo, no Outlook coleta o último evento de rotulagem que foi gerado antes das ações de envio de arquivo/envio de email.

|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sim         |
|Outlook         |sim         |Ganhar 32|
|SharePoint Online, OneDrive         |sim         |
|Exchange         |sim         |
|Cliente unificado AIP         |sim         |a ação remover *rótulo* do AIP é mapeada para a *ação removida do rótulo* no explorador de atividades|
|Scanner unificado AIP         |sim         |a ação remover *rótulo* do AIP é mapeada para a *ação removida do rótulo* no explorador de atividades |
|MIP SDK         |sim         |a ação remover *rótulo* do AIP é mapeada para a *ação removida do rótulo* no explorador de atividades |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não         |acessíveis nos logs Microsoft 365 de auditoria |
|MCAS     |não         |         |
 

## <a name="sensitivity-label-file-read"></a>Leitura de arquivo de rótulo de confidencialidade

Esse evento é gerado sempre que um documento rotulado ou protegido é aberto.

|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sim         |
|Outlook         |não         |
|SharePoint Online, OneDrive         |não         |
|Exchange         |não         |
|Cliente unificado AIP         |sim         |a ação de *acesso AIP* é mapeada para a ação de leitura *de* arquivo no explorador de atividades|
|Scanner unificado AIP         |sim         |a ação de *acesso AIP* é mapeada para a ação de leitura *de* arquivo no explorador de atividades|
|MIP SDK         |sim         |a ação de *acesso AIP* é mapeada para a ação de leitura *de* arquivo no explorador de atividades|
|Serviço RMS         |sim         |a *ação de* acesso é mapeada para a ação de leitura *de* arquivo no explorador de atividades |
|Power BI desktop e Web         |não         |acessíveis nos logs Microsoft 365 de auditoria |
|MCAS     |não         |         |


## <a name="files-discovered"></a>Arquivos descobertos

Esse evento é gerado sempre que os arquivos são descobertos quando o Scanner AIP é usado para a verificação de dados confidenciais em vários locais e localiza arquivos.

|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |não se aplica         |
|Outlook         |não se aplica         |
|SharePoint Online, OneDrive         |não se aplica         |
|Exchange         |não se aplica         |
|Cliente unificado AIP         |não se aplica       |
|Scanner unificado AIP         |sim         |a ação *descoberta* do AIP é mapeada para os *arquivos descobertos ação* no explorador de atividades|
|MIP SDK         |sim         |a ação *descoberta* do AIP é mapeada para a ação *descoberta de arquivo* no explorador de atividades|
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não se aplica         |
|MCAS     |não se aplica         |         |


## <a name="sensitivity-label-file-renamed"></a>Arquivo de rótulo de confidencialidade renomeado

Esse evento é gerado sempre que um documento com um rótulo de sensibilidade é renomeado. 

|Source  | Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sim         |
|Outlook         |não se aplica         |
|SharePoint Online, OneDrive         |não        |
|Exchange         |não se aplica         |
|Cliente unificado AIP         |não         |
|Scanner unificado AIP         |não         |
|MIP SDK         |não         |
|Serviço RMS         |não      |
|Power BI desktop e Web         |não         |
|MCAS     |não         |         |


## <a name="file-removed"></a>Arquivo removido

Esse evento é gerado sempre que o verificador AIP detecta que um arquivo verificado anteriormente foi removido.

|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |não se aplica         |
|Outlook         |não se aplica         |
|SharePoint Online, OneDrive         |não se aplica           |
|Exchange         |não se aplica         |
|Cliente unificado AIP         |não se aplica            |
|Scanner unificado AIP         |sim         |
|MIP SDK         |não se aplica            |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não se aplica  |
|MCAS     |não se aplica        |         |

### <a name="protection-applied"></a>Proteção aplicada

Esse evento é gerado, a proteção de primeira vez é adicionada manualmente a um item que não tem um rótulo.

|Source  |Relatado no explorador de atividades | Observação  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |não         |
|Outlook         |não         |
|SharePoint Online, OneDrive         |não se aplica           |
|Exchange         |não       |
|Cliente unificado AIP         |sim            |
|Scanner unificado AIP         |não se aplica         |
|MIP SDK         |sim            |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não se aplica            |
|MCAS     |não se aplica        |         |

## <a name="protection-changed"></a>Proteção alterada

Esse evento é gerado sempre que a proteção em um documento não rotulado é alterada manualmente.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Word, Excel, PowerPoint         |não         |
|Outlook         |não         |
|SharePoint Online, OneDrive         |não se aplica           |
|Exchange         |não       |
|Cliente unificado AIP         |sim            |
|Scanner unificado AIP         |não se aplica         |
|MIP SDK         |sim            |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não se aplica            |
|MCAS     |não se aplica        |

## <a name="protection-removed"></a>Proteção removida

Esse evento é gerado sempre que a proteção em um documento não rotulado é alterada manualmente.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Word, Excel, PowerPoint         |não         |
|Outlook         |não         |
|SharePoint Online, OneDrive         |não se aplica           |
|Exchange         |não       |
|Cliente unificado AIP         |sim            |
|Scanner unificado AIP         |não se aplica         |
|MIP SDK         |sim            |
|Serviço RMS         |não se aplica         |
|Power BI desktop e Web         |não se aplica            |
|MCAS     |não se aplica        |

## <a name="dlp-policy-matched"></a>Política de DLP corresponder

Esse evento é gerado sempre que uma política de DLP é corresponder a um documento ou a um email.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Exchange         |sim       |
|SharePoint Online|sim          |
|OneDrive |sim|
|Teams |sim   |
|Dispositivos Windows 10         |sim |
|MAC         |não     |
|local         |não|
|MCAS     |não        | 

Os eventos para dispositivos Windows 10 (DLP do ponto de extremidade) são:

- arquivo excluído
- arquivo criado
- O arquivo foi copiado para a área de transferência
- arquivo modificado
- leitura de arquivo
- arquivo impresso
- arquivo renomeado
- arquivo copiado para compartilhamento de rede
- arquivo acessado por aplicativo não alotado


## <a name="retention-label-applied"></a>Rótulo de retenção aplicado 

Esse evento é gerado sempre que um documento não rotulado é rotulado ou um email é enviado com um rótulo de retenção.

- Ele é capturado no momento da salvação de um documento e no momento do envio de um email.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Exchange         |não       |
|SharePoint Online|sim          |
|OneDrive |sim|

## <a name="retention-label-changed"></a>Rótulo de retenção alterado

Esse evento é gerado sempre que um rótulo é atualizado em um documento ou email.

- Ele é capturado no momento da salvação de um documento e no momento do envio de um email.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Exchange         |não       |
|SharePoint Online|sim          |
|OneDrive |sim|
 
## <a name="retention-label-removed"></a>Rótulo de retenção removido

Esse evento é gerado sempre que um rótulo é removido de um arquivo ou documento.

- Ele é capturado no momento da salvação de um documento e no momento do envio de um email.

|Source  |Relatado no explorador de atividades |
|---------|---------| 
|Exchange         |não       |
|SharePoint Online|sim          |
|OneDrive |sim|


## <a name="known-issues"></a>Problemas conhecidos
  
- Quando a dica de ferramenta de rótulo recomendada é mostrada para um usuário final, ela não é capturada. Mas se o usuário optar por aplicar o rótulo recomendado, o rótulo será mostrado no campo Como *aplicado* como *recomendado*  

- O texto de justificativa não está disponível no momento em downgrade de rótulo de sensibilidade do Sharepoint e OneDrive.  

- No momento, os tipos de informações confidenciais não estão disponíveis para atividades de auto-rótulo do Word, Excel, PowerPoint e Outlook, bem como SharePoint Online e OneDrive.
