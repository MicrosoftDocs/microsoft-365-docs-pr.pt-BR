---
title: Documentos seguros no Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre documentos seguros no Office 365 ATP.
ms.openlocfilehash: 3980746eb2f48e77c22f5139827bead5640dad61
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170471"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Documentos seguros no Office 365 proteção avançada contra ameaças

Documentos seguros é um recurso da proteção avançada contra ameaças do Office 365 (ATP) que usa a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para verificar documentos e arquivos abertos no [modo de exibição protegido](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Este recurso está disponível apenas para usuários com a licença de segurança do Microsoft 365 E5 ou Microsoft 365 e5.

- No momento, documentos seguros estão disponíveis para visualização pública, disponível para os usuários que fazem parte do [programa Office Insider](https://insider.office.com/en-us/join) no ' canal mensal (direcionado) ' com o office versão 2002 (12527,20092) ou superior. Esse recurso está desativado por padrão e deverá ser habilitado pelo administrador de segurança.

- No momento, apenas a região americana tem suporte para processamento de arquivos em conformidade (todos os arquivos viajarão para a região dos EUA para verificação). O suporte para região UK/UE é planejado em uma atualização futura.

- Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões para poder executar os procedimentos deste tópico. Para habilitar e configurar documentos seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** . Para obter mais informações sobre grupos de função no centro de conformidade & segurança, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Usar o centro de conformidade & segurança do Office 365 para configurar documentos seguros

1. Abra o centro de conformidade & segurança do Office <https://protection.office.com>365 em.

2. Vá para **** \> **política** \> de gerenciamento de ameaças **anexos seguros de ATP**.

3. Na seção **ajudar as pessoas a permanecerem seguras ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** , configure qualquer uma das seguintes configurações:

   - **Ative documentos seguros para clientes do Office (os arquivos também serão enviados para a nuvem da Microsoft para análises profundas)**

   - **Permitir que as pessoas cliquem no modo de exibição protegido, mesmo se os documentos seguros identificam o arquivo como mal-intencionado**: Recomendamos que você não habilite essa opção.

4. Quando concluir, clique em **Salvar**.

![Página de anexos seguros de ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Usar o PowerShell do Exchange Online ou do Exchange Online Protection para configurar documentos seguros

Use a seguinte sintaxe:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- O parâmetro _EnableSafeDocs_ habilita ou desabilita documentos seguros para toda a organização.

- O parâmetro _AllowSafeDocsOpen_ permite ou impede que os usuários saiam do modo de exibição protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.

Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abram documentos identificados como mal-intencionados no modo de exibição protegido.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitou e configurou documentos seguros, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para a **política** \> de **Gerenciamento** \> de ameaças de **anexos seguros de ATP**e verifique as seleções na seção **ajuda para manter a segurança ao confiar em um arquivo para abrir fora do modo de exibição protegido em aplicativos do Office** .

- Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
