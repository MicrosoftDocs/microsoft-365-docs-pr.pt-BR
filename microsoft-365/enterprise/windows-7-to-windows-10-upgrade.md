---
title: Guia de atualização do Windows 7 para o Windows 10
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Atualização do Windows 7 para o Windows 10.
ms.openlocfilehash: aaa1ce39e63aebeb3c2ab6678b3c1ade6791ab22
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2019
ms.locfileid: "34821035"
---
# <a name="windows-7-to-windows-10-manual-upgrade-step-by-step-guide"></a><span data-ttu-id="81d0e-103">Guia passo a passo de atualização manual do Windows 7 para Windows 10</span><span class="sxs-lookup"><span data-stu-id="81d0e-103">Windows 7 to Windows 10 manual upgrade step-by-step guide</span></span>

<span data-ttu-id="81d0e-104">Este artigo descreve o processo de atualização manual de um PC com Windows 7 Enterprise para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="81d0e-104">This article describes the process to manually upgrade a Windows 7 Enterprise PC to Windows 10 Enterprise.</span></span> <span data-ttu-id="81d0e-105">Para outras edições do Windows 7, como Home e  Professional, o processo é muito semelhante, mas você também tem a opção de atualizar diretamente usando a ferramenta de criação de mídia.</span><span class="sxs-lookup"><span data-stu-id="81d0e-105">For other Windows 7 editions, such as Home and Professional, the process is very similar, but you also have the option to upgrade directly using the media creation tool.</span></span> <span data-ttu-id="81d0e-106">As atualizações para qualquer edição do Windows 7 para o Windows 10 requerem uma chave do produto (Product Key) válida, ou uma edição superior do Windows, por exemplo, o Windows 7 Professional pode atualizar para o Windows 10 Pro, mas não pode ser atualizado para o Windows 10 Home.</span><span class="sxs-lookup"><span data-stu-id="81d0e-106">Upgrades for any edition of Windows 7 to Windows 10 will require a valid product key and matching or higher edition of Windows, for example Windows 7 Professional can upgrade to Windows 10 Pro, but cannot be upgraded to Windows 10 Home.</span></span> <span data-ttu-id="81d0e-107">O Windows 7 Ultimate deve ser atualizado para o Windows 10 Pro.</span><span class="sxs-lookup"><span data-stu-id="81d0e-107">Windows 7 Ultimate will need to be upgraded to Windows 10 Pro.</span></span>

## <a name="windows-10-upgrades-using-the-media-creation-tool-or-iso-files"></a><span data-ttu-id="81d0e-108">O Windows 10 é atualizado usando a ferramenta de criação de mídia ou arquivos ISO</span><span class="sxs-lookup"><span data-stu-id="81d0e-108">Windows 10 upgrades using the media creation tool or ISO files</span></span>

