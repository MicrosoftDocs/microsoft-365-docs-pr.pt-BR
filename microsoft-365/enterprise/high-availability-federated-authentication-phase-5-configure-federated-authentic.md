---
title: Autenticação federada de alta disponibilidade Fase 5 Configurar autenticação federada para Microsoft 365
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
description: 'Resumo: Configure o Azure AD Conexão sua autenticação federada de alta disponibilidade para Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929403"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="3fcf4-103">Autenticação federada de alta disponibilidade Fase 5: Configurar autenticação federada para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fcf4-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="3fcf4-104">Nesta fase final da implantação da autenticação federada de alta disponibilidade para o Microsoft 365 nos serviços de infraestrutura do Azure, você obterá e instalará um certificado emitido por uma autoridade de certificação pública, verifique sua configuração e instale e execute o Azure AD Conexão no servidor de sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="3fcf4-105">O Azure AD Conexão configura sua assinatura Microsoft 365 e seus Serviços de Federação do Active Directory (AD FS) e servidores proxy de aplicativo Web para autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="3fcf4-106">Consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="3fcf4-107">Obter um certificado público e copiá-lo para o servidor de sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="3fcf4-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="3fcf4-108">Obter um certificado digital de uma autoridade de certificação pública com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="3fcf4-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="3fcf4-109">Um certificado X.509 adequado para criar conexões SSL.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="3fcf4-110">A propriedade estendida Nome Alternativo do Assunto (SAN) é definida como FQDN do serviço de federação (exemplo: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3fcf4-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="3fcf4-111">O certificado deve ter a chave privada e ser armazenado no formato PFX.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="3fcf4-112">Além disso, os computadores e dispositivos da sua organização devem confiar na autoridade de certificação pública que está em emissão do certificado digital.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-112">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate.</span></span> <span data-ttu-id="3fcf4-113">Essa confiança é estabelecida por ter um certificado raiz da autoridade de certificação pública instalada no armazenamento de autoridades de certificação raiz confiáveis em seus computadores e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-113">This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices.</span></span> <span data-ttu-id="3fcf4-114">Os computadores que executam o Microsoft Windows geralmente têm um conjunto desses tipos de certificados instalados de autoridades de certificação comumente usadas.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-114">Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities.</span></span> <span data-ttu-id="3fcf4-115">Se o certificado raiz da sua autoridade de certificação pública ainda não estiver instalado, você deverá implantá-lo nos computadores e dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-115">If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="3fcf4-116">Para obter mais informações sobre os requisitos de certificado para autenticação federada, consulte [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span><span class="sxs-lookup"><span data-stu-id="3fcf4-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="3fcf4-117">Quando você receber o certificado, copie-o para uma pasta na unidade C: do servidor de sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="3fcf4-118">Por exemplo, nomee o arquivo SSL.pfx e armazene-o na pasta C: \\ Certs no servidor de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="3fcf4-119">Verificar sua configuração</span><span class="sxs-lookup"><span data-stu-id="3fcf4-119">Verify your configuration</span></span>

