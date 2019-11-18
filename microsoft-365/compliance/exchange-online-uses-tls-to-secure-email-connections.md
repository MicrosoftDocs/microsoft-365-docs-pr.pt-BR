---
title: Como o Exchange Online usa o TLS para proteger conexões de email no Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Saiba como o Exchange Online e o Office 365 usam a segurança de camada de transporte (TLS) e o sigilo total de comunicação por email. Além disso, obtenha informações sobre o certificado emitido pela Microsoft para o Exchange Online.
ms.openlocfilehash: 34667714840e23be5d19aed8f47a539ea1474ab4
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38684797"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a>Como o Exchange Online usa o TLS para proteger conexões de email no Office 365

Saiba como o Exchange Online e o Office 365 usam a segurança de camada de transporte (TLS) e o sigilo total de comunicação por email. Também fornece informações sobre o certificado emitido pela Microsoft para o Exchange Online.
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a>Noções básicas do TLS para o Office 365 e o Exchange Online

TLS e SSL são protocolos de criptografia que protegem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. O TLS substitui o SSL e é conhecido como SSL 3.1. Para o Exchange Online, usamos o TLS para criptografar as conexões entre nossos servidores do Exchange e as conexões entre nossos servidores do Exchange e outros servidores, como seus servidores locais do Exchange ou os servidores de email dos destinatários. Depois que a conexão é criptografada, todos os dados enviados por essa conexão passam pelo canal criptografado. No entanto, se você encaminhar uma mensagem que foi enviada por uma conexão criptografada por TLS, essa mensagem não é necessariamente criptografada. Isso ocorre porque, em termos simples, o TLS não criptografa a mensagem, apenas a conexão.
  
Caso pretenda criptografar a mensagem, você deve usar uma tecnologia de criptografia adequada para criptografar conteúdo de mensagens; por exemplo, algo como o recurso Criptografia de Mensagens do Office. Confira [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md) para saber mais sobre as opções de criptografia de mensagens no Office 365. 
  
Recomendamos usar o TLS em situações em que você deseja configurar um canal seguro de correspondência entre o Office 365 e sua organização local ou outra organização, como um parceiro. O Exchange Online tenta primeiro usar o TLS para proteger seu email, mas não é possível fazer isso se a outra parte não oferecer segurança TLS. Continue lendo para saber como você pode proteger todos os emails para seus servidores locais ou parceiros importantes usando *conectores*. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Como o Exchange Online usa o TLS entre clientes do Exchange Online

Os servidores do Exchange Online sempre criptografam conexões com outros servidores do Exchange Online em nossos data centers com TLS 1.2. Quando você envia um email para um destinatário que está dentro da sua organização do Office 365, esse email é enviado automaticamente através de uma conexão criptografada usando TLS. Além disso, todos os emails enviados para outros clientes do Office 365 são enviados através de conexões criptografadas com TLS e protegidos por FS.
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a>Como o Office 365 usa o TLS entre o Office 365 e parceiros externos, confiáveis

