---
title: Classificação do Azure Active Directory e rótulos de confidencialidade para grupos do Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: Este artigo discute a classificação clássica do Azure Active Directory e os rótulos de confidencialidade.
ms.openlocfilehash: f11473653884392048d5f9a84f8e284dba5f6f27
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755385"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Classificação do Azure Active Directory e rótulos de confidencialidade para grupos do Microsoft 365

Este artigo discute a classificação clássica do Azure Active Directory e os rótulos de confidencialidade.

Os rótulos de confidencialidade são compatíveis com [esses serviços](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels).

Para obter informações completas sobre rótulos de sensibilidade, consulte [saiba mais sobre rótulos de sensibilidade](sensitivity-labels.md).

Para saber mais sobre rótulos de confidencialidade e seus comportamentos para sites e grupos do Microsoft 365, confira [usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, microsoft 365 grupos e sites do SharePoint](sensitivity-labels-teams-groups-sites.md).

Consulte os cenários a seguir para práticas recomendadas ao migrar da classificação clássica do AAD para os rótulos de sensibilidade.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Cenário 1: o locatário nunca usou classificações clássicas do AAD ou rótulos de confidencialidade para documentos e emails

- O administrador de locatários permite rótulos de confidencialidade para grupos Configurando o sinalizador de locatário "EnableMIPLabels" como true via cmdlet do AAD PowerShell.
- O administrador de locatários cria os rótulos de confidencialidade no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com).
    - O administrador de locatários pode escolher ações relacionadas a emails e arquivos, como criptografia e marca d' água.
    - O administrador de locatários pode escolher os grupos do Microsoft 365 e as ações relacionadas a sites do SharePoint Online para os rótulos de confidencialidade.
- O administrador de locatários publica a política.
- As **cargas de trabalho compatíveis** mostram rótulos de sensibilidade. Use os rótulos de sensibilidade para criar grupos. As cargas de trabalho compatíveis são os serviços que dão suporte a rótulos de sensibilidade.
- **Cargas de trabalho não compatíveis** são os serviços que ainda não dão suporte a rótulos de confidencialidade. Os grupos podem ser criados, no entanto, eles não podem ser associados ao rótulo de confidencialidade por meio de cargas de trabalho não compatíveis. Para associar esses grupos com rótulos de confidencialidade, os administradores de locatários podem executar cmdlets do PowerShell.

Tabela 1. Comportamento de cargas de trabalho compatíveis e não compatíveis – criar, editar ou excluir grupos

|Workload|Qual lista de etiquetas o usuário vê na janela de grupo?|Criar novo grupo |Editar grupo |Excluir grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatible   |rótulos de sensibilidade. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |
|Não compatível |Nenhum rótulo de confidencialidade visível. |O usuário pode criar um grupo sem selecionar um rótulo de confidencialidade. <br><br> Observe que o administrador pode executar cmdlets para aplicar rótulos de confidencialidade no plano de fundo. |**Caso 1**: nenhum rótulo de confidencialidade selecionado anteriormente. O usuário pode editar um grupo.<br><br> **Caso 2**: rótulo de confidencialidade aplicado anteriormente em segundo plano usando o cmdlet. O usuário pode editar um grupo com êxito, excluindo o caso em que o usuário seleciona uma combinação inválida de definição de privacidade em relação ao rótulo. |Nenhuma alteração no comportamento.|

> [!NOTE]
> No caso do cliente da área de trabalho do Outlook (Win 32), após o administrador habilitar os rótulos de confidencialidade em seus locatários e o usuário está em uma versão mais antiga do cliente da área de trabalho do Outlook (Win 32):
> - O usuário vê que os rótulos de confidencialidade aparecem na versão mais antiga do cliente da área de trabalho do Outlook.
> - No entanto, quando o usuário edita um grupo e salva o grupo com um rótulo de confidencialidade, a configuração de privacidade selecionada é substituída pela configuração de privacidade do rótulo de confidencialidade aplicado.
> Recomendamos que os usuários em uma versão antiga do cliente do Outlook sejam atualizados para a versão mais recente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Cenário 2: o locatário já está usando [classificações](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization) clássicas do AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: locatário nunca usados rótulos de confidencialidade para documentos e emails

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), recomendamos criar rótulos de confidencialidade com o mesmo nome dos rótulos clássicos do Azure AD.
2. Use o cmdlet do PowerShell para aplicar esses rótulos de sensibilidade a grupos existentes do Microsoft 365 e sites do SharePoint usando o mapeamento de nome.
3. O administrador pode optar por excluir os rótulos clássicos do Azure AD:
    - As cargas de trabalho compatíveis mostram que esses rótulos de confidencialidade e grupos são criados com eles.
    - Cargas de trabalho não compatíveis funcionam ao criar grupos, mas nenhum rótulo de confidencialidade está anexado a eles.
