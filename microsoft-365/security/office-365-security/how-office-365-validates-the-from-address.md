---
title: Como o Office 365 valida o endereço de para impedir o phishing
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 'Para ajudar a evitar phishing, o Office 365 e o Outlook.com agora exigem a conformidade RFC de: endereços.'
ms.openlocfilehash: da1728b59ce100d988538d572a24ca1a44fa9a7b
ms.sourcegitcommit: 96cbcfe8b02a5efc2d5a4fc070753ea96f298fda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749153"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Como o Office 365 valida o endereço de para impedir o phishing

As contas de email do Office 365 e do Outlook.com recebem um número cada vez maior de ataques de phishing. Uma técnica usada por phishers é enviar mensagens com valores para o endereço de: que não são compatíveis com a [RFC 5322](https://tools.ietf.org/html/rfc5322). O endereço de: também é chamado de endereço 5322. from. Para ajudar a evitar esse tipo de phishing, o Office 365 e o Outlook.com exigem que as mensagens recebidas pelo serviço incluam um endereço compatível com RFC de:, conforme descrito neste artigo.
  
> [!NOTE]
> As informações deste artigo exigem que você tenha uma compreensão básica do formato geral dos endereços de email. Para obter mais informações, consulte [rfc 5322](https://tools.ietf.org/html/rfc5322) (principalmente as seções 3.2.3, 3,4 e 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), bem como [RFC 3696](https://tools.ietf.org/html/rfc3696). Este artigo trata da imposição de política para o endereço 5322. from. Este artigo não se refere ao endereço 5321. MailFrom. 
  
Infelizmente, ainda há alguns servidores de email herdados na Internet que continuam a enviar mensagens de email "legítimas" com um endereço ausente ou malformado de:. Se você receber emails regularmente das organizações que usam esses sistemas herdados, incentive essas organizações a atualizar seus servidores de email para que estejam em conformidade com os padrões de segurança modernos.
  
A Microsoft começará a implantar as políticas descritas neste artigo em 9 de novembro de 2017.
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Como o Office 365 aplica o uso de um endereço válido de: para impedir ataques de phishing

O Office 365 está fazendo alterações no modo como ele impõe o uso do endereço from: nas mensagens recebidas para melhor proteção contra ataques de phishing. Neste artigo:
  
- [Todas as mensagens devem incluir um endereço válido de:](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [Formato do endereço de: se você não incluir um nome de exibição](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [Formato do endereço de: se você incluir um nome de exibição](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [Exemplos adicionais de endereços válidos e inválidos de:](how-office-365-validates-the-from-address.md#Examples)
    
- [Suprimir respostas automáticas para seu domínio personalizado sem quebrar a de: política](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Substituindo o Office 365 de: política de aplicação de endereços](how-office-365-validates-the-from-address.md#Override)
    
- [Outras maneiras de evitar e proteger contra o cybercrimes no Office 365](how-office-365-validates-the-from-address.md#OtherProtection)
    
Enviar em nome de outro usuário não é afetado por essa alteração, para obter mais detalhes, leia o blog de Terry Zink "[o que queremos dizer quando nos referimos ao" remetente "de um email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".
  
### <a name="all-messages-must-include-a-valid-from-address"></a>Todas as mensagens devem incluir um endereço válido de:
<a name="MustIncludeFromAddress"> </a>

Algumas mensagens automatizadas não incluem um endereço de: ao serem enviados. No passado, quando o Office 365 ou Outlook.com recebeu uma mensagem sem um endereço de:, o serviço adicionou o seguinte padrão de: endereço à mensagem para torná-lo possível:
  
```
From: <>
```

A partir de 9 de novembro de 2017, o Office 365 será distribuir alterações em seus datacenters e servidores de email que aplicarão uma nova regra onde as mensagens sem um endereço de: não serão mais aceitas pelo Office 365 ou Outlook.com. Em vez disso, todas as mensagens recebidas pelo Office 365 já devem conter um endereço válido de:. Caso contrário, a mensagem será enviada para as pastas lixo eletrônico ou itens excluídos no Outlook.com e no Office 365. 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Visão geral da sintaxe: formato válido para o endereço de: do Office 365
<a name="SyntaxOverviewFromAddress"> </a>

O formato para o valor do endereço de: é definido em detalhes em várias RFCs. Há várias variações no endereçamento e o que pode ser considerado válido ou inválido. Para simplificar, a Microsoft recomenda que você use o seguinte formato e definições:
  
```
From: "displayname " <emailaddress >
```

Onde:
  
- Opcion  *DisplayName* é uma frase que descreve o proprietário do endereço de email. Por exemplo, este pode ser um nome mais amigável para descrever o remetente do que o nome da caixa de correio. O uso de um nome de exibição é opcional. No entanto, se você optar por usar um nome de exibição, a Microsoft recomenda que você sempre o coloque entre aspas, conforme mostrado. 
    
- Precisam  *EmailAddress* é composto por: 
    
  ```
  local-part @domain
  ```

    Onde:
    
  - Precisam  *local-Part* é uma cadeia de caracteres que identifica a caixa de correio associada ao endereço. Isso é exclusivo no domínio. Geralmente, o nome de usuário ou o GUID do proprietário da caixa de correio é usado como o valor para a parte local. 
    
  - Precisam  *Domain* é o FQDN (nome de domínio totalmente qualificado) do servidor de email que hospeda a caixa de correio identificada pela parte local do endereço de email. 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Formato do endereço de: se você não incluir um nome de exibição
<a name="FormatNoDisplayName"> </a>

Um endereço com formatação adequada de: que não inclua um nome de exibição inclui apenas um endereço de email único com ou sem colchetes angulares. A Microsoft recomenda que você não separe os colchetes angulares com espaços. Além disso, não inclua nada após o endereço de email.
  
Os exemplos a seguir são válidos:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

O exemplo a seguir é válido, mas não é recomendado, pois contém espaços entre os colchetes angulares e o endereço de email:
  
```
From: < sender@contoso.com >
```

O exemplo a seguir é inválido porque contém texto após o endereço de email:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Formato do endereço de: se você incluir um nome de exibição
<a name="FormatDisplayName"> </a>

Para: endereços que incluem um valor para o nome de exibição, as seguintes regras se aplicam:
  
- Se o endereço do remetente incluir um nome de exibição e o nome de exibição incluir uma vírgula, o nome de exibição deverá ser colocado entre aspas. Por exemplo:
    
    O exemplo a seguir é válido:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    O exemplo a seguir não é válido:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    Não colocar o nome de exibição entre aspas se esse nome de exibição incluir uma vírgula é inválido de acordo com a RFC 5322.
    
    Como prática recomendada, coloque aspas em torno do nome de exibição, independentemente de haver ou não uma vírgula dentro do nome de exibição.
    
- Se o endereço do remetente incluir um nome de exibição, o endereço de email deverá ser colocado entre colchetes angulares.
    
    Como prática recomendada, a Microsoft recomenda que você insira um espaço entre o nome de exibição e o endereço de email.
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Exemplos adicionais de endereços válidos e inválidos de:
<a name="Examples"> </a>

- Inválido
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Inválido. O endereço de email não está entre colchetes angulares:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- Válido, mas não é recomendado. O nome de exibição não está entre aspas. Como prática recomendada, sempre coloque o nome de exibição entre aspas:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- Inválido. Tudo está entre aspas, não apenas o nome de exibição:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Inválido. Não há colchetes angulares em torno do endereço de email:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Inválido. Não há espaço entre o nome de exibição e o colchete angular esquerdo:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- Inválido. Não há espaço entre as aspas de fechamento ao redor do nome para exibição e o colchete angular esquerdo.
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Suprimir respostas automáticas para seu domínio personalizado sem quebrar a de: política
<a name="SuppressAutoReply"> </a>

Com o novo de: imposição de política, você não pode mais usar \< \> de: para suprimir respostas automáticas. Em vez disso, você precisa configurar um registro MX nulo para seu domínio personalizado.
  
O registro MX (Mail Exchanger) é um registro de recurso no DNS que identifica o servidor de email que recebe os emails do seu domínio. As respostas automáticas (e todas as respostas) são suprimidas naturalmente porque não há endereço publicado ao qual o servidor de resposta pode enviar mensagens.
  
Quando você configura um registro MX nulo para seu domínio personalizado:
  
- Escolha um domínio do qual enviar mensagens que não aceita (recebe) email. Por exemplo, se seu domínio primário for contoso.com, você poderá escolher noreply.contoso.com.
    
- Configure o registro MX nulo para seu domínio. Um registro MX nulo consiste em um único ponto, por exemplo:
    
  ```
  noreply.contoso.com IN MX .
  ```

Para obter mais informações sobre como publicar um MX nulo, consulte [RFC 7505](https://tools.ietf.org/html/rfc7505).
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Substituindo o Office 365 de: política de aplicação de endereços
<a name="Override"> </a>

Após a implantação da nova política, você só pode ignorar esta política para emails de entrada recebidos do Office 365 usando um dos seguintes métodos: 
  
- Listas de IPs permitidos
    
- Regras de fluxo de email do Exchange Online
    
A Microsoft recomenda a substituição da aplicação da diretiva from:. A substituição dessa política pode aumentar o risco de exposição da sua organização a spam, phishing e outros cybercrimes.
  
Você não pode substituir esta política para emails de saída enviados no Office 365. Além disso, o Outlook.com não permitirá substituições de nenhum tipo, mesmo através de suporte. 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Outras maneiras de evitar e proteger contra o cybercrimes no Office 365
<a name="OtherProtection"> </a>

Para obter mais informações sobre como você pode reforçar sua organização contra cybercrimes como phishing, spam, violações de dados e outras ameaças, consulte [Security Best Practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).
  
## <a name="related-topics"></a>Tópicos Relacionados

[Mnsagens backscatter e EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

