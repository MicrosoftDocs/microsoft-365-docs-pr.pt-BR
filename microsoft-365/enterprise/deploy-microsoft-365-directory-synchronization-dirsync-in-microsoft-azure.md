---
title: Implantar Microsoft 365 Sincronização de Diretórios no Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Saiba como implantar o Azure AD Conexão em uma máquina virtual no Azure para sincronizar contas entre o diretório local e o locatário do Azure AD.
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919081"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a><span data-ttu-id="a9a23-103">Implantar Microsoft 365 Sincronização de Diretórios no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-103">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>

<span data-ttu-id="a9a23-104">Azure Active Directory (Azure AD) Conexão (anteriormente conhecido como a ferramenta de Sincronização de Diretórios, a ferramenta de Sincronização de Diretórios ou a ferramenta DirSync.exe) é um aplicativo que você instala em um servidor ingressado em domínio para sincronizar seus usuários locais do Active Directory Domain Services (AD DS) ao locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-104">Azure Active Directory (Azure AD) Connect (formerly known as the Directory Synchronization tool, Directory Sync tool, or the DirSync.exe tool) is an application that you install on a domain-joined server to synchronize your on-premises Active Directory Domain Services (AD DS) users to the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="a9a23-105">Microsoft 365 usa o Azure AD para seu serviço de diretório.</span><span class="sxs-lookup"><span data-stu-id="a9a23-105">Microsoft 365 uses Azure AD for its directory service.</span></span> <span data-ttu-id="a9a23-106">Sua Microsoft 365 assinatura inclui um locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9a23-106">Your Microsoft 365 subscription includes an Azure AD tenant.</span></span> <span data-ttu-id="a9a23-107">Esse locatário também pode ser usado para o gerenciamento de identidades da sua organização com outras cargas de trabalho de nuvem, incluindo outros aplicativos SaaS e aplicativos no Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a23-107">This tenant can also be used for management of your organization's identities with other cloud workloads, including other SaaS applications and apps in Azure.</span></span>

<span data-ttu-id="a9a23-108">Você pode instalar o Azure AD Connect em um servidor local, mas pode também instalá-lo em uma máquina virtual no Azure pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="a9a23-108">You can install Azure AD Connect on a on-premises server, but you can also install it on a virtual machine in Azure for these reasons:</span></span>
  
- <span data-ttu-id="a9a23-109">Você pode provisionar e configurar servidores baseados na nuvem mais depressa, disponibilizando os serviços aos usuários com mais antecedência.</span><span class="sxs-lookup"><span data-stu-id="a9a23-109">You can provision and configure cloud-based servers faster, making the services available to your users sooner.</span></span>
- <span data-ttu-id="a9a23-110">O Azure oferece melhor disponibilidade de sites com menos esforço.</span><span class="sxs-lookup"><span data-stu-id="a9a23-110">Azure offers better site availability with less effort.</span></span>
- <span data-ttu-id="a9a23-111">Você pode reduzir o número de servidores locais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a9a23-111">You can reduce the number of on-premises servers in your organization.</span></span>