Por padrão, o Exchange Online sempre usa o TLS oportunista. Isso significa que o Exchange Online sempre tenta criptografar as conexões com a versão mais segura do TLS primeiro e, em seguida, testa a lista de codificações TLS até encontrar uma que seja aceita por ambas as partes. A menos que você tenha configurado o Exchange Online para garantir que as mensagens desse destinatário sejam enviadas apenas por meio de conexões seguras, por padrão a mensagem será enviada sem criptografia se a organização de destinatários não oferecer suporte à criptografia TLS. O TLS oportunista é suficiente para a maioria das empresas. No entanto, para empresas que têm requisitos de conformidade, como organizações médicas, de bancos ou governamentais, você pode configurar o Exchange Online para exigir ou forçar o TLS. Para obter instruções, consulte [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Se você decidir configurar o TLS entre sua organização e uma organização de parceiro confiável, o Exchange Online pode usar o TLS forçado para criar canais de comunicação confiáveis. O TLS forçado requer que a organização do parceiro autentique-se no Exchange Online com um certificado de segurança para enviar emails para você. Seu parceiro precisará gerenciar os próprios certificados para fazer isso. No Exchange Online, usamos conectores para proteger as mensagens enviadas de acesso não autorizado antes de chegarem ao provedor de email do destinatário. Para obter informações sobre como usar conectores para configurar o fluxo de emails, consulte [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implantações híbridas do Exchange Server

Se você estiver gerenciando uma implantação híbrida do Exchange, seu servidor local do Exchange deve se autenticar no Office 365 usando um certificado de segurança para enviar emails aos destinatários cujas caixas de correio estão somente no Office 365. Como resultado, você precisa gerenciar seus próprios certificados de segurança para seus servidores locais do Exchange. Você também deve armazenar e manter esses certificados de servidor de maneira segura. Para obter mais informações sobre o gerenciamento de certificados em implantações híbridas, consulte [Certificate Requirements for Hybrid Deployments](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Como configurar o TLS Forçado para Exchange Online no Office 365

Para clientes do Exchange Online, para que o TLS forçado proteja todos os emails enviados e recebidos, é necessário configurar mais de um conector que exija TLS. Você precisará de um conector para emails enviados para as caixas de correio dos seus usuários e outro para emails enviados a partir delas. Crie esses conectores no Centro de administração do Exchange no Office 365. Para obter instruções, consulte [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informações do certificado TLS para o Exchange Online

As informações do certificado usadas pelo Exchange Online são descritas na tabela a seguir. Se seu parceiro comercial estiver configurando a TLS forçada no servidor de email, você precisará fornecer essas informações para ele. Lembre-se de que, por motivos de segurança, os nossos certificados mudam de tempos em tempos. Fizemos uma atualização para nosso certificado em nossos data centers. O novo certificado é válido a partir de 3 de setembro de 2018.
  
 **Informações do certificado atual válidas de 3 de setembro de 2018**
  
|**Atributo**|**Valor**|
|:-----|:-----|
|Emissor da raiz da autoridade de certificação  <br/> |GlobalSign AC raiz – R1 <br/> |
|Nome do certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organização  <br/> |Microsoft Corporation  <br/> |
|Unidade organizacional  <br/> |  <br/> |
|Nível de segurança da chave do certificado  <br/> |2048  <br/> |
   
 **Informações de certificado preteridas válidas até 3 de setembro de 2018**
  
Para ajudar a garantir uma transição suave, continuaremos a fornecer as informações de certificado antigas para sua referência por algum tempo, no entanto, você deve usar as informações atuais do certificado de agora em diante.
  
****

|**Atributo**|**Valor**|
|:-----|:-----|
|Emissor da raiz da autoridade de certificação  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome do certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organização  <br/> |Microsoft Corporation  <br/> |
|Unidade organizacional  <br/> |Microsoft Corporation  <br/> |
|Nível de segurança da chave do certificado  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Preparar para o novo certificado do Exchange Online

O novo certificado é emitido por uma autoridade de certificação (CA) diferente do certificado anterior usado pelo Exchange Online. Como resultado, você pode precisar executar algumas ações para usar o novo certificado.

O novo certificado requer a conexão aos pontos de extremidade da nova AC como parte da validação do certificado. Se isso não for feito, o fluxo de email pode ser afetado negativamente. Se você proteger seus servidores de email com firewalls que permitem que apenas os servidores de email se conectem com determinados destinos, será necessário verificar se o servidor é capaz de validar o novo certificado. Para confirmar se o servidor pode usar o novo certificado, conclua estas etapas:

1. Conecte-se ao seu servidor Exchange local usando o Windows PowerShell e execute o seguinte comando:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. Na janela exibida, escolha **recuperar**.
3. Quando o utilitário concluir sua verificação, ele retornará um status. Se o status Exibir **OK**, seu servidor de email poderá validar com êxito o novo certificado. Caso contrário, você precisará determinar o que está causando falha nas conexões. Provavelmente, você precisará atualizar as configurações de um firewall. A lista completa de pontos de extremidade que precisam ser acessados incluem:
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

Normalmente, você recebe atualizações para seus certificados raiz automaticamente por meio do Windows Update. No entanto, algumas implantações têm segurança adicional no local que impede que essas atualizações ocorram automaticamente. Nessas implantações bloqueadas nas quais o Windows Update não pode atualizar automaticamente os certificados raiz, você precisa garantir que o certificado de autoridade de certificação raiz correto seja instalado executando estas etapas:
1.  Conecte-se ao seu servidor Exchange local usando o Windows PowerShell e execute o seguinte comando:  
  `certmgr.msc`
2. Em **autoridades de certificação raiz confiáveis/certificados**, confirme se o novo certificado está listado.

## <a name="get-more-information-about-tls-and-office-365"></a>Saiba mais sobre TLS e o Office 365

Para obter uma lista de pacotes de codificação com suporte, consulte [Technical Reference Details about Encryption in Office 365](technical-reference-details-about-encryption.md).
  
[Configurar conectores para fluxo de email seguro com uma organização parceira](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Conectores com segurança avançada de email](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Criptografia no Office 365](encryption.md)
  

