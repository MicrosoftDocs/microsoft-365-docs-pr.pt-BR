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
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051515"
---
# <a name="identity-for-the-contoso-corporation"></a>Identidade para a Contoso Corporation

A Microsoft fornece Identidade como Serviço (IDaaS) em suas ofertas de nuvem por meio Azure Active Directory (Azure AD). Para adotar Microsoft 365 para empresas, a solução contoso IDaaS precisava usar seu provedor de identidade local e incluir autenticação federada com seus provedores de identidade confiáveis e de terceiros existentes.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Floresta dos Serviços de Domínio do Active Directory da Contoso

A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso com sete subdomas, um para cada \. região do mundo. A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.

Aqui está a floresta Contoso com domínios regionais para as diferentes partes do mundo que contêm hubs regionais.

![Floresta e domínios da Contoso em todo o mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
A Contoso decidiu usar as contas e grupos na floresta contoso com para autenticação e autorização para suas Microsoft 365 \. cargas de trabalho e serviços.

## <a name="the-contoso-federated-authentication-infrastructure"></a>A infraestrutura de autenticação federada da Contoso

A Contoso permite que:

- Os clientes usam suas contas microsoft, Facebook ou Google Mail para entrar no site público da empresa.
- Fornecedores e parceiros para usar suas contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro da empresa.

Aqui está o DMZ da Contoso que contém um site público, uma extranet de parceiro e um conjunto de servidores do AD FS (Serviços de Federação do Active Directory). O DMZ está conectado à Internet que contém clientes, parceiros e serviços de Internet.

![Suporte da Contoso para autenticação federada para clientes e parceiros](../media/contoso-identity/contoso-identity-fig2.png)
 
Os servidores do AD FS no DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acesso ao site público e credenciais de parceiro para acesso à extranet do parceiro.

A Contoso decidiu manter essa infraestrutura e dedicá-la à autenticação de clientes e parceiros. Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) e [B2C](/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem

A Contoso queria usar sua floresta local do AD DS para autenticação para Microsoft 365 de nuvem. Ele decidiu usar a sincronização de hash de senha (PHS).

O PHS sincroniza a floresta local do AD DS com o locatário do Azure AD do seu Microsoft 365 para assinatura corporativa, copiando contas de usuário e grupo e uma versão com hashed de senhas de conta de usuário.

Para fazer a sincronização de diretórios, a Contoso implantou a ferramenta de Conexão do Azure AD em um servidor em seu datacenter de Paris.

Aqui está o servidor executando o Azure AD Conexão sondar a floresta contoso AD DS para alterações e, em seguida, sincronizar essas alterações com o locatário do Azure AD.

![A infraestrutura de sincronização de diretórios PHS contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Políticas de Acesso Condicional para acesso de identidades e dispositivos

A Contoso criou um conjunto de [políticas de Acesso Condicional](../security/defender-365-security/identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:

- *As* proteções de linha de base se aplicam a todas as contas de usuário.
- *Proteções* confidenciais se aplicam à liderança sênior e à equipe executiva.
- *Proteções altamente regulamentadas* se aplicam a usuários específicos nos departamentos de finanças, jurídicos e de pesquisa que têm acesso a dados altamente regulamentados.

Aqui está o conjunto resultante de políticas de Acesso Condicional da Contoso e identidade do dispositivo.

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso usa sua infraestrutura Microsoft Endpoint Configuration Manager para [implantar e manter](contoso-win10.md) as Windows 10 Enterprise em sua organização.

## <a name="see-also"></a>Confira também

[Mapa da identidade do Microsoft 365](identity-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)