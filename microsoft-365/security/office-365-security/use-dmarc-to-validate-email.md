---
title: Usar DMARC para validar emails no Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Saiba como configurar uma autenticação de mensagem baseada em domínio, relatórios e conformidade (DMARC) para validar as mensagens enviadas da sua organização do Office 365.
ms.openlocfilehash: 677b46f970edab98e950c9db49f264afc8d5dd73
ms.sourcegitcommit: aa878adee65a1cdf87d4cabda41ab35673957f40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37590485"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a>Usar DMARC para validar emails no Office 365

A autenticação de mensagens baseada em domínio, os relatórios e a conformidade ([DMARC](https://dmarc.org)) funciona com a SPF (estrutura de políticas de remetente) e com o DomainKeys Identified Mail (DKIM) para autenticar remetentes de email e garantir que as mensagens confiáveis de sistemas de email de destino sejam enviadas de seu domínio. Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email. O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM.
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a>Como o SPF e o DMARC trabalham juntos para proteger o email no Office 365?
<a name="SPFandDMARC"> </a>

 Uma mensagem de email pode conter vários endereços originadores ou de remetente. Esses endereços são usados com finalidades diferentes. Por exemplo, considere esses endereços: 
  
- **Endereço de "Email de"**: identifica o remetente e especifica onde enviar avisos de retorno se algum problema ocorrer com a entrega da mensagem, como notificações de falha na entrega. Isso aparece na parte do envelope de uma mensagem de email, e normalmente não é exibido pelo seu aplicativo de email. Isso algumas vezes é chamado de endereço 5321.MailFrom ou endereço reverso.
    
- **Endereço "De"** O endereço exibido como o endereço De pelo seu aplicativo de email. Esse endereço identifica o autor do email. Ou seja, a caixa de correio da pessoa ou sistema responsável por escrever a mensagem. Isso também é conhecido como endereço 5322.From.
    
O SPF usa um registro TXT DNS para fornecer uma lista de endereços IP de envio autorizados para um determinado domínio. Normalmente, só são executadas verificações de SPF contra o endereço 5321.MailFrom. Isso significa que o endereço 5322.From não é autenticado ao usar SPF por si só. Isso possibilita que exista um cenário em que um usuário recebe uma mensagem que passa por uma verificação de SPF mas tem um endereço de remetente 5322.From falso. Por exemplo, considere esta transcrição SMTP:
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

Nesta transcrição, os endereços de remetente são os seguintes:
  
- Endereço MailFrom (5321.MailFrom): phish@phishing.contoso.com
    
- Endereço De (5322.From): segurança@woodgrovebank.com
    
Se você configurou o SPF, o servidor de recebimento executa uma verificação do endereço MailFrom phish@phishing.contoso.com. Se a mensagem veio de uma fonte válida para o domínio phishing.contoso.com, ela passa na verificação de SPF. Como o cliente de email exibe apenas o endereço De, o usuário vê que essa mensagem é proveniente de segurança@woodgrovebank.com. Com o SPF sozinho, a validade de woodgrovebank.com nunca foi autenticada.
  
Quando você usa o DMARC, o servidor de recebimento também executa uma verificação do endereço De. No exemplo acima, se houver um registro TXT do DMARC para woodgrovebank.com, a verificação do endereço De falha.
  
## <a name="what-is-a-dmarc-txt-record"></a>O que é um registro TXT do DMARC?
<a name="WhatisDMARC"> </a>

Como os registros DNS para SPF, o registro do DMARC é um registro de texto (TXT) de DNS que ajuda a evitar os tipos de falsificação spoofing e phishing. Você publica registros TXT de DMARC no DNS. Os registros TXT de DMARC validam a origem das mensagens de email verificando o endereço IP do remetente em relação ao suposto proprietário do domínio de envio. O registro TXT do DMARC identifica os servidores de email de saída autorizados. Os sistemas de email de destino conseguem, então, verificar se as mensagens têm origem em servidores de email de saída autorizados.
  
O registro TXT DMARC da Microsoft tem a seguinte aparência:
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

A Microsoft envia seus relatórios de DMARC à [Agari](https://agari.com), uma terceirizada. A Agari coleta e analisa os relatórios de DMARC.
  
## <a name="implement-dmarc-for-inbound-mail"></a>Implementar DMARC para email de entrada
<a name="implementDMARCinbound"> </a>

Você não precisa fazer nada para configurar o DMARC para mensagens que receber no Office 365. Nós já cuidamos de tudo para você. Se você deseja saber o que acontece com as mensagens que não passam em nossas verificações de DMARC, confira [Como o Office 365 lida com emails de entrada que não passam na verificação do DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a>Implementar DMARC para emails de saída do Office 365
<a name="implementDMARCoutbound"> </a>

Se você usa o Office 365, mas não está usando um domínio personalizado, ou seja, você usa o onmicrosoft.com, não é preciso fazer mais nada para configurar ou implementar o DMARC para a sua organização. O SPF já está configurado, e o Office 365 gera automaticamente uma assinatura do DKIM para o seu email de saída. Para saber mais sobre essa assinatura, confira [Comportamento padrão para o DKIM e o Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
 Se tiver um domínio personalizado ou se estiver usando servidores do Exchange no local além do Office 365, você precisará implementar manualmente o DMARC para os seus emails de saída. Para implementar o DMARC no seu domínio personalizado, siga estas etapas: 
  
- [Etapa 1: Identificar fontes válidas de email para seu domínio](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [Etapa 2: Definir o SPF para seu domínio no Office 365](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [Etapa 3: Configurar o DKIM para o seu domínio personalizado no Office 365](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [Etapa 4: Formar o registro TXT do DMARC para seu domínio no Office 365](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>Etapa 1: Identificar fontes válidas de email para seu domínio
<a name="IdentifyValidSources"> </a>

Se você já configurou o SPF, já executou esta etapa. Entretanto, para o DMARC, há outras considerações. Ao identificar fontes de email para seu domínio, há duas perguntas que você deve responder:
  
- Que endereços IP enviam mensagens do meu domínio?
    
- Para emails enviados de terceiros em meu nome, os domínios de 5321.MailFrom e 5322.From são iguais?
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a>Etapa 2: Definir o SPF para seu domínio no Office 365
<a name="ConfigSPF"> </a>

Agora que você tem uma lista de todos os seus remetentes válidos, pode seguir as etapas para [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  
Por exemplo, supondo que contoso.com envia emails do Exchange Online, um servidor Exchange local cujo endereço IP é 192.168.0.1 e um aplicativo Web cujo endereço IP é 192.168.100.100, o registro TXT do SPF teria a seguinte aparência:
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

Como prática recomendada, certifique-se de que seu registro TXT do SPF leva em consideração contas de remetentes terceirizados.
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a>Etapa 3: Configurar o DKIM para o seu domínio personalizado no Office 365
<a name="ConfigDKIM"> </a>

Quando já tiver definido o SPF, precisará configurar o DKIM. O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem. Se você não configurar o DKIM e, ao invés disso, permitir que o Office 365 use as configurações padrão do DKIM para seu domínio, o DMARC poderá falhar. Isso ocorre porque a configuração padrão do DKIM usa seu domínio inicial onmicrosoft.com como o endereço 5322.From, e não o seu domínio personalizado. Isso causa uma incompatibilidade entre os endereços 5321.MailFrom e 5322.From em todos os emails enviados a partir do seu domínio.
  
Se você tem remetentes terceirizados que enviam emails em seu nome e o email que eles enviarem tiver endereços 5321.MailFrom e 5322.From incompatíveis, o DMARC falhará para aquele email. Para evitar isto, é preciso configurar especificamente o DKIM para seu domínio com o remetente terceirizado. Isso possibilita que o Office 365 autentique o email do serviço terceirizado. Também permite que outros serviços, como Yahoo, Gmail e Comcast, verifiquem o email enviado a eles pela parte terceirizada, como se o email tivesse sido enviado por você. Isso é benéfico porque permite que seus clientes confiem em seu domínio, independentemente de onde sua caixa de correio está localizada e, ao mesmo tempo, o Office 365 não marca a mensagem como spam devido a spoofing, porque ela passa nas verificações de autenticação para seu domínio.
  
Para obter instruções sobre como configurar o DKIM para seu domínio, incluindo como configurar o DKIM para remetentes terceirizados para que possam imitar o seu domínio, confira [Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md).
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a>Etapa 4: Formar o registro TXT do DMARC para seu domínio no Office 365
<a name="CreateDMARCRecord"> </a>

Apesar de haver outras opções de sintaxe que não são mencionadas aqui, essas são as opções mais comumente usadas para o Office 365. Formar o registro TXT do DMARC para seu domínio no formato:
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

em que:
  
- *domain* é o domínio que você deseja proteger. Por padrão, o registro protege os emails do domínio e de todos os seus subdomínios. Por exemplo, se você especificar\_dmarc.contoso.com, então o DMARC protegerá os emails desse domínio e de todos os seus subdomínios, como eletrodomesticos.contoso.com ou encanamento.contoso.com. 
    
- *TTL* deve ser sempre equivalente a uma hora. A unidade usada para TTL, horas (1 hora), minutos (60 minutos) ou segundos (3600 segundos), varia dependendo do registrador de seu domínio. 
    
- *pct=100* indica que esta regra deve ser usada para 100% dos emails.
    
- *policy* especifica quais políticas você deseja que o servidor de recebimento siga se o DMARC falhar. Você pode definir a política como none (nenhuma), quarantine (quarentena) ou reject (rejeitar). 
    
Para saber mais sobre quais opções usar, familiarize-se com os conceitos em [Práticas recomendadas para implementar o DMARC no Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).
  
Exemplos:
  
- Política definida como none
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- Política definida como quarantine
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- Política definida como reject
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Após formar seu registro, é preciso atualizá-lo com seu registrador de domínio. Para saber mais sobre como adicionar o registro TXT do DMARC em seus registros de DNS para o Office 365, confira [Criar registros DNS para o Office 365 ao gerenciar seus registros DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a>Práticas recomendadas para implementar o DMARC no Office 365
<a name="DMARCbestpractices"> </a>

Você pode implementar o DMARC gradualmente sem causar impacto no restante de seu fluxo de emails. Crie e execute um plano de implementação que siga estas etapas. Realize cada uma dessas etapas primeiro em um subdomínio, depois em outros subdomínios e, por fim, com o domínio principal de sua organização antes de seguir para a próxima etapa.
  
1. Monitorar o impacto da implementação do DMARC
    
    Comece com um registro de modo de monitoramento simples para um subdomínio ou domínio que exija que os receptores do DMARC enviem a você estatísticas sobre mensagens que virem usando esse domínio. Um registro de modo de monitoramento é um registro TXT do DMARC que tem a política definida como none (p=none). Muitas empresas publicam um registro TXT do DMARC com p=none porque não têm certeza sobre quantos emails eles podem perder ao publicar uma política de DMARC mais restritiva. 
    
    Você pode fazer isso até mesmo antes de ter implementado o SPF ou o DKIM em sua infraestrutura de mensagens. Entretanto, não será possível colocar em quarentena ou rejeitar eficazmente os emails usando o DMARC até que você também implemente o SPF e o DKIM. Conforme você introduz o SPF e o DKIM, os relatórios gerados pelo DMARC fornecem a quantidade e as fontes das mensagens que passam por essas verificações, e as que não passam. É possível ver facilmente quanto de seu tráfego legítimo é ou não abrangido por eles, e solucionar quaisquer problemas. Você também começará a ver quantas mensagens fraudulentas estão sendo enviadas, e de onde.
    
2. Solicitar que sistemas de email externos coloquem em quarentena as mensagens que não passam na verificação do DMARC
    
    Quando você acredita que todo o, ou a maior parte de, seu tráfego legítimo é protegido por SPF e DKIM, e quando compreende o impacto da implementação do DMARC, pode, então, implementar uma política de quarentena. Uma política de quarentena é um registro TXT do DMARC que tem sua política definida como quarantine (p=quarantine). Ao fazer isto, você pede que os receptores do DMARC coloquem as mensagens de seu domínio que falharem na verificação em um local equivalente a uma pasta de spam, ao invés de colocá-las nas caixas de entrada dos clientes.
    
3. Solicitar que sistemas de email externos rejeitem as mensagens que não passam na verificação do DMARC
    
    A etapa final é implementar uma política de rejeição. Uma política de rejeição é um registro TXT do DMARC que tem a política definida como reject (p=reject). Ao fazer isto, você pede aos receptores do DMARC que não aceitem as mensagens que falham na verificação. 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a>Como o Office 365 lida com emails de saída que não passam na verificação do DMARC
<a name="outbounddmarcfail"> </a>

Se uma mensagem que está saindo do Office 365 falhar na verificação do DMARC e você tiver a política definida como p=quarentena ou p=rejeitar, a mensagem será direcionada pelo [pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md). Não há cancelamentos para emails de saída.
  
Se você publicar uma política de rejeição (p=reject) do DMARC, nenhum outro cliente no Office 365 poderá imitar (spoof) seu domínio, porque as mensagens não conseguirão passar pelas verificações de SPF ou DKIM para seu domínio durante a retransmissão de uma mensagem de saída pelo serviço. No entanto, se você publicar uma política de rejeição do DMARC, mas não tiver todos os seus emails autenticados pelo Office 365, algumas mensagens poderão ser marcadas como spam para emails de entrada (conforme descrito acima), ou poderão ser rejeitadas, caso você não publique o SPF e tente retransmiti-las pelo serviço. Isso acontece, por exemplo, se você esquecer de incluir alguns dos endereços IP para servidores e aplicativos que enviam emails em nome do seu domínio ao formar o registro TXT do DMARC.
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a>Como o Office 365 lida com emails de entrada que não passam na verificação do DMARC
<a name="inbounddmarcfail"> </a>

Se a política do DMARC do servidor de envio for p=reject, o EOP marca a mensagem como spam ao invés de rejeitá-la. Em outras palavras, para emails de entrada, o Office 365 trata p=reject e p=quarantine da mesma forma.
  
O Office 365 é configurado assim porque alguns emails legítimos podem falhar na verificação do DMARC. Por exemplo, uma mensagem pode não passar na verificação do DMARC se for enviada a uma lista de endereçamento que retransmite a mensagem a todos os participantes da lista. Se o Office 365 rejeitar essas mensagens, as pessoas podem perder emails legítimos e não têm como recuperá-los. Em vez disso, essas mensagens ainda falharão na verificação do DMARC, mas serão marcadas como spam e não rejeitadas. Se quiserem, os usuários ainda podem receber essas mensagens em suas caixas de entrada fazendo o seguinte:
  
- Os usuários podem adicionar os remetentes seguros individualmente usando seus clientes de email
    
- Os administradores podem criar uma Regra de Transporte do Exchange (ETR) para todos os usuários que permitem mensagens desses remetentes específicos.  

## <a name="how-office-365-utilizes-authenticated-received-chain-arc"></a>Como o Office 365 usa o Authenticated Received Chain (ARC)
<a name="ARC"> </a>

Todas as caixas de correio hospedadas no Office 365 agora terão os benefícios do ARC com capacidade de entrega de mensagens e proteção anti-falsificação aprimoradas. O ARC preserva os resultados de autenticação de email de todos os participantes intermediários, ou saltos, quando um email é roteado do servidor de origem para a caixa de correio do destinatário. Antes do ARC, as modificações realizadas pelos intermediários no roteamento de emails, como as regras de encaminhamento ou assinaturas automáticas, podiam causar falhas no DMARC quando o email chegava à caixa de correio do destinatário. Com o ARC, a preservação criptográfica dos resultados da autenticação permite ao Office 365 verificar a autenticidade do remetente de um email. 

Atualmente, o Office 365 usa o ARC para verificar os resultados da autenticação quando a Microsoft é o ARC Sealer, porém está nos planos adicionar suporte para o ARC Sealer de terceiros no futuro. 
    
## <a name="troubleshooting-your-dmarc-implementation"></a>Solucionar problemas com sua implementação do DMARC
<a name="dmarctroubleshoot"> </a>

Se você tiver configurado os registros MX de seu domínio de forma que o EOP não é a primeira entrada, o DMARC não será aplicado ao seu domínio. 
  
Se você é um cliente do Office 365 e o registro MX primário de seu domínio não aponta para o EOP, você não terá os benefícios do DMARC. Por exemplo, o DMARC não funcionará se você apontar o registro MX para seu servidor de email local e direcionar os emails para o EOP usando um conector. Neste cenário, o domínio receptor é um de seus Domínios Aceitos, mas o EOP não é o MX primário. Por exemplo, suponha que contoso.com aponta seu registro MX para si mesmo e usa o EOP como registro MX secundário. O registro MX de contoso.com tem a seguinte aparência:
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

Todos os, ou a maioria dos, emails primeiro serão direcionados a mail.contoso.com, já que este é o MX primário e, então, serão direcionados para o EOP. Em alguns casos, o EOP pode nem estar listado como registro MX e você usa conectores para direcionar os emails. EOP não precisa ser a primeira entrada para a validação do DMARC. Ele só garante a validação, pois nem todos os servidores locais/não O365 farão a verificação de DMARCs.  A DMARC está qualificada para ser imposta para o domínio de um cliente (não para o servidor) ao configurar o registro TXT do DMARC, mas fica até o servidor de recebimento para realmente fazer a imposição.  Se você configurar o EOP como o servidor de recebimento, o EOP fará a imposição de DMARC.
  
## <a name="for-more-information"></a>Para obter mais informações
<a name="sectionSection8"> </a>

Quer mais informações sobre o DMARC? Estes recursos podem ajudar.
  
- [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md) inclui a sintaxe e os campos de cabeçalho usados pelo Office 365 para verificações de DMARC. 
    
- Faça a [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) do M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).
    
- Use a lista de verificação em [dmarcian](https://space.dmarcian.com/deployment/).
    
- Vá direto à fonte em [DMARC.org](https://dmarc.org).
    
## <a name="see-also"></a>Confira também
<a name="sectionSection8"> </a>

[Como o Office 365 usa o SPF (estrutura de política de remetente) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[Configurar o SPF no Office 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)

