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

A Microsoft fornece identidade como um serviço (IDaaS) em suas ofertas de nuvem por meio do Azure Active Directory (Azure AD). Para adotar o Microsoft 365 para empresas, a solução da Contoso IDaaS tinha que usar o provedor de identidade local e incluir a autenticação federada com os provedores de identidade confiáveis existentes de terceiros.

## <a name="the-contoso-active-directory-domain-services-forest"></a>A floresta de serviços de domínio do Active Directory da contoso

A contoso usa uma floresta única do AD DS (serviços de domínio Active Directory) para a contoso com \. com sete subdomínios, um para cada região do mundo. A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.

Aqui está a floresta contoso com domínios regionais para as diferentes partes do mundo que contêm hubs regionais.

![Floresta e domínios da Contoso em todo o mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
A Contoso decidiu usar as contas e os grupos na \. floresta com da Contoso para autenticação e autorização para seus serviços e cargas de trabalho do Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>A infraestrutura de autenticação federada da contoso

A Contoso permite que:

- Os clientes usem suas contas Microsoft, Facebook ou Google mail para entrar no site público da empresa.
- Fornecedores e parceiros usem suas contas de email do LinkedIn, Salesforce ou Google para entrar na extranet do parceiro da empresa.

Aqui está o DMZ da Contoso que contém um site público, uma extranet de parceiro e um conjunto de servidores de serviços de Federação do Active Directory (AD FS). O DMZ está conectado à Internet que contém clientes, parceiros e serviços de Internet.

![Suporte da Contoso para autenticação federada para clientes e parceiros](../media/contoso-identity/contoso-identity-fig2.png)
 
Os servidores do AD FS na DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acesso ao site público e às credenciais de parceiro para acesso à extranet do parceiro.

A Contoso decidiu manter essa infraestrutura e dedicar-a à autenticação de clientes e parceiros. Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem

A contoso queria usar sua floresta AD DS local para autenticação para recursos de nuvem da Microsoft 365. Ele decidiu usar a sincronização de hash de senha (PHS).

O PHS sincroniza a floresta do AD DS local com o locatário do Azure AD da sua assinatura do Microsoft 365 for Enterprise, copiando contas de usuário e de grupo e uma versão de hash de senhas de conta de usuário.

Para fazer a sincronização de diretório, a contoso implantou a ferramenta Azure AD Connect em um servidor em seu datacenter de Paris.

Aqui está o servidor que executa o Azure AD Connect sondando a floresta contoso AD DS para alterações e sincronizando essas alterações com o locatário do Azure AD.

![A infraestrutura de sincronização de diretórios do PHS da contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Políticas de Acesso Condicional para acesso de identidades e dispositivos

A Contoso criou um conjunto de [políticas de Acesso Condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:

- As proteções de *linha de base* são aplicadas a todas as contas de usuário.
- As proteções *confidenciais* se aplicam à liderança sênior e à equipe executiva.
- As proteções *altamente regulamentadas* se aplicam a usuários específicos nos departamentos financeiro, legal e de pesquisa que têm acesso a dados altamente regulamentados.

Veja a seguir o conjunto resultante de políticas de acesso condicional de dispositivo e identidade da contoso.

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Próxima etapa

Saiba como a contoso usa sua infraestrutura do Microsoft Endpoint Configuration Manager para [implantar e manter o Windows 10 Enterprise atual](contoso-win10.md) em toda a organização.

## <a name="see-also"></a>Confira também

[Mapa da identidade do Microsoft 365](identity-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
