---
title: Plano para certificados SSL de terceiros no Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Resumo: Descreve os certificados SSL necessários para o Exchange local e híbrido, o SSO usando o AD FS, os serviços do Exchange Online e os Serviços Web do Exchange.'
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687168"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Plano para certificados SSL de terceiros no Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para criptografar as comunicações entre seus clientes e o ambiente do Microsoft 365, certificados SSL de terceiros devem ser instalados em seus servidores de infraestrutura.

Este artigo faz parte do [planejamento de rede e ajuste de desempenho do Microsoft 365.](https://aka.ms/tune)
   
Os certificados são necessários para os seguintes componentes do Microsoft 365:
  
- Exchange local
    
- SSO (single sign-on) (para os servidores de federação dos Serviços de Federação do Active Directory (AD FS) e proxies do servidor de federação do AD FS)
    
- Serviços do Exchange Online, como Descoberta Automática, Outlook em Qualquer Lugar e Serviços Web do Exchange
    
- Servidor híbrido do Exchange
    
## <a name="certificates-for-exchange-on-premises"></a>Certificados para o Exchange local

Para obter uma visão geral sobre como usar certificados digitais para tornar a comunicação entre a organização local do Exchange e o Exchange Online segura, consulte o artigo TechNet noções básicas sobre requisitos [de certificado.](https://go.microsoft.com/fwlink/p/?LinkID=243657)
  
## <a name="certificates-for-single-sign-on"></a>Certificados de logon único

Para fornecer aos usuários uma experiência simplificada de logom único que inclua segurança robusta, os certificados mostrados na tabela a seguir são necessários nos servidores de federação ou nos proxies do servidor de federação. A tabela abaixo se concentra nos Serviços de Federação do Active Directory (AD FS), também temos mais informações sobre como usar provedores de [identidade de terceiros.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Tipo de Certificado | Descrição | O que você precisa saber antes de implantar |
|:-----|:-----|:-----|
|**Certificado SSL (também chamado de certificado de autenticação de servidor)** <br/> |Este é um certificado SSL padrão usado para tornar seguras as comunicações entre servidores de federação, clientes e computadores proxy do servidor de federação.  <br/> |O AD FS requer um certificado SSL. Por padrão, o AD FS usa o certificado SSL configurado para o site padrão nos Serviços de Informações da Internet (IIS).  <br/> O nome da assunto desse certificado SSL é usado para determinar o nome do Serviço de Federação (FS) para cada instância do AD FS que você implantar. Considere escolher um nome de assunto para quaisquer certificados emitidos pela nova autoridade de certificação (CA) que melhor representem o nome da sua empresa ou organização para o Microsoft 365. Esse nome deve ser de internet..  <br/>**Cuidado:** O AD FS requer que esse certificado SSL não tenha um nome de assunto sem pontos (nome curto).          <br/> **Recomendação:** Como esse certificado deve ser confiável para clientes do AD FS, recomendamos que você use um certificado SSL emitido por uma CA pública (de terceiros) ou por uma CA subordinada a uma raiz publicamente confiável; por exemplo, VeriSign ou Thawte.  <br/> |
|**Certificado de assinatura de token** <br/> |Este é um certificado X.509 padrão usado para assinar com segurança todos os tokens emitidos pelo servidor de federação e que o Microsoft 365 aceita e valida.  <br/> |O certificado de assinatura de token deve conter uma chave privada que é cadeia para uma raiz confiável no FS. Por padrão, o AD FS cria um certificado auto-assinado. No entanto, dependendo das necessidades da sua organização, você pode alterar esse certificado para um certificado emitido pela AC usando o snap-in de gerenciamento do AD FS.  <br/>**Cuidado:** O certificado de assinatura de token é fundamental para a estabilidade do FS. Se o certificado for alterado, o Microsoft 365 deverá ser notificado sobre a alteração. Se a notificação não for fornecida, os usuários não poderão entrar em suas ofertas de serviço do Microsoft 365.<br/>**Recomendação:** Recomendamos que você use o certificado de assinatura de token auto-assinado gerado pelo AD FS. Ao fazer isso, ele gerencia esse certificado para você por padrão. Por exemplo, quando esse certificado está prestes a expirar, o AD FS gerará um novo certificado auto-assinado.  <br/> |
   
Os proxies do servidor de federação exigem o certificado descrito na tabela a seguir.
  
| Tipo de Certificado | Descrição | O que você precisa saber antes de implantar |
|:-----|:-----|:-----|
|Certificado SSL  <br/> |Este é um certificado SSL padrão usado para proteger as comunicações entre um servidor de federação, um proxy de servidor de federação e computadores clientes da Internet.  <br/> |Esse certificado SSL deve ser vinculado ao site padrão no IIS antes que você possa executar com êxito o assistente de Configuração do Proxy do Servidor de Federação do AD FS.  <br/> Esse certificado deve ter o mesmo nome de assunto que o certificado SSL configurado no servidor de federação na rede corporativa.  <br/> **Recomendação:** Recomendamos que você use o mesmo certificado de autenticação de servidor configurado no servidor de federação ao que esse proxy do servidor de federação se conecta.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificados para Descoberta Automática, Outlook em Qualquer Lugar e Sincronização do Active Directory

Seus servidores de Acesso para Cliente (CASs) voltados para o Exchange 2013, Exchange 2010, Exchange 2007 e Exchange 2003 exigem um certificado SSL de terceiros para conexões seguras para os serviços de sincronização de Descoberta Automática, Outlook em Qualquer Lugar e Active Directory. Talvez você já tenha esse certificado instalado em seu ambiente local.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificado para um Servidor Híbrido do Exchange

O servidor ou servidores híbridos do Exchange voltados para o exterior exigem um certificado SSL de terceiros para conectividade segura com o serviço do Exchange Online. Você precisa obter esse certificado do provedor SSL de terceiros.
  
## <a name="microsoft-365-certificate-chains"></a>Cadeias de certificados do Microsoft 365

Este artigo descreve os certificados que talvez você precise instalar em sua infraestrutura. Para saber mais sobre os certificados instalados em nossos servidores do Microsoft 365, confira Cadeias de Certificados do [Microsoft 365.](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