<span data-ttu-id="81d0e-109">Você pode atualizar para o Windows 10 diretamente usando a [ferramenta de criação de mídia](https://www.microsoft.com/en-us/software-download/windows10ISO) ou usá-la para baixar o Windows 10 como um arquivo ISO.</span><span class="sxs-lookup"><span data-stu-id="81d0e-109">You can upgrade to Windows 10 directly using the [media creation tool](https://www.microsoft.com/en-us/software-download/windows10ISO) or use the it to download Windows 10 as an ISO file.</span></span> <span data-ttu-id="81d0e-110">Você deve observar se o seu sistema atual é de 32 ou 64 bits, o idioma padrão do sistema e a edição do Windows 7 (por exemplo, Home, Professional ou Enterprise).</span><span class="sxs-lookup"><span data-stu-id="81d0e-110">You’ll need to note whether your current system is 32 or 64-bit, your system’s default language and edition of Windows 7 (e.g. Home, Professional, or Enterprise).</span></span> <span data-ttu-id="81d0e-111">No Windows 7, essas informações estão localizadas no sistema do painel de controle \>Sistema e Segurança\>.</span><span class="sxs-lookup"><span data-stu-id="81d0e-111">In Windows 7, this information is located in the Control Panel \> System and Security \> System.</span></span> <span data-ttu-id="81d0e-112">A ferramenta de criação de mídia não oferece suporte ao Windows 10 Enterprise para atualizações, criação de mídia de instalação ou download de arquivos ISO.</span><span class="sxs-lookup"><span data-stu-id="81d0e-112">The media creation tool does not support Windows 10 Enterprise for upgrades, creating installation media or downloading ISO files.</span></span> <span data-ttu-id="81d0e-113">O Windows 10 Enterprise é necessário se você estiver atualizando do Windows 7 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="81d0e-113">Windows 10 Enterprise is required if you are upgrading from Windows 7 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-1.png)

> <span data-ttu-id="81d0e-114">Opções da ferramenta de criação de mídia do Windows 10</span><span class="sxs-lookup"><span data-stu-id="81d0e-114">Windows 10 media creation tool options</span></span>

<span data-ttu-id="81d0e-115">Ao atualizar do Windows 7 Enterprise para o Windows 10 Enterprise, você precisará fazer o download do arquivo ISO para seu idioma e arquitetura (32 bits ou 64 bits) no [Centro de Atendimento de Licenciamento por Volume](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="81d0e-115">When upgrading from Windows 7 Enterprise to Windows 10 Enterprise, you’ll need to download the ISO file for your language and architecture (32-bit or 64-bit) from the [Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

<span data-ttu-id="81d0e-116">Se você planeja executar a atualização usando um arquivo ISO, será necessário extrair os arquivos no ISO para o seu sistema de arquivos local, para uma unidade removível, ou você pode gravar o arquivo ISO em um DVD.</span><span class="sxs-lookup"><span data-stu-id="81d0e-116">If you plan to perform the upgrade using an ISO file, you will need to extract the files within the ISO to either your local file system, to a removable drive, or you can burn the ISO file to a DVD.</span></span> <span data-ttu-id="81d0e-117">Você pode extrair os arquivos de instalação dentro do ISO usando um PC com Windows 8 ou mais recente e salvá-los em um armazenamento USB removível ou usar um aplicativo como o [7zip](https://www.7-zip.org/) para extrair o conteúdo do seu arquivo ISO para uma pasta na sua unidade local no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-117">You can extract the installation files within the ISO using a Windows 8 or newer PC and save these files to removable USB storage or use an application such as [7zip](https://www.7-zip.org/) to extract the contents of your ISO file to a folder on your local drive within Windows 7.</span></span>

<span data-ttu-id="81d0e-118">Depois de ter a mídia de instalação disponível no Windows 7, você poderá iniciar a atualização executando o setup.exe, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="81d0e-118">Once you have the install media available in Windows 7, you can initiate the upgrade by running setup.exe as shown below.</span></span>

<span data-ttu-id="81d0e-119">**Dica importante: para uma atualização no local em que os aplicativos e seus dados são migrados para o Windows 10, você precisará iniciar o processo a partir de uma sessão do Windows 7 em execução. A inicialização para instalar mídia de um drive de DVD ou USB não lhe dará a opção de manter seus aplicativos e arquivos, em vez disso, executará uma instalação limpa do Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="81d0e-119">**Important tip: For an in-place upgrade where applications and your data are migrated to Window 10, you’ll need to initiate the process from within a running Windows 7 session. Booting to install media from a DVD or USB drive will not give you the option to keep your apps and files, instead it will perform a clean install of Windows 10.**</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-2.png)

> <span data-ttu-id="81d0e-120">Arquivos extraídos de um ISO de 32 bits do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="81d0e-120">Extracted files from a Windows 10 Enterprise 32-bit ISO</span></span>

<span data-ttu-id="81d0e-121">Na configuração do Windows 10, você será orientado durante o processo de instalação e a primeira tela fornece uma opção para baixar atualizações, drivers e recursos opcionais.</span><span class="sxs-lookup"><span data-stu-id="81d0e-121">Within Windows 10 Setup, you will be guided through the installation process and the first screen provides an option to download updates, drivers and optional features.</span></span> <span data-ttu-id="81d0e-122">Isso é recomendável para ajudar a garantir o sucesso com a atualização</span><span class="sxs-lookup"><span data-stu-id="81d0e-122">This is recommended to help ensure success with the upgrade</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-3.png)

> <span data-ttu-id="81d0e-123">Tela de configuração inicial do Windows 10</span><span class="sxs-lookup"><span data-stu-id="81d0e-123">Initial Windows 10 Setup screen</span></span>

<span data-ttu-id="81d0e-124">Depois que as atualizações forem aplicadas, a Instalação do Windows 10 passará para a próxima fase, Selecionar imagem.</span><span class="sxs-lookup"><span data-stu-id="81d0e-124">Once updates have been applied, Windows 10 Setup will move to the next phase, Select Image.</span></span> <span data-ttu-id="81d0e-125">Aqui, você precisará selecionar sua edição do Windows.</span><span class="sxs-lookup"><span data-stu-id="81d0e-125">Here, you will need to select your edition of Windows.</span></span> <span data-ttu-id="81d0e-126">Nesse caso, como o PC tem o Windows 7 Enterprise instalado, você selecionaria o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="81d0e-126">In this case, since the PC has Windows 7 Enterprise installed, you would select Windows 10 Enterprise.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-4.png)

> <span data-ttu-id="81d0e-127">Tela de seleção de imagens do Windows 10 Enterprise de 32 bits</span><span class="sxs-lookup"><span data-stu-id="81d0e-127">Windows 10 Enterprise 32-bit image selection screen</span></span>

<span data-ttu-id="81d0e-128">Na próxima tela da Configuração do Windows 10, você recebe os avisos e os termos de licençaa aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="81d0e-128">In the next screen in Windows 10 Setup, you’re presented with applicable notices and license terms.</span></span> <span data-ttu-id="81d0e-129">Depois de ler e entender os avisos e termos, clique em "Aceitar" para continuar ou "Recusar" para cancelar.</span><span class="sxs-lookup"><span data-stu-id="81d0e-129">Once you have read and understand the notices and terms, click “Accept” to continue or “Decline” to cancel.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-5.png)

