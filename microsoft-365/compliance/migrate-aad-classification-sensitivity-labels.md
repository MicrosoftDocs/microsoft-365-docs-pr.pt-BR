---
title: Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: Este artigo discute rótulos clássicos de classificação e sensibilidade do Azure Active Directory.
ms.openlocfilehash: 1be7e31ee4091e561f7eedb34b41958efc69a339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926329"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365

Este artigo discute rótulos clássicos de classificação e sensibilidade do Azure Active Directory.

Os rótulos de sensibilidade são suportados [por esses serviços.](./sensitivity-labels-teams-groups-sites.md#support-for-the-sensitivity-labels)

Para obter informações completas sobre rótulos de sensibilidade, [consulte Saiba mais sobre rótulos de sensibilidade.](sensitivity-labels.md)

Para saber mais sobre rótulos de sensibilidade e seu comportamento para sites e grupos do Microsoft 365, consulte Usar rótulos de sensibilidade para proteger conteúdo no Microsoft Teams, grupos do [Microsoft 365 e sites do SharePoint.](sensitivity-labels-teams-groups-sites.md)

Consulte os seguintes cenários para práticas recomendadas ao migrar da classificação clássica do AAD para os rótulos de sensibilidade.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Cenário 1: o locatário nunca usou classificações clássicas do AAD ou rótulos de sensibilidade para documentos e emails

- O Administrador de Locatários habilita rótulos de sensibilidade para grupos definindo o sinalizador de locatário "EnableMIPLabels" como true por meio do cmdlet powershell do AAD.
- O Administrador de Locatários cria os rótulos de sensibilidade no centro de [conformidade do Microsoft 365.](https://compliance.microsoft.com)
    - O administrador do locatário pode escolher ações relacionadas a arquivos e emails, como criptografia e marca d'água.
    - O administrador de locatários pode escolher grupos do Microsoft 365 e ações relacionadas ao site do SharePoint Online aos rótulos de sensibilidade.
- O Administrador de Locatários publica a política.
- **Cargas de trabalho compatíveis** mostram rótulos de sensibilidade. Use os rótulos de sensibilidade para criar grupos. Cargas de trabalho compatíveis são os serviços que suportam rótulos de sensibilidade.
- **Cargas de trabalho não compatíveis** são os serviços que ainda não suportam rótulos de sensibilidade. Os grupos podem ser criados, no entanto, eles não podem ser associados ao rótulo de sensibilidade por meio de cargas de trabalho não compatíveis. Para associar esses grupos a rótulos de sensibilidade, os administradores de locatários podem executar cmdlets do PowerShell.

Tabela 1. Comportamento de cargas de trabalho compatíveis e não compatíveis – criar, editar ou excluir grupos

|Workload|Qual lista de rótulos o usuário vê na janela de grupo?|Criar novo grupo |Editar grupo |Excluir grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatível   |rótulos de sensibilidade. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |
|Não compatível |Sem rótulos de sensibilidade visíveis. |O usuário pode criar um grupo sem selecionar o rótulo de sensibilidade. <br><br> Observação: o administrador pode executar cmdlets para aplicar rótulos de sensibilidade em segundo plano. |**Caso 1**: Nenhum rótulo de sensibilidade selecionado anteriormente. O usuário pode editar um grupo.<br><br> **Caso 2**: rótulo de sensibilidade aplicado anteriormente em segundo plano usando cmdlet. O usuário pode editar um grupo com êxito, excluindo o caso em que o usuário seleciona uma combinação inválida de configuração de privacidade em relação ao rótulo. |Nenhuma alteração no comportamento.|

> [!NOTE]
> No caso do cliente da área de trabalho do Outlook (Win 32), depois que o administrador habilita rótulos de sensibilidade em seu locatário e seu usuário está em uma versão mais antiga do cliente de área de trabalho do Outlook (Win 32):
>
> - O usuário vê rótulos de sensibilidade aparecerem na versão mais antiga do cliente da área de trabalho do Outlook.
> - No entanto, quando o usuário edita um grupo e salva o grupo com um rótulo de sensibilidade, a configuração de privacidade selecionada é substituído pela configuração de privacidade do rótulo de sensibilidade aplicado.
>
> Recomendamos que os usuários em uma versão antiga do cliente do Outlook atualizando para a versão mais recente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Cenário 2: o locatário já está usando classificações [clássicas do](../enterprise/manage-microsoft-365-groups-with-powershell.md) AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: o locatário nunca usou rótulos de sensibilidade para documentos e emails

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)recomendamos criar rótulos de sensibilidade com o mesmo nome que os rótulos clássicos do Azure AD existentes.
2. Use o cmdlet do PowerShell para aplicar esses rótulos de sensibilidade a grupos existentes do Microsoft 365 e sites do SharePoint usando mapeamento de nomes.
3. O administrador pode optar por excluir os rótulos clássicos do Azure AD:
    - Cargas de trabalho compatíveis mostram que esses rótulos e grupos de sensibilidade são criados com eles.
    - Cargas de trabalho não compatíveis funcionam ao criar grupos, mas nenhum rótulo de sensibilidade é anexado a eles.
4. Os administradores podem executar cmdlets do PowerShell para aplicar rótulos de sensibilidade a esses grupos sem rótulos.
    - Como alternativa, um administrador pode optar por manter os rótulos clássicos do Azure AD:
        - Cargas de trabalho compatíveis mostram esses rótulos de sensibilidade e grupos são criados com eles. Cargas de trabalho compatíveis são os serviços que suportam rótulos de sensibilidade.
        - Cargas de trabalho não compatíveis funcionam ao criar grupos e mostram rótulos clássicos do Azure AD. Esses rótulos clássicos do Azure AD são anexados a esses grupos criados com cargas de trabalho não compatíveis.
5. É altamente recomendável que os administradores executem cmdlets do PowerShell para aplicar rótulos de sensibilidade a esses grupos com rótulos clássicos do Azure AD.

Tabela 2. Comportamento de cargas de trabalho compatíveis e não compatíveis – criar, editar ou excluir grupos

|Workload|Qual lista de rótulos o usuário vê na janela de grupo?|Criar novo grupo |Editar grupo |Excluir grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatível   |rótulos de sensibilidade. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |
|Não compatível |Rótulos antigos do AAD clássico. |O usuário pode criar um grupo com o rótulo clássico do Azure AD selecionado. <br><br>Observação: o administrador pode executar cmdlets para aplicar rótulos de sensibilidade em segundo plano. |**Caso 1**: Nenhum rótulo de sensibilidade selecionado anteriormente. O usuário pode editar um grupo.<br><br> **Caso 2**: rótulos AAD clássicos selecionados anteriormente. O usuário pode editar um grupo.<br><br> **Caso 3**: rótulo de sensibilidade aplicado anteriormente em segundo plano usando cmdlet. O usuário deve ser capaz de editar um grupo, excluindo um caso em que o usuário selecione uma combinação inválida de configuração de privacidade em relação ao rótulo. |O usuário pode excluir um grupo. |

> [!NOTE]
> No caso do cliente da área de trabalho do Outlook (Win 32), depois que o administrador habilita rótulos de sensibilidade em seu locatário e seu usuário está em uma versão mais antiga do cliente de área de trabalho do Outlook (Win 32):
>
> - O usuário vê rótulos de sensibilidade aparecerem na versão mais antiga do cliente da área de trabalho do Outlook.
> - No entanto, quando o usuário edita um grupo e salva o grupo com um rótulo de sensibilidade, a configuração de privacidade selecionada é substituído pela configuração de privacidade do rótulo de sensibilidade aplicado.
>
> Recomendamos que os usuários em uma versão antiga do cliente do Outlook atualizando para a versão mais recente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: Locatário usou rótulos de sensibilidade para documentos e emails

1. Assim que o administrador habilita o recurso de rótulo de sensibilidade no locatário definindo o sinalizador de locatário "EnableMIPLabels" como true, os rótulos de sensibilidade de documento e email nas caixas de diálogo group/site/team criam e editam.
2. Um administrador pode usar os mesmos rótulos de identidade de documento e email para impor privacidade e acesso de usuário externo ao grupo/site/equipe especificando configurações de grupo relacionadas:
    1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)selecione a **guia Sites e Grupos.**
    2. Edite um documento ou rótulo de sensibilidade de email.

## <a name="sample-script"></a>Amostra de script

Para um script de exemplo migrar grupos com rótulos clássicos do AAD para rótulos de sensibilidade, consulte Classificação de grupo clássica [do Azure AD](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification).