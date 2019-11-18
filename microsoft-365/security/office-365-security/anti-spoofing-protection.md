---
title: Proteção antifalsificação no Office 365
ms.author: tracyp
author: MSFTtracyp
manager: dansimp
ms.date: 08/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Este artigo descreve como o Office 365 mitiga ataques de phishing que usam domínios de remetentes forjados, ou seja, domínios falsificados. Isso é feito analisando as mensagens e bloqueando as que não podem ser autenticadas com métodos de autenticação de email padrão nem outras técnicas de reputação de remetente. Essa alteração foi implementada para reduzir o número de ataques de phishing aos quais as organizações do Office 365 estão expostas.
ms.openlocfilehash: d435df901bf460c58a5b49e82458be1d6cf39eaf
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640800"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Proteção antifalsificação no Office 365

Este artigo descreve como o Office 365 mitiga ataques de phishing que usam domínios de remetentes forjados, ou seja, domínios falsificados. Isso é feito analisando as mensagens e bloqueando as que não podem ser autenticadas com métodos de autenticação de email padrão nem outras técnicas de reputação de remetente. Essa alteração foi implementada para reduzir o número de ataques de phishing aos quais as organizações do Office 365 estão expostas.
  
Este artigo também descreve por que essa alteração está sendo feita, como os clientes podem se preparar para a alteração, como exibir mensagens que serão afetadas, como enviar relatórios sobre mensagens, como reduzir a ocorrência de falsos positivos e como os remetentes para a Microsoft devem se preparar para essa alteração.
  
A tecnologia antifalsificação da Microsoft foi implantada inicialmente nas organizações da empresa que tinham uma assinatura do Office 365 Enterprise E5 ou que tinham o complemento ATP (Proteção Avançada contra Ameaças) do Office 365 na assinatura. Desde outubro de 2018, estendemos a proteção para organizações que também têm a EOP (Proteção do Exchange Online). Além disso, devido à maneira como todos os nossos filtros aprendem uns com os outros, os usuários do Outlook.com também podem ser afetados.
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Como a falsificação é usada em ataques de phishing

Quando se trata de proteger os usuários, a Microsoft leva a sério a ameaça de phishing. Uma das técnicas usadas por spammers e phishers é a falsificação, que é quando o remetente é forjado e uma mensagem parece se originar de alguém ou algum outro lugar que não seja a fonte atual. Essa técnica é frequentemente usada em campanhas de phishing criadas para obter credenciais de usuários. A tecnologia antifalsificação da Microsoft analisa especificamente a falsificação do "cabeçalho De:", que é o que aparece em um cliente de email como o Outlook. Quando a Microsoft tem alta confiança de que o cabeçalho De: é falsificado, identifica a mensagem como uma falsificação.
  
As mensagens falsificadas têm duas implicações negativas para os usuários da vida real:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. As mensagens falsificadas enganam os usuários
  
Primeiro, uma mensagem falsificada pode induzir o usuário a clicar em um link e fornecer as credenciais, baixar malware ou responder a uma mensagem com conteúdo confidencial (essa última situação é conhecida como Comprometimento de Email Empresarial). Por exemplo, a seguir está uma mensagem de phishing com o remetente falsificado msoutlook94@service.outlook.com:
  