<span data-ttu-id="81d0e-130">*Avisos e condições de licença aplicáveis do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-130">*Windows 10 Applicable notices and license terms*</span></span>

<span data-ttu-id="81d0e-131">Agora o programa de instalação do Windows 10 procurará atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="81d0e-131">Now Windows 10 Setup will look for additional updates.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-6.png)

<span data-ttu-id="81d0e-132">*Atualizações de configuração do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-132">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="81d0e-133">Uma vez concluída, a instalação do Windows 10 estará pronta para ser instalada, por padrão, é configurada para instalar o Windows 10 e manter seus arquivos pessoais e aplicativos instalados.</span><span class="sxs-lookup"><span data-stu-id="81d0e-133">Once complete, Windows 10 Setup is ready to install and by default is configured to install Windows 10 and keep your personal files and apps installed.</span></span> <span data-ttu-id="81d0e-134">Essa é a opção recomendada.</span><span class="sxs-lookup"><span data-stu-id="81d0e-134">This is the recommended option.</span></span> <span data-ttu-id="81d0e-135">Ao clicar em "Alterar o que manter", você encontrará opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="81d0e-135">By clicking, “Change what to keep,” you’ll find additional options.</span></span> <span data-ttu-id="81d0e-136">Caso contrário, clique em "Instalar".</span><span class="sxs-lookup"><span data-stu-id="81d0e-136">Otherwise, click “Install.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-7.png)

<span data-ttu-id="81d0e-137">*Opção de atualização do programa de instalação do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-137">*Windows 10 Setup upgrade option default*</span></span>

<span data-ttu-id="81d0e-138">Se você selecionar "Alterar o que manter", verá as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="81d0e-138">If you select “Change what to keep”, you’ll be presented with these options:</span></span>

