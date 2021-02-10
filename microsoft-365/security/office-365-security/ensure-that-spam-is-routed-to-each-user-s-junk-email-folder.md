---
title: Configurar o EOP para spam de lixo eletrônico em ambientes híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a rotear spam para pastas de Lixo Eletrônico do usuário em um ambiente híbrido da Proteção do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 926ac6dec33bf00fc8f0dcd292229e20ccc2b93f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167114"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurar o EOP autônomo para entregar spam à pasta Lixo Eletrônico em ambientes híbridos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](https://go.microsoft.com/fwlink/?linkid=2148611)

> [!IMPORTANT]
> Este tópico é destinado apenas a clientes autônomos do EOP em ambientes híbridos. Este tópico não se aplica aos clientes do Microsoft 365 com caixas de correio do Exchange Online.

Se você for um cliente autônomo do Exchange Online Protection (EOP) em um ambiente híbrido, será necessário configurar sua organização local do Exchange para reconhecer e traduzir os vereditos de filtragem de spam do EOP, para que a regra de lixo eletrônico na caixa de correio local possa mover mensagens para a pasta Lixo Eletrônico.

Especificamente, você precisa criar regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização local do Exchange com condições que encontram mensagens com qualquer um dos seguintes valores e headers anti-spam do EOP, e ações que configuram o nível de confiança de spam (SCL) dessas mensagens como 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (mensagem marcada como spam pela filtragem de spam)

- `X-Forefront-Antispam-Report: SFV:SKS` (mensagem marcada como spam pelas regras de fluxo de emails no EOP antes da filtragem de spam)

- `X-Forefront-Antispam-Report: SFV:SKB` (mensagem marcada como spam pela filtragem de spam devido ao endereço de email ou domínio de email do remetente estar na lista de remetentes bloqueados ou na lista de domínios bloqueados no EOP)

Para obter mais informações sobre esses valores de header, consulte Os headers de [mensagens anti-spam.](anti-spam-message-headers.md)

Este tópico descreve como criar essas regras de fluxo de emails no Centro de administração do Exchange (EAC) e no Shell de Gerenciamento do Exchange (Exchange PowerShell) na organização local do Exchange.

> [!TIP]
> Em vez de entregar as mensagens para a pasta Lixo Eletrônico do usuário local, você pode configurar políticas anti-spam no EOP para colocar as mensagens de spam em quarentena no EOP. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para fazer esses procedimentos, você precisa ter permissões no ambiente do Exchange local. Especificamente, você precisa ter  a função Regras de Transporte atribuída às funções Gerenciamento  da **Organização,** Gerenciamento de Conformidade e Gerenciamento de Registros por padrão.  Para obter mais informações, consulte [Adicionar membros a um grupo de funções](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).

- Se e quando uma mensagem é entregue à pasta Lixo Eletrônico em uma organização local do Exchange é controlada por uma combinação das seguintes configurações:

  - O _valor do parâmetro SCLJunkThreshold_ no cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) no Shell de Gerenciamento do Exchange. O valor padrão é 4, o que significa que um SCL de 5 ou superior deve entregar a mensagem para a pasta lixo eletrônico do usuário.

  - O _valor do parâmetro SCLJunkThreshold_ no cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) no Shell de Gerenciamento do Exchange. O valor padrão está em branco ($null), o que significa que a configuração da organização é usada.

  Para obter detalhes, consulte Limites do nível de confiança [de spam do Exchange (SCL).](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Se a regra de lixo eletrônico está habilitada na caixa de correio (o valor do parâmetro _Enabled_ é $true no cmdlet [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) no Shell de Gerenciamento do Exchange). É a regra de lixo eletrônico que, na verdade, move a mensagem para a pasta Lixo Eletrônico após a entrega. Por padrão, a regra de lixo eletrônico é habilitada em caixas de correio. Para obter mais informações, consulte [Configurar configurações antispam do Exchange em caixas de correio.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)

- Para abrir o EAC em um Exchange Server, consulte o Centro de administração [do Exchange no Exchange Server.](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center) Para abrir o Shell de Gerenciamento do Exchange, confira [Abrir o Shell de Gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange local, consulte os seguintes tópicos:

  - [Regras de fluxo de emails no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Ações de regra de fluxo de emails no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar o EAC para criar regras de fluxo de emails que configuram o SCL de mensagens de spam do EOP

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique **no** ![ ícone Adicionar e selecione Criar ](../../media/ITPro-EAC-AddIcon.png) **uma** nova regra no menu drop-down exibido.

3. Na página **Nova regra** que é aberta, de configure as seguintes configurações:

   - **Nome:** insira um nome exclusivo e descritivo para a regra. Por exemplo:

     - EOP SFV:SPM para SCL 6

     - EOP SFV:SKS para SCL 6

     - EOP SFV:SKB para SCL 6

   - Clique **em Mais Opções.**

   - **Aplicar esta regra se:** Selecione **um header** \> **de mensagem inclui qualquer uma destas palavras**.

     In the **Enter text header includes Enter words** sentence that appears, do the following steps:

     - Clique **em Inserir texto.** In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.

     - Clique  **em Inserir palavras**. Na caixa de diálogo Especificar  palavras ou **frases** exibida, insira um dos valores de header de spam do EOP (**SFV:SPM**, **SFV:SKS** ou **SFV:SKB),** clique no ícone Adicionar e clique em ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**

   - **Faça o seguinte:** selecione **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL).**

     Na caixa **de diálogo Especificar SCL** exibida, selecione **6** (o valor padrão é **5**).

   Quando terminar, clique em **Salvar**

Repita essas etapas para os valores restantes de veredito de spam do EOP (**SFV:SPM**, **SFV:SKS** ou **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar o Shell de Gerenciamento do Exchange para criar regras de fluxo de emails que configuram o SCL de mensagens de spam do EOP

Use a seguinte sintaxe para criar as três regras de fluxo de emails:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Por exemplo:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou com êxito o EOP autônomo para entregar spam à pasta Lixo Eletrônico no ambiente híbrido, faça uma das seguintes etapas:

- No EAC, vá para **Regras** de fluxo de emails, selecione a regra e clique em Editar ícone \> para verificar  ![ as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No Shell de Gerenciamento do Exchange, substitua pelo nome da regra de fluxo de emails e rul o seguinte comando \<RuleName\> para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Em um sistema de email externo que não verificar mensagens de saída em busca de **spam,** envie uma mensagem de Teste Genérico para Email em Massa Não Solicitado (GTUBE) para um destinatário afetado e confirme se ela foi entregue à pasta Lixo Eletrônico. A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.

  Para enviar uma mensagem do GTUBE, inclua o seguinte texto no corpo de uma mensagem de email em uma única linha, sem espaços ou quebras de linha:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
