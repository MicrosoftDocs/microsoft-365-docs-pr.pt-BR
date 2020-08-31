---
title: Como a estrutura de política de remetente (SPF) impede a falsificação
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como a Microsoft 365 usa o registro TXT da SPF (Sender Policy Framework) no DNS para garantir que os sistemas de email de destino confiem em mensagens enviadas de seu domínio personalizado.
ms.openlocfilehash: 702c5de90c53388a3d55ad752010fbaa04b5556b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307644"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Como o Microsoft 365 usa SPF (Sender Policy Framework) para evitar falsificação

 **Resumo:** Este artigo descreve como o Microsoft 365 usa o registro TXT da SPF (Sender Policy Framework) no DNS para garantir que os sistemas de email de destino confiem em mensagens enviadas de seu domínio personalizado. Isso se aplica ao email de saída enviado pelo Microsoft 365. As mensagens enviadas do Microsoft 365 para um destinatário no Microsoft 365 sempre passarão por SPF.

Um registro TXT SPF é um registro DNS que ajuda a evitar falsificação e phishing, verificando o nome de domínio do qual as mensagens de email são enviadas. O SPF valida a origem das mensagens de email, verificando o endereço IP do remetente em relação ao suposto proprietário do domínio de envio.

> [!NOTE]
> Os tipos de registro SPF tornaram-se obsoletos pela IETF (Internet Engineering Task Force) em 2014. Em vez disso, use os registros TXT no DNS para publicar as informações da sua SPF. O restante deste artigo usa o termo registro TXT SPF para maior clareza.

