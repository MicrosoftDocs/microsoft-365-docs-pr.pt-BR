---
title: Configurar o EOP para o lixo eletrônico em ambientes híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem saber como configurar o seu ambiente do Exchange local para rotear o spam para pastas de lixo eletrônico de usuários locais, se estiverem usando o Exchange Online Protection (EOP) autônomo em ambientes híbridos.
ms.openlocfilehash: f2964324c6d9104719fc79ff31f14b4b94c627cc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621277"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Configurar o EOP autônomo para fornecer spam para a pasta lixo eletrônico em ambientes híbridos

> [!IMPORTANT]
> Este tópico é somente para clientes autônomos do EOP em ambientes híbridos. Este tópico não se aplica a clientes da Microsoft 365 com caixas de correio do Exchange Online.

Se você for um cliente autônomo do Exchange Online Protection (EOP) em um ambiente híbrido, precisará configurar sua organização do Exchange local para reconhecer e traduzir o verdicts de filtragem de spam do EOP, para que a regra de lixo eletrônico na caixa de correio local possa mover mensagens para a pasta lixo eletrônico.

Especificamente, você precisa criar regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização local do Exchange com condições que encontrem mensagens com qualquer um dos seguintes valores e cabeçalhos antispam do EOP, e ações que definem o nível de confiança de spam (SCL) dessas mensagens como 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(mensagem marcada como spam por filtragem de spam)

- `X-Forefront-Antispam-Report: SFV:SKS`(mensagem marcada como spam por regras de fluxo de email no EOP antes de filtragem de spam)

- `X-Forefront-Antispam-Report: SFV:SKB`(mensagem marcada como spam por filtragem de spam devido ao endereço de email do remetente ou domínio de email que está na lista de remetentes bloqueados ou na lista de domínios bloqueados no EOP)

Para obter mais informações sobre esses valores de cabeçalho, consulte [anti-spam Message Headers](anti-spam-message-headers.md).

Este tópico descreve como criar essas regras de fluxo de emails do centro de administração do Exchange (Eat) e no Shell de gerenciamento do Exchange (Exchange PowerShell) na organização do Exchange local.

> [!TIP]
> Em vez de entregar as mensagens à pasta de lixo eletrônico do usuário local, você pode configurar políticas antispam no EOP para colocar mensagens de spam em quarentena no EOP. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa receber permissões no ambiente local do Exchange antes de poder executar estes procedimentos. Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão. Para obter mais informações, consulte [Adicionar membros a um grupo de funções](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Se e quando uma mensagem for enviada para a pasta lixo eletrônico em uma organização local do Exchange é controlada por uma combinação das seguintes configurações:

  - O valor do parâmetro _SCLJunkThreshold_ no cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) no Shell de gerenciamento do Exchange. O valor padrão é 4, o que significa que um SCL de 5 ou superior deve entregar a mensagem para a pasta lixo eletrônico do usuário.

  - O valor do parâmetro _SCLJunkThreshold_ no cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) no Shell de gerenciamento do Exchange. O valor padrão é Blank ($null), o que significa que a configuração da organização é usada.

  Para obter detalhes, consulte [Exchange spam nível de confiança (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Se a regra de lixo eletrônico está habilitada na caixa de correio (o valor do parâmetro _Enabled_ é $true no cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) no Shell de gerenciamento do Exchange). É a regra de lixo eletrônico que realmente move a mensagem para a pasta lixo eletrônico após a entrega. Por padrão, a regra de lixo eletrônico está habilitada nas caixas de correio. Para obter mais informações, consulte [Configurar configurações antispam do Exchange em caixas de correio](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).
  
- Para abrir o Eat em um servidor Exchange, confira [centro de administração do Exchange no Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Para abrir o Shell de gerenciamento do Exchange [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell), consulte.

- Para obter mais informações sobre regras de fluxo de emails no Exchange local, consulte os seguintes tópicos:

  - [Regras de fluxo de emails no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Ações de regra de fluxo de email no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Use o Eat para criar regras de fluxo de email que definem o SCL das mensagens de spam do EOP

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra** no menu suspenso que aparece.

3. Na página **nova regra** que é aberta, defina as seguintes configurações:

   - **Name**: Insira um nome exclusivo e descritivo para a regra. Por exemplo:

     - EOP SFV: SPM para SCL 6

     - EOP SFV: SKS para SCL 6

     - EOP SFV: SKB para SCL 6

   - Clique em **mais opções**.

   - **Aplicar esta regra se**: selecionar **um cabeçalho** \> de mensagem **inclui qualquer uma destas palavras**.

     Na frase **Inserir cabeçalho de texto inclui palavras de entrada** que aparecem, siga estas etapas:

     - Clique em **Inserir texto**. Na caixa de diálogo **especificar nome do cabeçalho** que aparece, insira **X-Forefront-antispam-Report** e clique em **OK**.

     - Clique em **inserir palavras**. Na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos valores de cabeçalho de spam do EOP (**SFV: SPM**, **SFV: SKS**ou **SFV: SKB**) **Add** ![, clique em](../../media/ITPro-EAC-AddIcon.png)adicionar ícone de adição e, em seguida, clique em **OK**.

   - **Faça o seguinte**: selecione **modificar as propriedades** \> da mensagem **definem o nível de confiança de spam (SCL)**.

     Na caixa de diálogo **especificar SCL** exibida, selecione **6** (o valor padrão é **5**).

   Quando tiver terminado, clique em **salvar**

Repita essas etapas para os valores de veredicto de spam restantes do EOP (**SFV: SPM**, **SFV: SKS**ou **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Usar o Shell de gerenciamento do Exchange para criar regras de fluxo de emails que definem o SCL das mensagens de spam do EOP

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

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou com êxito o EOP autônomo para entregar spam para a pasta lixo eletrônico no ambiente híbrido, execute uma das seguintes etapas:

- No Eat, vá para **regras**de **fluxo** \> de emails, selecione a regra e clique em **Editar** ![ícone](../../media/ITPro-EAC-EditIcon.png) de edição para verificar as configurações.

- No Shell de gerenciamento do Exchange, \<substitua\> RuleName pelo nome da regra de fluxo de emails e regra o comando a seguir para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- Em um sistema de email externo **que não examina mensagens de saída para spam**, envie um teste genérico para uma mensagem de email em massa não solicitado (GTUBE) para um destinatário afetado e confirme se ele é entregue na pasta lixo eletrônico. A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.

  Para enviar uma mensagem do GTUBE, inclua o seguinte texto no corpo de uma mensagem de email em uma única linha, sem espaços ou quebras de linha:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
