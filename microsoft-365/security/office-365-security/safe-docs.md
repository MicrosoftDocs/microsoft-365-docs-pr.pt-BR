---
title: Documentos Seguros no Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba mais sobre Documentos Seguros no Microsoft 365 E5 ou No Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f67dd21c4cea62012af4713bceddc2eebae33c7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908801"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos Seguros no Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Documentos Seguros é um recurso no Microsoft 365 E5 ou no Microsoft 365 E5 Security que usa o [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade para examinar documentos e arquivos abertos no [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Documentos Seguros está disponível apenas para usuários com licenças de Segurança do *Microsoft 365 E5* ou *Microsoft 365 E5.* Essas licenças não estão incluídas nos planos do Microsoft Defender para Office 365.

- Os Documentos Seguros são suportados no Microsoft 365 Apps for enterprise (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com>. Para ir diretamente para a página Anexos Seguros **da ATP,** abra <https://protection.office.com/safeattachmentv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:
  - Para definir as configurações de Documentos Seguros, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança.
  - Para acessar somente leitura às configurações documentos seguros, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

### <a name="how-does-microsoft-handle-your-data"></a>Como a Microsoft lida com seus dados?

Para mantê-lo protegido, Documentos Seguros envia arquivos para a [nuvem do Microsoft Defender para Ponto de](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Extremidade para análise. Detalhes sobre como o Microsoft Defender for Endpoint lida com seus dados podem ser encontrados aqui: Microsoft Defender para armazenamento de dados do Ponto de Extremidade [e privacidade.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Os arquivos enviados por Documentos Seguros não são mantidos no Defender além do tempo necessário para análise (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar o Centro de Conformidade & segurança para configurar Documentos Seguros

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças Anexos Seguros \>  \> **atp** e clique em **Configurações globais**.

2. Nas **configurações globais** que aparecem, configure as seguintes configurações:

   - **Ativar Documentos Seguros para clientes do Office:** mova a alternância para a direita para ativar o recurso: ![ Ativar a alternância ](../../media/scc-toggle-on.png) .

   - **Permitir que as** pessoas cliquem em Exibição Protegida, mesmo que Documentos Seguros identifiquem o arquivo como mal-intencionado : recomendamos que você deixe essa opção desligada (deixe a alternância para a esquerda: ![ Alternar para fora ](../../media/scc-toggle-off.png) ).

   Quando concluir, clique em **Salvar**.

   ![Configurações de Documentos Seguros depois de selecionar configurações globais na página Anexos Seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar o PowerShell do Exchange Online para configurar Documentos Seguros

Use a seguinte sintaxe:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- O _parâmetro EnableSafeDocs_ habilita ou desabilita Documentos Seguros para toda a organização.
- O _parâmetro AllowSafeDocsOpen_ permite ou impede que os usuários deixe o Protected View (ou seja, abrindo o documento) se o documento tiver sido identificado como mal-intencionado.

Este exemplo habilita Documentos Seguros para toda a organização e impede que os usuários abriam documentos identificados como mal-intencionados do Modo de Exibição Protegido.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar e configurar Documentos Seguros, faça qualquer uma das seguintes etapas:

- No Centro de Conformidade de Segurança  &, vá para Política de Gerenciamento de Ameaças \>  \> **Atp Anexos**   Seguros , clique em Configurações Globais e verifique a Opção Ativar Documentos Seguros para clientes do **Office** e Permitir que as pessoas cliquem em Exibir Protegido mesmo que Documentos Seguros identifiquem o arquivo como configurações mal-intencionadas.

- Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores da propriedade:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Os arquivos a seguir estão disponíveis para testar a proteção documentos seguros. Esses documentos são semelhantes ao arquivo EICAR.TXT para testar soluções anti-malware e antivírus. Os arquivos não são prejudiciais, mas acionarão a proteção documentos seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)