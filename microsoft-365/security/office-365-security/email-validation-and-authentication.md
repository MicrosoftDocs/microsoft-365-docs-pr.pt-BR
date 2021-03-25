---
title: Autenticação de email no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Os administradores podem saber como o EOP usa autenticação de email (SPF, DKIM e DMARC) para ajudar a evitar falsificações, phishing e spam.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 633494717ad7cf68319a2332f435fd8b56fc8aeb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203085"
---
# <a name="email-authentication-in-eop"></a>Autenticação de e-mail no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


A autenticação de email (também conhecida como validação de email) é um grupo de padrões que tenta interromper a falsificação (mensagens de email de remetentes forjados). Em todas as organizações do Microsoft 365, o EOP usa estes padrões para verificar emails de entrada:

- [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [DKIM](use-dkim-to-validate-outbound-email.md)

- [DMARCDMARC](use-dmarc-to-validate-email.md)

A autenticação de email verifica se as mensagens de email de um remetente (por exemplo, laura@contoso.com) são legítimas e vêm de fontes esperadas para o domínio de email (por exemplo, contoso.com.)

O restante deste artigo explica como essas tecnologias funcionam e como o EOP as usa para verificar emails de entrada.

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>Use a autenticação de email para ajudar a impedir a falsificação

O DMARC impede falsificações ao examinar o endereço **De** nas mensagens. O endereço **De** é o endereço de email do remetente que os usuários veem em seus clientes de email. As organizações de email de destino também podem verificar se o domínio de email passou pelo SPF ou DKIM. Em outras palavras, o domínio foi autenticado e, portanto, o endereço de email do remetente não é falso.

No entanto, os registros DNS para SPF, DKIM e DMARC (chamados coletivamente como políticas de autenticação de email) são opcionais. Domínios com políticas fortes de autenticação de email, como o microsoft.com e o skype.com, estão protegidos contra falsificação. No entanto, os domínios com políticas de autenticação de email mais fracas, ou sem nenhuma política, são os principais alvos de falsificação.

Em março de 2018, apenas 9% dos domínios de empresas da lista Fortune 500 publicavam políticas fortes de autenticação de email. Os 91% restantes das empresas podem ser falsificados por um invasor. A menos que haja outro mecanismo de filtragem de email, os emails de remetentes falsificados nesses domínios podem ser entregues aos usuários.

![Políticas do DMARC de empresas da lista Fortune 500](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

A quantidade de pequenas e médias empresas que publicam políticas fortes de autenticação de email é menor. E o número é ainda menor para domínios de email fora da América do Norte e da Europa Ocidental.

A falta de políticas fortes de autenticação de email é um grande problema. Embora as organizações possam não entender como funciona a autenticação de email, os invasores entendem perfeitamente e tiram vantagem. Devido às preocupações com phishing e à adoção limitada de políticas fortes de autenticação de email, a Microsoft usa *autenticação implícita de email* para verificar os emails recebidos.

A autenticação implícita de email é uma extensão das políticas comuns de autenticação de email. Essas extensões incluem: reputação do remetente, histórico do remetente, histórico do destinatário, análise comportamental e outras técnicas avançadas. Na ausência de outros sinais dessas extensões, as mensagens enviadas de domínios que não usam políticas de autenticação de email serão marcadas como falsas.

Para ver o anúncio geral da Microsoft, confira [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).

## <a name="composite-authentication"></a>Autenticação composta

Se um domínio não tiver registros SPF, DKIM e DMARC tradicionais, essas verificações de registro não comunicarão informações suficientes sobre o status de autenticação. Portanto, a Microsoft desenvolveu um algoritmo para autenticação implícita de email. Esse algoritmo combina vários sinais em um único valor chamado de _autenticação composta_, ou abreviada como `compauth`. O valor `compauth` é marcado no cabeçalho **Resultados de Autenticação** nos cabeçalhos da mensagem.

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

Estes valores são explicados em [Resultados de autenticação do cabeçalho da mensagem](anti-spam-message-headers.md#authentication-results-message-header).

Ao examinar os cabeçalhos das mensagens, os administradores ou usuários finais podem determinar como o Microsoft 365 determinou que o remetente é falsificado.

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Por que a autenticação de email nem sempre é suficiente para impedir a falsificação

Confiar apenas nos registros de autenticação de email para determinar se uma mensagem de entrada é falsa tem as seguintes limitações:

- O domínio de envio pode não ter os registros DNS necessários, ou os registros estão configurados incorretamente.

- O domínio de origem configurou corretamente os registros DNS, mas esse domínio não corresponde ao domínio no endereço De. O SPF e o DKIM não exigem que o domínio seja usado no endereço De. Os invasores ou serviços legítimos podem registrar um domínio, configurar o SPF e o DKIM para o domínio, e usar um domínio completamente diferente no endereço De. As mensagens de remetentes neste domínio passarão pelo SPF e DKIM.

A autenticação composta pode solucionar essas limitações transmitindo mensagens que, de outra forma, falhariam nas verificações de autenticação de email.

Para simplificar, os exemplos a seguir se concentram nos resultados da autenticação de email. Outros fatores de inteligência de back-end poderiam identificar mensagens aprovadas na autenticação de email como falsas, ou mensagens reprovadas na autenticação de email como legítimas.

Por exemplo, o domínio fabrikam.com não possui registros SPF, DKIM ou DMARC. Mensagens de remetentes no domínio fabrikam.com podem ser reprovadas na autenticação composta (observe o valor `compauth` e o motivo):

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

Se o fabrikam.com configurar um SPF sem um registro DKIM, a mensagem poderá passar pela autenticação composta. O domínio que passou pelas verificações de SPF está alinhado com o domínio no endereço De:

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Se o fabrikam.com configurar um registro DKIM sem um registro SPF, a mensagem poderá passar pela autenticação composta. O domínio na assinatura DKIM está alinhado com o domínio no endereço De:

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

Se o domínio no SPF ou a assinatura DKIM não estiver alinhado com o domínio no endereço De, a mensagem poderá falhar na autenticação composta:

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>Soluções para remetentes legítimos que enviam emails não autenticados

O Microsoft 365 mantém o controle de quem está enviando emails não autenticados para sua organização. Se o serviço considerar que o remetente não é legítimo, ele marcará as mensagens desse remetente como uma falha de autenticação composta. Para evitar essa decisão, você pode usar as recomendações nesta seção.

### <a name="configure-email-authentication-for-domains-you-own"></a>Configure a autenticação de email para domínios que você possui

Você pode usar este método para solucionar problemas de falsificação dentro da organização e falsificação entre domínios nos casos em que você possui ou interage com vários locatários. Ele também ajuda a resolver a falsificação entre domínios que você envia para outros clientes no Microsoft 365 ou em terceiros que são hospedados por outros provedores.

- [Configurar registros SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) para seus domínios.

- [Configurar registros DKIM](use-dkim-to-validate-outbound-email.md) para seus domínios principais.

- [Considere configurar registros DMARC](use-dmarc-to-validate-email.md) para seu domínio para determinar seus remetentes legítimos.

A Microsoft não fornece diretrizes detalhadas de implementação para registros SPF, DKIM e DMARC. No entanto, há várias informações disponíveis online. Também há empresas de terceiros dedicadas a ajudar sua organização a configurar registros de autenticação de email.

#### <a name="you-dont-know-all-sources-for-your-email"></a>Você não conhece todas as fontes do seu email

Muitos domínios não publicam registros SPF porque não conhecem todas as fontes de email das mensagens em seu domínio. Comece publicando um registro SPF que contenha todas as fontes de email que você conhece (especialmente onde o seu tráfego corporativo está localizado) e publique a política neutra de SPF `?all`. Por exemplo:

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

Este exemplo significa que emails da sua infraestrutura corporativa passarão pela autenticação de email, mas emails de fontes desconhecidas voltarão à neutralidade.

O Microsoft 365 tratará os emails de entrada da infraestrutura corporativa como autenticado. Os emails de fontes não identificadas ainda poderão ser marcados como falsos se houver falhas na autenticação implícita. No entanto, isso ainda é uma melhoria em relação à situação em que todos os emails são marcados como falsificação pelo Microsoft 365.

Após começar a usar um registro SPF com a política de fallback `?all`, você poderá gradualmente descobrir e incluir mais fontes de email para suas mensagens e, em seguida, atualizar seu registro SPF com uma política mais rígida.

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>Use a inteligência contra falsificação para configurar remetentes permitidos de email não autenticado

Você também pode usar a [inteligência contra falsificação](learn-about-spoof-intelligence.md) para permitir que os remetentes transmitam mensagens não autenticadas para a sua organização.

Para domínios externos, o usuário falsificado é o domínio no endereço De, enquanto a infraestrutura de envio é o endereço IP de origem (dividido em intervalos /24 CIDR) ou o domínio organizacional do registro de DNS reverso (PTR).

Na captura de tela abaixo, o IP de origem pode ser 131.107.18.4 com o registro PTR outbound.mail.protection.outlook.com. Isso apareceria como outlook.com para a infraestrutura de envio.

Para permitir que esse remetente envie emails não autenticados, altere **No** para **Yes**.

![Configurar remetentes permitidos pela antifalsificação](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>Crie uma permissão de entrada para o par remetente/destinatário

Para ignorar a filtragem de spam, algumas partes da filtragem de phishing, mas não a filtragem de malware de remetentes específicos, confira [Criar listas de remetentes confiáveis no Microsoft 365](create-safe-sender-lists-in-office-365.md).

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>Peça ao remetente para configurar a autenticação de email para domínios que você não possui

Devido ao problema de spam e phishing, a Microsoft recomenda autenticação de email para todas as organizações de email. Em vez de configurar substituições manuais em sua organização, você pode pedir a um administrador no domínio de envio para configurar seus registros de autenticação de email.

- Mesmo que ele não tenha precisado publicar registros de autenticação de email no passado, ele deverá fazê-lo se enviar emails para a Microsoft.

- Configure o SPF para publicar os endereços IP de envio do domínio e configure o DKIM (se disponível) para assinar digitalmente as mensagens. Ele também deve considerar a criação de registros DMARC.

- Se ele usar remetentes em massa para enviar emails em seu nome, verifique se o domínio no endereço De (se pertencer a ele) está alinhado com o domínio que passa no SPF ou no DMARC.

- Verifique se os seguintes locais (se ele não os usar) estão incluídos no registro SPF:

  - Servidores de email no local.
  - Email enviado de um provedor de software como serviço (SaaS).
  - Email enviado de um serviço de hospedagem em nuvem (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).

- Para domínios pequenos hospedados por um ISP, configure o registro SPF de acordo com as instruções do ISP.

Embora inicialmente possa ser difícil enviar domínios para autenticação, com o passar do tempo, à medida que mais e mais filtros de email começarem a acumular ou até mesmo rejeitar seus emails, isso fará com que eles configurem os registros apropriados para melhorar a entrega. Além disso, sua participação pode ajudar no combate a phishing e reduzir a possibilidade de phishing em sua organização ou organizações para as quais ele envia emails.

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>Informações para provedores de infraestrutura (ISPs, ESPs ou serviços de hospedagem em nuvem)

Se você hospedar o email de um domínio ou fornecer uma infraestrutura de hospedagem que possa enviar emails, execute as seguintes etapas:

- Garanta que seus clientes tenham uma documentação que explique como eles devem configurar seus registros SPF

- Considere a inclusão de assinaturas DKIM nos emails de saída, mesmo que o cliente não os configure explicitamente (assine com um domínio padrão). Você pode até mesmo assinar duplamente o email com assinaturas DKIM (uma vez com o domínio do cliente, se ele estiver configurado, e uma segunda vez com a assinatura DKIM de sua empresa)

A capacidade de entrega para a Microsoft não é garantida, mesmo que você autentique emails originados de sua plataforma, mas pelo menos isso garante que a Microsoft não marque seu email como lixo eletrônico porque ele não está autenticado.

## <a name="related-links"></a>Links relacionados

Para obter mais informações sobre as práticas recomendadas dos provedores de serviços, confira [Práticas Recomendadas de Mensagens Móveis do M3AAWG para Provedores de Serviços](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).

Saiba como o Office 365 usa SPF e tem suporte para a validação DKIM:

- [Mais sobre SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [Mais sobre DKIM](support-for-validation-of-dkim-signed-messages.md)
