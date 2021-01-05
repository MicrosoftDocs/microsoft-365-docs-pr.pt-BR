---
title: Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (também conhecidas como regras de transporte) para receber cópias das mensagens que os usuários reportam à Microsoft.
ms.openlocfilehash: ec7145b68548bb5e1d6841387a18e86b74ec2a78
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751566"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há várias maneiras para os usuários reportarem mensagens para a Microsoft para análise, conforme descrito em [mensagens e arquivos de relatórios para a Microsoft](report-junk-email-messages-to-microsoft.md).

Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens que os usuários relatam à Microsoft, e você pode configurar destinatários Cco para receber cópias dessas mensagens relatadas.

Você pode criar a regra de fluxo de emails no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa receber permissões no Exchange Online ou na proteção do Exchange Online antes de poder executar os procedimentos deste artigo. Especificamente, você precisa da função de **regras de transporte** , que é atribuída ao **Gerenciamento de organização**, gerenciamento de **conformidade** (administradores globais) e grupos de função de **Gerenciamento de registros** por padrão.

  Para mais informações, confira os seguintes tópicos:

  - [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Permissões no EOP autônomo](feature-permissions-in-eop.md)
  - [Usar o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Para abrir o Eat no EOP autônomo, confira [centro de administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:
  - [Regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Ações de regra de fluxo de email no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Use o Eat para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.

3. Na página **nova regra** que é aberta, defina as seguintes configurações:

   - **Name**: Insira um nome exclusivo e descritivo para a regra. Por exemplo, as mensagens Cco relatadas para a Microsoft.

   - Clique em **mais opções**.

   - **Aplicar esta regra se**: selecione **o endereço do destinatário** \> **inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou expressões** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) e repita até inserir todos os valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) . Para remover uma entrada, selecione-a e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-DeleteIcon.png) .

     Quando tiver concluído, clique em **OK**.

   - **Faça o seguinte**: selecione **Adicionar destinatários** \> **à caixa Cco**. Na caixa de diálogo exibida, localize e selecione os destinatários que você deseja adicionar. Quando tiver concluído, clique em **OK**.

4. Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações. Recomendamos testar a regra antes de aplicá-la.

5. Quando concluir, clique em **Salvar**.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Use o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

Este exemplo cria uma nova regra de fluxo de emails chamada Cco mensagens relatadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste artigo e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cco.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, execute uma das seguintes etapas:

- No Eat, vá para regras de **fluxo de emails** \>  \> Selecione a regra \> clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) e verifique as configurações.

- No PowerShell, execute o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.
