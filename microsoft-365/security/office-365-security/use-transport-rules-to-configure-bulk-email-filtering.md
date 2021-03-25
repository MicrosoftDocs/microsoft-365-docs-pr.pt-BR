---
title: Usar regras de fluxo de emails para filtrar emails em massa
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (regras de transporte) para identificar e filtrar emails em massa (email cinza) no Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203112"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Usar regras de fluxo de email para filtrar emails em massa no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas anti-spam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para verificar mensagens de entrada para spam e email em massa (também conhecido como email cinza). Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

Se quiser mais opções para filtrar emails em massa, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para pesquisar padrões de texto ou frases que são encontradas com frequência em emails em massa e marcar essas mensagens como spam. Para obter mais informações sobre emails em massa, consulte Qual é a diferença entre lixo eletrônico e email em [massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e Nível de reclamação em massa [(BCL) no EOP](bulk-complaint-level-values.md).

Este tópico explica como criar essas regras de fluxo de emails no Centro de administração do Exchange (EAC) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

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

- A lista de palavras e padrões de texto usados para identificar emails em massa nos exemplos não é exaustiva; você pode adicionar e remover entradas conforme necessário. No entanto, eles são um bom ponto de partida.

- A pesquisa de palavras ou padrões de texto nos campos de cabeçalho assunto ou outros na mensagem ocorre *após* a mensagem ter sido decodificada do método de codificação de transferência de conteúdo MIME, usado para transmitir a mensagem binária entre os servidores SMTP em texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens.

- Os procedimentos a seguir marcam uma mensagem em massa como spam para toda a organização. No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos, para que você possa usar a filtragem agressiva em alguns usuários altamente direcionados, enquanto o restante dos seus usuários (que, na maioria das vezes, recebe o email em massa para o qual se inscreveu) não é afetado.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar o EAC para criar regras de fluxo de emails que filtram emails em massa

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique **em Adicionar** ícone e selecione Criar uma nova ![ ](../../media/ITPro-EAC-AddIcon.png) **regra.**

3. Na página **Nova regra** que é aberta, configure as seguintes configurações:

   - **Nome**: Insira um nome exclusivo e descritivo para a regra.

   - Clique **em Mais Opções**.

   - **Aplique essa regra se**: Configurar uma das seguintes configurações para procurar conteúdo em mensagens usando expressões regulares (RegEx) ou palavras ou frases:

     - **O assunto ou o corpo** \> **subject ou body** corresponde a esses padrões de texto : na caixa de diálogo Especificar palavras ou **frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** Ícone e repita até que você tenha inserido todos os ![ ](../../media/ITPro-EAC-AddIcon.png) valores.

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

      Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar. Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .

       Quando terminar, clique em **OK**.

     - **O assunto ou o corpo** \> **subject or body includes** any of these words : In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** Add Icon , and repeat ![ until you've entered all the ](../../media/ITPro-EAC-AddIcon.png) values.

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

      Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar. Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .

       Quando terminar, clique em **OK**.

   - **Faça o seguinte:** Selecione **Modificar as propriedades da mensagem** definir o nível de confiança de spam \> **(SCL)**. Na caixa **de diálogo Especificar SCL** exibida, configure uma das seguintes configurações:

     - Para marcar mensagens como **Spam,** selecione **6**. A ação que você configurou para vereditos de filtragem de **spam** em suas políticas anti-spam é aplicada às mensagens (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).

     - Para marcar mensagens como **spam de alta confiança,** selecione **9**. A ação que você configurou para vereditos de filtragem de **spam** de alta confiança em suas políticas anti-spam é aplicada às mensagens (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico**).

    Para obter mais informações sobre valores de SCL, consulte Nível de confiança [de spam (SCL) no EOP](spam-confidence-levels.md).

   Quando terminar, clique em **Salvar**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Usar o PowerShell para criar regras de fluxo de emails que filtram emails em massa

Use a sintaxe a seguir para criar uma ou ambas as regras de fluxo de emails (expressões regulares versus palavras):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

Este exemplo cria uma nova regra chamada "Filtragem de email em massa - RegEx" que usa a mesma lista de expressões regulares de anteriormente no tópico para definir mensagens como **Spam**.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

Este exemplo cria uma nova regra chamada "Filtragem de email em massa - Palavras" que usa a mesma lista de palavras de anteriormente no tópico para definir mensagens como spam de alta **confiança.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou regras de fluxo de emails para filtrar emails em massa, faça qualquer uma das seguintes etapas:

- No EAC, vá para **Regras de fluxo de** email selecione a regra clique em \>  \> \> **Editar** ícone editar e verifique ![ as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell, substitua pelo nome da regra e execute \<Rule Name\> o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- De uma conta externa, envie uma mensagem de teste para um destinatário afetado que contém uma das frases ou padrões de texto e verifique os resultados.