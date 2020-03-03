---
title: Plano para a autenticação multifator para Implantações do Office 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre a autenticação multifator no Office 365 e as etapas que você precisa seguir para configurá-lo.
ms.openlocfilehash: 2e2cbc9d6d966a9858fafb62f08d26893c9f4353
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361172"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a><span data-ttu-id="64664-103">Plano para a autenticação multifator para Implantações do Office 365</span><span class="sxs-lookup"><span data-stu-id="64664-103">Plan for multi-factor authentication for Office 365 Deployments</span></span>

<span data-ttu-id="64664-p101">A MFA (autenticação multifator) é um método de autenticação que requer o uso de mais de um método de verificação e adiciona uma segunda camada de segurança a transações e conexões de usuário. Ela funciona solicitando dois ou mais dos seguintes métodos de verificação:</span><span class="sxs-lookup"><span data-stu-id="64664-p101">Multi-factor authentication (MFA) is a method of authentication that requires the use of more than one verification method and adds a second layer of security to user sign-ins and transactions. It works by requiring any two or more of the following verification methods:</span></span>
  
- <span data-ttu-id="64664-106">Uma senha gerada aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="64664-106">A randomly generated pass code</span></span>
    
- <span data-ttu-id="64664-107">Uma chamada telefônica</span><span class="sxs-lookup"><span data-stu-id="64664-107">A phone call</span></span>
    
- <span data-ttu-id="64664-108">Um cartão inteligente (físico ou virtual)</span><span class="sxs-lookup"><span data-stu-id="64664-108">A smart card (virtual or physical)</span></span> 
    
- <span data-ttu-id="64664-109">Um dispositivo biométrico</span><span class="sxs-lookup"><span data-stu-id="64664-109">A biometric device</span></span> 
    
## <a name="multi-factor-authentication-in-office-365"></a><span data-ttu-id="64664-110">Autenticação multifator no Office 365</span><span class="sxs-lookup"><span data-stu-id="64664-110">Multi-factor authentication in Office 365</span></span>

<span data-ttu-id="64664-111">O Office 365 usa a autenticação multifator para ajudar a fornecer segurança extra e é gerenciado no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64664-111">Office 365 uses multi-factor authentication to help provide the extra security and is managed from the Microsoft 365 admin center.</span></span> <span data-ttu-id="64664-112">O Office 365 oferece o seguinte subconjunto de recursos da autenticação multifator do Azure como parte da assinatura:</span><span class="sxs-lookup"><span data-stu-id="64664-112">Office 365 offers the following subset of Azure multi-factor authentication capabilities as a part of the subscription:</span></span> 
  
- <span data-ttu-id="64664-113">A capacidade de habilitar e aplicar a autenticação multifator para usuários finais</span><span class="sxs-lookup"><span data-stu-id="64664-113">The ability to enable and enforce multi-factor authentication for end users</span></span>
    
- <span data-ttu-id="64664-114">O uso de um aplicativo móvel (on-line e OTP [senha avulsa]) como segundo fator de autenticação</span><span class="sxs-lookup"><span data-stu-id="64664-114">The use of a mobile app (online and one-time password [OTP]) as a second authentication factor</span></span>
    
- <span data-ttu-id="64664-115">O uso de uma chamada telefônica como segundo fator de autenticação</span><span class="sxs-lookup"><span data-stu-id="64664-115">The use of a phone call as a second authentication factor</span></span>
    
- <span data-ttu-id="64664-116">O uso de uma mensagem SMS como segundo fator de autenticação</span><span class="sxs-lookup"><span data-stu-id="64664-116">The use of a Short Message Service (SMS) message as a second authentication factor</span></span>
    
