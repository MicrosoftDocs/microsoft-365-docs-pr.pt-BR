---
title: Defina configurações de proteção de dispositivos para PCs com Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Saiba mais sobre o padrão e outras configurações disponíveis no Microsoft 365 Business para proteger dispositivos Windows 10.
ms.openlocfilehash: ab306e3d5a6011a0e7d537c98ecca6ef49ff82d9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575749"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="77783-103">Defina configurações de proteção de dispositivos para PCs com Windows 10</span><span class="sxs-lookup"><span data-stu-id="77783-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="77783-104">Proteger dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="77783-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="77783-105">Exibir um vídeo sobre como proteger dispositivos Windows 10 com o Microsoft 365 Business:</span><span class="sxs-lookup"><span data-stu-id="77783-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="77783-106">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="77783-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="77783-107">No painel de navegação esquerdo, escolha **Adicionar** **políticas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="77783-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="77783-108">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="77783-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="77783-109">Em **Tipo de política**, escolha **Configuração de Dispositivo Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="77783-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="77783-p101">Expanda **Proteger dispositivos Windows 10** \> defina as configurações como desejar. Confira [Configurações disponíveis](#available-settings) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="77783-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="77783-112">Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="77783-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="77783-p102">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os usuários**, escolha **Alterar**, pesquise o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="77783-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="77783-116">Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="77783-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="77783-117">Configurações disponíveis</span><span class="sxs-lookup"><span data-stu-id="77783-117">Available settings</span></span>

<span data-ttu-id="77783-p103">Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77783-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="77783-120">Confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="77783-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="77783-121">Setting</span><span class="sxs-lookup"><span data-stu-id="77783-121">Setting</span></span>  <br/> |<span data-ttu-id="77783-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="77783-122">Description</span></span>  <br/> |
|<span data-ttu-id="77783-123">Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="77783-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="77783-124">Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.</span><span class="sxs-lookup"><span data-stu-id="77783-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="77783-125">Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="77783-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="77783-126">Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="77783-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="77783-127">Usar regras que reduzem a superfície de ataque de dispositivos</span><span class="sxs-lookup"><span data-stu-id="77783-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="77783-p104">Quando ativada, a redução da superfície de ataque ajuda a bloquear ações e aplicativos normalmente usados por malware para infectar dispositivos. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Confira [Reduzir superfícies de ataque](https://go.microsoft.com/fwlink/?linkid=870417) para saber mais.  </span><span class="sxs-lookup"><span data-stu-id="77783-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="77783-131">Proteger pastas de ameaças como ransomware</span><span class="sxs-lookup"><span data-stu-id="77783-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="77783-p105">Essa configuração usa o acesso a pastas controladas para proteger os dados da empresa contra modificações feitas por aplicativos suspeitos ou maliciosos, como ransomware. Esses tipos de aplicativos são impedidos de fazer alterações em pastas protegidas. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Confira [Proteger pastas com acesso à pasta controlado](https://go.microsoft.com/fwlink/?linkid=870418) para saber mais.  </span><span class="sxs-lookup"><span data-stu-id="77783-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="77783-136">Impedir o acesso da rede a conteúdo potencialmente malicioso na Internet</span><span class="sxs-lookup"><span data-stu-id="77783-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="77783-p106">Use essa configuração para bloquear conexões de usuários de saída a locais com baixa reputação na Internet que possam hospedar golpes de phishing, exploits ou outros conteúdos maliciosos. Esta configuração só estará disponível se o Windows Defender Antivírus for definido como ativado. Confira [Proteger sua rede](https://go.microsoft.com/fwlink/?linkid=870419) para saber mais.  </span><span class="sxs-lookup"><span data-stu-id="77783-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="77783-140">Ajudar a proteger os arquivos e pastas em computadores contra acesso não autorizado com o BitLocker</span><span class="sxs-lookup"><span data-stu-id="77783-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="77783-p107">O BitLocker protege os dados por meio da criptografia das unidades de disco do computador e da proteção contra exposição de dados caso um computador seja perdido ou roubado. Confira [Perguntas frequentes sobre Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000) para saber mais.  </span><span class="sxs-lookup"><span data-stu-id="77783-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="77783-143">Permitir que os usuários baixem aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="77783-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="77783-p108">Permite aos usuários baixar e instalar os aplicativos da Microsoft Store. Aplicativos incluem desde jogos a ferramentas de produtividade, portanto, deixamos essa configuração **Ativada**, mas você pode desativá-la para obter mais segurança.  </span><span class="sxs-lookup"><span data-stu-id="77783-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="77783-146">Permitir que os usuários acessem a Cortana</span><span class="sxs-lookup"><span data-stu-id="77783-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="77783-p109">A Cortana pode ser muito útil! Ela pode ativar ou desativar configurações para você, fornecer instruções e garantir que você cumpra compromissos pontualmente, então nós a mantemos **Ativadas**.  </span><span class="sxs-lookup"><span data-stu-id="77783-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="77783-149">Permitir que os usuários recebam anúncios e dicas sobre o Windows da Microsoft</span><span class="sxs-lookup"><span data-stu-id="77783-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="77783-150">Dicas sobre o Windows podem ser úteis e ajudar a orientar os usuários quando novos recursos forem lançados.</span><span class="sxs-lookup"><span data-stu-id="77783-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="77783-151">Manter dispositivos Windows 10 atualizados automaticamente</span><span class="sxs-lookup"><span data-stu-id="77783-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="77783-152">Garante que os dispositivos Windows 10 recebam automaticamente as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="77783-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="77783-153">Desligar a tela do dispositivo quando ele ficar ocioso durante este período</span><span class="sxs-lookup"><span data-stu-id="77783-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="77783-p110">Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.</span><span class="sxs-lookup"><span data-stu-id="77783-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

