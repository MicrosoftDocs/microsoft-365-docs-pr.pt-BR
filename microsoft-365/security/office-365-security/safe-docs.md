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
description: Saiba mais Cofre documentos em Microsoft 365 E5 ou Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1bd2150a04e51e0d06c6cd1c17a71a032df1a5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108602"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos Seguros no Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cofre Documentos é um recurso no Microsoft 365 E5 ou Microsoft 365 E5 Security que usa o [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade para examinar documentos e arquivos abertos no [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) ou no Application [Guard](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)para Office .

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Cofre Os documentos estão disponíveis apenas para usuários com *Microsoft 365 E5* ou *Microsoft 365 E5 Security* licenças. Essas licenças não estão incluídas no Microsoft Defender para Office 365 planos.

- Cofre Os documentos são suportados no Microsoft 365 Apps para Grandes Empresas (anteriormente conhecido como Office 365 ProPlus) versão 2004 ou posterior.

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a página **Cofre Anexos,** use <https://security.microsoft.com/safeattachmentv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa de permissões **Exchange Online** antes de poder fazer os procedimentos neste artigo:
  - Para configurar Cofre documentos, você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** Administrador **de** Segurança.
  - Para acessar somente leitura Cofre configurações de Documentos, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

### <a name="how-does-microsoft-handle-your-data"></a>Como a Microsoft lida com seus dados?

Para mantê-lo protegido, Cofre Documentos envia arquivos para a nuvem [do Microsoft Defender para Ponto](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) de Extremidade para análise. Detalhes sobre como o Microsoft Defender for Endpoint lida com seus dados podem ser encontrados aqui: Microsoft Defender para armazenamento de dados do Ponto de Extremidade [e privacidade.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Os arquivos enviados por Cofre Documentos não são mantidos no Defender além do tempo necessário para análise (normalmente, menos de 24 horas).

## <a name="use-the-microsoft-365-defender-to-configure-safe-documents"></a>Usar o Microsoft 365 Defender para configurar Cofre Documentos

1. Abra o portal Microsoft 365 Defender e acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** clique em **Configurações globais**.

3. Nas **configurações globais** que aparecem, configure as seguintes configurações:
   - **Ativar Cofre Documentos para** clientes Office : Mova a alternância para a direita para ativar o recurso: ![ Ativar a alternância ](../../media/scc-toggle-on.png) .
   - **Permitir que** as pessoas cliquem em Exibição Protegida, mesmo que Cofre Documentos identificaram o arquivo como mal-intencionado : recomendamos que você deixe essa opção desligada (deixe a alternância para a esquerda: Alternar para fora ![ ](../../media/scc-toggle-off.png) ).

   Quando concluir, clique em **Salvar**.

   ![Cofre Configurações de documentos após selecionar configurações globais na página Cofre Anexos.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar Exchange Online PowerShell para configurar Cofre Documentos

Use a seguinte sintaxe:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- O _parâmetro EnableSafeDocs_ habilita ou desabilita Cofre documentos para toda a organização.
- O _parâmetro AllowSafeDocsOpen_ permite ou impede que os usuários deixe o Protected View (ou seja, abrindo o documento) se o documento tiver sido identificado como mal-intencionado.

Este exemplo habilita Cofre documentos para toda a organização e impede que os usuários abriam documentos identificados como mal-intencionados do Modo de Exibição Protegido.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Integração ao Microsoft Defender for Endpoint Service para habilitar recursos de auditoria

Para implantar o Microsoft Defender para Ponto de Extremidade, você precisa passar pelas várias fases de implantação. Após a integração, você pode configurar recursos de auditoria no Microsoft 365 Defender portal.

Para saber mais, confira [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding). Se precisar de ajuda adicional, consulte Solução de problemas de integração do [Microsoft Defender para Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar e configurar Cofre Documentos, faça qualquer uma das seguintes etapas:

- No portal do Microsoft 365 Defender, acesse Email **& Políticas** de Colaboração & Página Políticas de Ameaças de Regras Políticas Cofre Configurações globais de \>  \>  \>  \> **anexos** e \>    verifique a página Ativar documentos do Cofre para clientes do Office e Permitir que as pessoas cliquem em Exibir Protegido mesmo que documentos Cofre identifiquem o arquivo como configurações mal-intencionadas.

- Execute o seguinte comando no Exchange Online PowerShell e verifique os valores da propriedade:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Os arquivos a seguir estão disponíveis para testar a proteção Cofre Documentos. Esses documentos são semelhantes ao arquivo EICAR.TXT para testar soluções anti-malware e antivírus. Os arquivos não são prejudiciais, mas dispararão a proteção Cofre Documentos.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
