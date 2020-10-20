---
title: Usar regras de fluxo de email para filtrar emails em massa
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (regras de transporte) para identificar e filtrar emails em massa (emails cinza) na proteção do Exchange Online (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82a93cdc7375468748f241e2d15d729811095330
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600304"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Usar regras de fluxo de email para filtrar emails em massa no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para examinar mensagens de entrada para spam e emails em massa (também conhecido como email cinza). Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Se quiser mais opções para filtrar emails em massa, você poderá criar regras de fluxo de emails (também conhecidas como regras de transporte) para procurar padrões de texto ou frases que sejam frequentemente encontradas em emails em massa e marcar essas mensagens como spam. Para saber mais sobre emails em massa, confira [a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [BCL (nível de reclamação em massa) no EOP](bulk-complaint-level-values.md).

Este tópico explica como criar essas regras de fluxo de email no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ter permissões para poder executar estes procedimentos:

  - No Exchange Online, consulte o entrada "fluxo de email" em [permissões de recurso no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).
  
  - Em EOP autônomo, você precisa da função de regras de transporte, que é atribuída às funções gerenciamento, ComplianceManagement e RecordsManagement por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Para abrir o Eat no EOP autônomo, confira [centro de administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:

  - [Regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Ações de regra de fluxo de email no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- A lista de palavras e padrões de texto usados para identificar emails em massa nos exemplos não são exaustivas; Você pode adicionar e remover entradas, conforme necessário. No entanto, eles são um bom ponto de partida.

- A pesquisa de palavras ou padrões de texto nos campos de cabeçalho assunto ou outros na mensagem ocorre *após* a mensagem ter sido decodificada do método de codificação de transferência de conteúdo MIME, usado para transmitir a mensagem binária entre os servidores SMTP em texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens.

- Os procedimentos a seguir marcam uma mensagem em massa como spam para toda a sua organização. No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos, de modo que você possa usar a filtragem agressiva em alguns usuários altamente direcionados, enquanto o restante de seus usuários (que recebem principalmente o email em massa que eles se inscreveram) não são afetados.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Use o Eat para criar regras de fluxo de email que filtram emails em massa

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.

3. Na página **nova regra** que é aberta, defina as seguintes configurações:

   - **Name**: Insira um nome exclusivo e descritivo para a regra.

   - Clique em **mais opções**.

   - **Aplique esta regra se**: Configure uma das seguintes configurações para procurar conteúdo em mensagens usando expressões regulares (Regex) ou palavras ou frases:

     - **O assunto ou corpo** \> o **assunto ou o corpo corresponde a estes padrões de texto**: na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) e repita até inserir todos os valores.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) . Para remover uma entrada, selecione-a e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-DeleteIcon.png) .

       Quando tiver concluído, clique em **OK**.

     - **O assunto ou corpo** \> o **assunto ou o corpo inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e repita até inserir todos os valores.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) . Para remover uma entrada, selecione-a e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-DeleteIcon.png) .

       Quando tiver concluído, clique em **OK**.

   - **Faça o seguinte**: selecione **modificar as propriedades da mensagem** \> **definem o nível de confiança de spam (SCL)**. Na caixa de diálogo **especificar SCL** que aparece, configure uma das seguintes configurações:

     - Para marcar mensagens como **spam**, selecione **6**. A ação que você configurou para filtragem de **spam** verdicts em suas políticas antispam é aplicada às mensagens (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).

     - Para marcar mensagens como **spam de alta confiança** , selecione **9**. A ação que você configurou para a filtragem de **spam de alta confiança** verdicts nas políticas antispam é aplicada às mensagens (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).

    Para obter mais informações sobre os valores de SCL, consulte [nível de confiança de spam (SCL) no EOP](spam-confidence-levels.md).

   Quando tiver terminado, clique em **salvar**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar o PowerShell para criar regras de fluxo de email que filtram emails em massa

Use a seguinte sintaxe para criar uma ou ambas as regras de fluxo de emails (expressões regulares versus palavras):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

Este exemplo cria uma nova regra chamada "filtragem de email em massa-RegEx" que usa a mesma lista de expressões regulares do tópico para definir mensagens como **spam**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

Este exemplo cria uma nova regra chamada "filtragem de email em massa-palavras" que usa a mesma lista de palavras do anterior no tópico para definir mensagens como **spam de alta confiança**.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou regras de fluxo de email para filtrar emails em massa, execute uma das seguintes etapas:

- No Eat, vá para regras de **fluxo de emails** \> **Rules** \> Selecione a regra \> clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) e verifique as configurações.

- No PowerShell, substitua o \<Rule Name\> nome da regra e execute o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- A partir de uma conta externa, envie uma mensagem de teste para um destinatário afetado que contenha uma das frases ou padrões de texto e verifique os resultados.
