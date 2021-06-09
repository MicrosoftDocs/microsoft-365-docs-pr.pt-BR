---
title: Como o Exchange Online usa TLS para proteger conexões de e-mail
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
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
description: Saiba como Exchange Online e Microsoft 365 usar o TLS (Transport Layer Security) e o Forward Secrety (FS) para proteger as comunicações de email. Também obter informações sobre o certificado emitido pela Microsoft para Exchange Online.
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906947"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Como o Exchange Online usa TLS para proteger conexões de e-mail

Saiba como Exchange Online e Microsoft 365 usar o TLS (Transport Layer Security) e o Forward Secrety (FS) para proteger as comunicações de email. Também fornece informações sobre o certificado emitido pela Microsoft para o Exchange Online.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Noções básicas de TLS para Microsoft 365 e Exchange Online

TLS e SSL são protocolos de criptografia que protegem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. O TLS substitui o SSL e é conhecido como SSL 3.1. Para Exchange Online, usamos o TLS para criptografar as conexões entre nossos servidores Exchange e as conexões entre nossos servidores do Exchange e outros servidores, como seus servidores Exchange locais ou servidores de email de seus destinatários. Depois que a conexão é criptografada, todos os dados enviados por essa conexão passam pelo canal criptografado. No entanto, se você encaminhar uma mensagem que foi enviada por uma conexão criptografada por TLS, essa mensagem não é necessariamente criptografada. Isso porque, em termos simples, o TLS não criptografa a mensagem, apenas a conexão.
  
Caso pretenda criptografar a mensagem, você deve usar uma tecnologia de criptografia adequada para criptografar conteúdo de mensagens; por exemplo, algo como o recurso Criptografia de Mensagens do Office. Confira [Email encryption in Office 365](email-encryption.md) e [Office 365 Message Encryption (OME)](ome.md) para saber mais sobre as opções de criptografia de mensagens no Office 365. 
  
Recomendamos o uso de TLS em situações em que você deseja configurar um canal seguro de correspondência entre a Microsoft e sua organização local ou outra organização, como um parceiro. O Exchange Online tenta primeiro usar o TLS para proteger seu email, mas não é possível fazer isso se a outra parte não oferecer segurança TLS. Continue lendo para descobrir como você pode proteger todos os emails para seus servidores locais ou parceiros importantes usando  *conectores*. 

Para fornecer a melhor criptografia na classe para nossos clientes, a Microsoft preterido o TLS (Transport Layer Security) 1.0 e 1.1 em [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) e [Office 365 GCC](tls-1-2-in-office-365-gcc.md). No entanto, você pode continuar a usar uma conexão SMTP não criptografada sem qualquer TLS. Não recomendamos a transmissão de email sem criptografia.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Como o Exchange Online usa o TLS entre clientes do Exchange Online

Os servidores do Exchange Online sempre criptografam conexões com outros servidores do Exchange Online em nossos data centers com TLS 1.2. Quando você envia emails para um destinatário que está dentro da sua organização, esse email é enviado automaticamente por uma conexão criptografada usando TLS. Além disso, todos os emails enviados a outros clientes são enviados por conexões criptografadas usando TLS e protegidas usando o Segredo de Encaminhamento.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Como Microsoft 365 usa TLS entre Microsoft 365 e parceiros confiáveis externos

