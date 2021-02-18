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
description: Os administradores podem aprender a usar regras de fluxo de emails (também conhecidas como regras de transporte) para receber cópias das mensagens que os usuários relatam à Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287600"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há várias maneiras de os usuários relatarem mensagens à Microsoft para análise, conforme descrito em Mensagens de relatório e arquivos para a [Microsoft.](report-junk-email-messages-to-microsoft.md)

Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens que os usuários relatam à Microsoft e pode configurar destinatários Cc para receber cópias dessas mensagens relatadas.

Você pode criar a regra de fluxo de emails no Centro de administração do Exchange (EAC) e no PowerShell (organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para fazer os procedimentos deste artigo, você precisa ter permissões no Exchange Online ou no Proteção do Exchange Online. Especificamente, você precisa da **função** Regras de Transporte, que é atribuída aos  grupos de função Gerenciamento da Organização **,** Gerenciamento de Conformidade **(administradores** globais) e Gerenciamento de Registros por padrão.

  Para mais informações, confira os seguintes tópicos:

  - [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Permissões no EOP autônomo](feature-permissions-in-eop.md)
  - [Usar o EAC para modificar a lista de membros em grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir o EAC no Exchange Online, confira o Centro de administração [do Exchange no Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Para abrir o EAC no EOP autônomo, confira o Centro de administração do [Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e no EOP autônomo, consulte os seguintes tópicos:
  - [Regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Ações de regras de fluxo de emails no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar o EAC para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique **no** ![ ícone Adicionar e selecione Criar uma nova ](../../media/ITPro-EAC-AddIcon.png) **regra.**

3. Na página **Nova regra** que é aberta, de configure as seguintes configurações:

   - **Nome:** insira um nome exclusivo e descritivo para a regra. Por exemplo, Cc Messages Reported to Microsoft.

   - Clique **em Mais Opções.**

   - Aplique esta regra  **se:** Selecione o endereço do destinatário incluir qualquer uma destas palavras: na caixa de diálogo Especificar palavras ou \>  **frases** que aparece, insira um dos seguintes valores, clique em Adicionar Ícone e repita até ter inserido todos os  ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Para editar uma entrada, selecione-a e clique no **ícone** ![ ](../../media/ITPro-EAC-EditIcon.png) Editar. Para remover uma entrada, selecione-a e clique **no ícone** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Remover.

     Quando terminar, clique em **OK.**

   - **Faça o seguinte:** selecione **Adicionar destinatários** \> **à caixa Cc**. Na caixa de diálogo exibida, encontre e selecione os destinatários que você deseja adicionar. Quando terminar, clique em **OK.**

4. Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações. Recomendamos testar a regra antes de impor.

5. Quando concluir, clique em **Salvar**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Usar o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

Este exemplo cria uma nova regra de fluxo de emails chamada Cc Messages Reported to Microsoft que procura por mensagens de email relatadas à Microsoft usando os métodos descritos neste artigo e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cc.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou regras de fluxo de emails para receber cópias de mensagens relatadas, faça uma das seguintes etapas:

- No EAC, vá para Regras de **fluxo** de emails, selecione a regra, clique no ícone Editar \>  \> e \> verifique as  ![ ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell, execute o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.
