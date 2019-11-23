---
title: Configurar o SPF no Office 365 para ajudar a evitar falsificações
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
description: 'Resumo: Este artigo descreve como atualizar um registro de Serviço de Nome de Domínio (DNS) para que você possa usar a Sender Policy Framework (SPF) com seu domínio personalizado no Office 365. Usar a SPF ajuda a validar emails de saída enviados do seu domínio personalizado.'
ms.openlocfilehash: 547577fbcddca6e17d8e70a7fda8ffa469dfb525
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191276"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>Configurar o SPF no Office 365 para ajudar a evitar falsificações

 **Resumo:** Este artigo descreve como atualizar um registro de Serviço de Nome de Domínio (DNS) para que você possa usar a Sender Policy Framework (SPF) com seu domínio personalizado no Office 365. Usar a SPF ajuda a validar emails de saída enviados do seu domínio personalizado.
  
Para usar um domínio personalizado, o Office 365 exige que você adicione um registro TXT da Sender Policy Framework (SPF) ao registro DNS para ajudar a evitar falsificações. A SPF identifica quais servidores de email têm permissão para enviar emails em seu nome. Basicamente, a SPF, juntamente com DKIM, DMARC e outras tecnologias suportadas pelo Office 365 ajudam a evitar falsificações e phishing. A SPF é adicionada como um registro TXT que é usado para identificar quais servidores de email podem enviar emails em nome do seu domínio personalizado. Os sistemas de email dos destinatários podem consultar o registro TXT SPF para determinar se uma mensagem de seu domínio personalizado vem de um servidor de mensagens autorizado.
  
Por exemplo, digamos que seu domínio personalizado contoso.com usa o Office 365. Você adiciona um registro TXT SPF que lista os servidores de mensagens do Office 365 como servidores de email legítimos para seu domínio. Quando o servidor de mensagens de recebimento recebe uma mensagem de joe@contoso.com, o servidor procura pelo registro TXT SPF para contoso.com e descobre se a mensagem é válida. Se o servidor de recebimento descobrir que a mensagem é proveniente de um servidor diferente dos servidores de mensagens do Office 365 listados no registro SPF, o servidor de email de recebimento pode optar por rejeitar a mensagem como spam.

Além disso, se o seu domínio personalizado não tiver um registro TXT SPF, alguns servidores de recebimento poderão rejeitar a mensagem imediatamente. Isso ocorre porque o servidor de recebimento não consegue validar se a mensagem vem de um servidor de mensagens autorizado.
  
Se você já configurou o email do Office 365, então você já incluiu os servidores de mensagens da Microsoft no DNS como um registro TXT SPF. No entanto, há alguns casos em que talvez você precise atualizar seu registro TXT SPF no DNS. Por exemplo:
  
- Antes, era necessário adicionar um registro TXT SPF diferente para o seu domínio personalizado se você estivesse usando o SharePoint Online. Isso não é mais necessário. Essa alteração deve reduzir o risco de mensagens de notificação do SharePoint Online acabarem na pasta Lixo Eletrônico. Atualize seu registro TXT SPF se você estiver atingindo o limite de 10 pesquisas e recebendo mensagens de erros que informam coisas como "excedeu o limite de pesquisa" e "excesso de saltos".

- Se você tiver um ambiente híbrido com o Office 365 e o Exchange locais.

- Você pretende configurar o DKIM e o DMARC (recomendado).

## <a name="updating-your-spf-txt-record-for-office-365"></a>Atualizando seu registro TXT da SPF para o Office 365

