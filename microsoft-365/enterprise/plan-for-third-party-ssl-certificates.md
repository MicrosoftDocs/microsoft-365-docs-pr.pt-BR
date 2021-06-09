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
description: 'Resumo: descreve os certificados SSL necessários para o Exchange local e híbrido, o SSO usando o AD FS, os serviços Exchange Online e o Exchange Web.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927483"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Plano para certificados SSL de terceiros no Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para criptografar as comunicações entre seus clientes e o ambiente Microsoft 365, certificados SSL (Secure Socket Layer) de terceiros devem ser instalados em seus servidores de infraestrutura.

Este artigo faz parte do [planejamento de rede e ajuste de desempenho para Microsoft 365](./network-planning-and-performance.md).
   
Os certificados são necessários para os seguintes Microsoft 365 componentes:
  
- Exchange local
    
- SSO (sign-on único) (para servidores de federação do Active Directory Federation Services (AD FS) e proxies de servidor de federação do AD FS)
    
- Exchange Online, como Descoberta Automática, Outlook em Qualquer Lugar e Exchange Web
    
- Exchange servidor híbrido
    
## <a name="certificates-for-exchange-on-premises"></a>Certificados para Exchange local

Para obter uma visão geral sobre como usar certificados digitais para tornar a comunicação entre a organização Exchange local e a Exchange Online segura, consulte o artigo TechNet [Understanding Certificate Requirements](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).
  
## <a name="certificates-for-single-sign-on"></a>Certificados de logon único

Para fornecer aos usuários uma experiência de logona simples simplificada que inclua segurança robusta, os certificados mostrados na tabela a seguir são necessários nos servidores de federação ou nos proxies do servidor de federação. A tabela abaixo se concentra nos Serviços de Federação do Active Directory (AD FS), também temos mais informações sobre como usar provedores de identidade [de terceiros.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Tipo de certificado | Descrição | O que você precisa saber antes de implantar |
|:-----|:-----|:-----|
|**Certificado SSL (também chamado de certificado de autenticação de servidor)** <br/> |Este é um certificado SSL padrão usado para tornar as comunicações entre servidores de federação, clientes e computadores proxy de servidor de federação seguros.  <br/> |O AD FS requer um certificado SSL. Por padrão, o AD FS usa o certificado SSL configurado para o site padrão no Serviços de Informações da Internet (IIS).  <br/> O nome do assunto deste certificado SSL é usado para determinar o nome do Serviço de Federação (FS) para cada instância do AD FS implantado. Considere escolher um nome de assunto para quaisquer certificados emitidos pela autoridade de certificação (CA) que melhor representem o nome da sua empresa ou organização para Microsoft 365. Esse nome deve ser instável na Internet.  <br/>**Cuidado:** O AD FS exige que esse certificado SSL não tenha um nome de assunto sem ponto (nome curto).          <br/> **Recomendação:** Como esse certificado deve ser confiável por clientes do AD FS, recomendamos que você use um certificado SSL emitido por uma CA pública (de terceiros) ou por uma AC subordinada a uma raiz publicamente confiável; por exemplo, VeriSign ou Thawte.  <br/> |
|**Certificado de assinatura de token** <br/> |Este é um certificado X.509 padrão usado para assinar com segurança todos os tokens que o servidor de federação emite e que Microsoft 365 aceita e valida.  <br/> |O certificado de assinatura de token deve conter uma chave privada que a cadeia para uma raiz confiável no FS. Por padrão, o AD FS cria um certificado auto-assinado. No entanto, dependendo das necessidades da sua organização, você pode alterar esse certificado para um certificado emitido pela CA usando o snap-in de gerenciamento do AD FS.  <br/>**Cuidado:** O certificado de assinatura de token é fundamental para a estabilidade do FS. Se o certificado for alterado, Microsoft 365 deverá ser notificado sobre a alteração. Se a notificação não for fornecida, os usuários não poderão entrar em suas ofertas Microsoft 365 serviço.<br/>**Recomendação:** Recomendamos que você use o certificado de assinatura de token auto-assinado gerado pelo AD FS. Ao fazer isso, ele gerencia esse certificado para você por padrão. Por exemplo, quando esse certificado estiver prestes a expirar, o AD FS gerará um novo certificado auto-assinado.  <br/> |
   
Proxies de servidor de federação exigem o certificado descrito na tabela a seguir.
  
| Tipo de certificado | Descrição | O que você precisa saber antes de implantar |
|:-----|:-----|:-----|
|Certificado SSL  <br/> |Este é um certificado SSL padrão usado para proteger comunicações entre um servidor de federação, um proxy de servidor de federação e computadores cliente da Internet.  <br/> |Esse certificado SSL deve estar vinculado ao site padrão no IIS para que você possa executar com êxito o assistente de Configuração de Proxy do Servidor de Federação do AD FS.  <br/> Esse certificado deve ter o mesmo nome de assunto que o certificado SSL configurado no servidor de federação na rede corporativa.  <br/> **Recomendação:** Recomendamos que você use o mesmo certificado de autenticação de servidor configurado no servidor de federação ao que esse proxy de servidor de federação se conecta.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificados para Descoberta Automática, Outlook em Qualquer Lugar e Sincronização do Active Directory

Seus servidores de Acesso para Cliente (CASs) voltados para o Exchange 2013, Exchange 2010, Exchange 2007 e Exchange 2003 exigem um certificado SSL de terceiros para conexões seguras para serviços de sincronização de Descoberta Automática, Outlook Em Qualquer Lugar e Active Directory. Você já pode ter esse certificado instalado em seu ambiente local.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificado para um servidor Exchange híbrido

Seus servidores ou servidores híbridos voltados Exchange externos exigem um certificado SSL de terceiros para conectividade segura com o serviço Exchange Online de terceiros. Você precisa obter esse certificado do provedor SSL de terceiros.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Cadeias de certificados

Este artigo descreve os certificados que talvez você precise instalar em sua infraestrutura. Para obter mais informações sobre os certificados instalados em nossos servidores Microsoft 365, [consulte Microsoft 365 Cadeias de Certificados.](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)