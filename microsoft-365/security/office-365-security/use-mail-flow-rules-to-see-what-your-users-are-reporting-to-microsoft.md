---
title: Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (também conhecidas como regras de transporte) para receber cópias das mensagens relatadas pelos usuários à Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203117"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há várias maneiras de os usuários relatarem mensagens à Microsoft para análise, conforme descrito em Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md).

Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens que os usuários relatam para a Microsoft e pode configurar destinatários Cc para receber cópias dessas mensagens relatadas.

Você pode criar a regra de fluxo de emails no Centro de administração do Exchange (EAC) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ter permissões atribuídas no Exchange Online ou no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da função **Regras** de Transporte, que é atribuída aos  grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** (administradores globais) e Gerenciamento de Registros por padrão.

  Para mais informações, confira os seguintes tópicos:

  - [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Permissões no EOP autônomo](feature-permissions-in-eop.md)
  - [Usar o EAC modificar a lista de membros em grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir o EAC no Exchange Online, consulte [Centro de administração do Exchange no Exchange Online](/Exchange/exchange-admin-center). Para abrir o EAC no EOP autônomo, consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e no EOP autônomo, consulte os seguintes tópicos:
  - [Regras de fluxo de emails (regras de transporte) no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Condições e exceções de regra de fluxo de email (predicados) no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Ações de regra de fluxo de emails no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar o EAC para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique **em Adicionar** ícone e selecione Criar uma nova ![ ](../../media/ITPro-EAC-AddIcon.png) **regra.**

3. Na página **Nova regra** que é aberta, configure as seguintes configurações:

   - **Nome**: Insira um nome exclusivo e descritivo para a regra. Por exemplo, Mensagens de Cc Reportadas à Microsoft.

   - Clique **em Mais Opções**.

   - Aplique esta regra se **:** **Selecione** O endereço do destinatário inclui qualquer uma dessas palavras : na caixa de diálogo Especificar palavras ou \>  **frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** Ícone e repita até que você tenha inserido todos os ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar. Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .

     Quando terminar, clique em **OK**.

   - **Faça o seguinte:** Selecione **Adicionar destinatários** \> **à caixa Cc**. Na caixa de diálogo exibida, encontre e selecione os destinatários que você deseja adicionar. Quando terminar, clique em **OK**.

4. Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações. Recomendamos testar a regra antes de impor isso.

5. Quando concluir, clique em **Salvar**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

Este exemplo cria uma nova regra de fluxo de emails chamada Mensagens Bcc Reportadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste artigo e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cc.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, faça qualquer uma das seguintes etapas:

- No EAC, vá para **Regras de fluxo de** email selecione a regra clique em \>  \> \> **Editar** ícone editar e verifique ![ as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell, execute o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.