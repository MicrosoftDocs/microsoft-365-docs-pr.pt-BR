---
title: Laboratório de avaliação do Microsoft Defender para Ponto de Extremidade
description: Saiba mais sobre os recursos do Microsoft Defender para Ponto de Extremidade, execute simulações de ataque e veja como ele impede, detecta e corre ameaças.
keywords: avaliar mdatp, avaliação, laboratório, simulação, windows 10, windows server 2019, laboratório de avaliação
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ead616b7af3df05f4c0c5755ad779f0251555734
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053981"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="c284c-104">Laboratório de avaliação do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c284c-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c284c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c284c-105">**Applies to:**</span></span>
- [<span data-ttu-id="c284c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c284c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c284c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c284c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c284c-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c284c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c284c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c284c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="c284c-110">A realização de uma avaliação abrangente do produto de segurança pode ser um processo complexo que exige ambiente e configuração de dispositivos complicados antes que uma simulação de ataque de ponta a ponta possa realmente ser feita.</span><span class="sxs-lookup"><span data-stu-id="c284c-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="c284c-111">Adicionar à complexidade é o desafio de controlar onde as atividades de simulação, alertas e resultados são refletidas durante a avaliação.</span><span class="sxs-lookup"><span data-stu-id="c284c-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="c284c-112">O laboratório de avaliação do Microsoft Defender for Endpoint foi projetado para eliminar as complexidades da configuração de dispositivo e ambiente para que você possa se concentrar na avaliação dos recursos da plataforma, na execução de simulações e na visão dos recursos de prevenção, detecção e correção em ação.</span><span class="sxs-lookup"><span data-stu-id="c284c-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="c284c-113">Com a experiência de configuração simplificada, você pode se concentrar na execução de seus próprios cenários de teste e nas simulações pré-feitas para ver como o Defender for Endpoint é executado.</span><span class="sxs-lookup"><span data-stu-id="c284c-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="c284c-114">Você terá acesso total aos recursos avançados da plataforma, como investigações automatizadas, busca avançada e análise de ameaças, permitindo que você teste a pilha de proteção abrangente que o Defender para Ponto de Extremidade oferece.</span><span class="sxs-lookup"><span data-stu-id="c284c-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="c284c-115">Você pode adicionar dispositivos Windows 10 ou Windows Server 2019 que vêm pré-configurados para ter as versões mais recentes do sistema operacional e os componentes de segurança corretos instalados, bem como o Office 2019 Standard instalado.</span><span class="sxs-lookup"><span data-stu-id="c284c-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="c284c-116">Você também pode instalar simuladores de ameaças.</span><span class="sxs-lookup"><span data-stu-id="c284c-116">You can also install threat simulators.</span></span> <span data-ttu-id="c284c-117">O Defender for Endpoint fez parceria com plataformas de simulação de ameaças líderes do setor para ajudá-lo a testar os recursos do Defender para o Ponto de Extremidade sem precisar sair do portal.</span><span class="sxs-lookup"><span data-stu-id="c284c-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="c284c-118">Instale seu simulador preferencial, execute cenários no laboratório de avaliação e veja instantaneamente como a plataforma é realizada - tudo convenientemente disponível sem custo adicional para você.</span><span class="sxs-lookup"><span data-stu-id="c284c-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="c284c-119">Você também terá acesso conveniente a uma ampla matriz de simulações que você pode acessar e executar a partir do catálogo de simulações.</span><span class="sxs-lookup"><span data-stu-id="c284c-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="c284c-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c284c-120">Before you begin</span></span>
<span data-ttu-id="c284c-121">Você precisará atender aos requisitos de [licenciamento](minimum-requirements.md#licensing-requirements) ou ter acesso de avaliação ao Microsoft Defender para Endpoint para acessar o laboratório de avaliação.</span><span class="sxs-lookup"><span data-stu-id="c284c-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="c284c-122">Você deve ter **permissões Gerenciar configurações de** segurança para:</span><span class="sxs-lookup"><span data-stu-id="c284c-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="c284c-123">Criar o laboratório</span><span class="sxs-lookup"><span data-stu-id="c284c-123">Create the lab</span></span>
- <span data-ttu-id="c284c-124">Criar dispositivos</span><span class="sxs-lookup"><span data-stu-id="c284c-124">Create devices</span></span>
- <span data-ttu-id="c284c-125">Redefinir senha</span><span class="sxs-lookup"><span data-stu-id="c284c-125">Reset password</span></span>
- <span data-ttu-id="c284c-126">Criar simulações</span><span class="sxs-lookup"><span data-stu-id="c284c-126">Create simulations</span></span> 
 
<span data-ttu-id="c284c-127">Se você habilitar o controle de acesso baseado em função (RBAC) e tiver criado pelo menos um grupo de máquinas, os usuários devem ter acesso a Todos os grupos de máquinas.</span><span class="sxs-lookup"><span data-stu-id="c284c-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="c284c-128">Para obter mais informações, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c284c-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="c284c-129">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c284c-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c284c-130">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c284c-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="c284c-131">Começar com o laboratório</span><span class="sxs-lookup"><span data-stu-id="c284c-131">Get started with the lab</span></span>
<span data-ttu-id="c284c-132">Você pode acessar o laboratório no menu.</span><span class="sxs-lookup"><span data-stu-id="c284c-132">You can access the lab from the menu.</span></span> <span data-ttu-id="c284c-133">No menu de navegação, selecione **Avaliação e tutoriais > Laboratório de Avaliação.**</span><span class="sxs-lookup"><span data-stu-id="c284c-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Imagem do laboratório de avaliação no menu](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="c284c-135">Cada ambiente é provisionado com um conjunto limitado de dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="c284c-135">Each environment is provisioned with a limited set of test devices.</span></span>
>- <span data-ttu-id="c284c-136">Dependendo do tipo de estrutura de ambiente selecionada, os dispositivos estarão disponíveis para o número especificado de horas a partir do dia da ativação.</span><span class="sxs-lookup"><span data-stu-id="c284c-136">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="c284c-137">Quando você usou os dispositivos provisionados, nenhum novo dispositivo é fornecido.</span><span class="sxs-lookup"><span data-stu-id="c284c-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="c284c-138">Um dispositivo excluído não atualize a contagem de dispositivos de teste disponível.</span><span class="sxs-lookup"><span data-stu-id="c284c-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="c284c-139">Considerando os recursos limitados, é recomendável usar os dispositivos cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="c284c-139">Given the limited resources, it’s advisable to use the devices carefully.</span></span>

<span data-ttu-id="c284c-140">Já tem um laboratório?</span><span class="sxs-lookup"><span data-stu-id="c284c-140">Already have a lab?</span></span> <span data-ttu-id="c284c-141">Certifique-se de habilitar os novos simuladores de ameaças e ter dispositivos ativos.</span><span class="sxs-lookup"><span data-stu-id="c284c-141">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="c284c-142">Configurar o laboratório de avaliação</span><span class="sxs-lookup"><span data-stu-id="c284c-142">Setup the evaluation lab</span></span>

1. <span data-ttu-id="c284c-143">No painel de navegação, selecione **Avaliação e tutoriais** Laboratório de  >  Avaliação, em seguida, selecione **Laboratório de Instalação**.</span><span class="sxs-lookup"><span data-stu-id="c284c-143">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Imagem da página de boas-vindas do laboratório de avaliação](images/evaluation-lab-setup.png)

2. <span data-ttu-id="c284c-145">Dependendo das suas necessidades de avaliação, você pode optar por configurar um ambiente com menos dispositivos por um período maior ou mais dispositivos por um período mais curto.</span><span class="sxs-lookup"><span data-stu-id="c284c-145">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="c284c-146">Selecione sua configuração de laboratório preferencial e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="c284c-146">Select your preferred lab configuration then select **Next**.</span></span>

    ![Imagem das opções de configuração de laboratório](images/lab-creation-page.png) 


3. <span data-ttu-id="c284c-148">(Opcional) Você pode optar por instalar simuladores de ameaças no laboratório.</span><span class="sxs-lookup"><span data-stu-id="c284c-148">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Imagem do agente de simuladores de instalação](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="c284c-150">Primeiro, você precisará aceitar e fornecer consentimento para os termos e instruções de compartilhamento de informações.</span><span class="sxs-lookup"><span data-stu-id="c284c-150">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="c284c-151">Selecione o agente de simulação de ameaça que você gostaria de usar e insira seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="c284c-151">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="c284c-152">Você também pode optar por instalar simuladores de ameaças posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c284c-152">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="c284c-153">Se você optar por instalar agentes de simulação de ameaças durante a instalação do laboratório, aproveitará o benefício de instalá-los convenientemente nos dispositivos que você adicionar.</span><span class="sxs-lookup"><span data-stu-id="c284c-153">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Imagem da página de resumo](images/lab-setup-summary.png)

5.  <span data-ttu-id="c284c-155">Revise o resumo e selecione **Laboratório de Instalação.**</span><span class="sxs-lookup"><span data-stu-id="c284c-155">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="c284c-156">Depois que o processo de instalação do laboratório for concluído, você poderá adicionar dispositivos e executar simulações.</span><span class="sxs-lookup"><span data-stu-id="c284c-156">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="c284c-157">Adicionar dispositivos</span><span class="sxs-lookup"><span data-stu-id="c284c-157">Add devices</span></span>
<span data-ttu-id="c284c-158">Quando você adiciona um dispositivo ao seu ambiente, o Defender for Endpoint configura um dispositivo bem configurado com detalhes de conexão.</span><span class="sxs-lookup"><span data-stu-id="c284c-158">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="c284c-159">Você pode adicionar dispositivos Windows 10 ou Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c284c-159">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="c284c-160">O dispositivo será configurado com a versão mais atualizada do sistema operacional e do Office 2019 Standard, bem como outros aplicativos, como Java, Python e SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="c284c-160">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="c284c-161">Precisa de mais dispositivos em seu laboratório?</span><span class="sxs-lookup"><span data-stu-id="c284c-161">Need more devices in your lab?</span></span> <span data-ttu-id="c284c-162">Envie um tíquete de suporte para que sua solicitação seja revisada pela equipe do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c284c-162">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="c284c-163">Se você optar por adicionar um simulador de ameaças durante a configuração do laboratório, todos os dispositivos terão o agente simulador de ameaças instalado nos dispositivos que você adicionar.</span><span class="sxs-lookup"><span data-stu-id="c284c-163">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="c284c-164">O dispositivo será automaticamente integrado ao seu locatário com os componentes de segurança do Windows recomendados ativados e no modo de auditoria - sem esforço do seu lado.</span><span class="sxs-lookup"><span data-stu-id="c284c-164">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="c284c-165">Os seguintes componentes de segurança são pré-configurados nos dispositivos de teste:</span><span class="sxs-lookup"><span data-stu-id="c284c-165">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="c284c-166">Redução da superfície do ataque.</span><span class="sxs-lookup"><span data-stu-id="c284c-166">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="c284c-167">Bloquear à primeira vista</span><span class="sxs-lookup"><span data-stu-id="c284c-167">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="c284c-168">Acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c284c-168">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="c284c-169">Proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="c284c-169">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="c284c-170">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="c284c-170">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="c284c-171">Detecção de aplicativo potencialmente indesejado</span><span class="sxs-lookup"><span data-stu-id="c284c-171">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="c284c-172">Proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="c284c-172">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="c284c-173">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="c284c-173">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="c284c-174">O Microsoft Defender Antivírus estará em (não no modo de auditoria).</span><span class="sxs-lookup"><span data-stu-id="c284c-174">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="c284c-175">Se o Microsoft Defender Antivírus o impede de executar sua simulação, você pode desativar a proteção em tempo real no dispositivo por meio do Windows Security.</span><span class="sxs-lookup"><span data-stu-id="c284c-175">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="c284c-176">Para obter mais informações, consulte [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="c284c-176">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="c284c-177">As configurações de investigação automatizadas dependerão das configurações do locatário.</span><span class="sxs-lookup"><span data-stu-id="c284c-177">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="c284c-178">Ele será configurado para ser semi-automatizado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c284c-178">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="c284c-179">Para obter mais informações, consulte [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="c284c-179">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="c284c-180">A conexão com os dispositivos de teste é feita usando RDP.</span><span class="sxs-lookup"><span data-stu-id="c284c-180">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="c284c-181">Certifique-se de que suas configurações de firewall permitem conexões RDP.</span><span class="sxs-lookup"><span data-stu-id="c284c-181">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="c284c-182">No painel, selecione **Adicionar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c284c-182">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="c284c-183">Escolha o tipo de dispositivo a ser acrescentado.</span><span class="sxs-lookup"><span data-stu-id="c284c-183">Choose the type of device to add.</span></span> <span data-ttu-id="c284c-184">Você pode optar por adicionar o Windows 10 ou o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c284c-184">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Imagem da configuração de laboratório com opções de dispositivo](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="c284c-186">Se algo der errado com o processo de criação do dispositivo, você será notificado e precisará enviar uma nova solicitação.</span><span class="sxs-lookup"><span data-stu-id="c284c-186">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="c284c-187">Se a criação do dispositivo falhar, ela não será contada em relação à cota permitida geral.</span><span class="sxs-lookup"><span data-stu-id="c284c-187">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="c284c-188">Os detalhes da conexão são exibidos.</span><span class="sxs-lookup"><span data-stu-id="c284c-188">The connection details are displayed.</span></span> <span data-ttu-id="c284c-189">Selecione **Copiar** para salvar a senha do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c284c-189">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="c284c-190">A senha só é exibida uma vez.</span><span class="sxs-lookup"><span data-stu-id="c284c-190">The password is only displayed once.</span></span> <span data-ttu-id="c284c-191">Certifique-se de salvá-lo para uso posterior.</span><span class="sxs-lookup"><span data-stu-id="c284c-191">Be sure to save it for later use.</span></span>

    ![Imagem do dispositivo adicionada com detalhes de conexão](images/add-machine-eval-lab.png)

4. <span data-ttu-id="c284c-193">A configuração do dispositivo começa.</span><span class="sxs-lookup"><span data-stu-id="c284c-193">Device set up begins.</span></span> <span data-ttu-id="c284c-194">Isso pode levar até aproximadamente 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c284c-194">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="c284c-195">Consulte o status dos dispositivos de teste, os níveis de risco e exposição e o status das instalações do simulador selecionando a guia **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="c284c-195">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Guia Imagem de dispositivos](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="c284c-197">Na coluna **status do Simulador,** você pode passar o mouse sobre o ícone de informações para saber o status de instalação de um agente.</span><span class="sxs-lookup"><span data-stu-id="c284c-197">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="c284c-198">Simular cenários de ataque</span><span class="sxs-lookup"><span data-stu-id="c284c-198">Simulate attack scenarios</span></span>
<span data-ttu-id="c284c-199">Use os dispositivos de teste para executar suas próprias simulações de ataque conectando-se a eles.</span><span class="sxs-lookup"><span data-stu-id="c284c-199">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="c284c-200">Você pode simular cenários de ataque usando:</span><span class="sxs-lookup"><span data-stu-id="c284c-200">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="c284c-201">Os cenários de ataque ["Faça você mesmo"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="c284c-201">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="c284c-202">Simuladores de ameaças</span><span class="sxs-lookup"><span data-stu-id="c284c-202">Threat simulators</span></span>

<span data-ttu-id="c284c-203">Você também pode usar [a busca avançada](advanced-hunting-query-language.md) para consultar dados e análise de [ameaças](threat-analytics.md) para exibir relatórios sobre ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="c284c-203">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="c284c-204">Cenários de ataque do faça você mesmo</span><span class="sxs-lookup"><span data-stu-id="c284c-204">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="c284c-205">Se você estiver procurando uma simulação pré-feita, poderá usar nossos cenários de ataque ["Faça você mesmo".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="c284c-205">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="c284c-206">Esses scripts são seguros, documentados e fáceis de usar.</span><span class="sxs-lookup"><span data-stu-id="c284c-206">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="c284c-207">Esses cenários refletirão os recursos do Defender para o Ponto de Extremidade e o passarão pela experiência de investigação.</span><span class="sxs-lookup"><span data-stu-id="c284c-207">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="c284c-208">A conexão com os dispositivos de teste é feita usando RDP.</span><span class="sxs-lookup"><span data-stu-id="c284c-208">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="c284c-209">Certifique-se de que suas configurações de firewall permitem conexões RDP.</span><span class="sxs-lookup"><span data-stu-id="c284c-209">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="c284c-210">Conecte-se ao dispositivo e execute uma simulação de ataque selecionando **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c284c-210">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Imagem do botão de conexão para dispositivos de teste](images/test-machine-table.png)

2. <span data-ttu-id="c284c-212">Salve o arquivo RDP e o iniciar selecionando **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c284c-212">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Imagem da conexão de área de trabalho remota](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="c284c-214">Se você não tiver uma cópia da senha salva durante a configuração inicial, poderá redefinir a senha selecionando **Redefinir** senha no menu: Imagem da redefinição de ![ senha](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="c284c-214">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="c284c-215">O dispositivo alterará seu estado para "Executando redefinição de senha", em seguida, você será apresentado com sua nova senha em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c284c-215">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="c284c-216">Insira a senha exibida durante a etapa de criação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c284c-216">Enter the password that was displayed during the device creation step.</span></span> 

   ![Imagem da janela para inserir credenciais](images/enter-password.png)

4. <span data-ttu-id="c284c-218">Execute simulações de ataque Do-it-yourself no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c284c-218">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="c284c-219">Cenários de simulador de ameaças</span><span class="sxs-lookup"><span data-stu-id="c284c-219">Threat simulator scenarios</span></span>
<span data-ttu-id="c284c-220">Se você optar por instalar qualquer um dos simuladores de ameaça com suporte durante a configuração do laboratório, poderá executar as simulações internas nos dispositivos de laboratório de avaliação.</span><span class="sxs-lookup"><span data-stu-id="c284c-220">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="c284c-221">Executar simulações de ameaças usando plataformas de terceiros é uma boa maneira de avaliar os recursos do Microsoft Defender para o Ponto de Extremidade dentro dos limites de um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="c284c-221">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="c284c-222">Antes de executar simulações, certifique-se de que os seguintes requisitos sejam atendidos:</span><span class="sxs-lookup"><span data-stu-id="c284c-222">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="c284c-223">Os dispositivos devem ser adicionados ao laboratório de avaliação</span><span class="sxs-lookup"><span data-stu-id="c284c-223">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="c284c-224">Simuladores de ameaças devem ser instalados no laboratório de avaliação</span><span class="sxs-lookup"><span data-stu-id="c284c-224">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="c284c-225">No portal, selecione **Criar simulação**.</span><span class="sxs-lookup"><span data-stu-id="c284c-225">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="c284c-226">Selecione um simulador de ameaças.</span><span class="sxs-lookup"><span data-stu-id="c284c-226">Select a threat simulator.</span></span>

    ![Imagem da seleção do simulador de ameaças](images/select-simulator.png)

3. <span data-ttu-id="c284c-228">Escolha uma simulação ou procure na galeria de simulação para navegar pelas simulações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c284c-228">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="c284c-229">Você pode chegar à galeria de simulação de:</span><span class="sxs-lookup"><span data-stu-id="c284c-229">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="c284c-230">O painel de avaliação principal no painel **de visão geral de** Simulações ou</span><span class="sxs-lookup"><span data-stu-id="c284c-230">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="c284c-231">Navegando no painel de navegação Avaliação e **tutoriais** De  >  **simulação & tutoriais,** selecione **Catálogo de Simulações**.</span><span class="sxs-lookup"><span data-stu-id="c284c-231">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="c284c-232">Selecione os dispositivos em que você gostaria de executar a simulação.</span><span class="sxs-lookup"><span data-stu-id="c284c-232">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="c284c-233">Selecione **Criar simulação**.</span><span class="sxs-lookup"><span data-stu-id="c284c-233">Select **Create simulation**.</span></span>

6. <span data-ttu-id="c284c-234">Exibir o progresso de uma simulação selecionando a guia **Simulações.** Exibir o estado de simulação, alertas ativos e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="c284c-234">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Guia Imagem de simulações](images/simulations-tab.png)
    
<span data-ttu-id="c284c-236">Depois de executar suas simulações, recomendamos que você ande pela barra de progresso do laboratório e explore o Microsoft Defender para Ponto de Extremidade acionou uma investigação **e correção automatizadas.**</span><span class="sxs-lookup"><span data-stu-id="c284c-236">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="c284c-237">Confira as evidências coletadas e analisadas pelo recurso.</span><span class="sxs-lookup"><span data-stu-id="c284c-237">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="c284c-238">Procure evidências de ataque por meio da busca avançada usando a linguagem de consulta avançada e a telemetria bruta e confira algumas ameaças em todo o mundo documentadas na análise de ameaças.</span><span class="sxs-lookup"><span data-stu-id="c284c-238">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="c284c-239">Galeria de simulação</span><span class="sxs-lookup"><span data-stu-id="c284c-239">Simulation gallery</span></span>
<span data-ttu-id="c284c-240">O Microsoft Defender for Endpoint fez parceria com várias plataformas de simulação de ameaças para lhe dar acesso conveniente para testar os recursos da plataforma desde o portal.</span><span class="sxs-lookup"><span data-stu-id="c284c-240">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="c284c-241">Exibir todas as simulações disponíveis indo para **Simulações** e tutoriais Catálogo de Simulações  >   no menu.</span><span class="sxs-lookup"><span data-stu-id="c284c-241">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="c284c-242">Uma lista de agentes de simulação de ameaças de terceiros com suporte está listada, e tipos específicos de simulações, juntamente com descrições detalhadas, são fornecidos no catálogo.</span><span class="sxs-lookup"><span data-stu-id="c284c-242">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="c284c-243">Você pode executar convenientemente qualquer simulação disponível a partir do catálogo.</span><span class="sxs-lookup"><span data-stu-id="c284c-243">You can conveniently run any available simulation right from the catalog.</span></span>  


![Imagem do catálogo de simulações](images/simulations-catalog.png)

<span data-ttu-id="c284c-245">Cada simulação vem com uma descrição detalhada do cenário de ataque e referências, como as técnicas de ataque MITRE usadas e exemplo de consultas de busca avançadas que você executar.</span><span class="sxs-lookup"><span data-stu-id="c284c-245">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="c284c-246">**Exemplos:** 
 ![ Imagem dos detalhes da descrição da simulação1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="c284c-246">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Imagem dos detalhes da descrição da simulação2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="c284c-248">Relatório de avaliação</span><span class="sxs-lookup"><span data-stu-id="c284c-248">Evaluation report</span></span>
<span data-ttu-id="c284c-249">Os relatórios de laboratório resumem os resultados das simulações realizadas nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c284c-249">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Imagem do relatório de avaliação](images/eval-report.png)

<span data-ttu-id="c284c-251">Rapidamente, você poderá ver:</span><span class="sxs-lookup"><span data-stu-id="c284c-251">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="c284c-252">Incidentes que foram disparados</span><span class="sxs-lookup"><span data-stu-id="c284c-252">Incidents that were triggered</span></span>
- <span data-ttu-id="c284c-253">Alertas gerados</span><span class="sxs-lookup"><span data-stu-id="c284c-253">Generated alerts</span></span>
- <span data-ttu-id="c284c-254">Avaliações no nível de exposição</span><span class="sxs-lookup"><span data-stu-id="c284c-254">Assessments on exposure level</span></span> 
- <span data-ttu-id="c284c-255">Categorias de ameaças observadas</span><span class="sxs-lookup"><span data-stu-id="c284c-255">Threat categories observed</span></span>
- <span data-ttu-id="c284c-256">Fontes de detecção</span><span class="sxs-lookup"><span data-stu-id="c284c-256">Detection sources</span></span>
- <span data-ttu-id="c284c-257">Investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="c284c-257">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="c284c-258">Faça comentários</span><span class="sxs-lookup"><span data-stu-id="c284c-258">Provide feedback</span></span>
<span data-ttu-id="c284c-259">Seus comentários nos ajudam a melhorar a proteção do ambiente contra ataques avançados.</span><span class="sxs-lookup"><span data-stu-id="c284c-259">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="c284c-260">Compartilhe sua experiência e impressões de recursos do produto e resultados de avaliação.</span><span class="sxs-lookup"><span data-stu-id="c284c-260">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="c284c-261">Deixe-nos saber o que você acha, selecionando **Fornecer comentários**.</span><span class="sxs-lookup"><span data-stu-id="c284c-261">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Imagem de fornecer comentários](images/send-us-feedback-eval-lab.png)