Antes de atualizar o registro TXT no DNS, você precisará reunir algumas informações e determinar o formato do registro. Isso ajudará a impedir a geração de erros de DNS. Para exemplos avançados e uma discussão mais detalhada sobre sintaxe de SPF compatível, confira [Como a SPF funciona para evitar a falsificação e phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
Reúna essas informações:
  
- O registro TXT SPF atual para seu domínio personalizado. Para obter instruções, confira [Coletar as informações de que você precisa para criar registros DNS do Office 365](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67).

- Endereços IP de todos os servidores de mensagens no local. Por exemplo, **192.168.0.1**.

- Os nomes de domínio a serem usados para todos os domínios de terceiros que você precisa para incluir em seu registro TXT da SPF. Alguns provedores de email em massa configuraram subdomínios a serem usados para seus clientes. Por exemplo, a empresa MailChimp configurou **servers.mcsv.net**.

- Determine qual regra de imposição você deseja usar para seu registro TXT SPF. Recomendamos **-all**. Para obter informações detalhadas sobre outras opções de sintaxe, confira [Sintaxe do registro TXT SPF para o Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>Para adicionar ou atualizar seu registro TXT da SPF

1. Verifique se está familiarizado com a sintaxe SFP na tabela a seguir.

||**Se você estiver usando...**|**Comum para clientes do Office 365?**|**Adicione este...**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualquer sistema de email (obrigatório)  <br/> |Comum. Todos os registros TXT da SPF começam com esse valor  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online  <br/> |Comum  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Somente Exchange Online dedicado  <br/> |Incomum  <br/> |ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com  <br/> |
|4  <br/> |Office 365 Alemanha, Microsoft Cloud Alemanha apenas  <br/> |Incomum  <br/> |include:spf.protection.outlook.de  <br/> |
|5  <br/> |Sistema de email de terceiros  <br/> |Incomum  <br/> |incluir:\<nome do domínio\>  <br/> Onde o nome de domínio é o nome de domínio do sistema de email de terceiros.  <br/> |
|6  <br/> |Sistema de emails local. Por exemplo, o Exchange Online Protection mais outro sistema de email  <br/> |Incomum  <br/> | Use um destes procedimentos para cada sistema de email adicional:  <br/>  ip4:\<  _IP address_\>  <br/>  ip6:\<  _IP address_\>  <br/>  incluir:\<  _domain name_\>  <br/>  Em que o valor de \<  _IP address_\> é o endereço IP do outro sistema de email e \< _domain name_\> é o nome de domínio de outro sistema de email que envia emails em nome de seu domínio.  <br/> |
|7  <br/> |Qualquer sistema de email (obrigatório)  <br/> |Comum. Todos os registros TXT da SPF terminam com esse valor  <br/> |\< _enforcement rule_\>  <br/> Isso pode ser um dos vários valores. Recomendamos que se use **-all**.  <br/> |
|

2. Se ainda não tiver feito isso, crie seu registro TXT SPF usando a sintaxe da tabela:

   Por exemplo, se você estiver totalmente hospedado no Office 365, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 2 e 7 e teria esta aparência:

   `v=spf1 include:spf.protection.outlook.com -all`

   Este é o registro TXT SPF do Office 365. Esse registro funciona para praticamente qualquer pessoa, não importa se seu datacenter do Office 365 está situado nos Estados Unidos ou na Europa (incluindo a Alemanha) ou em outro local.

   No entanto, se você comprou o Office 365 Alemanha, parte do Microsoft Cloud Alemanha, você deve usar a instrução incluir na linha 4, em vez de na linha 2. Por exemplo, se você estiver totalmente hospedado no Office 365 Alemanha, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 4 e 7 e teria esta aparência:

   `v=spf1 include:spf.protection.outlook.de -all`

   Se você já implementou no Office 365 e configurou seus registros TXT SPF para o seu domínio personalizado e estiver migrando para o Office 365 Germany, será preciso atualizar o registro TXT SPF. Para fazer isso, altere **include:spf.protection.outlook.com** para **include.spf.protection.outlook.de**.

2. Depois que você formar seu registro TXT SPF, precisará atualizar o registro no DNS. Você só pode ter um registro TXT SPF para um domínio. Se em vez de adicionar um novo registro, você precisa atualizar o registro existente. Vá para [Criar registros de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide) e clique no link do seu host DNS.

3. Testar o registro do SPF TXT.

## <a name="more-information-about-spf"></a>Mais informações sobre a SPF

Para exemplos avançados, uma discussão mais detalhada sobre sintaxe de SPF compatível, falsificação, solução de problemas e como o Office 365 oferece suporte à SPF, confira [Como a SPF funciona para evitar a falsificação e o phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Próximas etapas: Depois de configurar a SPF para o Office 365

Algum problema com seu registro TXT da SPF? Leia [Solução de problemas: Práticas recomendadas para a SPF no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).
  
 A SPF foi projetada para ajudar a evitar a falsificação, mas existem técnicas de falsificação que a SPF não ajuda a proteger. Para proteger contra essas técnicas, depois de configurar a SPF, você também deve configurar o DKIM e o DMARC para o Office 365. Para começar, confira [Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md). A seguir, veja [Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md).
  

