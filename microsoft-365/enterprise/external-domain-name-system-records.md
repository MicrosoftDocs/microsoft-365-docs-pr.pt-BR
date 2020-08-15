---
title: Registros de Sistema de Nomes de Domínio Externos para o Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/21/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0
description: Uma lista de referências de registros do Sistema de Nomes de Domínio externos para serem usados ao planejar uma implantação do Office 365.
ms.openlocfilehash: da5a9a1095e50de779ee2fc148803e31583426a2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687462"
---
# <a name="external-domain-name-system-records-for-office-365"></a>Registros de Sistema de Nomes de Domínio Externos para o Office 365

|||
|:-----|:-----|
|![Domínio](../media/e05b1c78-1df0-4200-ba40-6e26b7ead68f.png)|**Deseja ver uma lista personalizada de registros DNS para sua organização do Office 365? ** Encontre [ as informações necessárias para criar registros DNS do Office 365](https://support.office.microsoft.com/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67) para seu domínio no Office 365.  <br/> **Precisa de ajuda passo a passo para adicionar esses registros ao host de DNS de seu domínio, como GoDaddy ou eNom? ** [Encontre links de instruções passo a passo para vários hosts DNS conhecidos](https://go.microsoft.com/fwlink/?LinkId=286745). <br/>  **Ainda deseja usar a lista de referências para sua implantação personalizada?** A lista abaixo deve ser usada como uma referência para sua implantação personalizada do Office 365. Será necessário selecionar quais registros se aplicam à sua organização e preencher os valores apropriados. <br/> **Volte para o** [Planejamento de rede e ajuste de desempenho para o Office 365](https://aka.ms/tune).  <br/> |

Geralmente, os registros SPF e MX são os mais difíceis de entender. Atualizamos nossa orientação para registros SPF no final deste artigo. O mais importante é lembrar que _você pode ter apenas um único registro SPF para seu domínio_. Você pode ter vários registros MX, mas isso costuma causar problemas de entrega de emails. Ter um único registro MX que direciona os emails para um sistema de email elimina muitos desses possíveis problemas.
  
As seções abaixo são organizadas por serviço no Office 365. Para ver uma lista personalizada de registros DNS do Office 365 para seu domínio, entre no Office 365 e [Reúna as informações necessárias para criar registros DNS do Office 365](https://support.office.com/article/77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
  
## <a name="external-dns-records-required-for-office-365-core-services"></a>Registros DNS externos exigidos para o Office 365 (serviços essenciais)
<a name="BKMK_ReqdCore"> </a>

Cada cliente do Office 365 precisa adicionar dois registros ao seu DNS externo. O primeiro CNAME garante que o Office 365 possa direcionar estações de trabalho à plataforma de identidade apropriada. O segundo registro necessário é um registro para comprovar que você possui o nome de domínio.
  
||||
|:-----|:-----|:-----|
|**Registro DNS** <br/> |**Objetivo** <br/> |**Valor a ser usado** <br/> |
|**CNAME** <br/> **(Suite)** <br/> |Usado pelo Office 365 para direcionar a autenticação para a plataforma de identificação correta. [Mais informações](https://go.microsoft.com/fwlink/p/?LinkId=322005) <br/> **Observação:** Este CNAME só se aplica ao Office 365 operado pela 21Vianet. [Mais informações](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet)  |**Alias:** msoid  <br/> **Destino:** clientconfig.partner.microsoftonline-p.net.cn  <br/> |
|**TXT** <br/> **(Verificação de domínio)** <br/> |Usado pelo Office 365 somente para verificar se você é o proprietário do seu domínio. Não afeta nada mais.  <br/> |**Host:** @ (ou, para alguns provedores de hospedagem DNS, o nome do seu domínio)  <br/> **Valor do TXT:** _uma cadeia de texto fornecida pelo_ Office 365  <br/> O **assistente de configuração de domínio** do Office 365 fornece os valores usados para criar esse recurso.  <br/> |


## <a name="external-dns-records-required-for-email-in-office-365-exchange-online"></a>Registros DNS externos exigidos para email no Office 365 (Exchange Online)
<a name="BKMK_ReqdCore"> </a>

OO email no Office 365 exige diversos registros diferentes. Os três registros principais que todos os clientes devem usar são a Descoberta Automática, MX e SPF.
  
- **O registro de Descoberta Automática** permite que os computadores clientes encontrem o Exchange automaticamente e configurem o cliente corretamente.

- **O registro MX** informa aos outros sistemas de email aonde enviar emails para o seu domínio. **Observação:** Quando você altera seu email para o Office 365, ao atualizar o registro MX do seu domínio, TODOS os emails enviados para esse domínio são enviados para o Office 365.  
Você só quer migrar alguns endereços de email para o Office 365? Você pode [Coordenar o Office 365 com alguns endereços de email em seu domínio personalizado](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7).

- **O registro TXT para SPF** é usado por sistemas de email do destinatário para validar se o servidor que envia seu email é aquele que você aprova. Isso ajuda a evitar problemas como a falsificação e o phishing de emails. Consulte os [Registros DNS externos necessários para SPF](external-domain-name-system-records.md#BKMK_SPFrecords) neste artigo para ajudá-lo a entender o que incluir em seu registro.

Os clientes de email que estão usando a Federação do Exchange também terão um registro CNAME e TXT adicional listado no final da tabela.
  
||||
|:-----|:-----|:-----|
|**Registro DNS** <br/> |**Objetivo** <br/> |**Valor a ser usado** <br/> |
|**CNAME** <br/> **(Exchange Online)** <br/> |Ajuda os clientes do Outlook a se conectarem com facilidade ao serviço do Exchange Online usando o serviço de Descoberta Automática. A Descoberta Automática encontra automaticamente o host correto do Exchange Server e configura o Outlook para os usuários.  <br/> |**Alias:** descoberta automática  <br/> **Destino:** autodiscover.outlook.com  <br/> |
|**MX** <br/> **(Exchange Online)** <br/> |Envia emails de entrada de seu domínio para o serviço Exchange Online no Office 365.  <br/> [!NOTE] Quando os emails estão sendo enviados para o Exchange Online, você deve remover os registros MX que apontam para o sistema antigo.   |**Domínio:** por exemplo, contoso.com  <br/> **Servidor de email de destino:**\<MX token\>.mail.protection.outlook.com  <br/> **Preferência/Prioridade:** menor do que outros registros MX (isso garante que o email seja entregue ao Exchange Online), por exemplo, 1 ou “baixa”  <br/>  Encontre o seu \<MX token\> seguindo estas etapas:  <br/>  Entre no Office 365, vá para o administrador do Office 365 \>Domínios.  <br/>  Na coluna Ação de seu domínio, escolha Corrigir problemas.  <br/>  Na seção de registros MX, escolha O que corrigir?  <br/>  Siga as instruções nesta página para atualizar seu registro MX.  <br/> [O que é prioridade MX?](https://go.microsoft.com/fwlink/p/?LinkId=396471) <br/> |
|**SPF (TXT)** <br/> **(Exchange Online)**  <br/> |Ajuda a impedir que outras pessoas usem seu domínio para enviar spam ou outros emails mal-intencionados. Os registros SPF (sender policy framework) identificam os servidores autorizados a enviar email de seu domínio.  <br/> |[Registros DNS externos necessários para SPF](external-domain-name-system-records.md#BKMK_SPFrecords) <br/> |
|**TXT** <br/> **(Federação do Exchange)** <br/> |Usado na federação do Exchange para implantação híbrida.  <br/> |**Registro TXT 1:** por exemplo, contoso.com e um texto de hash associado, gerado de forma personalizada e à prova de domínio (por exemplo, Y96nu89138789315669824)  <br/> **Registro TXT 2:** por exemplo, exchangedelegation.contoso.com e um texto de hash associado gerado de forma personalizada e à prova de domínio (por exemplo, Y3259071352452626169)  <br/> |
|**CNAME** <br/> **(Federação do Exchange)** <br/> |Ajuda os clientes do Outlook a se conectarem com facilidade ao serviço do Exchange Online usando o serviço de Descoberta Automática quando sua empresa estiver usando a federação do Exchange. A Descoberta Automática encontra automaticamente o host correto do Exchange Server e configura o Outlook para os usuários.  <br/> |**Alias:** por exemplo, Autodiscover.service.contoso.com  <br/> **Destino:** autodiscover.outlook.com  <br/> |


## <a name="external-dns-records-required-for-skype-for-business-online"></a>Registros DNS externos necessários para o Skype for Business Online
<a name="BKMK_ReqdCore"> </a>

Há etapas específicas a serem seguidas quando você usa [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) para garantir que sua rede esteja configurada corretamente.

> [!NOTE]
> Esses registros DNS também se aplicam ao Teams, especialmente em um cenário híbrido do Teams e do Skype for Business, onde podem surgir certos problemas de federação.
  
||||
|:-----|:-----|:-----|
|**Registro DNS** <br/> |**Objetivo** <br/> |**Valor a ser usado** <br/> |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Permite que o domínio do Office 365 compartilhe recursos de mensagens instantâneas (IM) com clientes externos habilitando a federação SIP. Leia mais sobre [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |**Serviço:** sipfederationtls  <br/> **Protocolo:** TCP  <br/> **Priority:** 100  <br/> **Peso:** 1  <br/> **Porta:** 5061  <br/> **Destino:** sipfed.online.lync.com  <br/> **Observação:** Se o firewall ou o servidor proxy bloquearem pesquisas SRV em um DNS externo, você deverá adicionar esse registro ao registro DNS interno.   |
|**SRV** <br/> **(Skype for Business Online)** <br/> |Usado pelo Skype for Business para coordenar o fluxo de informações entre clientes do Lync.  <br/> |**Serviço:** sip  <br/> **Protocolo:** TLS  <br/> **Priority:** 100  <br/> **Peso:** 1  <br/> **Porta:** 443  <br/> **Destino:** sipdir.online.lync.com  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Usado pelo cliente do Lync para ajudar a localizar o serviço do Skype for Business Online e entrar.  <br/> |**Alias:** sip  <br/> **Destino:** sipdir.online.lync.com  <br/> Para obter mais informações, confira [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO).  <br/> |
|**CNAME** <br/> **(Skype for Business Online)** <br/> |Usado pelo cliente móvel do Lync para ajudar a localizar o serviço do Skype for Business Online e entrar.  <br/> |**Alias:** lyncdiscover  <br/> **Destino:** webdir.online.lync.com  <br/> |

## <a name="external-dns-records-required-for-office-365-single-sign-on"></a>Registros DNS externos exigidos para Acesso por Logon Único ao Office 365
<a name="BKMK_ReqdCore"> </a>

||||
|:-----|:-----|:-----|
|**Registro DNS** <br/> |**Objetivo** <br/> |**Valor a ser usado** <br/> |
|**Host (A)** <br/> |Usado para logon único (SSO). Fornece o ponto de extremidade para que seus usuários externos (e usuários locais, se você quiser) se conectem aos proxies do servidor de federação dos Serviços de Federação do Active Directory (AD FS) ou ao IP virtual com balanceamento de carga (VIP).  <br/> |**Destino:** por exemplo, sts.contoso.com  <br/> |

## <a name="external-dns-records-required-for-spf"></a>Registros DNS externos necessários para SPF
<a name="BKMK_SPFrecords"> </a>

> [!IMPORTANT]
> A SPF foi projetada para ajudar a evitar a falsificação, mas existem técnicas de falsificação que a SPF não ajuda a proteger. Para proteger contra essas técnicas, depois de configurar a SPF, você também deve configurar o DKIM e o DMARC para o Office 365. Para começar, confira [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). A seguir, veja [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
  
Os registros SPF são registros TXT que ajudam a impedir que outras pessoas usem seu domínio para enviar spam ou outros emails mal-intencionados. Os registros SPF (sender policy framework) identificam os servidores autorizados a enviar emails de seu domínio.
  
Você só pode ter um registro SPF (ou seja, um registro TXT que define SPF) para seu domínio. Este registro único pode ter algumas inclusões diferentes, mas o total de pesquisas DNS resultantes não pode ser superior a 10 (isso ajuda a evitar ataques de negação de serviço). Confira a tabela e os outros exemplos a seguir para ajudá-lo a criar ou atualizar os valores de registro SPF corretos para seu ambiente.
  
### <a name="structure-of-an-spf-record"></a>Estrutura de um registro SPF

Todos os registros SPF contêm três partes: a declaração de que é um registro SPF, os domínios e endereços IP que devem enviar emails e uma regra de aplicação. Você precisa das três partes para ter um registro SPF válido. Veja um exemplo do registro SPF mais comum para o Office 365 quando você usa apenas o email do Exchange Online:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com -all
```

Um sistema de emails que recebe um email do seu domínio analisa o registro SPF. Se o servidor de email que enviou a mensagem era um servidor do Office 365, a mensagem é aceita. Se o servidor que enviou a mensagem era o seu antigo sistema de emails ou um sistema mal-intencionado na Internet, por exemplo, a verificação de SPF pode falhar, e a mensagem não ser enviada. Verificações como esta ajudam a evitar mensagens de falsificação e phishing.
  
### <a name="choose-the-spf-record-structure-you-need"></a>Escolha a estrutura de registro de SPF que precisar

Para cenários em que você não está usando apenas o email do Exchange Online no Office 365 (por exemplo, quando você também usa o email proveniente do SharePoint Online), use a tabela a seguir para determinar o que incluir no valor do registro.
  
> [!NOTE]
> Se você tiver um cenário complicado que inclui, por exemplo, servidores de email de borda para o gerenciamento de tráfego de email em seu firewall, você terá um registro SPF mais detalhado para configurar. Saiba como: [Configurar registros SPF no Office 365 para ajudar a evitar falsificação](https://go.microsoft.com/fwlink/?LinkId=787656). Você também pode aprender muito mais sobre como o SPF funciona com o Office 365 lendo [Como o Office 365 usa Sender Policy Framework (SPF) para ajudar a evitar falsificação](https://go.microsoft.com/fwlink/?LinkId=787065).
  
| Número|Se você estiver usando...  <br/> |Finalidade  <br/> |Adicionar isso inclui  <br/> |
|:-----|:-----|:-----|:-----|
|1  <br/> |Todos os sistemas de email (obrigatório)  <br/> |Todos os registros SPF começam com esse valor  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online (comum)  <br/> |Usar apenas com o Exchange Online  <br/> |include:spf.protection.outlook.com  <br/> |
|3  <br/> |Sistema de email de terceiros (menos comum)  <br/> ||include:\<email system like mail.contoso.com\>  <br/> |
|4  <br/> |Sistema de email local (menos comum)  <br/> |Usar se você estiver usando o Exchange Online Protection ou o Exchange Online e outro sistema de email  <br/> |ip4:\<0.0.0.0\>  <br/> ip6:\< : : \>  <br/> include:\<mail.contoso.com\>  <br/> O valor entre colchetes (\<\>) deve ser outros sistemas de email que enviarão emails para seu domínio.  <br/> |
|5  <br/> |Todos os sistemas de email (obrigatório)  <br/> ||-tudo  <br/> |

### <a name="example-adding-to-an-existing-spf-record"></a>Exemplo: adicionar a um registro SPF existente
<a name="bkmk_addtospf"> </a>

Se você já tiver um registro SPF, será preciso adicionar ou atualizar os valores para o Office 365. Por exemplo, digamos que seu registro SPF existente para contoso.com seja esse:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
```

Agora, você está atualizando seu registro SPF do Office 365. Edite o registro atual para que você tenha um registro SPF que inclua os valores de que você precisa. Para o Office 365, "spf.protection.outlook.com".
  
Correto:
  
``` dns
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:spf.protection.outlook.com include:smtp.adatum.com -all
```

Incorreto:
  
``` dns
Record 1:
TXT Name @
Values: v=spf1 ip4:60.200.100.30 include:smtp.adatum.com -all
Record 2:
Values: v=spf1 include:spf.protection.outlook.com -all
```

### <a name="more-examples-of-common-spf-values"></a>Mais exemplos de valores de SPF comuns
<a name="bkmk_addtospf"> </a>

Se você estiver usando o pacote completo do Office 365 e estiver usando MailChimp para enviar emails de marketing em seu nome, seu registro SPF em contoso.com poderá se parecer com o seguinte, que usa as linhas 1, 3 e 5 da tabela acima. Lembre-se de que as linhas 1 e 5 são necessárias.
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:servers.mcsv.net -all
```

Como alternativa, se você tiver uma configuração híbrida do Exchange na qual o email é enviado do Office 365 e também do seu sistema de email local, seu registro SPF em contoso.com pode ser assim:
  
``` dns
TXT Name @
Values: v=spf1 include:spf.protection.outlook.com include:mail.contoso.com -all
```

Existem alguns exemplos comuns que podem ajudar você a adaptar seu registro SPF existente quando você adicionar seu domínio ao Office 365 para emails. Se você tiver um cenário complicado que inclua, por exemplo, servidores de email de borda para o gerenciamento de tráfego de email em seu firewall, você terá um registro SPF mais detalhado para configurar. Saiba como: [Configurar registros SPF no Office 365 para evitar a falsificação](https://go.microsoft.com/fwlink/?LinkId=787656).
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365edns](https://aka.ms/o365edns)