- <span data-ttu-id="64664-117">Senhas de aplicativo para clientes que não estão no navegador (por exemplo, o software de comunicação Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="64664-117">Application passwords for non browser clients (for example, the Microsoft Lync 2013 communications software)</span></span>
    
- <span data-ttu-id="64664-118">Saudações padrão da Microsoft durante as chamadas de autenticação</span><span class="sxs-lookup"><span data-stu-id="64664-118">Default Microsoft greetings during authentication phone calls</span></span>
    
<span data-ttu-id="64664-p103">Para a lista completa de recursos adicionais, confira [a comparação das versões da autenticação multifator do Azure](https://go.microsoft.com/fwlink/?LinkId=506927). Você sempre pode obter a funcionalidade completa comprando o serviço Autenticação Multifator do Azure.</span><span class="sxs-lookup"><span data-stu-id="64664-p103">For the full list of added features, see [the comparison of Azure Multi-Factor Authentication version](https://go.microsoft.com/fwlink/?LinkId=506927). You can always get the full functionality by purchasing the Azure Multi-Factor Authentication service.</span></span> 
  
<span data-ttu-id="64664-121">Você recebe um subconjunto de recursos, dependendo se tem uma implantação somente na nuvem para o Office 365 ou um híbrido configurado com logon único e Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="64664-121">You get a different subset of capabilities depending on whether you have a cloud-only deployment for Office 365 or a hybrid set up with single sign-on and Active Directory Federation Services (AD FS).</span></span> 
  
|<span data-ttu-id="64664-122">**Onde você gerencia seu locatário do Office 365?**</span><span class="sxs-lookup"><span data-stu-id="64664-122">**Where do you manage your Office 365 tenant?**</span></span>|<span data-ttu-id="64664-123">**Opções do segundo fator da MFA**</span><span class="sxs-lookup"><span data-stu-id="64664-123">**MFA second factor options**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64664-124">Somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="64664-124">Cloud only</span></span>  <br/> |<span data-ttu-id="64664-125">MFA do Azure Active Directory (mensagem ou chamada telefônica)</span><span class="sxs-lookup"><span data-stu-id="64664-125">Azure Active Directory MFA (text or phone call)</span></span>  <br/> |
|<span data-ttu-id="64664-126">Configuração híbrida, gerenciada no local</span><span class="sxs-lookup"><span data-stu-id="64664-126">Hybrid setup, managed on-premises</span></span>  <br/> | <span data-ttu-id="64664-127">Se você gerencia identidades de usuário no local, tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="64664-127">If you manage user identity on-premises, you have the following choices:</span></span>  <br/>  <span data-ttu-id="64664-128">Cartão inteligente físico ou virtual (AD FS)</span><span class="sxs-lookup"><span data-stu-id="64664-128">Physical or virtual smart card (AD FS)</span></span>  <br/> <span data-ttu-id="64664-129">[MFA do Azure](https://go.microsoft.com/fwlink/p/?LinkId=526677) (módulo para o AD FS)</span><span class="sxs-lookup"><span data-stu-id="64664-129">[Azure MFA](https://go.microsoft.com/fwlink/p/?LinkId=526677) (module for AD FS)</span></span>  <br/>  <span data-ttu-id="64664-130">MFA do Azure AD</span><span class="sxs-lookup"><span data-stu-id="64664-130">Azure AD MFA</span></span>  <br/> |
   
  
<span data-ttu-id="64664-p104">A figura a seguir mostra como os aplicativos de dispositivo do Office 2013 (no Windows) permitem aos usuários entrar com MFA. Os aplicativos de dispositivo do Office 2013 dão suporte à autenticação multifator com o uso da [ADAL (biblioteca de autenticação do Active Directory)](https://go.microsoft.com/fwlink/p/?LinkId=526684). O Azure AD hospeda uma página da Web onde os usuários podem entrar. O provedor de identidade pode ser o Azure AD ou um provedor de identidade federada, como o AD FS. A autenticação para usuários federados envolve as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="64664-p104">The following figure shows how the updated Office 2013 device apps (on Windows) enable users to sign in with MFA. TheOffice 2013 device apps support multi-factor authentication through the use of the [Active Directory Authentication Library (ADAL)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hosts a webpage where users can sign in. The identity provider can be Azure AD or a federated identity provider like AD FS. The authentication for federated users follows these steps:</span></span>
  
1. <span data-ttu-id="64664-p105">O Azure AD redireciona o usuário para a página da Web de entrada hospedada pelo provedor de identidade do registro para o locatário do Office 365. O provedor de identidade é determinado pelo domínio especificado no nome de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="64664-p105">Azure AD redirects the user to the sign-in web page hosted by the identity provider of record for the Office 365 tenant. The identity provider is determined by the domain specified in the user's sign in name.</span></span>
    
2. <span data-ttu-id="64664-138">O usuário entra na página de entrada da Web em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64664-138">The user signs in on the sign in web page on his or her device.</span></span> 
    
3. <span data-ttu-id="64664-139">O provedor de identidade retorna um token para o Azure AD quando o usuário é conectado com êxito.</span><span class="sxs-lookup"><span data-stu-id="64664-139">The identity provider returns a token to Azure AD when the user is successfully signed in.</span></span>
    
4. <span data-ttu-id="64664-140">O Azure AD retorna um JWT (token Web JSON) para o aplicativo de dispositivo do Office e o aplicativo de dispositivo é autenticado usando um JWT com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="64664-140">Azure AD returns a JSON Web Token (JWT) to the Office device app, and the device app is authenticated by using a JWT with Office 365.</span></span> 
    
<span data-ttu-id="64664-141">Isso é detalhado na figura abaixo:</span><span class="sxs-lookup"><span data-stu-id="64664-141">This is detailed in the following figure:</span></span>
  
![Modern authentication for Office 2013 device apps.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)
  
## <a name="software-requirements"></a><span data-ttu-id="64664-143">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="64664-143">Software requirements</span></span>

<span data-ttu-id="64664-144">Para habilitar a MFA para aplicativos clientes do Office 2013, você deve ter o software a seguir instalado (a versão listada abaixo ou uma versão posterior) dependendo se tem uma [Instalações baseadas em clique para executar](#click-to-run-based-installations) ou uma [Instalações baseada em MSI](#msi-based-installations).</span><span class="sxs-lookup"><span data-stu-id="64664-144">To enable MFA for Office 2013 client apps, you must have the following software installed (the version listed below, or a later version) based on whether you have a [Click-to-run based installations](#click-to-run-based-installations) or an [MSI-based installations](#msi-based-installations).</span></span>
  
<span data-ttu-id="64664-145">Para determinar se a instalação do Office é baseada em MSI ou clique para executar:</span><span class="sxs-lookup"><span data-stu-id="64664-145">To determine whether your Office installation is Click-to-run or MSI-base:</span></span>
  
1. <span data-ttu-id="64664-146">Inicie o Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="64664-146">Start Outlook 2013.</span></span>
    
2. <span data-ttu-id="64664-147">No menu **arquivo** , escolha **conta do Office**.</span><span class="sxs-lookup"><span data-stu-id="64664-147">On the **File** menu, choose **Office Account**.</span></span>
    
3. <span data-ttu-id="64664-p106">Para Outlook 2013 instalações de clique para executar, é exibido um item **Opções de Atualização**. Para instalações baseada em MSI, o item **Opções de Atualização** não é exibido.</span><span class="sxs-lookup"><span data-stu-id="64664-p106">For Outlook 2013 Click-to-Run installations, an **Update Options** item is displayed. For MSI-based installations, the **Update Options** item is not displayed.</span></span> 
    
    ![Graphic that shows how to tell if Office 2013 install is click-to-run or MSI-based](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)
  
### <a name="click-to-run-based-installations"></a><span data-ttu-id="64664-151">Instalações baseadas em clique para executar</span><span class="sxs-lookup"><span data-stu-id="64664-151">Click-to-run based installations</span></span>

<span data-ttu-id="64664-p107">Para instalações baseadas em clique para executar, você deve ter o software a seguir instalado com a versão do arquivo listado abaixo ou uma versão posterior do arquivo. Se sua versão do arquivo não é igual ou superior à versão do arquivo listada, atualize-a usando as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="64664-p107">For Click-to-run based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the steps below.</span></span>
  
|<span data-ttu-id="64664-154">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="64664-154">**File name**</span></span>|<span data-ttu-id="64664-155">**Caminho de instalação no seu computador**</span><span class="sxs-lookup"><span data-stu-id="64664-155">**Install path on your computer**</span></span>|<span data-ttu-id="64664-156">**Versão do arquivo**</span><span class="sxs-lookup"><span data-stu-id="64664-156">**File version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64664-157">Ficheiro. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-157">MSO.DLL</span></span>  <br/> |<span data-ttu-id="64664-158">C:\Arquivos de Programas\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="64664-158">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |<span data-ttu-id="64664-159">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="64664-159">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="64664-160">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-160">CSI.DLL</span></span>  <br/> |<span data-ttu-id="64664-161">CSI.DLL C:\Arquivos de Programas\Microsoft Office 15\root\office15\csi.dll</span><span class="sxs-lookup"><span data-stu-id="64664-161">CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll</span></span>  <br/> |<span data-ttu-id="64664-162">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="64664-162">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="64664-163">Groove. EXE</span><span class="sxs-lookup"><span data-stu-id="64664-163">Groove.EXE</span></span>  <br/> |<span data-ttu-id="64664-164">C:\Arquivos de Programas\Microsoft Office 15\root\office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="64664-164">C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe</span></span>  <br/> |<span data-ttu-id="64664-165">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="64664-165">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="64664-166">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="64664-166">Outlook.exe</span></span>  <br/> |<span data-ttu-id="64664-167">C:\Arquivos de Programas\Microsoft Office 15\root\office15\OUTLOOK.exe</span><span class="sxs-lookup"><span data-stu-id="64664-167">C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe</span></span>  <br/> |<span data-ttu-id="64664-168">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="64664-168">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="64664-169">Adal. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-169">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="64664-170">C:\Arquivos de Programas\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="64664-170">C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |<span data-ttu-id="64664-171">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="64664-171">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="64664-172">Iexplore. exe</span><span class="sxs-lookup"><span data-stu-id="64664-172">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="64664-173">C:\Arquivos de Programas\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="64664-173">C:\Program Files\Internet Explorer</span></span>  <br/> |<span data-ttu-id="64664-174">varia</span><span class="sxs-lookup"><span data-stu-id="64664-174">varies</span></span>  <br/> |
   
### <a name="msi-based-installations"></a><span data-ttu-id="64664-175">Instalações baseada em MSI</span><span class="sxs-lookup"><span data-stu-id="64664-175">MSI-based installations</span></span>

<span data-ttu-id="64664-p108">Para instalações baseadas em MSI, você deve ter o software a seguir instalado com a versão do arquivo listado abaixo ou uma versão posterior do arquivo. Se sua versão do arquivo não é igual ou superior à versão do arquivo listada, atualize-a usando o link na coluna Atualizar artigo da base de dados.</span><span class="sxs-lookup"><span data-stu-id="64664-p108">For MSI-based installations, you must have the following software installed, at file version listed below or a later file version. If your file version is not equal to or greater than the file version listed, update it using the link in the Update KB Article column.</span></span>
  
|<span data-ttu-id="64664-178">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="64664-178">**File name**</span></span>|<span data-ttu-id="64664-179">**Caminho de instalação no seu computador**</span><span class="sxs-lookup"><span data-stu-id="64664-179">**Install path on your computer**</span></span>|<span data-ttu-id="64664-180">**Onde obter a atualização**</span><span class="sxs-lookup"><span data-stu-id="64664-180">**Where to get the update**</span></span>|<span data-ttu-id="64664-181">**Versão**</span><span class="sxs-lookup"><span data-stu-id="64664-181">**Version**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64664-182">Ficheiro. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-182">MSO.DLL</span></span>  <br/> |<span data-ttu-id="64664-183">C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span><span class="sxs-lookup"><span data-stu-id="64664-183">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL</span></span>  <br/> |[<span data-ttu-id="64664-184">KB3085480</span><span class="sxs-lookup"><span data-stu-id="64664-184">KB3085480</span></span>](https://support.microsoft.com/kb/3085480) <br/> |<span data-ttu-id="64664-185">15.0.4753.1001</span><span class="sxs-lookup"><span data-stu-id="64664-185">15.0.4753.1001</span></span>  <br/> |
|<span data-ttu-id="64664-186">CSI. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-186">CSI.DLL</span></span>  <br/> |<span data-ttu-id="64664-187">C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span><span class="sxs-lookup"><span data-stu-id="64664-187">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll</span></span>  <br/> |[<span data-ttu-id="64664-188">KB3085504</span><span class="sxs-lookup"><span data-stu-id="64664-188">KB3085504</span></span>](https://support.microsoft.com/kb/3085504) <br/> |<span data-ttu-id="64664-189">15.0.4753.1000</span><span class="sxs-lookup"><span data-stu-id="64664-189">15.0.4753.1000</span></span>  <br/> |
|<span data-ttu-id="64664-190">Groove. exe</span><span class="sxs-lookup"><span data-stu-id="64664-190">Groove.exe</span></span>  <br/> |<span data-ttu-id="64664-191">C:\Arquivos de Programas\Microsoft Office\Office15\GROOVE.exe</span><span class="sxs-lookup"><span data-stu-id="64664-191">C:\Program Files\Microsoft Office\Office15\GROOVE.EXE</span></span>  <br/> |[<span data-ttu-id="64664-192">KB3085509</span><span class="sxs-lookup"><span data-stu-id="64664-192">KB3085509</span></span>](https://support.microsoft.com/kb/3085509) <br/> |<span data-ttu-id="64664-193">15.0.4763.1000</span><span class="sxs-lookup"><span data-stu-id="64664-193">15.0.4763.1000</span></span>  <br/> |
|<span data-ttu-id="64664-194">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="64664-194">Outlook.exe</span></span>  <br/> |<span data-ttu-id="64664-195">C:\Arquivos de Programas\Microsoft Office\Office15\OUTLOOK.EXE</span><span class="sxs-lookup"><span data-stu-id="64664-195">C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE</span></span>  <br/> |[<span data-ttu-id="64664-196">KB3085495</span><span class="sxs-lookup"><span data-stu-id="64664-196">KB3085495</span></span>](https://support.microsoft.com/kb/3085495) <br/> |<span data-ttu-id="64664-197">15.0.4753.1002</span><span class="sxs-lookup"><span data-stu-id="64664-197">15.0.4753.1002</span></span>  <br/> |
|<span data-ttu-id="64664-198">Adal. DLL</span><span class="sxs-lookup"><span data-stu-id="64664-198">ADAL.DLL</span></span>  <br/> |<span data-ttu-id="64664-199">C:\Arquivos de Programas\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span><span class="sxs-lookup"><span data-stu-id="64664-199">C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL</span></span>  <br/> |[<span data-ttu-id="64664-200">KB3055000</span><span class="sxs-lookup"><span data-stu-id="64664-200">KB3055000</span></span>](https://support.microsoft.com/kb/3055000) <br/> |<span data-ttu-id="64664-201">1.0.2016.624</span><span class="sxs-lookup"><span data-stu-id="64664-201">1.0.2016.624</span></span>  <br/> |
|<span data-ttu-id="64664-202">Iexplore. exe</span><span class="sxs-lookup"><span data-stu-id="64664-202">Iexplore.exe</span></span>  <br/> |<span data-ttu-id="64664-203">C:\Arquivos de Programas\Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="64664-203">C:\Program Files\Internet Explorer</span></span>  <br/> |[<span data-ttu-id="64664-204">MS14-052</span><span class="sxs-lookup"><span data-stu-id="64664-204">MS14-052</span></span>](https://support.microsoft.com/kb/2977629) <br/> |<span data-ttu-id="64664-205">Não se aplica</span><span class="sxs-lookup"><span data-stu-id="64664-205">Not applicable</span></span>  <br/> |
   
## <a name="enable-mfa"></a><span data-ttu-id="64664-206">Habilitar a MFA</span><span class="sxs-lookup"><span data-stu-id="64664-206">Enable MFA</span></span>

<span data-ttu-id="64664-207">Para habilitar a MFA, você deve concluir este procedimento:</span><span class="sxs-lookup"><span data-stu-id="64664-207">To enable MFA, you have to complete the following:</span></span>
  
1. <span data-ttu-id="64664-208">Habilitar os clientes para autenticação moderna:</span><span class="sxs-lookup"><span data-stu-id="64664-208">Enable clients for modern authentication:</span></span>
    
  - <span data-ttu-id="64664-209">[Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows](enable-modern-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="64664-209">[Enable Modern Authentication for Office 2013 on Windows devices](enable-modern-authentication.md) .</span></span> 
    
  - <span data-ttu-id="64664-210">Configure o MFA do Azure com serviços de diretório de terceiros.</span><span class="sxs-lookup"><span data-stu-id="64664-210">Set up Azure MFA with third-party directory services.</span></span>
    
    <span data-ttu-id="64664-211">Consulte os [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter informações sobre provedores de identidade específicos aceitos para este programa.</span><span class="sxs-lookup"><span data-stu-id="64664-211">See the [Advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for information on specific identity providers accepted to this program.</span></span> 
    
2. [<span data-ttu-id="64664-212">Configurar a autenticação multifator para o Office 365</span><span class="sxs-lookup"><span data-stu-id="64664-212">Set up multi-factor authentication for Office 365</span></span>](set-up-multi-factor-authentication.md)
    
3. <span data-ttu-id="64664-213">Explicar aos usuários individuais como entrar usando MFA: [entrar no Office 365 com a verificação em duas etapas](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span><span class="sxs-lookup"><span data-stu-id="64664-213">Tell individual users how to sign in by MFA: [Sign in to Office 365 with 2-step verification](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="64664-p109">Se você habilitou seus usuários para o MFA do Azure AD e eles têm algum dispositivo executando o Office 2013 que não está habilitado para a Autenticação Moderna, precisará usar o AppPasswords nesses dispositivos. Mais informações sobre o AppPasswords e quando/onde/como elas devem ser usadas podem ser encontradas aqui: [AppPasswords com a autenticação multifator do Azure](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span><span class="sxs-lookup"><span data-stu-id="64664-p109">If you have enabled your users for Azure AD MFA and they have any devices running Office 2013 that are not enabled for Modern Authentication, they will need to use AppPasswords on those devices. More information on AppPasswords and when/where/how they should be used can be found here: [App Passwords with Azure Multi_Factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=528178).</span></span> 
  
## <a name="faq"></a><span data-ttu-id="64664-216">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="64664-216">FAQ</span></span>

[<span data-ttu-id="64664-217">Perguntas Frequentes sobre o artigo do wiki de Autenticação Moderna</span><span class="sxs-lookup"><span data-stu-id="64664-217">FAQ about Modern Authentication wiki article</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
 <span data-ttu-id="64664-218">**Problemas conhecidos:**</span><span class="sxs-lookup"><span data-stu-id="64664-218">**Known issues:**</span></span>
  
[<span data-ttu-id="64664-219">Autenticação Moderna do Office 2013 e do Office 365 ProPlus: Como se preparar para a integração</span><span class="sxs-lookup"><span data-stu-id="64664-219">Office 2013 and Office 365 ProPlus modern authentication : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="64664-220">**Solução de problemas da Autenticação Multifator do Azure:**</span><span class="sxs-lookup"><span data-stu-id="64664-220">**Troubleshooting Azure Multi-Factor Authentication:**</span></span>
  
<span data-ttu-id="64664-221">Confira [Solucionar problemas do MFA do Azure](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span><span class="sxs-lookup"><span data-stu-id="64664-221">See [Troubleshoot Azure MFA](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).</span></span>
  
[<span data-ttu-id="64664-222">Como solucionar problemas de entrada com a autenticação moderna do Office 2013 ao usar o AD FS</span><span class="sxs-lookup"><span data-stu-id="64664-222">How to troubleshoot sign-in issues with Office 2013 modern authentication when you use AD FS</span></span>](https://support.microsoft.com/kb/3052203/)
  
 <span data-ttu-id="64664-223">**Quando IDs alternativas não funcionam:**</span><span class="sxs-lookup"><span data-stu-id="64664-223">**When alternate IDs don't work:**</span></span>
  
[<span data-ttu-id="64664-224">Como usar o PowerShell para corrigir UPN duplicado</span><span class="sxs-lookup"><span data-stu-id="64664-224">How to use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[<span data-ttu-id="64664-225">Script para corrigir UPNs duplicados</span><span class="sxs-lookup"><span data-stu-id="64664-225">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 <span data-ttu-id="64664-226">**Filtragem de acesso do cliente:**</span><span class="sxs-lookup"><span data-stu-id="64664-226">**Client access filtering:**</span></span>
  
[<span data-ttu-id="64664-227">Autenticação moderna do Office 2013 e do Office 365 ProPlus e políticas de filtragem de acesso do cliente: Como se preparar para a integração</span><span class="sxs-lookup"><span data-stu-id="64664-227">Office 2013 and Office 365 ProPlus modern authentication and client access filtering policies : Things to know before onboarding</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 <span data-ttu-id="64664-228">**Quais aplicativos dão suporte a MFA?**</span><span class="sxs-lookup"><span data-stu-id="64664-228">**Which apps support MFA?**</span></span>
  
|<span data-ttu-id="64664-229">**Windows**</span><span class="sxs-lookup"><span data-stu-id="64664-229">**Windows**</span></span>|<span data-ttu-id="64664-230">**Mac**</span><span class="sxs-lookup"><span data-stu-id="64664-230">**Mac**</span></span>|<span data-ttu-id="64664-231">**iOS**</span><span class="sxs-lookup"><span data-stu-id="64664-231">**iOS**</span></span>|<span data-ttu-id="64664-232">**Celular Android**</span><span class="sxs-lookup"><span data-stu-id="64664-232">**Android phone**</span></span>|<span data-ttu-id="64664-233">**Tablet Android**</span><span class="sxs-lookup"><span data-stu-id="64664-233">**Android tablet**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64664-234">A autenticação moderna para Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 e Skype for Business tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-234">Modern authentication for Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013, and Skype for Business is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-235">A autenticação moderna para Word 2016 para Mac, Excel 2016 para Mac e PowerPoint 2016 para Mac tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-235">Modern authentication for Word 2016 for Mac, Excel 2016 for Mac, and PowerPoint 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-236">A autenticação moderna para Word para iPad, Excel para iPad e PowerPoint para iPad tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-236">Modern authentication for Word for iPad, Excel for iPad, and PowerPoint for iPad is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-237">A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-237">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-238">A autenticação moderna do Word para Android, do Excel para Android e do PowerPoint para Android tem suporte nesta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-238">Modern authentication for Word for Android, Excel for Android, and PowerPoint for Android is supported with this release.</span></span>  <br/> |
|<span data-ttu-id="64664-239">A autenticação moderna para Outlook 2013 e Outlook 2016 tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-239">Modern authentication for Outlook 2013 and Outlook 2016 is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-240">A autenticação moderna para Outlook 2016 para Mac tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-240">Modern authentication for Outlook 2016 for Mac is supported with this release.</span></span>  <br/> |<span data-ttu-id="64664-241">A autenticação moderna do Outlook para iPad tem suporte por esta versão.</span><span class="sxs-lookup"><span data-stu-id="64664-241">Modern authentication for Outlook for iPad is supported with this release.</span></span>  <br/> |||
   

