---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: bcd83eaafb5df86d9a660aeb74b2e97f7bdc6b7b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277554"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidade para a Contoso Corporation

**Resumo:** como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece autenticação baseada em nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.

A Microsoft fornece identidade como um serviço (IDaaS) em todas as suas ofertas de nuvem com o Azure Active Directory (Azure AD). Para adotar o Microsoft 365 Enterprise, a solução IDaaS da Contoso teve que aproveitar seu provedor de identidade local e ainda assim incluir autenticação federada com seus atuais provedores de identidade confiáveis de terceiros.

## <a name="contosos-active-directory-domain-services-forest"></a>Floresta dos Serviços de Domínio do Active Directory da Contoso

A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso.com com sete subdomínios, uma para cada região do mundo. A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.

A Figura 1 mostra a floresta da Contoso com domínios regionais para diferentes partes do mundo que possuem hubs regionais.

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**Figura 1: floresta e domínios da Contoso em todo o mundo**

A Contoso queria usar as contas e grupos na floresta de contoso.com para autenticação e autorização de suas cargas de trabalho e serviços do Microsoft 365.

## <a name="contosos-federated-authentication-infrastructure"></a>Infraestrutura de autenticação federada da Contoso

A Contoso permite que:

- Clientes usem as contas da Microsoft, Facebook ou Google Mail para entrar no site público.
- Fornecedores e parceiros usam as contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro.

A Figura 2 mostra a DMZ da Contoso, contendo um site público, uma extranet de parceiro e um conjunto de servidores dos Serviços de Federação do Active Directory (AD FS). A DMZ está conectada à Internet, onde estão os clientes, parceiros e serviços de Internet.

![](./media/contoso-identity/contoso-identity-fig2.png)

**Figura 2: suporte da Contoso para autenticação federada para clientes e parceiros**
 
Os servidores AD FS (Serviços de Federação do Active Directory) na DMZ autenticam as credenciais do cliente para acesso ao site público e as credenciais de parceiro para acesso à extranet do parceiro.

A Contoso decidiu manter esta infraestrutura e dedicá-la a autenticações de parceiros e clientes. Os engenheiros de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções de [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) do Azure AD.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem

A Contoso queria aproveitar sua floresta do AD DS local para autenticação para os recursos de nuvem do Microsoft 365. Ela escolheu sincronização de hash de senha (PHS).

A PHS sincroniza a floresta do AD DS local com o locatário do Azure AD de sua assinatura do Microsoft 365 Enterprise, copiando contas de usuários e de grupo e uma versão especificada como hash de senhas de contas de usuários. 

Para realizar a sincronização de diretórios em andamento, a Contoso implantou a ferramenta Azure AD Connect em um servidor no seu datacenter em Paris. A figura 3 mostra o servidor executando o Azure AD Connect sondando mudanças na floresta do AD DS da Contoso e sincronizando essas mudanças com o locatário do Azure AD.

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**Figura 3: infraestrutura PHS de sincronização de diretórios da Contoso**


## <a name="conditional-access-policies-for-identity-and-device-access"></a>Políticas de acesso condicional para identidades e dispositivos

A Contoso criou um conjunto de [políticas de acesso condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:

- Proteções de **linha de base** aplicam-se a todas as contas de usuários
- Proteções **confidenciais** aplicam-se à liderança sênior e equipe executiva
- Proteções **altamente controladas** aplicam-se a usuários específicos nos departamentos de finanças, jurídico e de pesquisa que têm acesso a dados altamente controlados.

A figura 4 mostra o conjunto resultante de políticas de acesso condicional de identidades e dispositivos.

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**Figura 4: as políticas de acesso condicional de identidades e dispositivos da Contoso**

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-win10.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Windows 10 Enterprise atualizado em toda a organização.

## <a name="see-also"></a>Confira também

[Identidade para Microsoft 365 Enterprise](identity-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