Por padrão, o Exchange Online sempre usa o TLS oportunista. Isso significa que o Exchange Online sempre tenta criptografar as conexões com a versão mais segura do TLS primeiro e, em seguida, testa a lista de codificações TLS até encontrar uma que seja aceita por ambas as partes. A menos que você tenha configurado o Exchange Online para garantir que as mensagens para esse destinatário sejam enviadas apenas por meio de conexões seguras, por padrão, a mensagem será enviada sem criptografia se a organização do destinatário não suportar a criptografia TLS. O TLS oportunista é suficiente para a maioria das empresas. No entanto, para empresas que têm requisitos de conformidade, como organizações médicas, bancárias ou governamentais, você pode configurar Exchange Online exigir ou forçar o TLS. Para obter instruções, consulte [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
Se você decidir configurar o TLS entre sua organização e uma organização de parceiro confiável, o Exchange Online pode usar o TLS forçado para criar canais de comunicação confiáveis. O TLS forçado requer que a organização do parceiro autentique-se no Exchange Online com um certificado de segurança para enviar emails para você. Seu parceiro precisará gerenciar os próprios certificados para fazer isso. Em Exchange Online, usamos conectores para proteger mensagens que você envia de acesso não autorizado antes que elas cheguem ao provedor de email do destinatário. Para obter informações sobre como usar conectores para configurar o fluxo de emails, consulte [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS e implantações híbridas do Exchange Server

Se você estiver gerenciando uma implantação híbrida de Exchange, seu servidor local Exchange precisa se autenticar para Microsoft 365 usando um certificado de segurança para enviar emails aos destinatários cujas caixas de correio estão apenas Office 365. Como resultado, você precisa gerenciar seus próprios certificados de segurança para seus servidores Exchange locais. Você também deve armazenar e manter esses certificados de servidor de maneira segura. Para obter mais informações sobre como gerenciar certificados em implantações híbridas, consulte [Requisitos de certificado para implantações híbridas.](/exchange/certificate-requirements)
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Como configurar o TLS Forçado para Exchange Online no Office 365

Para clientes do Exchange Online, para que o TLS forçado proteja todos os emails enviados e recebidos, é necessário configurar mais de um conector que exija TLS. Você precisará de um conector para emails enviados para as caixas de correio dos seus usuários e outro para emails enviados a partir delas. Crie esses conectores no Centro de administração do Exchange no Office 365. Para obter instruções, consulte [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).
  
## <a name="tls-certificate-information-for-exchange-online"></a>Informações do certificado TLS para o Exchange Online

As informações do certificado usadas pelo Exchange Online são descritas na tabela a seguir. Se seu parceiro comercial estiver configurando a TLS forçada no servidor de email, você precisará fornecer essas informações para ele. Lembre-se de que, por motivos de segurança, os nossos certificados mudam de tempos em tempos. Nós rolamos uma atualização para nosso certificado em nossos datacenters. O novo certificado é válido a partir de 3 de setembro de 2018.
  
 **Informações de certificado atuais válidas a partir de 3 de setembro de 2018**
  
| Atributo | Valor |
|:-----|:-----|
|Emissor da raiz da autoridade de certificação  <br/> |GlobalSign Root CA – R1 <br/> |
|Nome do certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organização  <br/> |Microsoft Corporation  <br/> |
|Unidade organizacional  <br/> |  <br/> |
|Nível de segurança da chave do certificado  <br/> |2048  <br/> |
   
 **Informações de certificado preterido válidas até 3 de setembro de 2018**
  
Para ajudar a garantir uma transição suave, continuaremos fornecendo as informações antigas do certificado para sua referência por algum tempo, no entanto, você deve usar as informações de certificado atuais a partir de agora.
  
****

| Atributo | Valor |
|:-----|:-----|
|Emissor da raiz da autoridade de certificação  <br/> |Baltimore CyberTrust Root  <br/> |
|Nome do certificado  <br/> |mail.protection.outlook.com  <br/> |
|Organização  <br/> |Microsoft Corporation  <br/> |
|Unidade organizacional  <br/> |Microsoft Corporation  <br/> |
|Nível de segurança da chave do certificado  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Prepare-se para o novo Exchange Online certificado

O novo certificado é emitido por uma autoridade de certificação diferente (CA) do certificado anterior usado pelo Exchange Online. Como resultado, talvez seja necessário executar algumas ações para usar o novo certificado.

O novo certificado requer a conexão com os pontos de extremidade da nova AC como parte da validação do certificado. Se não fizer isso, o fluxo de emails será afetado negativamente. Se você proteger seus servidores de email com firewalls que permitem apenas que os servidores de email se conectem a determinados destinos, você precisa verificar se seu servidor é capaz de validar o novo certificado. Para confirmar se o servidor pode usar o novo certificado, conclua estas etapas:

1. Conexão para seu Exchange Server local usando Windows PowerShell e execute o seguinte comando:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. Na janela exibida, escolha **Recuperar**.

1. Quando o utilitário conclui sua verificação, ele retorna um status. Se o status for exibido **OK**, seu servidor de email poderá validar com êxito o novo certificado. Caso não seja, você precisará determinar o que está causando a falha das conexões. O mais provável é que você precise atualizar as configurações de um firewall. A lista completa de pontos de extremidade que precisam ser acessados incluem:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

Normalmente, você recebe atualizações para seus certificados raiz automaticamente por meio Windows Update. No entanto, algumas implantações têm segurança adicional que impede que essas atualizações ocorram automaticamente. Nessas implantações bloqueadas em que o Windows Update não pode atualizar automaticamente certificados raiz, você precisa garantir que o certificado de AC raiz correto seja instalado concluindo estas etapas:
1.  Conexão para seu Exchange Server local usando Windows PowerShell e execute o seguinte comando:  
  `certmgr.msc`

2. Em **Autoridade/Certificados de Certificação Raiz Confiáveis**, confirme se o novo certificado está listado.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Obter mais informações sobre TLS e Microsoft 365

Para obter uma lista de pacote de codificação com suporte, consulte [Detalhes de referência técnica sobre criptografia](technical-reference-details-about-encryption.md).
  
[Configurar conectores para fluxo de email seguro com uma organização parceira](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[Conectores com segurança de email aprimorada](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Criptografia no Microsoft 365](encryption.md)
