---
title: Configure o SPF para ajudar a evitar falsificações
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo descreve como atualizar um registro de Serviço de Nome de Domínio (DNS) para que você possa usar a Sender Policy Framework (SPF) com seu domínio personalizado no Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1aff62792be86b9c77430777c23edc655fe3bb9b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202969"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configure o SPF para ajudar a evitar falsificações

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Este artigo descreve como atualizar um registro Sistema de Nomes de Domínio (DNS) para que você possa usar a autenticação de email Sender Policy Framework (SPF) com O seu domínio personalizado no Office 365.

Usar o SPF ajuda a validar emails de saída enviados de seu domínio personalizado. É uma primeira etapa na configuração de outros métodos de autenticação de email recomendados DMARC e DKIM (dois métodos adicionais de autenticação de email com suporte no Office 365).

## <a name="prerequisites"></a>Pré-requisitos

> [!IMPORTANT]
> Se você for uma **pequena empresa** ou não estiver familiarizado com endereços IP ou configuração de DNS, ligue para o registrador de domínios da Internet (por exemplo, GoDaddy, Bluehost, web.com) para pedir ajuda com a configuração do DNS do SPF (e qualquer outro método de autenticação de email). *Além disso*, se você não comprou ou não usa um URL personalizado (em outras palavras, o URL que você e seus clientes navegam para acessar o Office 365 termina em **onmicrosoft.com**), O SPF foi configurado para você no serviço Office 365. Nenhuma outra etapa é necessária nesse caso. Obrigado pela leitura.

