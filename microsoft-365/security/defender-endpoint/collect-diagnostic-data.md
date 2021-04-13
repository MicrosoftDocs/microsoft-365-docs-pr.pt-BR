---
title: Coletar dados de diagnóstico do Microsoft Defender Antivírus
description: Usar uma ferramenta para coletar dados para solucionar problemas do Microsoft Defender Antivírus
keywords: solução de problemas, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender av, objeto de política de grupo, configuração, dados de diagnóstico
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689830"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="e4e1c-104">Coletar dados de diagnóstico do Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="e4e1c-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4e1c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4e1c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e4e1c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e4e1c-107">Este artigo descreve como coletar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas que você pode encontrar ao usar o Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="e4e1c-108">Como parte do processo de investigação ou resposta, você pode coletar um pacote de investigação de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="e4e1c-109">Veja como: Coletar o pacote [de investigação de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="e4e1c-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="e4e1c-110">Em pelo menos dois dispositivos que estão enfrentando o mesmo problema, obtenha o arquivo de diagnóstico .cab seguindo as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="e4e1c-111">Abra uma versão no nível de administrador do prompt de comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="e4e1c-112">a.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-112">a.</span></span> <span data-ttu-id="e4e1c-113">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="e4e1c-114">b.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-114">b.</span></span> <span data-ttu-id="e4e1c-115">Digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-115">Type **cmd**.</span></span> <span data-ttu-id="e4e1c-116">Clique com o botão direito do mouse **no Prompt de** Comando e clique em Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="e4e1c-117">c.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-117">c.</span></span> <span data-ttu-id="e4e1c-118">Insira credenciais de administrador ou aprove o prompt.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="e4e1c-119">Navegue até o diretório do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="e4e1c-120">Por padrão, é `C:\Program Files\Windows Defender`</span><span class="sxs-lookup"><span data-stu-id="e4e1c-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="e4e1c-121">Se você estiver executando uma versão atualizada da [Plataforma do Microsoft Defender,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)execute a `MpCmdRun` partir do seguinte local: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="e4e1c-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="e4e1c-122">Digite o seguinte comando e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="e4e1c-123">Um arquivo .cab será gerado que contém vários logs de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="e4e1c-124">O local do arquivo será especificado na saída no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="e4e1c-125">Por padrão, o local é `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="e4e1c-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="e4e1c-126">Para redirecionar o arquivo de cab para um caminho diferente ou compartilhamento UNC, use o seguinte comando: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="e4e1c-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="e4e1c-127">Para obter mais informações, consulte [Redirecionar dados de diagnóstico para um compartilhamento UNC](#redirect-diagnostic-data-to-a-unc-share).</span><span class="sxs-lookup"><span data-stu-id="e4e1c-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="e4e1c-128">Copie esses arquivos .cab para um local que pode ser acessado pelo suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="e4e1c-129">Um exemplo pode ser uma pasta do OneDrive protegida por senha que você pode compartilhar conosco.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="e4e1c-130">Se você tiver um problema com a conformidade de Atualização, envie um email usando o modelo de email de suporte de Conformidade de Atualização <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">e</a>preencha o modelo com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="e4e1c-131">Redirecionar dados de diagnóstico para um compartilhamento UNC</span><span class="sxs-lookup"><span data-stu-id="e4e1c-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="e4e1c-132">Para coletar dados de diagnóstico em um repositório central, você pode especificar o parâmetro SupportLogLocation.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="e4e1c-133">Copia os dados de diagnóstico para o caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="e4e1c-134">Se o caminho não for especificado, os dados de diagnóstico serão copiados para o local especificado na Configuração de Local do Log de Suporte.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="e4e1c-135">Quando o parâmetro SupportLogLocation for usado, uma estrutura de pasta como a seguir será criada no caminho de destino:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="e4e1c-136">campo</span><span class="sxs-lookup"><span data-stu-id="e4e1c-136">field</span></span>  | <span data-ttu-id="e4e1c-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="e4e1c-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="e4e1c-138">caminho</span><span class="sxs-lookup"><span data-stu-id="e4e1c-138">path</span></span> | <span data-ttu-id="e4e1c-139">O caminho conforme especificado na linha de comando ou recuperado da configuração</span><span class="sxs-lookup"><span data-stu-id="e4e1c-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="e4e1c-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="e4e1c-140">MMDD</span></span> | <span data-ttu-id="e4e1c-141">Mês e dia em que os dados de diagnóstico foram coletados (por exemplo, 0530)</span><span class="sxs-lookup"><span data-stu-id="e4e1c-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="e4e1c-142">hostname</span><span class="sxs-lookup"><span data-stu-id="e4e1c-142">hostname</span></span> | <span data-ttu-id="e4e1c-143">O nome do host do dispositivo no qual os dados de diagnóstico foram coletados</span><span class="sxs-lookup"><span data-stu-id="e4e1c-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="e4e1c-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="e4e1c-144">HHMM</span></span> | <span data-ttu-id="e4e1c-145">Horas e minutos quando os dados de diagnóstico foram coletados (por exemplo, 1422)</span><span class="sxs-lookup"><span data-stu-id="e4e1c-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="e4e1c-146">Ao usar um compartilhamento de arquivos, certifique-se de que a conta usada para coletar o pacote de diagnóstico tenha acesso de gravação ao compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="e4e1c-147">Especificar o local onde os dados de diagnóstico são criados</span><span class="sxs-lookup"><span data-stu-id="e4e1c-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="e4e1c-148">Você também pode especificar onde o arquivo .cab de diagnóstico será criado usando um OBJETO de Política de Grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="e4e1c-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="e4e1c-149">Abra o Editor de Política de Grupo Local e encontre o GPO SupportLogLocation em: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="e4e1c-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="e4e1c-150">Selecione **Definir o caminho do diretório para copiar arquivos de log de suporte.**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Captura de tela do editor de política de grupo local](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Captura de tela de definir caminho para configuração de arquivos de log](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="e4e1c-153">Dentro do editor de política, selecione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="e4e1c-154">Especifique o caminho do diretório onde você deseja copiar os arquivos de log de suporte no **campo Opções.**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="e4e1c-155">![Captura de tela da configuração personalizada do caminho do diretório habilitado](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="e4e1c-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="e4e1c-156">Selecione **OK** ou **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4e1c-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4e1c-157">See also</span></span>

- [<span data-ttu-id="e4e1c-158">Solucionar problemas de relatórios do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="e4e1c-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)