Administradores de domínio publicam informações do SPF em registros TXT no DNS. As informações do SPF identificam servidores de email de saída autorizados. Os sistemas de email de destino verificam se as mensagens têm origem em servidores de email de saída autorizados. Se você já estiver familiarizado com o SPF ou se tiver uma implantação simples e precisar saber o que incluir em seu registro TXT SPF no DNS para o Microsoft 365, poderá ir para [Configurar o SPF no microsoft 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Se você não tem uma implantação totalmente hospedada no Microsoft 365 ou deseja obter mais informações sobre como o SPF funciona ou como solucionar problemas de SPF para o Microsoft 365, continue lendo.

> [!NOTE]
> Antes, era preciso adicionar um registro TXT SPF diferente ao seu domínio personalizado se você também usou o SharePoint Online. Isso não é mais necessário. Essa alteração deve reduzir o risco de mensagens de notificação do SharePoint Online acabarem na pasta Lixo Eletrônico. Não é necessário fazer qualquer alteração imediatamente, mas se você receber o erro "muitas pesquisas", modifique o registro TXT SPF conforme descrito em [Configurar o SPF no Microsoft 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>Como o SPF funciona para evitar falsificação e phishing no Microsoft 365
<a name="HowSPFWorks"> </a>

O SPF determina se um remetente tem ou não permissão para enviar em nome de um domínio. Se o remetente não tiver permissão para fazer isso, ou seja, se o email falhar na verificação do SPF no servidor de recebimento, a política de spam configurada nesse servidor determinará o que fazer com a mensagem.

Cada registro TXT SPF contém três partes: a instrução de que ele é um registro TXT SPF, os endereços IP que estão autorizados a enviar email proveniente do seu domínio e de domínios externos que podem fazer envios em nome do seu domínio e uma regra de aplicação. É preciso todos os três em um registro TXT SPF válido. Este artigo descreve como você forma seu registro TXT SPF e fornece as práticas recomendadas para trabalhar com os serviços no Microsoft 365. Também são fornecidos links para instruções sobre como trabalhar com o registrador de domínios para publicar seu registro para o DNS.

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>Noções básicas da SPF: endereços IP que podem enviar do seu domínio personalizado
<a name="SPFBasicsIPaddresses"> </a>

Observe a sintaxe básica de uma regra de SPF:

v = spf1 \<IP\>\<enforcement rule\>

Por exemplo, digamos que exista a seguinte regra de SPF para contoso.com:

v = spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\>

Neste exemplo, a regra de SPF instrui o servidor de email de recebimento a apenas aceitar emails desses endereços IP para o domínio contoso.com:

- Endereço IP 1

- Endereço IP 2

- Endereço IP 3

Essa regra de SPF informa o servidor de email de recebimento que, se uma mensagem for proveniente de contoso.com, mas não de um desses três endereços IP, o servidor de recebimento deverá fazer valer a regra de aplicação à mensagem. A regra de aplicação é geralmente uma das seguintes opções:

- **Falha irrecuperável.** Marca a mensagem com "falha irrecuperável" no envelope de mensagem e segue a política de spam configurada do servidor de recebimento para esse tipo de mensagem.

- **Falha recuperável.** Marca a mensagem com "falha recuperável" no envelope de mensagem. Normalmente, os servidores de email estão configurados para entregar essas mensagens de qualquer maneira. A maioria dos usuários finais não vê essa marca.

- **Neutro.** Não faz nada, ou seja, não marca o envelope de mensagem. Isso é geralmente reservado para fins de teste e é raramente usado.

Os exemplos a seguir mostram como o SPF funciona em diferentes situações. Nestes exemplos, contoso.com é o remetente e woodgrovebank.com é o destinatário.

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>Exemplo 1: Autenticação de email de uma mensagem enviada diretamente do remetente para o destinatário
<a name="spfExample1"> </a>

O SPF funciona melhor quando o caminho do remetente para o destinatário é direto, por exemplo:

![Diagrama que mostra como o SPF autentica o email quando ele é enviado diretamente de um servidor para outro.](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

Quando woodgrovebank.com recebe a mensagem, se o endereço IP 1 está no registro TXT SPF para contoso.com, a mensagem passa na verificação do SPF e é autenticada.

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>Exemplo 2: Endereço falsificado do remetente falha na verificação do SPF
<a name="spfExample2"> </a>

Suponha que um agente de phishing encontre uma maneira de falsificar contoso.com:

![Diagrama que mostra como o SPF autentica o email quando ele é enviado de um servidor falso.](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

Como o endereço IP 12 não está no registro TXT SPF de contoso.com, a mensagem falha na verificação do SPF, e o destinatário pode optar por marcá-la como spam.

### <a name="example-3-spf-and-forwarded-messages"></a>Exemplo 3: SPF e mensagens encaminhadas
<a name="spfExample3"> </a>

Uma desvantagem do SPF é que ele não funciona quando um email é encaminhado. Por exemplo, suponha que o usuário em woodgrovebank.com configurou uma regra de encaminhamento para enviar todos os e-mails para uma conta do outlook.com:

![Diagrama que mostra como o SPF não consegue autenticar o email quando a mensagem é encaminhada.](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

A mensagem passa originalmente na verificação do SPF em woodgrovebank.com, mas falha na verificação do SPF em outlook.com, pois o IP 25 não está no registro TXT SPF de contoso.com. O domínio outlook.com pode marcar a mensagem como spam. Para contornar esse problema, use o SPF em conjunto com outros métodos de autenticação de email, como DKIM e DMARC.

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>Noções básicas do SPF: Inclusão de domínios de terceiros que podem enviar emails em nome do seu domínio
<a name="SPFBasicsIncludes"> </a>

Além de endereços IP, também é possível configurar seu registro TXT SPF para incluir domínios como remetentes. Eles são adicionados ao registro TXT SPF como instruções "incluir". Por exemplo, contoso.com pode querer incluir todos os endereços IP dos servidores de email de contoso.net e contoso.org que ele também possui. Para fazer isso, contoso.com publica um registro TXT SPF parecido com este:

```text
v=spf1 include:contoso.net include:contoso.org -all
```

Quando o servidor de recebimento enxerga esse registro no DNS, ele também executa uma pesquisa de DNS no registro TXT SPF para contoso.net e, em seguida, para o contoso.org. Se encontrar uma instrução include adicional nos registros de contoso.net ou contoso.org, ela também a seguirá. Para ajudar a evitar ataques de negação de serviço, o número máximo de pesquisas de DNS para uma única mensagem de email é 10. Cada instrução include representa uma pesquisa DNS adicional. Se uma mensagem exceder o limite de 10, a mensagem falha SPF. Depois que uma mensagem atinge esse limite, dependendo da maneira como o servidor de recebimento está configurado, o remetente pode receber uma mensagem dizendo que "muitas pesquisas" ou que a "contagem de saltos máxima da mensagem foi excedida" (que pode acontecer quando o loop lookups e exceder o tempo limite do DNS). Para obter dicas sobre como evitar isso, consulte [Troubleshooting: Best Practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>Requisitos para o seu registro TXT SPF e Microsoft 365
<a name="SPFReqsinO365"> </a>

Se você configurar o email quando configurar o Microsoft 365, você já criou um registro TXT SPF que identifica os servidores de mensagens da Microsoft como uma fonte de email legítima para seu domínio. Esse registro provavelmente tem a seguinte aparência:

```text
v=spf1 include:spf.protection.outlook.com -all
```

Se você é um cliente totalmente hospedado, ou seja, não tem servidores de email locais que enviam emails de saída, este é o único registro TXT SPF que você precisa publicar para o Office 365.

Se você tiver uma implantação híbrida (ou seja, você tem algumas caixas de correio locais e algumas hospedadas no Microsoft 365), ou se você é um cliente autônomo do Exchange Online Protection (EOP) (ou seja, sua organização usa o EOP para proteger suas caixas de correio locais), você deve adicionar o endereço IP de saída de cada um dos servidores de email de borda no local ao registro TXT SPF no DNS.

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>Formulário seu registro TXT SPF para o Microsoft 365
<a name="FormYourSPF"> </a>

Use as informações de sintaxe neste artigo para formular o registro TXT SPF do seu domínio personalizado. Apesar de haver outras opções de sintaxe que não são mencionadas aqui, essas são as opções mais usadas. Após formular seu registro, atualize-o no seu registrador de domínios.

Para obter informações sobre os domínios que você precisará incluir no Microsoft 365, consulte [registros DNS externos necessários para o SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records). Use as [instruções passo a passo](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) para atualizar registros TXT SPF para o seu registrador de domínios.

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Sintaxe do registro TXT SPF para o Microsoft 365
<a name="SPFSyntaxO365"> </a>

Um registro TXT SPF típico para o Microsoft 365 tem a seguinte sintaxe:

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

Por exemplo:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

em que:

- **v=spf1** é obrigatório. Isso define o registro TXT como um registro TXT SPF.

- **ip4** indica que você está usando endereços IP versão 4. **ip6** indica que você está usando endereços IP versão 6. Se estiver usando endereços IP IPv6, substitua **ip4** por **ip6** nos exemplos deste artigo. Você também pode especificar intervalos de endereços IP usando a notação CIDR, por exemplo, **ip4:192.168.0.1/26**.

- _IP address_ é o endereço IP que você deseja adicionar ao registro TXT SPF. Geralmente, esse é o endereço IP do servidor de email de saída da sua organização. É possível listar vários servidores de email de saída. Para obter mais informações, consulte [exemplo: registro txt SPF para vários servidores de email locais de saída e Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).

- _domain name_ é o domínio que você deseja adicionar como remetente legítimo. Para obter uma lista de nomes de domínio que você deve incluir no Microsoft 365, confira [registros DNS externos necessários para o SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).

- A regra de aplicação é geralmente uma das seguintes:

  - -all

    Indica falha irrecuperável. Se você conhece todos os endereços IP autorizados do seu domínio, liste-os no registro TXT SPF e use o qualificador -all (falha irrecuperável). Além disso, se estiver usando apenas o SPF, ou seja, se não estiver usando DMARC ou DKIM, você deverá usar o qualificador -all. Recomendamos que você sempre use esse qualificador.

  - ~all

    Indica falha recuperável. Se você não sabe se tem a lista completa de endereços IP, convém usar o qualificador ~all (falha recuperável). Além disso, se você estiver usando DMARC com p=quarantine ou p=reject, poderá usar ~all. Caso contrário, use -all.

  - ?all

    Indica neutralidade. Usado ao testar o SPF. Não recomendamos o uso desse qualificador na sua implantação dinâmica.

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>Exemplo: registro TXT SPF a ser usado quando todos os seus emails são enviados pelo Microsoft 365
<a name="ExampleSPFNoSP"> </a>

Se todos os seus emails forem enviados pela Microsoft 365, use-o em seu registro TXT SPF:

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>Exemplo: registro TXT SPF para um cenário híbrido com um Exchange Server local e o Microsoft 365
<a name="ExampleSPFHybridOneExchangeServer"> </a>

Em um ambiente híbrido, se o endereço IP do seu Exchange Server local for 192.168.0.1, para definir a regra de aplicação da SPF como falha irrecuperável, formule o registro TXT SPF da seguinte maneira:

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>Exemplo: registro TXT SPF para vários servidores de email locais de saída e Microsoft 365
<a name="ExampleSPFMultipleMailServerO365"> </a>

Se tiver vários servidores de saída de email, inclua o endereço IP de cada servidor de email no registro TXT SPF e separe cada endereço IP com um espaço seguido de um "ip4".declaração. Por exemplo:

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>Próximas etapas: configurar o SPF para o Microsoft 365
<a name="SPFNextSteps"> </a>

Depois de formular seu registro TXT SPF, siga as etapas em [Configurar o SPF no Microsoft 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md) de adicioná-lo ao seu domínio.

Embora o SPF tenha sido projetado para ajudar a evitar falsificação, existem técnicas de falsificação contra as quais o SPF não pode oferecer proteção. Para proteger-se contra elas, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365. Para começar, confira [usar DKIM para validar emails de saída enviados do seu domínio personalizado no Microsoft 365](use-dkim-to-validate-outbound-email.md). Em seguida, consulte [Usar DMARC para validar emails no Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>Solução de problemas: práticas recomendadas para SPF no Microsoft 365
<a name="SPFTroubleshoot"> </a>

Você só pode criar um registro TXT SPF para o seu domínio personalizado. A criação de vários registros causa uma situação de round robin e a falha do SPF. Para evitar isso, crie registros separados para cada subdomínio. Por exemplo, crie um registro para contoso.com e outro para bulkmail.contoso.com.

Se uma mensagem de email causar mais de 10 pesquisas de DNS antes de ser entregue, o servidor de email de recebimento responderá com um erro permanente, também chamado de  _permerror_, e fará com que a mensagem falhe na verificação do SPF. O servidor de recebimento também pode responder com uma NDR (notificação de falha na entrega) que contém um erro semelhante a estes:

- A mensagem excedeu a contagem de saltos.

- A mensagem exigiu muitas pesquisas.

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>Evitando o erro "muitas pesquisas" quando você usa domínios de terceiros com o Microsoft 365
<a name="SPFTroubleshoot"> </a>

Alguns registros TXT SPF de domínios de terceiros instruem o servidor de recebimento a realizar um grande número de pesquisas de DNS. Por exemplo, na ocasião da elaboração deste artigo, Salesforce.com contém cinco instruções de inclusão em seu registro:

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

Para evitar o erro, você pode implementar uma política na qual qualquer pessoa que enviar emails em massa, por exemplo, precisará usar um subdomínio especificamente para essa finalidade. Em seguida, você define um registro TXT SPF diferente para o subdomínio que inclui os emails em massa.

 Em alguns casos, como no exemplo salesforce.com, você precisa usar o domínio no seu registro TXT SPF, mas, em outros casos, terceiros podem já ter criado um subdomínio a ser usado para essa finalidade. Por exemplo, exacttarget.com criou um subdomínio que você precisa usar para o seu registro TXT SPF:

```text
cust-spf.exacttarget.com
```

Quando você inclui domínios de terceiros no seu registro TXT SPF, precisa confirmar com eles qual domínio ou subdomínio deve ser usado para evitar o limite de 10 pesquisas.

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>Como visualizar seu registro TXT SPF atual e determinar o número de pesquisas que ele exige
<a name="SPFTroubleshoot"> </a>

Você pode usar nslookup para visualizar seus registros DNS, incluindo seu registro TXT SPF. Ou, se preferir, há uma série de ferramentas online gratuitas disponíveis que você pode usar para visualizar o conteúdo do seu registro TXT SPF. Ao examinar seu registro TXT SPF e seguir a cadeia de redirecionamentos e instruções de inclusão, é possível determinar quantas pesquisas de DNS o registro exige. Algumas ferramentas online até mesmo contarão e exibirão essas pesquisas para você. Manter o controle desse número ajudará a evitar que mensagens enviadas da sua organização disparem um erro permanente, chamado de permerror, do servidor de recebimento.

## <a name="for-more-information"></a>Para obter mais informações
<a name="SPFTroubleshoot"> </a>

Precisa de ajuda para adicionar o registro TXT SPF? Leia o artigo [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) para obter informações detalhadas sobre o uso da estrutura de política de remetente com seu domínio personalizado no Microsoft 365. [Cabeçalhos de mensagens antispam](anti-spam-message-headers.md) inclui os campos de sintaxe e de cabeçalho usados pelo Microsoft 365 para verificações de SPF.