<span data-ttu-id="3fcf4-120">Agora você deve estar pronto para configurar o Azure AD Conexão autenticação federada para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="3fcf4-121">Para garantir que você está, aqui está uma lista de verificação:</span><span class="sxs-lookup"><span data-stu-id="3fcf4-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="3fcf4-122">O domínio público da sua organização é adicionado à sua assinatura Microsoft 365 usuário.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="3fcf4-123">As contas de usuário Microsoft 365 da sua organização são configuradas com o nome de domínio público da sua organização e podem entrar com êxito.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="3fcf4-124">Você determinou um FQDN de serviço de federação com base em seu nome de domínio público.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="3fcf4-125">Um registro DNS A público para o FQDN do serviço de federação aponta para o endereço IP público do balanceador de carga do Azure voltado para a Internet para os servidores proxy do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="3fcf4-126">Um registro DNS A privado para o FQDN do serviço de federação aponta para o endereço IP privado do balanceador de carga interno do Azure para os servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="3fcf4-127">Um certificado digital emitido pela autoridade de certificação pública adequado para conexões SSL com a SAN definida como FQDN do serviço de federação é um arquivo PFX armazenado no servidor de sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="3fcf4-128">O certificado raiz da autoridade de certificação pública está instalado no armazenamento autoridades de certificação raiz confiáveis em seus computadores e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="3fcf4-129">Veja um exemplo para a organização Contoso:</span><span class="sxs-lookup"><span data-stu-id="3fcf4-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="3fcf4-130">**Um exemplo de configuração para uma infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="3fcf4-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Um exemplo de configuração da infraestrutura de autenticação federada Microsoft 365 alta disponibilidade no Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="3fcf4-132">Executar o Azure AD Conexão configurar a autenticação federada</span><span class="sxs-lookup"><span data-stu-id="3fcf4-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="3fcf4-133">A ferramenta de Conexão do Azure AD configura os servidores do AD FS, os servidores proxy de aplicativo Web e Microsoft 365 para autenticação federada com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3fcf4-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="3fcf4-134">Crie uma conexão de área de trabalho remota com seu servidor de sincronização de diretório com uma conta de domínio que tenha privilégios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="3fcf4-135">Na área de trabalho do servidor de sincronização de diretórios, abra o Internet Explorer e vá para [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="3fcf4-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="3fcf4-136">Na página **Microsoft Azure Active Directory Conexão,** clique em **Baixar** e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="3fcf4-137">Na página **Bem-vindo ao Azure AD** Conexão, clique em **Eu concordo** e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="3fcf4-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="3fcf4-138">Na página **Configurações Expressas**, clique em **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="3fcf4-139">Na página **Instalar componentes necessários**, clique em **Instalar**. </span><span class="sxs-lookup"><span data-stu-id="3fcf4-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="3fcf4-140">Na página **Entrada do usuário**, clique em **Federação com AD FS** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3fcf4-141">Na página Conexão para o **Azure AD,** digite o nome e a senha de uma conta de administrador global para sua assinatura Microsoft 365 e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="3fcf4-142">Na página Conexão diretórios, certifique-se de que sua floresta local dos Serviços de Domínio do Active Directory (AD DS) está selecionada em **Floresta,** digite o nome e **a** senha de uma conta de administrador de domínio, clique em **Adicionar** Diretório e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="3fcf4-143">Na página configuração de entrada do **Azure AD,** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="3fcf4-144">Na página **Filtragem de Domínio e UO,** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="3fcf4-145">Na página **Identificar seus** usuários com exclusividade, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="3fcf4-146">Na página **Filtrar usuários e dispositivos,** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="3fcf4-147">Na página **Recursos opcionais,** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="3fcf4-148">Na página **do farm do AD FS,** clique em **Configurar um novo farm do AD FS.**</span><span class="sxs-lookup"><span data-stu-id="3fcf4-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="3fcf4-149">Clique **em Procurar** e especifique o local e o nome do certificado SSL da autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="3fcf4-150">Quando solicitado, digite a senha do certificado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="3fcf4-151">Verifique se o **Nome do Assunto e** o Nome do Serviço de **Federação** estão definidos como FQDN do serviço de federação e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="3fcf4-152">Na página servidores **do AD FS,** digite o nome do seu primeiro servidor do AD FS (Tabela M - Item 4 - coluna nome da máquina virtual) e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="3fcf4-153">Digite o segundo nome do servidor do AD FS (Tabela M - Item 5 - coluna nome da máquina virtual), clique em **Adicionar** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="3fcf4-154">Na página **Servidores Proxy** de Aplicativo Web, digite o nome do seu primeiro servidor proxy de aplicativo Web (Tabela M - Item 6 - coluna nome da máquina virtual) e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="3fcf4-155">Digite o nome do seu segundo servidor proxy de aplicativo Web (Tabela M - Item 7 - coluna nome da máquina virtual), clique em **Adicionar** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="3fcf4-156">Na página **Credenciais de Administrador** de Domínio, digite o nome de usuário e a senha de uma conta de administrador de domínio e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="3fcf4-157">Na página **conta de serviço do AD FS,** digite o nome de usuário e a senha de uma conta de administrador da empresa e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="3fcf4-158">Na página **Domínio do Azure AD,** em **Domínio,** selecione o nome de domínio DNS da sua organização e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="3fcf4-159">Na página **Pronto para configurar**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="3fcf4-160">Na página **Instalação Completa**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-160">On the **Installation complete** page, click **Verify**.</span></span> <span data-ttu-id="3fcf4-161">Você deve ver duas mensagens indicando que a intranet e a configuração da Internet foram verificadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-161">You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="3fcf4-162">A mensagem intranet deve listar o endereço IP privado do balanceador de carga interno do Azure para seus servidores do AD FS.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="3fcf4-163">A mensagem da Internet deve listar o endereço IP público do balanceador de carga voltado para a Internet do Azure para seus servidores proxy de aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="3fcf4-164">Na página **Instalação Completa**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="3fcf4-165">Aqui está a configuração final, com nomes de espaço reservado para os servidores.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="3fcf4-166">**Fase 5: a configuração final de uma infraestrutura de autenticação federada de alta disponibilidade no Azure**</span><span class="sxs-lookup"><span data-stu-id="3fcf4-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![A configuração final da infraestrutura de autenticação Microsoft 365 de autenticação federada no Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="3fcf4-168">Sua infraestrutura de autenticação federada de alta disponibilidade para Microsoft 365 no Azure está concluída.</span><span class="sxs-lookup"><span data-stu-id="3fcf4-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3fcf4-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="3fcf4-169">See Also</span></span>

[<span data-ttu-id="3fcf4-170">Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure</span><span class="sxs-lookup"><span data-stu-id="3fcf4-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="3fcf4-171">Identidade federada para seu ambiente Microsoft 365 dev/test</span><span class="sxs-lookup"><span data-stu-id="3fcf4-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="3fcf4-172">Centro de soluções e arquitetura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fcf4-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="3fcf4-173">Identidade federada para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3fcf4-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)