<span data-ttu-id="81d0e-139">"Manter somente arquivos pessoais" não migrará os aplicativos instalados ou as configurações do Windows 7 para o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81d0e-139">“Keep personal files only” will not move your installed apps or settings from Windows 7 to Windows 10.</span></span> <span data-ttu-id="81d0e-140">Em vez disso, os arquivos e as contas de usuário serão movidos para o Windows.</span><span class="sxs-lookup"><span data-stu-id="81d0e-140">Instead it will only move your files and user accounts to Windows.</span></span> <span data-ttu-id="81d0e-141">Será necessário reinstalar os aplicativos mais tarde com essa opção.</span><span class="sxs-lookup"><span data-stu-id="81d0e-141">Apps will need to be reinstalled later with this option.</span></span> <span data-ttu-id="81d0e-142">Use essa opção somente se você tiver certeza de que pode reinstalar e configurar os aplicativos necessários após a instalação do Windows, caso contrário, mantenha a opção padrão "Manter arquivos pessoais e aplicativos".</span><span class="sxs-lookup"><span data-stu-id="81d0e-142">Only use this option if you are confident you can reinstall and configure the apps you will need after Windows is installed, otherwise stick with the default “Keep personal files and apps” option.</span></span>

<span data-ttu-id="81d0e-143">"Nada" excluirá seus arquivos, aplicativos e configurações e executará uma instalação limpa do Windows.</span><span class="sxs-lookup"><span data-stu-id="81d0e-143">“Nothing” will delete your files, apps and settings and perform a clean install of Windows.</span></span> <span data-ttu-id="81d0e-144">Use essa opção somente se você tiver feito o backup dos dados que deseja manter e reinstalar os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="81d0e-144">Use this option only if you have previously backed up the data you want to keep and you are able to reinstall your apps.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-8.png)

<span data-ttu-id="81d0e-145">*Opções de instalação do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-145">*Windows 10 Setup installation options*</span></span>

<span data-ttu-id="81d0e-146">Agora, a instalação do Windows 10 receberá as atualizações novamente com base no que você selecionou na tela anterior.</span><span class="sxs-lookup"><span data-stu-id="81d0e-146">Now Windows 10 Setup will get updates again based on what you selected in the previous screen.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-9.png)

<span data-ttu-id="81d0e-147">*Atualizações de configuração do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-147">*Windows 10 Setup getting updates*</span></span>

<span data-ttu-id="81d0e-148">Agora, o Windows 10 será instalado durante vários minutos, e caso você tenha optado por manter seus arquivos pessoais e aplicativos, tudo estará nos mesmos locais de arquivo, e seus aplicativos estarão disponíveis no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81d0e-148">Now Windows 10 will install for several minutes and if you chose to keep your personal files and apps, everything will be in the same file locations and your apps will now be available in Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-10.png)

<span data-ttu-id="81d0e-149">*Progresso da instalação do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-149">*Windows 10 installation progress*</span></span>

## 

## <a name="recovery-in-windows-10"></a><span data-ttu-id="81d0e-150">Recuperação no Windows 10</span><span class="sxs-lookup"><span data-stu-id="81d0e-150">Recovery in Windows 10</span></span>

<span data-ttu-id="81d0e-151">Após a instalação do Windows 10, a opção recuperação no Windows 10 oferecerá até 10 dias para voltar para o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-151">After Windows 10 is installed, the Recovery option in Windows 10 gives you up to 10 days to go back to Windows 7.</span></span> <span data-ttu-id="81d0e-152">Isso é útil se um aplicativo ou dispositivo não funcionar corretamente, e você precisar voltar para a sua instalação anterior do Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-152">This is useful if a device or app on your system does not function properly and you need to go back to your previous Windows 7 installation.</span></span> <span data-ttu-id="81d0e-153">Após 10 dias, por padrão, o Windows 10 liberará o espaço consumido pelos arquivos de recuperação do Windows 7 no disco rígido e excluirá arquivos da instalação anterior.</span><span class="sxs-lookup"><span data-stu-id="81d0e-153">After 10 days, by default Windows 10 will free up the space consumed by your Windows 7 recovery files on your hard drive and delete files from the previous installation.</span></span> <span data-ttu-id="81d0e-154">Embora o Windows 7 seja excluído após esse e você não consiga reverter o Windows 7, seus aplicativos e arquivos pessoais permanecerão no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81d0e-154">Although Windows 7 after this time is deleted and you won’t be able to revert Windows 7, your apps and personal files will remain in Windows 10.</span></span>

