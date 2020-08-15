---
title: Autenticação federada de alta disponibilidade fase 5 configurar a autenticação federada para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Resumo: Configure o Azure AD Connect para sua autenticação federada de alta disponibilidade para o Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: f00763487261b62940ac5def38d35158db77a699
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687302"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="4a496-103">Autenticação federada de alta disponibilidade fase 5: configurar a autenticação federada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4a496-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="4a496-104">Nesta fase final da implantação da autenticação federada de alta disponibilidade para o Microsoft 365 nos serviços de infraestrutura do Azure, você obtém e instala um certificado emitido por uma autoridade de certificação pública, verifica sua configuração e instala e executa o Azure AD Connect no servidor de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="4a496-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="4a496-105">O Azure AD Connect configura sua assinatura do Microsoft 365 e seus serviços de Federação do Active Directory (AD FS) e servidores de proxy de aplicativo Web para autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="4a496-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="4a496-106">Consulte [implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas as fases.</span><span class="sxs-lookup"><span data-stu-id="4a496-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="4a496-107">Obter um certificado público e copiá-lo para o servidor de sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="4a496-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="4a496-108">Obtenha um certificado digital de uma autoridade de certificação pública com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="4a496-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="4a496-109">Um certificado X. 509 adequado para a criação de conexões SSL.</span><span class="sxs-lookup"><span data-stu-id="4a496-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="4a496-110">A propriedade estendida do nome alternativo da entidade (SAN) é definida como o FQDN do serviço de Federação (exemplo: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4a496-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="4a496-111">O certificado deve ter a chave privada e ser armazenado no formato PFX.</span><span class="sxs-lookup"><span data-stu-id="4a496-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="4a496-112">Além disso, seus computadores e dispositivos da organização devem confiar na autoridade de certificação pública que está emitindo o certificado digital.</span><span class="sxs-lookup"><span data-stu-id="4a496-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="4a496-113">Essa relação de confiança é estabelecida com um certificado raiz da autoridade de certificação pública instalada no repositório de autoridades de certificação raiz confiáveis em seus computadores e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4a496-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="4a496-114">Os computadores que executam o Microsoft Windows normalmente têm um conjunto desses tipos de certificados instalados a partir de autoridades de certificação comumente usadas.</span><span class="sxs-lookup"><span data-stu-id="4a496-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="4a496-115">Se o certificado raiz da autoridade de certificação pública ainda não estiver instalado, você deve implantá-lo nos computadores e dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4a496-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="4a496-116">Para obter mais informações sobre os requisitos de certificado para autenticação federada, consulte [pré-requisitos para instalação e configuração de Federação](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span><span class="sxs-lookup"><span data-stu-id="4a496-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="4a496-117">Ao receber o certificado, copie-o para uma pasta na unidade C: do servidor de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="4a496-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="4a496-118">Por exemplo, nomeie o arquivo SSL. pfx e armazene-o na pasta C: \\ certs no servidor de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="4a496-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="4a496-119">Verificar a configuração</span><span class="sxs-lookup"><span data-stu-id="4a496-119">Verify your configuration</span></span>

<span data-ttu-id="4a496-120">Agora você deve estar pronto para configurar o Azure AD Connect e a autenticação federada para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a496-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="4a496-121">Para garantir que você está, aqui está uma lista de verificação:</span><span class="sxs-lookup"><span data-stu-id="4a496-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="4a496-122">O domínio público da sua organização é adicionado à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a496-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="4a496-123">As contas de usuário do Microsoft 365 da sua organização são configuradas para o nome de domínio público da sua organização e podem entrar com êxito.</span><span class="sxs-lookup"><span data-stu-id="4a496-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="4a496-124">Você determinou um FQDN de serviço de Federação com base em seu nome de domínio público.</span><span class="sxs-lookup"><span data-stu-id="4a496-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="4a496-125">Um registro de DNS público para o FQDN do serviço de Federação aponta para o endereço IP público do balanceador de carga do Azure voltado para a Internet para os servidores proxy de aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="4a496-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="4a496-126">Um registro de DNS privado para o FQDN do serviço de Federação aponta para o endereço IP privado do balanceador de carga interno do Azure para os servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="4a496-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="4a496-127">Uma autoridade de certificação pública-isssued certificado digital adequado para conexões SSL com o conjunto SAN como o FQDN do serviço de Federação é um arquivo PFX armazenado no servidor de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="4a496-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="4a496-128">O certificado raiz da autoridade de certificação pública é instalado no repositório de autoridades de certificação raiz confiáveis em seus computadores e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4a496-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="4a496-129">Veja um exemplo da organização Contoso:</span><span class="sxs-lookup"><span data-stu-id="4a496-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="4a496-130">**Uma configuração de exemplo para uma infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="4a496-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Um exemplo de configuração da infraestrutura de autenticação federada de alta disponibilidade da Microsoft 365 no Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="4a496-132">Executar o Azure AD Connect para configurar a autenticação federada</span><span class="sxs-lookup"><span data-stu-id="4a496-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="4a496-133">A ferramenta Azure AD Connect configura os servidores do AD FS, os servidores de proxy de aplicativo Web e o Microsoft 365 para autenticação federada com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4a496-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="4a496-134">Crie uma conexão de área de trabalho remota para seu servidor de sincronização de diretório com uma conta de domínio que tenha privilégios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="4a496-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="4a496-135">Na área de trabalho do servidor de sincronização de diretório, abra o Internet Explorer e vá para [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="4a496-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="4a496-136">Na página do **Microsoft Azure Active Directory Connect** , clique em **baixar**e em **executar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="4a496-137">Na página **Bem-vindo ao Azure ad Connect** , clique em **concordo**e, em seguida, clique em **continuar.**</span><span class="sxs-lookup"><span data-stu-id="4a496-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="4a496-138">Na página **Configurações Expressas**, clique em **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="4a496-139">Na página **Instalar componentes necessários**, clique em **Instalar**. </span><span class="sxs-lookup"><span data-stu-id="4a496-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="4a496-140">Na página **Entrada do usuário**, clique em **Federação com AD FS** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4a496-141">Na página **conectar ao Azure ad** , digite o nome e a senha de uma conta de administrador global para sua assinatura do Microsoft 365 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="4a496-142">Na página **conectar seus diretórios** , verifique se a floresta de serviços de domínio do Active Directory (AD DS) local está selecionada em **floresta**, digite o nome e a senha de uma conta de administrador de domínio, clique em **Adicionar diretório**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="4a496-143">Na página **configuração de entrada do Azure ad** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="4a496-144">Na página **filtragem de ou domínio** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="4a496-145">Na página **identificando exclusivamente os usuários** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="4a496-146">Na página **Filtrar usuários e dispositivos** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="4a496-147">Na página **recursos opcionais** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="4a496-148">Na página **farm do AD FS** , clique em **configurar um novo farm do AD FS**.</span><span class="sxs-lookup"><span data-stu-id="4a496-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="4a496-149">Clique em **procurar** e especifique o local e o nome do certificado SSL da autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="4a496-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="4a496-150">Quando solicitado, digite a senha do certificado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a496-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="4a496-151">Verifique se o **nome do requerente** e o **nome do serviço de Federação** estão definidos para o FQDN do serviço de Federação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="4a496-152">Na página **servidores do AD FS** , digite o nome do seu primeiro servidor AD FS (tabela M-item 4-coluna nome da máquina virtual) e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="4a496-153">Digite o segundo nome do servidor AD FS (tabela M-item 5-coluna nome da máquina virtual), clique em **Adicionar**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="4a496-154">Na página **servidores de proxy de aplicativo Web** , digite o nome do seu primeiro servidor proxy de aplicativo Web (tabela M-item 6-coluna nome da máquina virtual) e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="4a496-155">Digite seu segundo nome de servidor proxy de aplicativo Web (tabela M-item 7-coluna nome da máquina virtual), clique em **Adicionar**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="4a496-156">Na página **credenciais de administrador de domínio** , digite o nome de usuário e a senha de uma conta de administrador de domínio e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="4a496-157">Na página **conta de serviço do AD FS** , digite o nome de usuário e a senha de uma conta de administrador corporativo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="4a496-158">Na página **domínio do Azure ad** , em **domínio**, selecione o nome de domínio DNS da sua organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="4a496-159">Na página **Pronto para configurar**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="4a496-160">Na página **Instalação Completa**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="4a496-161">Você deve ver duas mensagens indicando que a configuração da intranet e da Internet foi verificada com êxito.</span><span class="sxs-lookup"><span data-stu-id="4a496-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="4a496-162">A mensagem intranet deve listar o endereço IP privado do seu balanceador de carga interno do Azure para seus servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="4a496-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="4a496-163">A mensagem da Internet deve listar o endereço IP público do balanceador de carga voltado para a Internet do Azure para seus servidores de proxy de aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="4a496-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="4a496-164">Na página **Instalação Completa**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4a496-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="4a496-165">Aqui está a configuração final, com nomes de espaços reservados para os servidores.</span><span class="sxs-lookup"><span data-stu-id="4a496-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="4a496-166">**Fase 5: a configuração final de uma infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="4a496-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![A configuração final da infraestrutura de autenticação federada de alta disponibilidade da Microsoft 365 no Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="4a496-168">Sua infraestrutura de autenticação federada de alta disponibilidade para o Microsoft 365 no Azure foi concluída.</span><span class="sxs-lookup"><span data-stu-id="4a496-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a496-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="4a496-169">See Also</span></span>

[<span data-ttu-id="4a496-170">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="4a496-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="4a496-171">Identidade federada para seu ambiente de desenvolvimento/teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4a496-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="4a496-172">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4a496-172">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="4a496-173">Identidade federada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4a496-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)


