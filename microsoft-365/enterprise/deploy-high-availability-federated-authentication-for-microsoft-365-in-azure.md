---
title: Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 'Resumo: Configure a autenticação federada de alta disponibilidade para sua assinatura do Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687285"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure

Este artigo tem links para as instruções passo a passo para implantar a autenticação federada de alta disponibilidade para o Microsoft Microsoft 365 nos serviços de infraestrutura do Azure com estas máquinas virtuais:
  
- Dois servidores proxy de aplicativo Web
    
- Dois servidores dos Serviços de Federação do Active Directory (AD FS)
    
- Dois controladores de domínio de réplica
    
- Um servidor de sincronização de diretório que executa o Azure AD Connect
    
Aqui está a configuração, com nomes de espaço reservado para cada servidor.
  
**Uma autenticação federada de alta disponibilidade para a infraestrutura do Microsoft 365 no Azure**

![A configuração final da infraestrutura de autenticação federada de alta disponibilidade da Microsoft 365 no Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Todas as máquinas virtuais estão em uma única rede virtual do Azure entre instalações (VNet). 
  
> [!NOTE]
> A autenticação federada de usuários individuais não confia em nenhum recurso local. No entanto, se a conexão entre instalações ficar indisponível, os controladores de domínio na VNet não receberão as atualizações das contas de usuários e grupos feitas no AD do Serviços de Domínio do Active Directory(AD DS). Para garantir que isso não aconteça, você pode configurar a alta disponibilidade para sua conexão entre instalações. Veja mais informações em [Conectividade VNet para VNet e entre instalações altamente disponível](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
Cada par de máquinas virtuais para uma função específica está em sua própria sub-rede e conjunto de disponibilidade.
  
> [!NOTE]
> Como esta VNet está conectada à rede local, essa configuração não inclui jumpbox ou monitoramento de máquinas virtuais em uma sub-rede de gerenciamento. Veja mais informações em [Executando VMs do Windows para uma arquitetura de N camadas](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm). 
  
O resultado dessa configuração é que você terá autenticação federada para todos os seus usuários do Microsoft 365, nos quais eles podem usar suas credenciais do AD DS para entrar em vez de sua conta do Microsoft 365. A infraestrutura de autenticação federada usa um conjunto redundante de servidores que são mais facilmente implantados em serviços de infraestrutura do Azure, em vez de em sua rede de borda local.
  
## <a name="bill-of-materials"></a>Lista de materiais

Essa configuração da linha de base requer o conjunto de serviços do Azure e os componentes a seguir:
  
- Sete máquinas virtuais
    
- Uma rede virtual entre locais com quatro sub-redes
    
- Quatro grupos de recursos
    
- Três conjuntos de disponibilidade
    
- Uma assinatura do Azure
    
Veja as máquinas virtuais e seus respectivos tamanhos padrão para essa configuração.
  
|**Item**|**Descrição da máquina virtual**|**Imagem da galeria do Azure**|**Tamanho padrão**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Primeiro controlador de domínio  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|2.  <br/> |Segundo controlador de domínio  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|3.  <br/> |Servidor do Azure AD Connect  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|4.  <br/> |Primeiro servidor do AD FS  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|5.  <br/> |Segundo servidor do AD FS  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|6.  <br/> |Primeiro servidor proxy de aplicativo Web  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|7.  <br/> |Segundo servidor proxy de aplicativo Web  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
   
Para calcular os custos estimados para essa configuração, veja a [Calculadora de preços do Azure](https://azure.microsoft.com/pricing/calculator/).
  
## <a name="phases-of-deployment"></a>Fases da implantação

Implante essa carga de trabalho nas seguintes fases:
  
- [Fase 1: Configurar o Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Crie grupos de recursos, contas de armazenamento, conjuntos de disponibilidade e uma rede virtual entre locais.
    
- [Fase 2: configurar os controladores de domínio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Criar e configurar os controladores de domínio de réplica e o servidor de sincronização de diretório do AD DS.
    
- [Fase 3: Configurar os servidores do AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Crie e configure os dois servidores do AD FS.
    
- [Fase 4: Configurar proxies de aplicativos Web](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Crie e configure os dois servidores proxy de aplicativos Web.
    
- [Fase 5: configurar a autenticação federada para o Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Configure a autenticação federada para sua assinatura do Microsoft 365.
    
Estes artigos fornecem um guia prescritiva passo a passo para uma arquitetura predefinida para criar uma autenticação federada funcional e de alta disponibilidade para o Microsoft 365 nos serviços de infraestrutura do Azure. Lembre-se do seguinte:
  
- Se você for um implementador experiente do AD FS, fique à vontade para adaptar as instruções nas fases 3 e 4 e crie o conjunto de servidores que seja mais adequado às suas necessidades. 
    
- Se você já tiver uma implantação de nuvem híbrida do Azure com uma rede virtual entre instalações, fique à vontade para adaptar ou ignorar as instruções nas etapas 1 e 2 e coloque os servidores proxy de aplicativo Web e o AD FS nas sub-redes adequadas.
    
Para criar um ambiente de desenvolvimento/teste ou uma prova de conceito dessa configuração, consulte [identidade federada para seu ambiente de desenvolvimento/teste do Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md).
  
## <a name="next-step"></a>Próxima etapa

Inicie a configuração dessa carga de trabalho com [Fase 1: Configurar o Azure](high-availability-federated-authentication-phase-1-configure-azure.md). 
  