<span data-ttu-id="81d0e-155">Para iniciar o processo de voltar para o Windows 7, navegue até as Configurações de Recuperação \>Atualização & Segurança\>.</span><span class="sxs-lookup"><span data-stu-id="81d0e-155">To start the Go back to Windows 7 process, navigate to Settings \> Update & Security \> Recovery.</span></span> <span data-ttu-id="81d0e-156">Em Voltar para o Windows 7, selecione "Introdução".</span><span class="sxs-lookup"><span data-stu-id="81d0e-156">Under Go back to Windows 7, select “Get started.”</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-11.png)

<span data-ttu-id="81d0e-157">*Opções de recuperação do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-157">*Windows 10 Recovery options*</span></span>

<span data-ttu-id="81d0e-158">Agora, o Windows 10 perguntará por que você está voltando.</span><span class="sxs-lookup"><span data-stu-id="81d0e-158">Now, Windows 10 will ask why you are going back.</span></span> <span data-ttu-id="81d0e-159">Se houver um motivo técnico, isso é útil para preencher, a fim de ajudar a impulsionar a resolução e garantir que outras pessoas possam se beneficiar da sua experiência.</span><span class="sxs-lookup"><span data-stu-id="81d0e-159">If there is a technical reason, this is useful to fill out in order to help drive resolution and ensure others can benefit from your experience.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-12.png)

<span data-ttu-id="81d0e-160">*Windows 10 perguntando por que você está voltando para o Windows 7*</span><span class="sxs-lookup"><span data-stu-id="81d0e-160">*Windows 10 asking why you are going back to Windows 7*</span></span>

<span data-ttu-id="81d0e-161">Em muitos casos, a sua versão do Windows 10 terá sido emitida por atualizações, o que pode resolver problemas técnicos.</span><span class="sxs-lookup"><span data-stu-id="81d0e-161">In many cases, your version of Windows 10 will have had updates issued, which may resolve technical issues.</span></span> <span data-ttu-id="81d0e-162">É recomendável verificar se há atualizações e, se encontradas e instaladas, verifique se isso resolve os problemas que você enfrentou.</span><span class="sxs-lookup"><span data-stu-id="81d0e-162">It is encouraged that you check for updates and if found and installed, then check if that fixes the problems you have experienced.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-13.png)

<span data-ttu-id="81d0e-163">*Recuperação de atualizações do Windows 10*</span><span class="sxs-lookup"><span data-stu-id="81d0e-163">*Windows 10 Recovery check for updates*</span></span>

<span data-ttu-id="81d0e-164">Se as atualizações não resolverem os problemas e você precisar reverter para a instalação anterior do Windows 7, há uma chance de alguns aplicativos precisarem ser reinstalados - como qualquer aplicativo instalado durante o período de execução do Windows 10 - e algumas configurações podem ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="81d0e-164">If the updates do not resolve issues and you do need to revert to your previous installation of Windows 7, there is a chance that some apps will need to be reinstalled – such as any app that installed during the time you were running Windows 10 – and some settings may be lost.</span></span> <span data-ttu-id="81d0e-165">É importante saber que os arquivos e os documentos salvos localmente enquanto você usa o Windows 10 permanecem e estarão disponíveis quando você estiver novamente no Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-165">Importantly, files and docs you’ve saved locally while using Windows 10 will remain and be available for you once you’re back in Windows 7.</span></span> 

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-14.png)

<span data-ttu-id="81d0e-166">*Recuperação do Windows 10: o que você precisa saber*</span><span class="sxs-lookup"><span data-stu-id="81d0e-166">*Windows 10 Recovery: What you need to know*</span></span>

<span data-ttu-id="81d0e-167">Antes de começar, certifique-se de que você tenha uma conta de domínio ou local e uma senha prontos para a instalação anterior do Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-167">Before you get started, make sure you have a local or domain account and password ready from the previous Windows 7 installation.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-15.png)