Antes de criar ou atualizar o registro TXT da SPF para o Office 365 no DNS externo, você precisa reunir algumas informações necessárias para fazer o registro. Para obter exemplos avançados e uma discussão mais detalhada sobre a sintaxe SPF com suporte, confira [Como funciona o SPF para evitar spoofing e phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

Reúna essas informações:

- O registro TXT SPF atual do seu domínio personalizado, se houver. Para obter instruções, confira [Reúna as informações necessárias para criar registros DNS do Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).

- Vá para o(s) seu(s) servidor(es) de mensagens e descubra os endereços IP externos (necessários de todos os servidores de mensagens locais). Por exemplo, **131.107.2.200**.

- Os nomes de domínio a serem usados para todos os domínios de terceiros que você precisa para incluir em seu registro TXT da SPF. Alguns provedores de email em massa configuraram subdomínios a serem usados para seus clientes. Por exemplo, a empresa MailChimp configurou **servers.mcsv.net**.

- Descubra qual regra de aplicação você deseja usar para o seu registro SPF TXT. A regra **-all** é recomendada. Para obter informações detalhadas sobre outras opções de sintaxe, confira [Sintaxe de registro SPF TXT para Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Para usar um domínio personalizado, o Office 365 exige que você adicione um registro TXT da Sender Policy Framework (SPF) ao registro DNS para ajudar a evitar falsificações.

## <a name="create-or-update-your-spf-txt-record"></a>Criar ou atualizar seu registro TXT da SPF

1. Verifique se está familiarizado com a sintaxe SPF na tabela a seguir.

   ****

   |Elemento|Se você estiver usando...|Comum para clientes?|Adicione este...|
   |---|---|---|---|
   |1|Qualquer sistema de email (obrigatório)|Comum. Todos os registros TXT da SPF começam com esse valor|`v=spf1`|
   |2|Exchange Online|Comum|`include:spf.protection.outlook.com`|
   |3|Somente Exchange Online dedicado|Incomum|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Alemanha, Microsoft Cloud Alemanha apenas|Incomum|`include:spf.protection.outlook.de`|
   |5|Sistema de email de terceiros|Incomum|`include:<domain_name>` <p> O \<domain_name\> é o domínio do sistema de email de terceiros.|
   |6|Sistema de emails local. Por exemplo, o Proteção do Exchange Online mais outro sistema de email|Incomum|Use um destes procedimentos para cada sistema de email adicional: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> O \<IP_address\> e o \<domain_name\> são o endereço IP e o domínio do sistema de emails que enviam emails em nome de seu domínio.|
   |7|Qualquer sistema de email (obrigatório)|Comum. Todos os registros TXT da SPF terminam com esse valor|`<enforcement rule>` <p> Este pode ser um dos vários valores. Recomendamos o valor `-all`|
   |

2. Se ainda não tiver feito isso, crie seu registro TXT SPF usando a sintaxe da tabela.

   Por exemplo, se você estiver totalmente hospedado no Office 365, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 2 e 7 e teria esta aparência:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   Esse é o registro SPF TXT mais comum. Esse registro funciona para praticamente todas as pessoas, independentemente de seu data center da Microsoft estar localizado nos Estados Unidos ou na Europa (incluindo a Alemanha) ou em outro local.

   No entanto, se você comprou o Office 365 Alemanha, parte do Microsoft Cloud Alemanha, você deve usar a instrução incluir na linha 4, em vez de na linha 2. Por exemplo, se você estiver totalmente hospedado no Office 365 Alemanha, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 4 e 7 e teria esta aparência:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Se você já implementou no Office 365 e configurou seus registros TXT SPF para o seu domínio personalizado e estiver migrando para o Office 365 Germany, será preciso atualizar o registro TXT SPF. Para fazer isso, altere `include:spf.protection.outlook.com` para `include:spf.protection.outlook.de`.

3. Depois que você formar seu registro TXT SPF, precisará atualizar o registro no DNS. Você só pode ter um registro TXT SPF para um domínio. Se em vez de adicionar um novo registro, você precisa atualizar o registro existente. Vá para [Criar registros de DNS para o Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) e clique no link do seu host DNS.

4. Testar o registro do SPF TXT.

## <a name="how-to-handle-subdomains"></a>Como lidar com subdomínios?

É importante observar que *você precisa criar um registro separado para cada subdomínio, pois os subdomínios não herdam o registro SPF de seu domínio de nível superior*.

É necessário um registro SPF curinga adicional (`*.`) para todos os domínios e subdomínios para impedir que os ataques por envio de emails que alegam ser de subdomínios não existentes. Por exemplo:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Solução de problemas da SPF

Algum problema com seu registro TXT da SPF? Leia [Solução de problemas: práticas recomendadas para o SPF no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).


## <a name="what-does-spf-email-authentication-actually-do"></a>O que a autenticação de email SPF realmente faz?

O SPF identifica quais servidores de email têm permissão para enviar e-mails em seu nome. Basicamente, o SPF, junto com DKIM, DMARC e outras tecnologias suportadas pelo Office 365, ajudam a prevenir spoofing e phishing. A SPF é adicionada como um registro TXT que é usado pelo DNS para identificar quais servidores de email podem enviar emails em nome de seu domínio personalizado. Os sistemas de email dos destinatários podem consultar o registro TXT SPF para determinar se uma mensagem de seu domínio personalizado vem de um servidor de mensagens autorizado.

Por exemplo, digamos que seu domínio personalizado contoso.com usa o Office 365. Você adiciona um registro TXT SPF que lista os servidores de mensagens do Office 365 como servidores de email legítimos para seu domínio. Quando o servidor de mensagens de recebimento recebe uma mensagem de joe@contoso.com, o servidor procura pelo registro TXT SPF para contoso.com e descobre se a mensagem é válida. Se o servidor de recebimento descobrir que a mensagem é proveniente de um servidor diferente dos servidores de mensagens do Office 365 listados no registro SPF, o servidor de email de recebimento pode optar por rejeitar a mensagem como spam.

Além disso, se o seu domínio personalizado não tiver um registro TXT SPF, alguns servidores de recebimento poderão rejeitar a mensagem imediatamente. Isso ocorre porque o servidor de recebimento não consegue validar se a mensagem vem de um servidor de mensagens autorizado.

Se você já configurou o email do Office 365, então você já incluiu os servidores de mensagens da Microsoft no DNS como um registro TXT SPF. No entanto, há alguns casos em que talvez você precise atualizar seu registro TXT SPF no DNS. Por exemplo:

- Antes, era necessário adicionar um registro TXT SPF diferente para o seu domínio personalizado se você estivesse usando o SharePoint Online. Isso não é mais necessário. Essa alteração deve reduzir o risco de mensagens de notificação do SharePoint Online acabarem na pasta Lixo Eletrônico. Atualize seu registro TXT SPF se você estiver atingindo o limite de 10 pesquisas e recebendo mensagens de erros que informam coisas como "excedeu o limite de pesquisa" e "excesso de saltos".

- Se você tiver um ambiente híbrido com o Office 365 e o Exchange locais.

- Você pretende configurar o DKIM e o DMARC (recomendado).

## <a name="more-information-about-spf"></a>Mais informações sobre a SPF

Para exemplos avançados, uma discussão mais detalhada sobre sintaxe de SPF compatível, falsificação, solução de problemas e como o Office 365 oferece suporte à SPF, confira [Como a SPF funciona para evitar a falsificação e o phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="links-to-configure-dkim-and-dmarc"></a>Links para configurar DKIM e DMARC

 O SPF foi projetado para ajudar a evitar falsificação, mas existem técnicas de falsificação contra as quais o SPF não pode proteger. Para se defender deles, depois de configurar o SPF, você deve configurar o DKIM e o DMARC para o Office 365.

O objetivo da autenticação de email [DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) é provar que o conteúdo do email não foi adulterado.

O objetivo da autenticação de email [DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) é garantir que as informações SPF e DKIM correspondam ao endereço De.