![Mensagem de phishing se passando por service.outlook.com](../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
O exemplo acima não veio realmente de service.outlook.com. Em vez disso, foi falsificado pelo phisher para parecer que veio. Está tentando enganar um usuário para clicar no link na mensagem.
  
O próximo exemplo está falsificando contoso.com:
  
![Mensagem de phishing ‒ comprometimento de email empresarial](../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
A mensagem parece legítima, mas na verdade é uma falsificação. Essa mensagem de phishing é um tipo de Comprometimento de Email Empresarial, que é uma subcategoria de phishing.

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. Os usuários confundem as mensagens reais com as falsas
  
Em segundo lugar, as mensagens falsificadas criam incerteza para os usuários que sabem da existência de mensagens de phishing, mas não conseguem distinguir entre uma mensagem real e uma falsificada. Por exemplo, a seguir há uma redefinição de senha real do endereço de email da conta de Segurança da Microsoft:
  
![Redefinição de senha da Microsoft legítima](../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
A mensagem acima veio da Microsoft, mas, ao mesmo tempo, os usuários estão acostumados a receber mensagens de phishing que podem enganá-los para clicar em um link e fornecer credenciais, baixar malware ou responder a uma mensagem com conteúdo confidencial. Como é difícil distinguir entre uma redefinição de senha real e uma falsa, muitos usuários ignoram essas mensagens, as relatam como spam ou desnecessariamente à Microsoft como tentativas de phishing perdidas.

Para impedir a falsificação, o setor de filtragem de email desenvolveu protocolos de autenticação de email, como [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) e [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). O DMARC impede que falsificações examinem o remetente de uma mensagem. Ou seja, o remetente que os usuários veem em seus clientes de email (nos exemplos acima, são o service.outlook.com, o outlook.com e o accountprotection.microsoft.com). Além disso, os usuários também podem ver se o domínio já passou no SPF ou no DKIM, o que significa que o domínio foi autenticado e, portanto, não é falso. Para uma discussão mais completa, confira a seção "*Entender por que a autenticação de email nem sempre é suficiente para impedir a falsificação"* mais adiante neste artigo.
  
No entanto, o problema é que os registros de autenticação de email são opcionais, não obrigatórios. Portanto, embora domínios com políticas de autenticação fortes, como microsoft.com e skype.com, sejam protegidos contra falsificação, domínios que publicam políticas de autenticação mais fracas ou nenhuma política são alvo de falsificação. Em março de 2018, apenas 9% dos domínios de empresas da lista Fortune 500 publicavam políticas de autenticação de email fortes. Os 91% restantes podem ser falsificados por um phisher e, a menos que o filtro de email os detecte usando outra política, podem ser entregues a um usuário final e enganá-lo:
  
![Políticas do DMARC de empresas da lista Fortune 500](../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
A proporção de pequenas e médias empresas que não fazem parte da lista Fortune 500 e que publicam políticas de autenticação de email fortes é menor, sendo ainda menor para domínios fora da América do Norte e da Europa Ocidental.
  
Esse é um grande problema porque, embora as empresas possam não estar cientes de como a autenticação de email funciona, os phishers entendem e aproveitam a falta dela.
  
Para obter informações sobre como configurar o SPF, o DKIM e o DMARC, confira a seção "*Clientes do Office 365"*, mais adiante neste documento. 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>Impedir a falsificação com a autenticação de email implícita

Como o phishing e o spear phishing são um problema muito sério, e devido à adoção limitada de políticas de autenticação de email fortes, a Microsoft continua investindo em recursos para proteger os clientes. Portanto, a Microsoft está progredindo com a *autenticação de email implícita*. Se um domínio não for autenticado, a Microsoft o tratará como se como se ele tivesse publicado registros de autenticação de email e o tratará da maneira apropriada, se não for aprovado. 
  
Para isso, a Microsoft criou várias extensões para a autenticação regular de emails, incluindo a reputação do remetente, o histórico do remetente/destinatário, a análise comportamental e outras técnicas avançadas. Uma mensagem enviada de um domínio que não publica a autenticação de email será marcada como falsificação, a menos que contenha outros sinais para indicar que é legítima.
  
Dessa forma, os usuários finais podem saber com confiança que um email não foi falsificado, os remetentes podem ter certeza de que ninguém está fingindo ser o domínio deles e os clientes do Office 365 podem oferecer proteção ainda melhor, como a proteção contra falsificação de identidade.
  
Para ver o comunicado geral da Microsoft, confira [Um mar de phishing, parte 2 ‒ antifalsificação aprimorada no Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>Identificar que uma mensagem foi classificada como falsificada

### <a name="composite-authentication"></a>Autenticação composta

Embora o SPF, o DKIM e o DMARC sejam úteis por si só, não comunicam um status de autenticação suficiente caso uma mensagem não tenha registros de autenticação explícitos. Portanto, a Microsoft desenvolveu um algoritmo que combina vários sinais em um único valor chamado Autenticação Composta, abreviada como compauth. Os clientes no Office 365 têm valores compartilhados marcados no cabeçalho *Authentication-Results* nos cabeçalhos das mensagens. 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**Resultado de CompAuth**|**Descrição**|
|:-----|:-----|
|fail|A mensagem foi reprovada na autenticação explícita (envio de registros publicados no domínio explicitamente no DNS) ou autenticação implícita (o domínio de envio não publicou registros no DNS, assim, o Office 365 interpolou o resultado como se tivesse registros publicados).|
|pass|A mensagem foi aprovada na autenticação explícita (a mensagem foi aprovada no DMARC ou [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) ou autenticação implícita com alta confiança (o domínio de envio não publica registros de autenticação de email, mas o Office 365 tem sinais de back-end fortes para indicar que a mensagem é provavelmente legítima).|
|softpass|A mensagem foi aprovada na autenticação implícita com confiança de baixa a média (o domínio de envio não publica a autenticação de email, mas o Office 365 tem sinais de back-end para indicar que a mensagem é legítima, embora a intensidade do sinal seja mais fraca).|
|nenhuma|A mensagem não foi autenticada (ou foi autenticada, mas não foi alinhada), mas a autenticação composta não foi aplicada devido à reputação do remetente ou a outros fatores.|
   
|||
|:-----|:-----|
|**Motivo**|**Descrição**|
|0xx |A mensagem foi reprovada na autenticação composta.<br/>**000** significa que a mensagem foi reprovada no DMARC com uma ação de rejeição ou quarentena.  <br/>**001** significa que a mensagem foi reprovada na autenticação de email implícita. Isso significa que o domínio de envio não tinha registros de autenticação de email publicados ou, se os tinha, eles usavam uma política de falha mais fraca (falha não grave do SPF ou neutra; política do DMARC de p=nenhum).  <br/>**002** significa que a organização tem uma política para o par remetente/domínio, que é explicitamente proibido de enviar emails falsificados. Essa configuração é definida manualmente por um administrador.  <br/>**010** significa que a mensagem foi reprovada no DMARC com uma ação de rejeição ou quarentena, e o domínio de envio é um dos domínios aceitos de sua organização (isso faz parte da falsificação self-to-self ou dentro da organização). <br/> |
|1xx, 2xx, 3xx, 4xx e 5xx|Corresponde a vários códigos internos que indicam o motivo pelo qual uma mensagem foi aprovada na autenticação implícita ou não teve autenticação, mas nenhuma ação foi aplicada.|
|6xx|Significa que a mensagem foi reprovada na autenticação de email implícita e o domínio de envio é um dos domínios aceitos de sua organização (isso faz parte da falsificação self-to-self ou dentro da organização).|

Examinando os cabeçalhos de uma mensagem, um administrador ou até mesmo um usuário final pode determinar como o Office 365 chega à conclusão de que o remetente pode ser falsificado.
  
### <a name="differentiating-between-different-types-of-spoofing"></a>Diferenciar os tipos de falsificação

A Microsoft diferencia dois tipos de mensagens de falsificação:
  
 **Falsificação dentro da organização**
  
Também conhecida como falsificação self-to-self, ocorre quando o domínio no endereço De: é igual ou está alinhado ao domínio do destinatário (quando o domínio do destinatário é um dos [Domínios Aceitos](https://technet.microsoft.com/library/jj945194%28v=exchg.150%29.aspx) de sua organização) ou quando o domínio no endereço De: faz parte da mesma organização.
  
O exemplo a seguir tem remetente e destinatário do mesmo domínio (contoso.com). Espaços são inseridos no endereço de email para evitar a coleta de spambot na página):
  
De: remetente @ contoso.com
  
Para: destinatário @ contoso.com
  
No seguinte exemplo, os domínios de remetente e destinatário estão alinhados com o domínio organizacional (fabrikam.com):
  
De: remetente @ foo.fabrikam.com
  
Para: destinatário @ bar.fabrikam.com
  
No seguinte exemplo, os domínios de remetente e destinatário são diferentes (microsoft.com e bing.com), mas pertencem à mesma organização (ou seja, ambos fazem parte dos Domínios Aceitos da organização):
  
De: remetente @ microsoft.com
  
Para: destinatário @ bing.com
  
As mensagens reprovadas na falsificação dentro da organização contêm os seguintes valores nos cabeçalhos:
  
X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11
  
CAT é a categoria da mensagem, normalmente carimbada como SPM (spam), mas ocasionalmente pode ser HSPM (spam de alta confiança) ou PHISH (phishing), dependendo de quais outros tipos de padrões ocorrem na mensagem.
  
SFTY é o nível de segurança da mensagem. O primeiro dígito (9) significa que se trata de uma mensagem de phishing, e o segundo conjunto de dígitos após o ponto (11) significa que é uma falsificação dentro da organização.
  
Não há um código de razão específico de Autenticação Composta para falsificação dentro da organização. Ela será marcada mais tarde em 2018 (a linha do tempo ainda não está definida).
  
 **Falsificação entre domínios**
  
Isso ocorre quando o domínio de envio no endereço De: é um domínio externo à organização receptora. Mensagens que são reprovadas na Autenticação Composta devido a falsificação entre domínios contêm os seguintes valores nos cabeçalhos:
  
Authentication-Results: … compauth=fail reason=000/001
  
X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22
  
Em ambos os casos, a seguinte dica de segurança vermelha está marcada na mensagem ou há um equivalente que é personalizado para o idioma da caixa de correio do destinatário:
  
![Dica de segurança vermelha ‒ detecção de fraudes](../media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
É apenas observando o endereço De: e sabendo qual é o email do destinatário ou inspecionando os cabeçalhos de email que você pode diferenciar entre falsificação dentro da organização e entre domínios.
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Como os clientes do Office 365 podem se preparar para a nova proteção antifalsificação

### <a name="information-for-administrators"></a>Informações para administradores

Como administrador de uma organização no Office 365, há várias informações importantes que você deve conhecer.
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>Entender por que a autenticação de email nem sempre é suficiente para impedir a falsificação

A nova proteção antifalsificação depende da autenticação de email (SPF, DKIM e DMARC) para não marcar uma mensagem como falsificada. Um exemplo comum é quando um domínio de envio nunca publicou registros SPF. Se não houver registros SPF ou eles estiverem configurados incorretamente, uma mensagem enviada será marcada como falsificada, a menos que a Microsoft tenha inteligência de back-end para informar que a mensagem é legítima.
  
Por exemplo, antes de a antifalsificação ser implantada, uma mensagem pode ter a seguinte aparência, sem nenhum registro SPF, nenhum registro DKIM e nenhum registro DMARC: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
Após a antifalsificação, se você tiver o Office 365 Enterprise E5, EOP ou ATP, o valor de compauth será marcado:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

Se example.com corrigiu isso configurando um registro SPF, mas não um registro DKIM, isso seria aprovado pela autenticação composta porque o domínio aprovado no SPF estava alinhado com o domínio no endereço De: 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

Ou, caso tenha sido configurado um registro DKIM, mas não um registro SPF, isso também será aprovado na autenticação composta porque o domínio na Assinatura DKIM aprovada estava alinhado com o domínio no endereço De: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

No entanto, um phisher também pode configurar o SPF e o DKIM e assinar a mensagem com seu próprio domínio, mas especificar um domínio diferente no endereço De:. O SPF e o DKIM não exigem que o domínio se alinhe com o domínio no endereço De:. Portanto, a menos que example.com tenha publicado registros DMARC, isso não será marcado como uma falsificação usando DMARC: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

No cliente de email (Outlook, Outlook na Web ou qualquer outro cliente de email), apenas o domínio De: é exibido, não o domínio no SPF ou DKIM. Isso pode induzir o usuário a pensar que a mensagem veio de example.com, mas na verdade, ela veio de maliciousDomain.com.
  
![A mensagem foi autenticada, mas o domínio De: não está alinhado com o que foi aprovado no SPF ou no DKIM](../media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
Por esse motivo, o Office 365 exige que o domínio no endereço De: se alinhe com o domínio na assinatura SPF ou DKIM e, se ele não se alinhar, que contenha alguns outros sinais internos que indiquem que a mensagem é legítima. Caso contrário, a mensagem será reprovada em compauth. 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

Portanto, a antifalsificação do Office 365 protege contra domínios sem autenticação e contra domínios que configuram a autenticação, mas não correspondem ao domínio no endereço De: porque ele é o que o usuário vê e acredita ser o remetente da mensagem. Isso vale para is domínios externos à sua organização e para os domínios dela.
  
Portanto, se você receber uma mensagem que foi reprovada na autenticação composta e está marcada como falsificada, mesmo que a mensagem tenha sido aprovada no SPF e no DKIM, é porque o domínio que foi aprovado no SPF e no DKIM não está alinhado com o domínio no endereço De:.
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>Entender as alterações na maneira como os emails falsificados são tratados

Atualmente, para todas as organizações no Office 365 (com e sem ATP), as mensagens reprovadas no DMARC com uma política de rejeição ou quarentena são marcadas como spam e geralmente são submetidas à ação de spam de alta confiança ou, às vezes, à ação de spam regular (dependendo de outras regras de spam as identificarem primeiro como spam). Detecções de spoofs dentro da organização levam à ação regular de spam. Esse comportamento não precisa ser habilitado nem pode ser desabilitado.
  
No entanto, para mensagens de spoofing entre domínios, antes dessa alteração, elas passariam por verificações regulares de spam, phishing e malware, e se outras partes do filtro as identificassem como suspeitas, seriam marcadas como spam, phishing ou malware, respectivamente. Com a nova proteção contra falsificação entre domínios, qualquer mensagem que não puder ser autenticada será submetida, por padrão, à ação definida na política Antiphishing \> Antifalsificação. Se não houver uma definida, ela será movida para uma pasta Lixo Eletrônico do usuário. Em alguns casos, mensagens mais suspeitas também terão a dica de segurança vermelha adicionada a elas.
  
Isso pode fazer com que algumas mensagens marcadas anteriormente como spam continuem sendo marcadas assim, mas agora elas também terão uma dica de segurança vermelha. Em outros casos, as mensagens marcadas como não spam começarão a ser marcadas como spam (CAT:SPOOF), com uma dica de segurança vermelha adicionada. Em outros casos, os clientes que estavam movendo todos os itens de spam e phishing para a quarentena agora os verão na Pasta de Lixo Eletrônico (esse comportamento pode ser alterado; confira [Alterar suas configurações antifalsificação](#changing-your-anti-spoofing-settings)).
  
Há várias maneiras diferentes de falsificar uma mensagem (confira [Diferenciar entre tipos de falsificação](#differentiating-between-different-types-of-spoofing) anteriormente neste artigo), mas, em março de 2018, a maneira como o Office 365 trata essas mensagens ainda não está unificada. A tabela a seguir é um resumo rápido, em que a proteção contra falsificação entre domínios é um novo comportamento: 
  
|**Tipo de falsificação**|**Categoria**|**Dica de segurança adicionada?**|**Aplica-se a**|
|:-----|:-----|:-----|:-----|
|Reprovação no DMARC (quarentena ou rejeição)  <br/> |HSPM (padrão); também pode ser SPM ou PHSH  <br/> |Não (ainda não)  <br/> |Todos os clientes do Office 365, Outlook.com  <br/> |
|Self-to-self  <br/> |SPM  <br/> |Sim  <br/> |Todas as organizações do Office 365, Outlook.com  <br/> |
|Entre domínios  <br/> |SPOOF  <br/> |Sim  <br/> |Clientes da Proteção Avançada contra Ameaças do Office 365 e E5  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>Alterar suas configurações antifalsificação

Para criar ou atualizar suas configurações antifalsificação (entre domínios), navegue até as configurações Antiphishing \> Antifalsificação na guia Política do Gerenciamento de Ameaças \> no Centro de Conformidade &amp; Segurança. Se você nunca tiver criado uma configuração antiphishing, será necessário criar uma:
  
![Antiphishing ‒ criar uma nova política](../media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
Se já tiver criado uma, você poderá selecioná-la para modificá-la:
  
![Antiphishing ‒ modificar uma política existente](../media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
Selecione a política que você acabou de criar e siga as etapas descritas em [Saiba mais sobre a falsificação de informações](learn-about-spoof-intelligence.md).
  
![Habilitar ou desabilitar a antifalsificação](../media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![Habilitar ou desabilitar dicas de segurança de antifalsificação](../media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
Para criar uma nova política usando o PowerShell: 
  
```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

Você pode modificar os parâmetros da política antiphishing usando o PowerShell, seguindo a documentação em [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). Você pode especificar $name como parâmetro:
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

Mais adiante em 2018,em vez de você ter que criar uma política padrão, ela será criada para você com escopo para todos os destinatários de sua organização. Assim, você não precisará especificá-la manualmente (as capturas de tela a seguir estão sujeitas a alterações antes da implementação final).
  
![Política antiphishing padrão](../media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
Diferentemente de uma política que você cria, não é possível excluir a política padrão, modificar sua prioridade ou escolher quais usuários, domínios ou grupos estão no escopo para ela.
  
![Detalhes da política antiphishing padrão](../media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
Para configurar sua proteção padrão usando o PowerShell:
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

Você só deverá desabilitar a proteção antifalsificação se tiver outro servidor de email ou servidores na frente do Office 365 (confira Cenários legítimos para desabilitar a antifalsificação para obter mais detalhes).
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> Se o primeiro salto no caminho de email for o Office 365 e você estiver recebendo muitos emails legítimos marcados como falsificação, primeiro configure os remetentes com permissão para enviar e-mails falsificados para seu domínio (confira a seção *"Gerenciar remetentes legítimos que estão enviando emails não autenticados"*). Se você ainda está recebendo muitos falsos positivos (ou seja, mensagens legítimas marcadas como falsificação), NÃO recomendamos desabilitar a proteção antifalsificação. Em vez disso, recomendamos escolher a proteção Básica em vez de Alta. É melhor trabalhar com falsos positivos do que expor sua organização a emails falsificados, o que poderia acabar acarretando custos significativamente mais altos em longo prazo.

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>Gerenciar remetentes legítimos que estão enviando emails não autenticados

O Office 365 mantém o controle de quem está enviando emails não autenticados para sua organização. Se o serviço achar que o remetente não é legítimo, ele será marcado como uma falha de *compauth*. Isso será classificado como SPOOF, embora dependa da política antifalsificação aplicada à mensagem.
  
No entanto, como administrador, você pode especificar quais remetentes têm permissão para enviar emails falsificados, substituindo a decisão do Office 365.
  
**Método 1 ‒ se sua organização possui o domínio, configure a autenticação de email**
  
Esse método pode ser usado para resolver o spoofing dentro da organização e o spoofing entre domínios, nos casos em que você possui ou interage com vários locatários. Também ajuda a resolver a falsificação entre domínios, em que você envia a outros clientes no Office 365 e também a terceiros hospedados em outros provedores.
  
Para obter mais detalhes, confira [Clientes do Office 365](#customers-of-office-365).

**Método 2 ‒ use a Inteligência contra Falsificação para configurar os remetentes permitidos de emails não autenticados**
  
Você também pode usar a [Inteligência contra Falsificação](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) para permitir que os remetentes transmitam mensagens não autenticadas para sua organização. 
  
Para domínios externos, o usuário falsificado é o domínio no endereço De, enquanto a infraestrutura de envio é o endereço IP de envio (dividido em /24 intervalos CIDR) ou o domínio organizacional do registro PTR (na captura de tela a seguir, o IP de envio pode ser 131.107.18.4, cujo registro PTR é outbound.mail.protection.outlook.com, e isso seria exibido como outlook.com para a infraestrutura de envio).
  
Para permitir que esse remetente envie emails não autenticados, altere **No** para **Yes**.
  
![Configurar remetentes permitidos pela antifalsificação](../media/d4334921-d820-4334-8217-788279701e94.jpg)
  
Você também pode usar o PowerShell para permitir que um remetente específico falsifique seu domínio:
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![Obter remetentes falsificados do PowerShell](../media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
Na imagem anterior, foram adicionadas quebras de linha para ajustar a captura de tela. Normalmente, todos os valores apareceriam em uma única linha.
  
Edite o arquivo, procure a linha que corresponde a outlook.com e bing.com e altere a entrada AllowedToSpoof de No para Yes:
  
![Definir spoof allow como Yes no PowerShell](../media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
Salve o arquivo e execute:
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

Agora isso permitirá que bing.com envie emails não autenticados de \*.outlook.com.

**Método 3 ‒ crie uma entrada de permissão para o par emissor/destinatário**
  
Você também pode optar por ignorar toda a filtragem de spam para determinado remetente. Para obter mais detalhes, confira [Como adicionar com segurança um remetente a uma lista de permissões no Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).
  
Se você usar esse método, ele ignorará o spam e alguns dos filtros de phishing, mas não a filtragem de malware.
  
**Método 4 ‒ entre em contato com o remetente e peça que ele configure a autenticação de email**
  
Devido ao problema de spam e phishing, a Microsoft recomenda que todos os remetentes configurem a autenticação de email. Se você conhece um administrador do domínio de envio, entre em contato com ele e solicite que ele configure registros de autenticação de email para que você não precise adicionar nenhuma substituição. Para obter mais informações, confira [Administradores de domínios que não são clientes do Office 365](#administrators-of-domains-that-are-not-office-365-customers) mais adiante neste artigo. 
  
Embora inicialmente possa ser difícil enviar domínios para autenticação, com o passar do tempo, à medida que mais e mais filtros de email começarem a acumular ou até mesmo rejeitar seus emails, isso fará com que eles configurem os registros apropriados para melhorar a entrega.
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>Exibir relatórios de quantas mensagens foram marcadas como falsificadas

Depois que a política antifalsificação estiver habilitada, você poderá usar os recursos de resposta e investigação de ameaça para obter o número de mensagens marcadas como phishing. Para fazer isso, vá até o Centro de Conformidade &amp; Segurança, em Gerenciamento de Ameaças \> Explorer, defina a Exibição como Phish e agrupe por Domínio de Remetente ou Status de Proteção:
  
![Exibir quantas mensagens estão marcadas como phishing](../media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
Você pode interagir com vários relatórios para ver quantas foram marcadas como phishing, inclusive mensagens marcadas como FALSAS. Para saber mais, confira [Introdução à resposta e investigação de ameaças do Office 365](office-365-ti.md).
  
Você ainda não pode separar as mensagens que foram marcadas devido à falsificação de outros tipos de phishing (phishing geral, representação de domínio ou usuário e assim por diante). No entanto, mais tarde, você poderá fazer isso por meio do Centro de Conformidade &amp; Segurança. Depois disso, você poderá usar esse relatório como ponto de partida para identificar domínios de envio que possam ser legítimos e que estejam sendo marcados como falsificação devido a falhas na autenticação.
  
A captura de tela a seguir é uma proposta da aparência que esses dados terão, mas eles poderão mudar quando forem lançados:
  
![Exibir relatórios de phishing por tipo de detecção](../media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
Para clientes não ATP e E5, esses relatórios estarão disponíveis mais tarde nos relatórios de TPS (Status de Proteção contra Ameaças), mas serão atrasados em pelo menos 24 horas. Essa página será atualizada à medida que eles forem integrados ao Centro de Conformidade &amp; Segurança.
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>Prever quantas mensagens serão marcadas como falsas

Depois que o Office 365 atualizar suas configurações para permitir que você ative ou desative a imposição de antifalsificação com a imposição Básica ou Alta, você poderá ver como a disposição da mensagem será alterada nas várias configurações. Ou seja, se a antifalsificação estiver desativada, você poderá ver quantas mensagens serão detectadas como Falsas se você ativar a opção Básica. Se ela for Básica, você poderá ver quantas outras mensagens serão detectadas como Falsas se você mudar para a opção Alta.
  
No momento esse recurso está em desenvolvimento. À medida que mais detalhes forem definidos, essa página será atualizada com capturas de tela do Centro de Segurança e Conformidade e com exemplos do PowerShell.
  
![Relatório "What If" para habilitar a antifalsificação](../media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![Possível experiência do usuário para permitir um remetente falsificado](../media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>Cenários legítimos para desabilitar a antifalsificação

A antifalsificação protege melhor os clientes contra ataques de phishing. Portanto, a desabilitação da proteção antifalsificação é altamente desencorajada. Se a desabilitar, você poderá resolver alguns falsos positivos de curto prazo, mas estará exposto a mais riscos em longo prazo. O custo da configuração da autenticação no lado do remetente ou dos ajustes nas políticas de phishing geralmente envolve eventos únicos ou apenas manutenção mínima e periódica. No entanto, o custo para se recuperar de um ataque de phishing em que os dados foram expostos ou os ativos foram comprometidos é muito maior.
  
Por esse motivo, é melhor trabalhar com falsos positivos antifalsificação do que desabilitar a proteção antifalsificação.
  
No entanto, há um cenário legítimo em que a antifalsificação deve ser desabilitada. É quando há produtos adicionais de filtragem de mensagens no roteamento de mensagens, e o Office 365 não é o primeiro salto no caminho de email:
  
![O registro MX do cliente não aponta para o Office 365](../media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
O outro servidor pode ser um servidor de correio local do Exchange, um dispositivo de filtragem de email, como o Ironport, ou outro serviço hospedado na nuvem.
  
Se o registro MX do domínio do destinatário não apontar para o Office 365, não será necessário desabilitar a antifalsificação porque o Office 365 procura o registro MX do domínio de recebimento e suprime a antifalsificação se ela aponta para outro serviço. Se você não sabe se seu domínio tem outro servidor diante dele, poderá usar um site como o MX Toolbox para pesquisar o registro MX. Ele poderá dizer algo como:
  
![O registro indica que o domínio não aponta para o Office 365](../media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
Esse domínio tem um registro MX que não aponta para o Office 365. Portanto, o Office 365 não aplicaria a imposição antifalsificação.
  
No entanto, se o registro MX do domínio do destinatário *apontar* para o Office 365, mesmo que haja outro serviço diante do Office 365, você deverá desabilitar a antifalsificação. O exemplo mais comum é com o uso de uma reescrita de destinatário: 
  
![Diagrama de roteamento para reescrita do destinatário](../media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
O registro MX do domínio contoso.com aponta para o servidor local, enquanto o registro MX do domínio @office365.contoso.net aponta para o Office 365 porque contém \*.protection.outlook.com ou \*.eo.outlook.com no registro MX:
  
![O registro MX aponta para o Office 365. Portanto, provavelmente será necessária a reescrita do destinatário](../media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
Diferencie quando o registro MX de um domínio de destinatário não aponta para o Office 365 e quando ele foi submetido a uma reescrita de destinatário. É importante saber a diferença entre esses dois casos.
  
Se você não tem certeza se seu domínio de recebimento foi ou não submetido a uma reescrita de destinatário, às vezes é possível determinar isso examinando os cabeçalhos das mensagens.
  
a) Primeiro, examine os cabeçalhos na mensagem do domínio do destinatário no cabeçalho Authentication-Results:
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

O domínio do destinatário é encontrado no texto em negrito acima; neste caso, é office365.contoso.net. Isso pode ser diferente do destinatário no cabeçalho Para:
  
Para: Exemplo de Destinatário \<destinatário @ contoso.com\>
  
Execute uma pesquisa de registro MX do domínio real do destinatário. Se ele contiver \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com ou mail.global.frontbridge.com, isso indicará que o MX aponta para o Office 365.
  
Se não contiver esses valores, isso indicará que o MX não aponta para o Office 365. Uma ferramenta que você pode usar para verificar isso é o MX Toolbox.
  
Para esse exemplo específico, o seguinte item informa que contoso.com, o domínio que parece ser do destinatário, já que era o cabeçalho Para:, tem um registro MX que aponta para um servidor local:
  
![O registro MX aponta para o servidor local](../media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
No entanto, o destinatário real é office365.contoso.net, cujo registro MX aponta para o Office 365:
  
![O MX aponta para o Office 365; deve ser executada a reescrita do destinatário](../media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
Portanto, essa mensagem provavelmente foi submetida à reescrita de destinatário.
  
b) Em segundo lugar, diferencie os casos de uso comum de reescrita de destinatários. Se você vai reescrever o domínio do destinatário para \*.onmicrosoft.com, em vez disso, reescreva-o para \*.mail.onmicrosoft.com.
  
Após identificar o domínio do destinatário final roteado por trás de outro servidor e verificar se o registro MX do domínio do destinatário realmente aponta para o Office 365 (conforme publicado em seus registros DNS), você pode desabilitar a antifalsificação.
  
Lembre-se: você não deverá desabilitar a antifalsificação se o primeiro salto do domínio no caminho de roteamento for o Office 365, mas somente quando ele estiver por trás de um ou mais serviços.
  
### <a name="how-to-disable-anti-spoofing"></a>Como desabilitar a antifalsificação

Se você já tiver criado uma política antiphishing, defina o parâmetro EnableAntispoofEnforcement como $false:
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

Se você não souber o nome da(s) política(s) a ser(em) desabilitada(s), poderá exibi-la(s):
  
```
Get-AntiphishPolicy | fl Name
```

Se não tiver políticas antiphishing, você poderá criar uma e desabilitá-la (mesmo que você não tenha uma política, a antifalsificação ainda será aplicada; mais adiante em 2018, uma política padrão será criada e você poderá então desabilitá-la em vez de criar uma). Você terá que fazer isso em várias etapas:
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

A desabilitação da antifalsificação está disponível apenas via cmdlet (mais tarde, ele estará disponível no Centro de Conformidade &amp; Segurança). Se você não tiver acesso ao PowerShell, crie um tíquete de suporte.
  
Lembre-se: isso só deve ser aplicado a domínios que passam por roteamento indireto quando enviados para o Office 365. Resista à tentação de desativar a antifalsificação por causa de alguns falsos positivos. Em longo prazo, será melhor lidar com eles.
  
### <a name="information-for-individual-users"></a>Informações para usuários individuais

Há limitações na maneira como usuários individuais podem interagir com a dica de segurança antifalsificação. No entanto, há várias coisas que você pode fazer para resolver cenários comuns.
 
### <a name="common-scenario-1---discussion-lists"></a>Cenário comum nº 1 ‒ Listas de discussão

Sabe-se que as listas de discussão têm problemas com a antifalsificação, devido à maneira como encaminham mensagens e modificam o conteúdo, mas mantêm o endereço De: original.
  
Por exemplo, suponha que seu endereço de email seja usuario@contoso.com e você esteja interessado em Observação de Pássaros e participe da lista de discussão observacaodepassaros@example.com. Quando você envia uma mensagem para a lista de discussão, pode enviá-la desta maneira:
  
**De:** Carlos Lima \<usuario @ contoso.com\> 
  
**Para:** Lista de Discussão de Observação de Pássaros \<observacaodepassaros @ example.com\> 
  
**Assunto:** Belo exemplo de gaios azuis no topo do Monte Rainier esta semana 
  
Alguém quer conferir esta semana a vista do Monte Rainier?
  
Quando a lista de email recebe a mensagem, a formata, modifica seu conteúdo e a reproduz para o restante dos membros da lista de discussão, composta de participantes de vários destinatários de email diferentes.
  
**De:** Carlos Lima \<usuario @ contoso.com\> 
  
**Para:** Lista de Discussão de Observação de Pássaros \<observacaodepassaros @ example.com\> 
  
**Assunto:** [OBSERVAÇÃODEPÁSSAROS] Belo exemplo de gaios azuis no topo do Monte Rainier esta semana 
  
Alguém quer conferir esta semana a vista do Monte Rainier?
  
---
  
Esta mensagem foi enviada para a lista de discussão de Observação de Pássaros. Você pode cancelar a assinatura a qualquer momento.
  
No exemplo acima, a mensagem repetida tem o mesmo endereço De: (usuario @ contoso.com), mas a mensagem original foi modificada com a adição de uma marca à linha Assunto e um rodapé à parte inferior da mensagem. Esse tipo de modificação de mensagem é comum em listas de discussão e pode resultar em falsos positivos.
  
Se você ou alguém de sua organização for um administrador de lista de discussão, você poderá configurá-la para aprovação em verificações antifalsificação.
  
- Confira as perguntas frequentes em DMARC.org: [Opero uma lista de discussão e quero interoperar com o DMARC. O que devo fazer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- Leia as instruções nesta postagem do blog: [Uma dica para operadores de listas de discussão interoperarem com o DMARC para evitar falhas](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- Considere a instalação de atualizações em seu servidor de lista de discussão para dar suporte ao ARC. Veja [https://arc-spec.org](https://arc-spec.org/)

Se você não é proprietário da propriedade da lista de discussão:
  
- Você pode solicitar ao mantenedor da lista de discussão que implemente uma das opções acima (ele também deve configurar a autenticação de email para o domínio do qual a lista de discussão está sendo retransmitida)

- Você pode criar regras de caixa de correio em seu cliente de email para mover mensagens para a Caixa de Entrada. Você também pode solicitar que os administradores de sua organização configurem regras de permissão ou substituições, conforme discutido na seção Gerenciar remetentes legítimos que estão enviando emails não autenticados

- Você pode criar um tíquete de suporte com o Office 365 para criar uma substituição para a lista de distribuição a fim de tratá-la como legítima

### <a name="other-scenarios"></a>Outros cenários

1. Se nenhum dos cenários comuns acima se aplicar à sua situação, relate a mensagem como um falso positivo para a Microsoft. Para obter mais informações, confira a seção [Como relatar mensagens de spam ou não spam à Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) mais adiante neste artigo. 

2. Você também pode entrar em contato com seu administrador de email, que pode criar um tíquete de suporte na Microsoft. A equipe de engenharia da Microsoft investigará por que a mensagem foi marcada como uma falsificação.

3. Além disso, se você souber quem é o remetente e tiver certeza de que ele não está sendo falsificado de forma mal-intencionada, poderá responder ao remetente para indicar que ele está enviando mensagens de um servidor de email que não está autenticado. Às vezes isso faz com que o remetente original entre em contato com o administrador de TI, que configurará os registros de autenticação de email necessários.
  
Quando um número suficiente de remetentes responde aos proprietários do domínio que devem configurar registros de autenticação de email, isso os incentiva a agir. Embora a Microsoft também trabalhe com proprietários de domínio para publicar os registros necessários, é ainda mais eficaz quando usuários individuais solicitam isso.

4. Opcionalmente, adicione o remetente à sua lista de Remetentes Confiáveis. No entanto, lembre-se de que, se um phisher falsificar essa conta, ela será entregue em sua caixa postal. Portanto, essa opção deve ser usada com moderação.

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>Como os remetentes para a Microsoft devem se preparar para proteção antifalsificação

Se você é um administrador que atualmente envia mensagens para a Microsoft, para o Office 365 ou o Outlook.com, deve garantir que seu email esteja devidamente autenticado. Caso contrário, ele poderá ser marcado como spam ou phishing.
  
### <a name="customers-of-office-365"></a>Clientes do Office 365

Se você é um cliente do Office 365 e usa o Office 365 para enviar emails de saída:
  
- Para seus domínios, [Configure o SPF no Office 365 para impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- Para seus domínios primários, [Use o DKIM para validar emails de saída enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)

- [Considere a configuração de registros DMARC](use-dmarc-to-validate-email.md) para seu domínio a fim de determinar quem são seus remetentes legítimos

A Microsoft não fornece diretrizes de implementação detalhadas para SPF, DKIM e DMARC. No entanto, há muitas informações publicadas online. Também há empresas de terceiros dedicadas a ajudar sua organização a configurar registros de autenticação de email.
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>Administradores de domínios que não são clientes do Office 365

Se você é um administrador de domínio, mas não é cliente do Office 365:
  
- Você deve configurar o SPF para publicar os endereços IP de envio de seu domínio e também configurar o DKIM (se disponível) para assinar digitalmente as mensagens. Você também pode considerar a configuração de registros DMARC.

- Se você tiver remetentes em massa que transmitem emails em seu nome, trabalhe com eles para enviar emails de forma que o domínio de envio no endereço De: (se pertencer a você) esteja alinhado ao domínio aprovado por SPF ou DMARC.

- Se você tiver servidores de email locais, enviar de um provedor de software como um serviço ou de um serviço de hospedagem na nuvem como Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services ou semelhante, garanta que eles sejam adicionado ao registro SPF.

- Se você é um pequeno domínio hospedado por um ISP, deve configurar seu registro SPF de acordo com as instruções fornecidas pelo ISP. A maioria dos ISPs fornece esses tipos de instruções, e elas podem ser encontradas nas páginas de suporte da empresa.

- Mesmo que você não tenha precisado publicar registros de autenticação de email antes e isso tenha funcionado bem, ainda deverá publicar registros de autenticação de email para enviar à Microsoft. Fazendo isso, você ajuda na luta contra o phishing e reduz a possibilidade de que você ou organizações para as quais envia sejam afetados por phishing.

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>E se você não souber quem envia emails como seu domínio?

Muitos domínios não publicam registros SPF porque não sabem quem são todos os seus remetentes. Não há problemas. Você não precisa saber quem são todos eles. Em vez disso, você deve começar publicando um registro SPF para aqueles que conhece, especialmente onde o tráfego corporativo está localizado, e publicar uma política de SPF neutra, ?all:
  
example.com IN TXT "v=spf1 include:spf.example.com ?all"
  
A política de SPF neutra significa que qualquer email que saia de sua infraestrutura corporativa passará pela autenticação de email em todos os outros destinatários de email. O email proveniente de remetentes que você não conhece retornará ao nível neutro, o que é quase o mesmo que não publicar um registro SPF.
  
Ao enviar para o Office 365, os emails provenientes de seu tráfego corporativo serão marcados como autenticados, mas os emails provenientes de fontes que você não conhece ainda poderão ser marcados como falsificados (dependendo de o Office 365 poder autenticá-los implicitamente ou não). No entanto, isso ainda é uma melhoria em relação à situação em que todos os emails são marcados como falsificação pelo Office 365.
  
Após começar a usar um registro SPF com a política de fallback ?all, você pode gradualmente incluir mais infraestrutura de envio e publicar uma política mais rígida. 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>E se você for o proprietário de uma lista de discussão?

Confira a seção [Cenário comum nº 1 ‒ Listas de discussão](#common-scenario-1---discussion-lists).
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>E se você for um provedor de infraestrutura, como um ISP (Provedor de Serviços de Internet), um ESP (Provedor de Serviços de Email) ou um serviço de hospedagem na nuvem?

Se você hospedar o email de um domínio, e ele enviar um email ou fornecer uma infraestrutura de hospedagem que possa enviar emails, faça o seguinte:
  
- Garanta que seus clientes tenham a documentação com detalhes sobre o que publicar nos registros SPF

- Considere a inclusão de assinaturas DKIM nos emails de saída, mesmo que o cliente não os configure explicitamente (assine com um domínio padrão). Você pode até mesmo assinar duplamente o email com assinaturas DKIM (uma vez com o domínio do cliente, se ele estiver configurado, e uma segunda vez com a assinatura DKIM de sua empresa)

A capacidade de entrega para a Microsoft não é garantida, mesmo que você autentique emails originados de sua plataforma, mas pelo menos isso garante que a Microsoft não marque seu email como lixo eletrônico porque ele não está autenticado. Para obter mais detalhes sobre como o Outlook.com filtra os emails, confira a [Página Postmaster do Outlook.com](https://postmaster.live.com/pm/postmaster.aspx).
  
Para obter mais detalhes sobre as práticas recomendadas dos provedores de serviços, confira [Práticas recomendadas de mensagens móveis do M3AAWG para provedores de serviços](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).
  
## <a name="frequently-asked-questions"></a>Perguntas Frequentes

### <a name="why-is-microsoft-making-this-change"></a>Por que a Microsoft está fazendo essa alteração?

Devido ao impacto de ataques de phishing e porque a autenticação de email existe há mais de 15 anos, a Microsoft acredita que o risco de continuar a permitir emails não autenticados é maior do que o risco de perder emails legítimos.
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>Essa alteração fará com que emails legítimos sejam marcados como spam?

Inicialmente, algumas mensagens serão marcadas como spam. No entanto, com o tempo, os remetentes se ajustarão e, em seguida, a quantidade de mensagens rotuladas incorretamente como falsificadas será insignificante para a maioria dos caminhos de email.
  
A própria Microsoft adotou esse recurso várias semanas antes de implantá-lo no restante de seus clientes. Embora tenha havido dificuldades no início, elas diminuíram gradualmente.
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>A Microsoft levará esse recurso para o Outlook.com e clientes que não tenham a Proteção Avançada contra Ameaças do Office 365?

A tecnologia antifalsificação da Microsoft foi implantada inicialmente nas organizações da empresa que tinham uma assinatura do Office 365 Enterprise E5 ou que tinham o complemento ATP (Proteção Avançada contra Ameaças) do Office 365 na assinatura. Desde outubro de 2018, estendemos a proteção para organizações que também têm a EOP (Proteção do Exchange Online). No futuro, podemos lançá-la para o Outlook.com. No entanto, se fizermos isso, alguns recursos poderão não ser aplicados, como relatórios e substituições personalizadas.
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Como relatar mensagens de spam ou não spam para a Microsoft?

Você pode usar o [Suplemento para Relatar Mensagens para o Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2) ou, se não estiver instalado, [Enviar mensagens de spam, não spam e de phishing à Microsoft para análise](https://technet.microsoft.com/library/jj200769%28v=exchg.150%29.aspx).
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>Sou um administrador de domínio que não sabe quem são todos os meus remetentes!

Confira [Administradores de domínios que não são clientes do Office 365](#administrators-of-domains-that-are-not-office-365-customers).
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>O que acontecerá se eu desabilitar a proteção antifalsificação em minha organização, mesmo que o Office 365 seja meu filtro principal?

Não recomendamos isso porque você será exposto a mais mensagens de phishing e spam. Nem todos os tipos de phishing são falsificações, e nem todas as falsificações serão ignoradas. No entanto, seu risco será maior do que um cliente que habilita a antifalsificação.
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>A habilitação da proteção antifalsificação significa que ficarei protegido contra todos os tipos de phishing?

Infelizmente, não, porque os phishers vão se adaptar para usar outras técnicas, como contas comprometidas, ou vão configurar contas de serviços gratuitos. No entanto, a proteção antiphishing funciona muito melhor para detectar esses outros tipos de métodos de phishing porque as camadas de proteção do Office 365 são projetadas para trabalhar juntas e auxiliar umas às outras.
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>Outros grandes receptores de email bloqueiam emails não autenticados?

Quase todos os grandes receptores de email implementam SPF, DKIM e DMARC tradicionais. Alguns receptores têm outras verificações que são mais rigorosas do que apenas esses padrões, mas poucos chegam ao mesmo nível que o Office 365 para bloquear emails não autenticados e tratá-los como uma falsificação. No entanto, a maior parte do setor está se tornando cada vez mais rigorosa em relação a esse tipo específico de email, principalmente devido ao problema de phishing.
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>Ainda precisarei ter a opção Filtragem de Spam Avançada habilitada para "Falha Irrecuperável de FPS" se eu habilitar a antifalsificação?

Não, essa opção não é mais necessária porque o recurso antifalsificação não considera apenas as falhas graves de SPF, mas um conjunto muito mais amplo de critérios. Se você tiver antifalsificação e a opção Falha Irrecuperável de FPS habilitadas, provavelmente obterá mais falsos positivos. Recomendamos desabilitar esse recurso porque ele não fornece quase nenhuma captura adicional de spam ou phishing, e gera principalmente falsos positivos.
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>O SRS (Esquema de Reescrita de Remetente) ajuda a corrigir o email encaminhado?

O SRS corrige apenas parcialmente o problema dos emails encaminhados. Reescrevendo SMTP MAIL FROM, o SRS pode garantir que a mensagem encaminhada seja aprovada no SPF no próximo destino. No entanto, como a antifalsificação é baseada no endereço De: em combinação com o domínio de assinatura MAIL FROM ou DKIM (ou outros sinais), não é suficiente para impedir que emails encaminhados sejam marcados como falsificados.
