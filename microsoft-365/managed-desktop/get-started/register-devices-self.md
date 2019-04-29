---
title: Registrar dispositivos no Microsoft Managed desktop sozinho
description: Registre os dispositivos de modo que eles possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400061"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="ca00a-103">Registrar dispositivos na área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca00a-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="ca00a-104">Este tópico descreve as etapas para você registrar dispositivos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="ca00a-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="ca00a-105">O processo para parceiros está documentado em [registrar dispositivos no Microsoft Managed desktop para parceiros](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="ca00a-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="ca00a-106">A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente).</span><span class="sxs-lookup"><span data-stu-id="ca00a-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="ca00a-107">Você pode registrar dispositivos usando a área de trabalho gerenciada da Microsoft no portal do Azure ou ganhar flexibilidade usando uma API.</span><span class="sxs-lookup"><span data-stu-id="ca00a-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="ca00a-108">Preparar para registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="ca00a-108">Prepare to register devices</span></span>

<span data-ttu-id="ca00a-109">Se você ainda não tiver obtido os dispositivos que deseja usar, verifique os [dispositivos de área de trabalho gerenciaDa da Microsoft](../service-description/device-list.md) e trabalhe com um parceiro de dispositivo para adquirir dispositivos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="ca00a-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="ca00a-110">Se você estiver trabalhando com dispositivos totalmente novos ou reutilizar os existentes, para registrá-los com a área de trabalho gerenciada da Microsoft, será necessário preparar um **arquivo separado por vírgula (CSV)**.</span><span class="sxs-lookup"><span data-stu-id="ca00a-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="ca00a-111">Esse arquivo deve incluir as seguintes informações para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="ca00a-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="ca00a-112">Este formato é somente para registro de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="ca00a-112">This format is for self-service registration only.</span></span> <span data-ttu-id="ca00a-113">O formato que os parceiros devem usar está documentado em [registrar dispositivos no Microsoft Managed desktop para parceiros](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="ca00a-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="ca00a-114">Esses valores são usados para fins de exibição e não precisam corresponder as propriedades do dispositivo exatamente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="ca00a-115">Fabricante do dispositivo (exemplo: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="ca00a-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="ca00a-116">Modelo de dispositivo (exemplo: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="ca00a-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="ca00a-117">Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca00a-117">Device serial number</span></span>

<span data-ttu-id="ca00a-118">O hash de hardware deve ser uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="ca00a-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="ca00a-119">Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="ca00a-119">Hardware hash</span></span>

<span data-ttu-id="ca00a-120">Para obter o hash de hardware, você pode solicitar ajuda do seu OEM ou parceiro ou seguir estas etapas para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="ca00a-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="ca00a-121">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ca00a-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="ca00a-122">Sejam`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="ca00a-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="ca00a-123">Sejam`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ca00a-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="ca00a-124">Como alternativa, você pode seguir estas etapas em um dispositivo novo (antes de passar pelo OOBE pela primeira vez):</span><span class="sxs-lookup"><span data-stu-id="ca00a-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="ca00a-125">Em um dispositivo diferente, insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="ca00a-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="ca00a-126">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ca00a-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="ca00a-127">Sejam`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="ca00a-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="ca00a-128">Ative o dispositivo de destino, mas não inicie a experiência de instalação.</span><span class="sxs-lookup"><span data-stu-id="ca00a-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="ca00a-129">Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca00a-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="ca00a-130">Insira a unidade USB e, em seguida, pressione SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="ca00a-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="ca00a-131">Abra um prompt do PowerShell com direitos administrativos e, em `cd <pathToUsb>`seguida, execute.</span><span class="sxs-lookup"><span data-stu-id="ca00a-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="ca00a-132">Sejam`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="ca00a-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="ca00a-133">Sejam`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ca00a-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="ca00a-134">Remova a unidade USB e desligue o dispositivo executando`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="ca00a-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="ca00a-135">Não ligue o dispositivo de destino novamente até concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="ca00a-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="ca00a-136">Para sua conveniência, é possível baixar um [modelo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para esse arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ca00a-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="ca00a-137">O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas.</span><span class="sxs-lookup"><span data-stu-id="ca00a-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="ca00a-138">Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo.</span><span class="sxs-lookup"><span data-stu-id="ca00a-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="ca00a-139">Se você esquecer de alterar qualquer um dos dados de exemplo, o registro falhará.</span><span class="sxs-lookup"><span data-stu-id="ca00a-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="ca00a-140">Registrar dispositivos usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="ca00a-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="ca00a-141">No [portal do Azure](https://aka.ms/mmdportal)de área de trabalho gerenciaDa da Microsoft, selecione **dispositivos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ca00a-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="ca00a-142">Selecione **+ registrar dispositivos**; o funcionamento é aberto:</span><span class="sxs-lookup"><span data-stu-id="ca00a-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="ca00a-143">[![Surgir após selecionar registrar dispositivos](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="ca00a-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Infelizmente, isso não é verdadeiro. Podemos remover esta anotação, mas deixá-la agora até que haja uma oportunidade de conversar sobre ela.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="ca00a-145">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ca00a-145">Follow these steps:</span></span>

1. <span data-ttu-id="ca00a-146">Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="ca00a-147">Opcionalmente, você pode adicionar uma ID de **pedido** ou de **compra** para seus próprios fins de controle.</span><span class="sxs-lookup"><span data-stu-id="ca00a-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="ca00a-148">Não há requisitos de formato para esses valores.</span><span class="sxs-lookup"><span data-stu-id="ca00a-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="ca00a-149">Selecione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ca00a-149">Select **Register devices**.</span></span> <span data-ttu-id="ca00a-150">O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**.</span><span class="sxs-lookup"><span data-stu-id="ca00a-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="ca00a-151">O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário final comece a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="ca00a-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="ca00a-152">Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="ca00a-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="ca00a-153">Os Estados possíveis relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="ca00a-153">Possible states reported there include:</span></span>

| <span data-ttu-id="ca00a-154">Estado</span><span class="sxs-lookup"><span data-stu-id="ca00a-154">State</span></span> | <span data-ttu-id="ca00a-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca00a-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="ca00a-156">Registro pendente</span><span class="sxs-lookup"><span data-stu-id="ca00a-156">Registration pending</span></span> | <span data-ttu-id="ca00a-157">O registro ainda não foi feito.</span><span class="sxs-lookup"><span data-stu-id="ca00a-157">Registration is not done yet.</span></span> <span data-ttu-id="ca00a-158">Verifique novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="ca00a-158">Check back later.</span></span> |
| <span data-ttu-id="ca00a-159">Falha no registro</span><span class="sxs-lookup"><span data-stu-id="ca00a-159">Registration failed</span></span> | <span data-ttu-id="ca00a-160">Não foi possível concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="ca00a-160">Registration could not be completed.</span></span> <span data-ttu-id="ca00a-161">Consulte [solução de problemas](register-devices-self.md#troubleshooting) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca00a-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="ca00a-162">Pronto para o usuário</span><span class="sxs-lookup"><span data-stu-id="ca00a-162">Ready for user</span></span> | <span data-ttu-id="ca00a-163">O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="ca00a-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="ca00a-164">A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos.</span><span class="sxs-lookup"><span data-stu-id="ca00a-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="ca00a-165">Ativo</span><span class="sxs-lookup"><span data-stu-id="ca00a-165">Active</span></span> | <span data-ttu-id="ca00a-166">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ca00a-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="ca00a-167">Isso também indica que eles estão usando o dispositivo regularmente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="ca00a-168">Inativa</span><span class="sxs-lookup"><span data-stu-id="ca00a-168">Inactive</span></span> | <span data-ttu-id="ca00a-169">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ca00a-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="ca00a-170">No enTanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).</span><span class="sxs-lookup"><span data-stu-id="ca00a-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="ca00a-171">Registrar dispositivos usando uma API</span><span class="sxs-lookup"><span data-stu-id="ca00a-171">Register devices by using an API</span></span>

<span data-ttu-id="ca00a-172">Uma API REST está disponível para permitir maior flexibilidade e repetição com registros de dispositivo separados frequentes.</span><span class="sxs-lookup"><span data-stu-id="ca00a-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="ca00a-173">Atualmente, para usar a API, peça ajuda ao seu contato da Microsoft para participar de uma prévia desse recurso.</span><span class="sxs-lookup"><span data-stu-id="ca00a-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="ca00a-174">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="ca00a-174">Troubleshooting</span></span>

| <span data-ttu-id="ca00a-175">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="ca00a-175">Error message</span></span> | <span data-ttu-id="ca00a-176">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ca00a-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="ca00a-177">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="ca00a-177">Device not found</span></span> | <span data-ttu-id="ca00a-178">Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido.</span><span class="sxs-lookup"><span data-stu-id="ca00a-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="ca00a-179">Confirme esses valores com seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ca00a-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="ca00a-180">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="ca00a-180">Device not found</span></span> | <span data-ttu-id="ca00a-181">Não foi possível cancelar o registro deste dispositivo porque ele não existe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ca00a-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="ca00a-182">Nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="ca00a-182">No further action required.</span></span> |
| <span data-ttu-id="ca00a-183">Hash de hardware inválido</span><span class="sxs-lookup"><span data-stu-id="ca00a-183">Hardware hash not valid</span></span> | <span data-ttu-id="ca00a-184">O hash de hardware fornecido para este dispositivo não foi formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="ca00a-185">Verifique novamente o hash de hardware e envie novamente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="ca00a-186">Dispositivo já registrado</span><span class="sxs-lookup"><span data-stu-id="ca00a-186">Device already registered</span></span> | <span data-ttu-id="ca00a-187">Este dispositivo já está registrado na sua organização.</span><span class="sxs-lookup"><span data-stu-id="ca00a-187">This device is already registered to your organization.</span></span> <span data-ttu-id="ca00a-188">Nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="ca00a-188">No further action required.</span></span> |
| <span data-ttu-id="ca00a-189">Dispositivo solicitado por outra organização</span><span class="sxs-lookup"><span data-stu-id="ca00a-189">Device claimed by another organization</span></span> | <span data-ttu-id="ca00a-190">Este dispositivo já foi reivindicado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="ca00a-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="ca00a-191">Consulte seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ca00a-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="ca00a-192">Erro inesperado</span><span class="sxs-lookup"><span data-stu-id="ca00a-192">Unexpected error</span></span> | <span data-ttu-id="ca00a-193">Sua solicitação não pôde ser processada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ca00a-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="ca00a-194">Entre em contato com o suporte e forneça a ID da solicitação:<requestId></span><span class="sxs-lookup"><span data-stu-id="ca00a-194">Contact Support and provide the Request ID: <requestId></span></span> |