4. Os administradores podem executar cmdlets do PowerShell para aplicar rótulos de confidencialidade nesses grupos sem rótulos.
    - Como alternativa, um administrador pode optar por manter os rótulos do Azure AD clássicos:
        - As cargas de trabalho compatíveis mostram os rótulos de confidencialidade e os grupos são criados com eles. As cargas de trabalho compatíveis são os serviços que dão suporte a rótulos de sensibilidade.
        - Cargas de trabalho não compatíveis funcionam ao criar grupos e mostrar rótulos clássicos do Azure AD. Esses rótulos clássicos do Azure AD são anexados a esses grupos criados com cargas de trabalho não compatíveis.
5. É altamente recomendável que os administradores executem cmdlets do PowerShell para aplicar rótulos de confidencialidade a esses grupos com rótulos clássicos do Azure AD.

Tabela 2. Comportamento de cargas de trabalho compatíveis e não compatíveis – criar, editar ou excluir grupos

|Workload|Qual lista de etiquetas o usuário vê na janela de grupo?|Criar novo grupo |Editar grupo |Excluir grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatible   |rótulos de sensibilidade. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |Nenhuma alteração no comportamento. |
|Não compatível |Rótulos AAD clássicos antigos. |O usuário pode criar um grupo com o rótulo clássico do Azure AD selecionado. <br><br>Observe que o administrador pode executar cmdlets para aplicar rótulos de confidencialidade no plano de fundo. |**Caso 1**: nenhum rótulo de confidencialidade selecionado anteriormente. O usuário pode editar um grupo.<br><br> **Caso 2**: rótulos do AAD clássicos previamente selecionados. O usuário pode editar um grupo.<br><br> **Caso 3**: rótulo de confidencialidade aplicado anteriormente em segundo plano usando o cmdlet. O usuário deve ser capaz de editar um grupo, excluindo um caso em que o usuário seleciona uma combinação inválida de definição de privacidade em relação ao rótulo. |O usuário pode excluir um grupo. |

> [!NOTE]
> No caso do cliente da área de trabalho do Outlook (Win 32), após o administrador habilitar os rótulos de confidencialidade em seus locatários e o usuário está em uma versão mais antiga do cliente da área de trabalho do Outlook (Win 32):
> - O usuário vê que os rótulos de confidencialidade aparecem na versão mais antiga do cliente da área de trabalho do Outlook.
> - No entanto, quando o usuário edita um grupo e salva o grupo com um rótulo de confidencialidade, a configuração de privacidade selecionada é substituída pela configuração de privacidade do rótulo de confidencialidade aplicado.
> Recomendamos que os usuários em uma versão antiga do cliente do Outlook sejam atualizados para a versão mais recente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: locatários usados rótulos de confidencialidade para documentos e emails

1. Assim que o administrador habilitar o recurso de rótulo de confidencialidade no locatário, configurando o sinalizador de locatário ' EnableMIPLabels ' como true, os rótulos de confidencialidade de documentos e de email nas caixas de diálogo de criação e edição de grupo/site/equipe serão exibidos.
2. Um administrador pode usar o mesmo documento e os rótulos de confidencialidade de email para impor privacidade e acesso de usuário externo ao grupo/site/equipe especificando as configurações de grupo relacionadas:
    1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), selecione a guia **sites e grupos** .
    2. Editar um rótulo de confidencialidade de email ou documento.

## <a name="sample-script"></a>Amostra de script

Para que um script de exemplo migre grupos com rótulos do AAD clássicos para rótulos de confidencialidade, confira [classificação clássica de grupos do Azure ad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

