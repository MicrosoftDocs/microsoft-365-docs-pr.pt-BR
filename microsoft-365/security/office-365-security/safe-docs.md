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
description: Saiba mais sobre Documentos Seguros no Microsoft 365 E5 ou no Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47bb6c66d51575c91b829e9688a074aaf9a18ab5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166646"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos Seguros no Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Documentos Seguros é um recurso do Microsoft 365 E5 ou do Microsoft 365 E5 Security que usa o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade para verificar documentos e arquivos abertos no [Protected View.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Os Documentos Seguros estão disponíveis apenas para usuários com licenças de Segurança do *Microsoft 365 E5* ou *Microsoft 365 E5.* Essas licenças não estão incluídas no Microsoft Defender para planos do Office 365.

- Os Documentos Seguros são suportados no Microsoft 365 Apps para empresas (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com>. Para ir diretamente para a página Anexos Seguros da **ATP,** <https://protection.office.com/safeattachmentv2> abra.

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:
  - Para definir as configurações de Documentos Seguros,  você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura às configurações de Documentos Seguros, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  > 
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  >
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

### <a name="how-does-microsoft-handle-your-data"></a>Como a Microsoft lida com seus dados?

Para mantê-lo protegido, Os Documentos Seguros enviam arquivos para a [nuvem do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para análise. Detalhes sobre como o Microsoft Defender para Ponto de Extremidade lida com seus dados podem ser encontrados aqui: Privacidade e armazenamento de dados do Microsoft Defender para Pontos [de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Os arquivos enviados por Documentos Seguros não são mantidos no Defender além do tempo necessário para análise (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar o Centro de Conformidade & Segurança para configurar Documentos Seguros

1. No Centro de Conformidade & Segurança, vá para Anexos Seguros da  ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**

2. No menu **Desdolização** das configurações Globais exibido, de configure as seguintes configurações:

   - **Ativar Documentos Seguros para clientes do Office:** mover o alternância para a direita para ativar o recurso: ![ Ativar/desativar. ](../../media/scc-toggle-on.png)

   - Permitir **que** as pessoas cliquem por meio do Exibição Protegido mesmo se os Documentos Seguros identificarem o arquivo como mal-intencionado: recomendamos que você deixe essa opção desligada (deixe o botão de alternância para a esquerda: ![ ](../../media/scc-toggle-off.png) Alternar).

   Quando concluir, clique em **Salvar**.

   ![Configurações de Documentos Seguros após selecionar Configurações Globais na página Anexos Seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar o PowerShell do Exchange Online para configurar Documentos Seguros

Use a seguinte sintaxe:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- O _parâmetro EnableSafeDocs_ habilita ou desabilita Documentos Seguros para toda a organização.
- O _parâmetro AllowSafeDocsOpen_ permite ou impede que os usuários deixem o Exibição Protegido (ou seja, abrir o documento) se o documento tiver sido identificado como mal-intencionado.

Este exemplo habilita documentos seguros para toda a organização e impede que os usuários abrem documentos identificados como mal-intencionados do Modo de Exibição Protegido.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar e configurar documentos seguros, faça uma das seguintes etapas:

- No Centro de Conformidade de Segurança  &, vá para Anexos Seguros da POLÍTICA de Gerenciamento de Ameaças da \>  \> **ATP,**   clique em Configurações Globais e verifique a opção Ativar Documentos Seguros para clientes do **Office** e Permitir que as pessoas cliquem em Exibição Protegida, mesmo se Os Documentos Seguros identificarem o arquivo como configurações mal-intencionadas.

- Execute o seguinte comando no PowerShell do Exchange Online e verifique os valores de propriedade:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Os arquivos a seguir estão disponíveis para testar a proteção de Documentos Seguros. Esses documentos são semelhantes ao arquivo EICAR.TXT para testar soluções anti-malware e antivírus. Os arquivos não são prejudiciais, mas acionarão a proteção de Documentos Seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
