---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754627"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidade para a Contoso Corporation

A Microsoft fornece a Identidade como serviço (IDaaS) em suas ofertas de nuvem por meio do Azure Active Directory (Azure AD). Para adotar o Microsoft 365 para empresas, a solução IDaaS da Contoso precisava usar seu provedor de identidade local e incluir a autenticação federada com seus provedores de identidade confiáveis de terceiros existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>A floresta dos Serviços de Domínio active Directory da Contoso

A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso com sete sub-domínios, um para cada \. região do mundo. A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.

Esta é a floresta da Contoso com domínios regionais para as diferentes partes do mundo que contêm hubs regionais.

![Floresta e domínios da Contoso em todo o mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
A Contoso decidiu usar as contas e grupos na floresta contoso com para autenticação e autorização para suas cargas de trabalho e serviços \. do Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>A infraestrutura de autenticação federada da Contoso

A Contoso permite que:

- Clientes usem suas contas da Microsoft, Facebook ou Google Mail para entrar no site público da empresa.
- Fornecedores e parceiros usem suas contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro da empresa.

Aqui está a DMZ da Contoso que contém um site público, uma extranet de parceiro e um conjunto de servidores dos Serviços de Federação do Active Directory (AD FS). A DMZ está conectada à Internet que contém clientes, parceiros e serviços de Internet.

![Suporte da Contoso para autenticação federada para clientes e parceiros](../media/contoso-identity/contoso-identity-fig2.png)
 
Os servidores do AD FS na DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acessar o site público e as credenciais de parceiros para acessar a extranet do parceiro.

A Contoso decidiu manter essa infraestrutura e dedicá-la à autenticação de clientes e parceiros. Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem

A Contoso queria usar sua floresta local do AD DS para autenticação em recursos de nuvem do Microsoft 365. Ele decidiu usar a sincronização de hash de senha (PHS).

O PHS sincroniza a floresta local do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 para empresas, copiando contas de usuário e grupo e uma versão com senhas de conta de usuário com código.

Para fazer a sincronização de diretórios, a Contoso implantou a ferramenta Azure AD Connect em um servidor em seu datacenter de Paris.

Aqui está o servidor que executa o Azure AD Connect sondando a floresta do AD DS da Contoso para alterações e sincronizando essas alterações com o locatário do Azure AD.

![A infraestrutura de sincronização de diretórios PHS da Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Políticas de Acesso Condicional para acesso de identidades e dispositivos

A Contoso criou um conjunto de [políticas de Acesso Condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:

- *As proteções* de linha de base se aplicam a todas as contas de usuário.
- *Proteções* confidenciais se aplicam à liderança sênior e à equipe executiva.
- *As proteções altamente* regulamentadas se aplicam a usuários específicos nos departamentos de finanças, jurídicos e de pesquisa que têm acesso a dados altamente regulamentados.

Aqui está o conjunto resultante de políticas de Acesso Condicional de dispositivo e identidade da Contoso.

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso usa sua infraestrutura do Microsoft Endpoint Configuration Manager para implantar e manter [o Windows 10 Enterprise](contoso-win10.md) atual em toda a organização.

## <a name="see-also"></a>Confira também

[Mapa da identidade do Microsoft 365](identity-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