<span data-ttu-id="81d0e-168">*Recuperação do Windows 10 garante que você tenha credenciais de logon da instalação anterior*</span><span class="sxs-lookup"><span data-stu-id="81d0e-168">*Windows 10 Recovery ensuring you have logon credentials from the previous installation*</span></span>

<span data-ttu-id="81d0e-169">A partir daqui, você pode iniciar o processo para voltar para o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81d0e-169">From here you can initiate the process to go back to Windows 7.</span></span> <span data-ttu-id="81d0e-170">Depois de alguns minutos, seu computador será reinicializado no Windows 7 com a mesma experiência anterior à atualização para o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81d0e-170">After a few minutes, your PC will boot back into Windows 7 with the same experience prior to upgrading to Windows 10.</span></span>

![](media/windows-7-to-windows-10-upgrade-media/windows-7-to-windows-10-upgrade-media-16.png)

<span data-ttu-id="81d0e-171">*Tela final de recuperação do Windows 10 para voltar para o Windows 7*</span><span class="sxs-lookup"><span data-stu-id="81d0e-171">*Windows 10 Recovery final screen before going back to Windows 7*</span></span>

## <a name="moving-to-windows-10-on-a-new-pc"></a><span data-ttu-id="81d0e-172">Migrar para o Windows 10 em um novo computador</span><span class="sxs-lookup"><span data-stu-id="81d0e-172">Moving to Windows 10 on a new PC</span></span>

<span data-ttu-id="81d0e-173">Outra opção recomendada é mover para o Windows 10 em um novo computador.</span><span class="sxs-lookup"><span data-stu-id="81d0e-173">Another recommended option is to move to Windows 10 on a new PC.</span></span> <span data-ttu-id="81d0e-174">Se essa for a sua preferência, você pode transferir seus arquivos do computador antigo usando o backup do [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10), o [Backup e a Restauração integrados ao Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), o uso manual de um [dispositivo de armazenamento externo](https://support.microsoft.com/pt-BR/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10) ou ferramentas como o [PCmover Express da Laplink](https://www.microsoft.com/en-us/windows/transfer-your-data).</span><span class="sxs-lookup"><span data-stu-id="81d0e-174">If this is your preference, you can transfer your files from your old computer using [OneDrive](https://support.office.com/article/b5e918be-0fd4-4095-98da-bceed57f8e0c?ocid=MoveToWindows10) backup, [Backup and Restore built into Windows](https://support.microsoft.com/help/4469209?ocid=MoveToWindows10), manually using an [external storage device](https://support.microsoft.com/en-us/help/4465814/windows-7-move-files-off-pc-with-an-external-storage-device?ocid=MoveToWindows10), or tools like [Laplink’s PCmover Express](https://www.microsoft.com/en-us/windows/transfer-your-data).</span></span> <span data-ttu-id="81d0e-175">Com qualquer uma dessas opções, você ainda precisará reinstalar todos os aplicativos necessários que não estão incluídos no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81d0e-175">With any of these options, you will still need to re-install any required applications not included with Windows 10.</span></span> <span data-ttu-id="81d0e-176">Para saber mais sobre as suas opções para mover-se manualmente de um PC existente com Windows 7 para um novo PC com Windows 10, consulte [Movendo para um PC com Windows 10](https://support.microsoft.com/pt-BR/help/4229823?ocid=MoveToWindows10) no Suporte do Windows.</span><span class="sxs-lookup"><span data-stu-id="81d0e-176">To learn more about your options for manually moving from an existing PC running Windows 7 to a new PC with Windows 10, see [Moving to a Windows 10 PC](https://support.microsoft.com/en-us/help/4229823?ocid=MoveToWindows10) in Windows Support.</span></span>

## <a name="desktop-deployment-centerhttpsakamshowtoshift"></a>[<span data-ttu-id="81d0e-177">Centro de Implantação do Computador</span><span class="sxs-lookup"><span data-stu-id="81d0e-177">Desktop Deployment Center</span></span>](https://aka.ms/howtoshift)