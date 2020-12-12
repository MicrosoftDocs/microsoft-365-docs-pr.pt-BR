---
title: Documentos Seguros no Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre documentos seguros no Microsoft 365 E5 ou Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659868"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos Seguros no Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Documentos seguros é um recurso no Microsoft 365 E5 ou no Microsoft 365 E5 segurança que usa [o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para verificar documentos e arquivos abertos no [modo de exibição protegido](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Os documentos seguros só estão disponíveis para usuários com licenças de segurança *do microsoft 365 E5* ou *Microsoft 365 E5* . Essas licenças não estão incluídas nos planos do Microsoft defender for Office 365.

- Os documentos seguros têm suporte no Microsoft 365 Apps for Enterprise (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com>. Para ir diretamente para a página de **anexos seguros de ATP** , abra <https://protection.office.com/safeattachmentv2> .

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para definir as configurações de documentos seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .
  - Para acesso somente leitura a configurações de documentos seguros, você precisa ser membro dos grupos de função **leitor global** ou **leitor de segurança** .

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

### <a name="how-does-microsoft-handle-your-data"></a>Como a Microsoft lida com seus dados?

Para mantê-lo protegido, os documentos seguros enviam arquivos para a nuvem do [Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para análise. Detalhes sobre como o Microsoft defender para ponto de extremidade lida com seus dados pode ser encontrado aqui: [Microsoft defender para armazenamento de dados do ponto de extremidade e privacidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Arquivos enviados por documentos seguros não são mantidos no defender além do tempo necessário para análise (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar o centro de conformidade de & de segurança para configurar documentos seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \>  \> e **anexos seguros de ATP** e clique em **configurações globais**.

2. Na saída **das configurações globais** exibida, defina as seguintes configurações:

   - **Ativar documentos seguros para clientes do Office**: mover o botão de alternância para o direito para ativar o recurso: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Permitir que as pessoas cliquem através do modo de exibição protegido, mesmo se os documentos seguros identificarem o arquivo como mal-intencionado**: Recomendamos que você deixe esta opção desativada (Mantenha a alternação para a esquerda: ![ desativar ](../../media/scc-toggle-off.png) ).

   Quando concluir, clique em **Salvar**.

   ![Configurações de documentos seguros depois de selecionar as configurações globais na página de anexos seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar o PowerShell do Exchange Online para configurar documentos seguros

Use a seguinte sintaxe:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- O parâmetro _EnableSafeDocs_ habilita ou desabilita documentos seguros para toda a organização.
- O parâmetro _AllowSafeDocsOpen_ permite ou impede que os usuários saiam do modo de exibição protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.

Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abram documentos identificados como mal-intencionados no modo de exibição protegido.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitou e configurou documentos seguros, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \>  \> de **anexos seguros de ATP**, clique em **configurações globais** e verifique o **Ativar documentos seguros para clientes do Office** e **permitir que as pessoas cliquem através do modo de exibição protegido, mesmo se os documentos seguros identificam o arquivo como configurações mal-intencionadas** .

- Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Os arquivos a seguir estão disponíveis para testar a proteção de documentos seguros. Estes documentos são semelhantes aos EICAR.TXT arquivo para testar soluções antimalware e antivírus. Os arquivos não são prejudiciais, mas eles disparam a proteção de documentos seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