<span data-ttu-id="a9a23-p102">Essa solução requer conectividade entre sua rede local e sua Rede Virtual do Azure. Para saber mais, confira o artigo [Conectar uma rede local a uma rede virtual do Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="a9a23-p102">This solution requires connectivity between your on-premises network and your Azure virtual network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9a23-114">Este artigo descreve a sincronização de um único domínio em uma única floresta.</span><span class="sxs-lookup"><span data-stu-id="a9a23-114">This article describes synchronization of a single domain in a single forest.</span></span> <span data-ttu-id="a9a23-115">O Azure AD Conexão sincroniza todos os domínios do AD DS em sua floresta do Active Directory com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-115">Azure AD Connect synchronizes all AD DS domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="a9a23-116">Se você tiver várias florestas do Active Directory para sincronizar com Microsoft 365, consulte [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="a9a23-116">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a><span data-ttu-id="a9a23-117">Visão geral da implantação Microsoft 365 sincronização de diretórios no Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-117">Overview of deploying Microsoft 365 directory synchronization in Azure</span></span>

<span data-ttu-id="a9a23-118">O diagrama a seguir mostra o Azure AD Conexão em execução em uma máquina virtual no Azure (o servidor de sincronização de diretórios) que sincroniza uma floresta local do AD DS a uma assinatura Microsoft 365 local.</span><span class="sxs-lookup"><span data-stu-id="a9a23-118">The following diagram shows Azure AD Connect running on a virtual machine in Azure (the directory sync server) that synchronizes an on-premises AD DS forest to a Microsoft 365 subscription.</span></span>
  
![Ferramenta de Conexão do Azure AD em uma máquina virtual no Azure sincronizando contas locais com o locatário do Azure AD de uma assinatura Microsoft 365 com fluxo de tráfego](../media/CP-DirSyncOverview.png)
  
<span data-ttu-id="a9a23-p104">No diagrama, há duas redes conectadas por meio de uma conexão VPN site a site ou ExpressRoute. Há uma rede local em que os controladores de domínio do AD DS estão localizados e há uma rede virtual do Azure com um servidor de sincronização de diretório, uma máquina virtual que executa o [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Existem dois fluxos de tráfego principais provenientes do servidor de sincronização de diretório:</span><span class="sxs-lookup"><span data-stu-id="a9a23-p104">In the diagram, there are two networks connected by a site-to-site VPN or ExpressRoute connection. There is an on-premises network where AD DS domain controllers are located, and there is an Azure virtual network with a directory sync server, which is a virtual machine running [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). There are two main traffic flows originating from the directory sync server:</span></span>
  
-  <span data-ttu-id="a9a23-123">O Azure AD Connect consulta um controlador de domínio na rede local para detectar alterações em contas e senhas.</span><span class="sxs-lookup"><span data-stu-id="a9a23-123">Azure AD Connect queries a domain controller on the on-premises network for changes to accounts and passwords.</span></span>
-  <span data-ttu-id="a9a23-124">O Azure AD Conexão as alterações em contas e senhas para a instância do Azure AD de sua assinatura Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-124">Azure AD Connect sends the changes to accounts and passwords to the Azure AD instance of your Microsoft 365 subscription.</span></span> <span data-ttu-id="a9a23-125">Como o servidor de sincronização de diretórios está em uma parte estendida da sua rede local, essas alterações são enviadas por meio do servidor proxy da rede local.</span><span class="sxs-lookup"><span data-stu-id="a9a23-125">Because the directory sync server is in an extended portion of your on-premises network, these changes are sent through the on-premises network's proxy server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a9a23-126">Esta solução descreve a sincronização de um único domínio do Active Directory, uma única floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9a23-126">This solution describes synchronization of a single Active Directory domain, in a single Active Directory forest.</span></span> <span data-ttu-id="a9a23-127">O Azure AD Conexão sincroniza todos os domínios do Active Directory em sua floresta do Active Directory com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-127">Azure AD Connect synchronizes all Active Directory domains in your Active Directory forest with Microsoft 365.</span></span> <span data-ttu-id="a9a23-128">Se você tiver várias florestas do Active Directory para sincronizar com Microsoft 365, consulte [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="a9a23-128">If you have multiple Active Directory forests to synchronize with Microsoft 365, see [Multi-forest Directory Sync with Single Sign-On Scenario](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span> 
  
<span data-ttu-id="a9a23-129">Há duas etapas principais quando você implanta essa solução:</span><span class="sxs-lookup"><span data-stu-id="a9a23-129">There are two major steps when you deploy this solution:</span></span>
  
1. <span data-ttu-id="a9a23-p107">Criar uma rede virtual do Azure e estabelecer uma conexão VPN de site a site para a sua rede local. Para saber mais, confira o artigo [Conectar uma rede local a uma rede virtual do Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="a9a23-p107">Create an Azure virtual network and establish a site-to-site VPN connection to your on-premises network. For more information, see [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
    
2. <span data-ttu-id="a9a23-132">Instale [o Azure AD Conexão](https://www.microsoft.com/download/details.aspx?id=47594) em uma máquina virtual ingressada no domínio no Azure e sincronizar o AD DS local para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-132">Install [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) on a domain-joined virtual machine in Azure, and then synchronize the on-premises AD DS to Microsoft 365.</span></span> <span data-ttu-id="a9a23-133">Isso envolve:</span><span class="sxs-lookup"><span data-stu-id="a9a23-133">This involves:</span></span>
    
    <span data-ttu-id="a9a23-134">Criar uma Máquina Virtual do Azure para executar o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="a9a23-134">Creating an Azure Virtual Machine to run Azure AD Connect.</span></span>
    
    <span data-ttu-id="a9a23-135">Instalar e configurar o [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span><span class="sxs-lookup"><span data-stu-id="a9a23-135">Installing and configuring [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).</span></span>
    
    <span data-ttu-id="a9a23-136">Configurar o Azure AD Conexão requer as credenciais (nome de usuário e senha) de uma conta de administrador do Azure AD e uma conta de administrador empresarial do AD DS.</span><span class="sxs-lookup"><span data-stu-id="a9a23-136">Configuring Azure AD Connect requires the credentials (user name and password) of an Azure AD administrator account and a AD DS enterprise administrator account.</span></span> <span data-ttu-id="a9a23-137">O Azure AD Conexão executado imediatamente e continuamente para sincronizar a floresta local do AD DS para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-137">Azure AD Connect runs immediately and on an ongoing basis to synchronize the on-premises AD DS forest to Microsoft 365.</span></span>
    
<span data-ttu-id="a9a23-138">Antes de implantar essa solução em produção, [](simulated-ent-base-configuration-microsoft-365-enterprise.md) você pode usar as instruções na configuração base corporativa simulada para configurar essa configuração como uma prova de conceito, para demonstrações ou para experimentação.</span><span class="sxs-lookup"><span data-stu-id="a9a23-138">Before you deploy this solution in production, you can use the instructions in [The simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to set this configuration up as a proof of concept, for demonstrations, or for experimentation.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a9a23-139">Quando a configuração do Azure AD Connect for concluída, ele não salvará as credenciais de conta de administrador corporativo do AD DS.</span><span class="sxs-lookup"><span data-stu-id="a9a23-139">When Azure AD Connect configuration completes, it does not save the AD DS enterprise administrator account credentials.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9a23-140">Esta solução descreve a sincronização de uma única floresta do AD DS para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-140">This solution describes synchronizing a single AD DS forest to Microsoft 365.</span></span> <span data-ttu-id="a9a23-141">A topologia abordada neste artigo representa apenas uma das maneiras de implementar essa solução.</span><span class="sxs-lookup"><span data-stu-id="a9a23-141">The topology discussed in this article represents only one way to implement this solution.</span></span> <span data-ttu-id="a9a23-142">A topologia de sua organização pode ser diferente, com base em requisitos de rede e considerações de segurança exclusivos.</span><span class="sxs-lookup"><span data-stu-id="a9a23-142">Your organization's topology might differ based on your unique network requirements and security considerations.</span></span> 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a><span data-ttu-id="a9a23-143">Planejar a hospedagem de um servidor de sincronização de diretórios Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-143">Plan for hosting a directory sync server for Microsoft 365 in Azure</span></span>
<span data-ttu-id="a9a23-144"><a name="PlanningVirtual"> </a></span><span class="sxs-lookup"><span data-stu-id="a9a23-144"><a name="PlanningVirtual"> </a></span></span>

### <a name="prerequisites"></a><span data-ttu-id="a9a23-145">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a9a23-145">Prerequisites</span></span>

<span data-ttu-id="a9a23-146">Antes de começar, examine os seguintes pré-requisitos para essa solução:</span><span class="sxs-lookup"><span data-stu-id="a9a23-146">Before you begin, review the following prerequisites for this solution:</span></span>
  
- <span data-ttu-id="a9a23-147">Examine o conteúdo de planejamento relacionado em [Planejar sua rede virtual do Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span><span class="sxs-lookup"><span data-stu-id="a9a23-147">Review the related planning content in [Plan your Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).</span></span>
    
- <span data-ttu-id="a9a23-148">Verifique se você atende a todos os [pré-requisitos](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) para configurar a Rede Virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a23-148">Ensure that you meet all [Prerequisites](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) for configuring the Azure virtual network.</span></span>
    
- <span data-ttu-id="a9a23-149">Tenha uma Microsoft 365 que inclui o recurso de integração do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9a23-149">Have a Microsoft 365 subscription that includes the Active Directory integration feature.</span></span> <span data-ttu-id="a9a23-150">Para obter informações sobre Microsoft 365 assinaturas, acesse a página Microsoft 365 [assinatura.](https://products.office.com/compare-all-microsoft-office-products?tab=2)</span><span class="sxs-lookup"><span data-stu-id="a9a23-150">For information about Microsoft 365 subscriptions, go to the [Microsoft 365 subscription page](https://products.office.com/compare-all-microsoft-office-products?tab=2).</span></span>
    
- <span data-ttu-id="a9a23-151">Provisione uma máquina virtual do Azure que executa o Azure AD Conexão sincronizar sua floresta local do AD DS com Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-151">Provision one Azure Virtual Machine that runs Azure AD Connect to synchronize your on-premises AD DS forest with Microsoft 365.</span></span>
    
    <span data-ttu-id="a9a23-152">Você deve ter as credenciais (nomes e senhas) para a conta de administrador corporativo do AD DS e uma conta de Administrador do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9a23-152">You must have the credentials (names and passwords) for a AD DS enterprise administrator account and an Azure AD Administrator account.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="a9a23-153">Suposições de design de arquitetura da solução</span><span class="sxs-lookup"><span data-stu-id="a9a23-153">Solution architecture design assumptions</span></span>

<span data-ttu-id="a9a23-154">A lista a seguir descreve as opções de design feitas para essa solução.</span><span class="sxs-lookup"><span data-stu-id="a9a23-154">The following list describes the design choices made for this solution.</span></span>
  
- <span data-ttu-id="a9a23-p112">Essa solução usa uma única rede virtual do Azure com uma conexão VPN de site a site. A rede virtual do Azure hospeda uma única sub-rede que contém um servidor, o servidor de sincronização de diretório que está executando o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p112">This solution uses a single Azure virtual network with a site-to-site VPN connection. The Azure virtual network hosts a single subnet that has one server, the directory sync server that is running Azure AD Connect.</span></span> 
    
- <span data-ttu-id="a9a23-157">Na rede local, existem servidores DNS e um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="a9a23-157">On the on-premises network, a domain controller and DNS servers exist.</span></span>
    
- <span data-ttu-id="a9a23-p113">O Azure AD Connect realiza a sincronização de hash de senha, em vez de logon único. Você não precisa implantar uma infraestrutura de AD FS (Serviços de Federação do Active Directory). Para saber mais sobre as opções de sincronização de hash de senha e logon único, confira [Escolher o método de autenticação correto para sua solução de identidade híbrida do Azure Active Directory](/azure/active-directory/hybrid/choose-ad-authn).</span><span class="sxs-lookup"><span data-stu-id="a9a23-p113">Azure AD Connect performs password hash synchronization instead of single sign-on. You do not have to deploy an Active Directory Federation Services (AD FS) infrastructure. To learn more about password hash synchronization and single sign-on options, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](/azure/active-directory/hybrid/choose-ad-authn).</span></span>
    
<span data-ttu-id="a9a23-p114">Há opções adicionais de design que você pode considerar ao implantar essa solução em seu ambiente. Elas incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a9a23-p114">There are additional design choices that you might consider when you deploy this solution in your environment. These include the following:</span></span>
  
- <span data-ttu-id="a9a23-163">Se houver servidores DNS em uma rede virtual existente do Azure, determine se você deseja que seu servidor de sincronização de diretório os use para resolução de nomes em vez dos servidores DNS da rede local.</span><span class="sxs-lookup"><span data-stu-id="a9a23-163">If there are existing DNS servers in an existing Azure virtual network, determine whether you want your directory sync server to use them for name resolution instead of DNS servers on the on-premises network.</span></span>
    
- <span data-ttu-id="a9a23-p115">Se houver controladores de domínio em uma rede virtual do Azure existente, determine se a configuração de Serviços e Sites do Active Directory pode ser uma opção melhor para você. O servidor de sincronização de diretório pode consultar controladores de domínio na rede virtual do Azure para procurar alterações em contas e senhas em vez de controladores de domínio na rede local.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p115">If there are domain controllers in an existing Azure virtual network, determine whether configuring Active Directory Sites and Services may be a better option for you. The directory sync server can query the domain controllers in the Azure virtual network for changes in accounts and passwords instead of domain controllers on the on-premises network.</span></span>
    
## <a name="deployment-roadmap"></a><span data-ttu-id="a9a23-166">Roteiro de implantação</span><span class="sxs-lookup"><span data-stu-id="a9a23-166">Deployment roadmap</span></span>

<span data-ttu-id="a9a23-167">A implantação do Azure AD Connect em uma máquina virtual no Azure tem três etapas:</span><span class="sxs-lookup"><span data-stu-id="a9a23-167">Deploying Azure AD Connect on a virtual machine in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="a9a23-168">Fase 1: Criar e configurar a rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-168">Phase 1: Create and configure the Azure virtual network</span></span>
    
- <span data-ttu-id="a9a23-169">Fase 2: Criar e configurar a máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-169">Phase 2: Create and configure the Azure virtual machine</span></span>
    
- <span data-ttu-id="a9a23-170">Fase 3: Instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="a9a23-170">Phase 3: Install and configure Azure AD Connect</span></span>
    
<span data-ttu-id="a9a23-171">Após a implantação, você também deve atribuir locais e licenças para as novas contas de usuário Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9a23-171">After deployment, you must also assign locations and licenses for the new user accounts in Microsoft 365.</span></span>


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a><span data-ttu-id="a9a23-172">Fase 1: Criar e configurar a rede virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-172">Phase 1: Create and configure the Azure virtual network</span></span>

<span data-ttu-id="a9a23-173">Para criar e configurar a rede virtual do Azure, conclua a [Fase 1: preparar sua rede local](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) e a [Fase 2: criar a rede virtual entre locais no Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) no roteiro de implantação de [Conectar uma rede local a uma rede virtual do Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span><span class="sxs-lookup"><span data-stu-id="a9a23-173">To create and configure the Azure virtual network, complete [Phase 1: Prepare your on-premises network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) and [Phase 2: Create the cross-premises virtual network in Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) in the deployment roadmap of [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).</span></span>
  
<span data-ttu-id="a9a23-174">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="a9a23-174">This is your resulting configuration.</span></span>
  
![Fase 1 do servidor de sincronização de diretórios Microsoft 365 hospedado no Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
<span data-ttu-id="a9a23-176">Esta figura mostra uma rede local conectada a uma rede virtual do Azure por meio de uma conexão VPN ou ExpressRoute de site a site.</span><span class="sxs-lookup"><span data-stu-id="a9a23-176">This figure shows an on-premises network connected to an Azure virtual network through a site-to-site VPN or ExpressRoute connection.</span></span>
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a><span data-ttu-id="a9a23-177">Fase 2: Criar e configurar a máquina virtual do Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-177">Phase 2: Create and configure the Azure virtual machine</span></span>

<span data-ttu-id="a9a23-p116">Criar a máquina virtual no Azure usando as instruções [Criar sua primeira máquina virtual do Windows no portal do Azure](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a9a23-p116">Create the virtual machine in Azure using the instructions [Create your first Windows virtual machine in the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use the following settings:</span></span>
  
- <span data-ttu-id="a9a23-p117">No painel **Básico**, selecione a mesma assinatura, local e grupo de recursos que sua rede virtual. Armazene o nome de usuário e a senha em um local seguro. Você precisará dessas informações posteriormente para se conectar à máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p117">On the **Basics** pane, select the same subscription, location, and resource group as your virtual network. Record the user name and password in a secure location. You will need these later to connect to the virtual machine.</span></span>
    
- <span data-ttu-id="a9a23-183">No painel **Escolher um tamanho**, escolha o tamanho **A2 Padrão**.</span><span class="sxs-lookup"><span data-stu-id="a9a23-183">On the **Choose a size** pane, choose the **A2 Standard** size.</span></span>
    
- <span data-ttu-id="a9a23-p118">No painel **Configurações**, na seção **Armazenamento**, escolha o tipo de armazenamento **Padrão**. Na seção **Rede**, escolha o nome da rede virtual e a sub-rede para hospedar o servidor de sincronização de diretório (não a GatewaySubnet). Deixe todas as outras configurações com seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p118">On the **Settings** pane, in the **Storage** section, select the **Standard** storage type. In the **Network** section, select the name of your virtual network and the subnet for hosting the directory sync server (not the GatewaySubnet). Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="a9a23-187">Para conferir se o servidor de sincronização de diretório está usando o DNS corretamente, verifique o DNS interno para garantir que um registro de endereço (A) foi adicionado à máquina virtual com o respectivo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="a9a23-187">Verify that your directory sync server is using DNS correctly by checking your internal DNS to make sure that an Address (A) record was added for the virtual machine with its IP address.</span></span> 
  
<span data-ttu-id="a9a23-p119">Use as instruções em [Conectar-se à máquina virtual e fazer login](/azure/virtual-machines/windows/connect-logon) para conectar-se ao servidor de sincronização de diretório com uma Conexão de Área de Trabalho Remota. Depois de entrar, ingresse na máquina virtual do domínio local AD DS.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p119">Use the instructions in [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon) to connect to the directory sync server with a Remote Desktop Connection. After signing in, join the virtual machine to the on-premises AD DS domain.</span></span>
  
<span data-ttu-id="a9a23-p120">Para que o Azure AD Connect acesse os recursos da Internet, você deve configurar o servidor de sincronização de diretório para usar o servidor proxy da rede local. Entre em contato com o administrador da rede para etapas de configuração adicionais para executar.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p120">For Azure AD Connect to gain access to Internet resources, you must configure the directory sync server to use the on-premises network's proxy server. You should contact your network administrator for any additional configuration steps to perform.</span></span>
  
<span data-ttu-id="a9a23-192">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="a9a23-192">This is your resulting configuration.</span></span>
  
![Fase 2 do servidor de sincronização de diretórios Microsoft 365 hospedado no Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
<span data-ttu-id="a9a23-194">Esta figura mostra a máquina virtual do servidor de sincronização de diretório na rede virtual entre locais do Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a23-194">This figure shows the directory sync server virtual machine in the cross-premises Azure virtual network.</span></span>
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a><span data-ttu-id="a9a23-195">Fase 3: Instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="a9a23-195">Phase 3: Install and configure Azure AD Connect</span></span>

<span data-ttu-id="a9a23-196">Faça o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="a9a23-196">Complete the following procedure:</span></span>
  
1. <span data-ttu-id="a9a23-p121">Conecte-se ao servidor de sincronização de diretório usando uma Conexão de Área de Trabalho Remota com uma conta de domínio do AD DS que tenha privilégios de administrador local. Confira [Conectar-se à máquina virtual e fazer login](/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="a9a23-p121">Connect to the directory sync server using a Remote Desktop Connection with an AD DS domain account that has local administrator privileges. See [Connect to the virtual machine and sign on](/azure/virtual-machines/windows/connect-logon).</span></span>
    
2. <span data-ttu-id="a9a23-199">No servidor de sincronização de diretórios, abra o artigo [Configurar](set-up-directory-synchronization.md) sincronização de diretório para Microsoft 365 e siga as instruções para sincronização de diretório com a sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="a9a23-199">From the directory sync server, open the [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) article and follow the directions for directory synchronization with password hash synchronization.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="a9a23-p122">A instalação cria a conta **AAD_xxxxxxxxxxxx** na unidade organizacional (UO) Usuários Locais. Não mova nem remova essa conta ou a sincronização falhará.</span><span class="sxs-lookup"><span data-stu-id="a9a23-p122">Setup creates the **AAD_xxxxxxxxxxxx** account in the Local Users organizational unit (OU). Do not move or remove this account or synchronization will fail.</span></span>
  
<span data-ttu-id="a9a23-202">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="a9a23-202">This is your resulting configuration.</span></span>
  
![Fase 3 do servidor de sincronização de diretórios Microsoft 365 hospedado no Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
<span data-ttu-id="a9a23-204">Esta figura mostra o servidor de sincronização de diretório com o Azure AD Connect na rede virtual entre locais do Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a23-204">This figure shows the directory sync server with Azure AD Connect in the cross-premises Azure virtual network.</span></span>
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a><span data-ttu-id="a9a23-205">Atribuir locais e licenças aos usuários no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9a23-205">Assign locations and licenses to users in Microsoft 365</span></span>

<span data-ttu-id="a9a23-206">O Azure AD Conexão adiciona contas à sua assinatura do Microsoft 365 do AD DS local, mas para que os usuários entre no Microsoft 365 e usem seus serviços, as contas devem ser configuradas com um local e licenças.</span><span class="sxs-lookup"><span data-stu-id="a9a23-206">Azure AD Connect adds accounts to your Microsoft 365 subscription from the on-premises AD DS, but in order for users to sign in to Microsoft 365 and use its services, the accounts must be configured with a location and licenses.</span></span> <span data-ttu-id="a9a23-207">Use essas etapas para adicionar o local e as licenças ativas às devidas contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="a9a23-207">Use these steps to add the location and activate licenses for the appropriate user accounts:</span></span>
  
1. <span data-ttu-id="a9a23-208">Entre no centro de administração [Microsoft 365 e](https://admin.microsoft.com)clique em **Admin**.</span><span class="sxs-lookup"><span data-stu-id="a9a23-208">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com), and then click **Admin**.</span></span>
    
2. <span data-ttu-id="a9a23-209">Na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="a9a23-209">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="a9a23-210">Na lista das contas de usuário, marque a caixa de seleção ao lado do usuário que você deseja ativar.</span><span class="sxs-lookup"><span data-stu-id="a9a23-210">In the list of user accounts, select the check box next to the user you want to activate.</span></span>
    
4. <span data-ttu-id="a9a23-211">Na página do usuário, clique em **Editar** para **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="a9a23-211">On the page for the user, click **Edit** for **Product licenses**.</span></span>
    
5. <span data-ttu-id="a9a23-212">Na página **Licenças de produto**, selecione um local para o usuário em **Local** e habilite as licenças apropriadas para ele.</span><span class="sxs-lookup"><span data-stu-id="a9a23-212">On the **Product licenses** page, select a location for the user for **Location**, and then enable the appropriate licenses for the user.</span></span>
    
6. <span data-ttu-id="a9a23-213">Ao concluir, clique em **Salvar** e, em seguida, clique em **Fechar** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="a9a23-213">When complete, click **Save**, and then click **Close** twice.</span></span>
    
7. <span data-ttu-id="a9a23-214">Volte à etapa 3 para usuários adicionais.</span><span class="sxs-lookup"><span data-stu-id="a9a23-214">Go back to step 3 for additional users.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a9a23-215">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9a23-215">See also</span></span>

[<span data-ttu-id="a9a23-216">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9a23-216">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)
  
[<span data-ttu-id="a9a23-217">Conectar uma rede local a uma rede virtual do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a9a23-217">Connect an on-premises network to a Microsoft Azure virtual network</span></span>](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[<span data-ttu-id="a9a23-218">Baixar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="a9a23-218">Download Azure AD Connect</span></span>](https://www.microsoft.com/download/details.aspx?id=47594)
  
[<span data-ttu-id="a9a23-219">Configurar a sincronização de diretórios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9a23-219">Set up directory synchronization for Microsoft 365</span></span>](set-up-directory-synchronization.md)
