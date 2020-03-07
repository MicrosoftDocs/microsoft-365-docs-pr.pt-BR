---
title: Etapas para registrar dispositivos de parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557559"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="290b1-103">Etapas para registrar dispositivos de parceiros</span><span class="sxs-lookup"><span data-stu-id="290b1-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="290b1-104">Este tópico descreve as etapas dos parceiros a serem seguidas para registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290b1-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="290b1-105">O processo de registro de seus próprios dispositivos está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="290b1-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="290b1-106">Preparar para o registro</span><span class="sxs-lookup"><span data-stu-id="290b1-106">Prepare for registration</span></span> 
<span data-ttu-id="290b1-107">Antes de concluir o registro de um cliente, primeiro você deve estabelecer uma relação com eles no [Partner Center](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="290b1-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="290b1-108">Certifique-se de selecionar **incluir privilégios de administração delegada para o Azure Active Directory e o Office 365**.</span><span class="sxs-lookup"><span data-stu-id="290b1-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="290b1-109">Saiba mais na [ajuda da central de parceiros](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="290b1-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="290b1-110">Para concluir o registro do cliente, primeiro crie um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="290b1-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="290b1-111">Para sua conveniência, você pode baixar um [arquivo CSV de exemplo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) para esta *versão do parceiro*.</span><span class="sxs-lookup"><span data-stu-id="290b1-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) for this *Partner version*.</span></span>

<span data-ttu-id="290b1-112">O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas.</span><span class="sxs-lookup"><span data-stu-id="290b1-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="290b1-113">Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo.</span><span class="sxs-lookup"><span data-stu-id="290b1-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="290b1-114">Este formato é somente para o processo de parceiro.</span><span class="sxs-lookup"><span data-stu-id="290b1-114">This format is only for the Partner process.</span></span> <span data-ttu-id="290b1-115">O processo de auto-registro está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="290b1-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="290b1-116">Esses valores devem corresponder exatamente aos valores do fabricante do SMBIOS, incluindo o uso de maiúsculas e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="290b1-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="290b1-117">Fabricante do dispositivo (exemplo: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="290b1-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="290b1-118">Modelo de dispositivo (exemplo: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="290b1-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="290b1-119">Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="290b1-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="290b1-120">Registrar dispositivos usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="290b1-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="290b1-121">O registro usando o portal do Azure é o mesmo que o de autoatendimento, exceto pelo fato de você acessar o portal de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="290b1-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="290b1-122">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="290b1-122">Follow these steps:</span></span>

1. <span data-ttu-id="290b1-123">Navegue até a [central de parceiros](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="290b1-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="290b1-124">Selecione **clientes**.</span><span class="sxs-lookup"><span data-stu-id="290b1-124">Select **Customers**.</span></span>
3. <span data-ttu-id="290b1-125">Selecione o cliente que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="290b1-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="290b1-126">Selecione **Administração de serviço**.</span><span class="sxs-lookup"><span data-stu-id="290b1-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="290b1-127">Selecione o **Intune**.</span><span class="sxs-lookup"><span data-stu-id="290b1-127">Select **Intune**.</span></span>
6. <span data-ttu-id="290b1-128">Procure "MMD" na caixa de pesquisa superior do portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="290b1-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="290b1-129">Selecione **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="290b1-129">Select **Devices**.</span></span>
8. <span data-ttu-id="290b1-130">Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="290b1-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="290b1-131">Opcionalmente, você pode adicionar uma ID de **pedido** ou de **compra** para seus próprios fins de controle.</span><span class="sxs-lookup"><span data-stu-id="290b1-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="290b1-132">Não há requisitos de formato para esses valores.</span><span class="sxs-lookup"><span data-stu-id="290b1-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="290b1-133">Selecione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="290b1-133">Select **Register devices**.</span></span> <span data-ttu-id="290b1-134">O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**.</span><span class="sxs-lookup"><span data-stu-id="290b1-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="290b1-135">O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário final comece a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="290b1-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="290b1-136">Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="290b1-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="290b1-137">Os Estados possíveis relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="290b1-137">Possible states reported there include:</span></span>

| <span data-ttu-id="290b1-138">Estado</span><span class="sxs-lookup"><span data-stu-id="290b1-138">State</span></span> | <span data-ttu-id="290b1-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="290b1-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="290b1-140">Registro pendente</span><span class="sxs-lookup"><span data-stu-id="290b1-140">Registration pending</span></span> | <span data-ttu-id="290b1-141">O registro ainda não foi feito.</span><span class="sxs-lookup"><span data-stu-id="290b1-141">Registration is not done yet.</span></span> <span data-ttu-id="290b1-142">Verifique novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="290b1-142">Check back later.</span></span> |
| <span data-ttu-id="290b1-143">Falha no registro</span><span class="sxs-lookup"><span data-stu-id="290b1-143">Registration failed</span></span> | <span data-ttu-id="290b1-144">Não foi possível concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="290b1-144">Registration could not be completed.</span></span> <span data-ttu-id="290b1-145">Consulte [Solucionando problemas de registro de dispositivo](register-devices-self.md#troubleshooting-device-registration) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="290b1-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="290b1-146">Pronto para o usuário</span><span class="sxs-lookup"><span data-stu-id="290b1-146">Ready for user</span></span> | <span data-ttu-id="290b1-147">O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="290b1-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="290b1-148">A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos.</span><span class="sxs-lookup"><span data-stu-id="290b1-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="290b1-149">Ativo</span><span class="sxs-lookup"><span data-stu-id="290b1-149">Active</span></span> | <span data-ttu-id="290b1-150">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="290b1-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="290b1-151">Isso também indica que eles estão usando o dispositivo regularmente.</span><span class="sxs-lookup"><span data-stu-id="290b1-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="290b1-152">Inativa</span><span class="sxs-lookup"><span data-stu-id="290b1-152">Inactive</span></span> | <span data-ttu-id="290b1-153">O dispositivo foi entregue ao usuário final e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="290b1-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="290b1-154">No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).</span><span class="sxs-lookup"><span data-stu-id="290b1-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="290b1-155">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="290b1-155">Troubleshooting</span></span>

| <span data-ttu-id="290b1-156">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="290b1-156">Error message</span></span> | <span data-ttu-id="290b1-157">Detalhes</span><span class="sxs-lookup"><span data-stu-id="290b1-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="290b1-158">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="290b1-158">Device not found</span></span> | <span data-ttu-id="290b1-159">Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido.</span><span class="sxs-lookup"><span data-stu-id="290b1-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="290b1-160">Confirme esses valores com seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290b1-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="290b1-161">Hash de hardware inválido</span><span class="sxs-lookup"><span data-stu-id="290b1-161">Hardware hash not valid</span></span> | <span data-ttu-id="290b1-162">O hash de hardware fornecido para este dispositivo não foi formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="290b1-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="290b1-163">Verifique novamente o hash de hardware e envie novamente.</span><span class="sxs-lookup"><span data-stu-id="290b1-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="290b1-164">Dispositivo já registrado</span><span class="sxs-lookup"><span data-stu-id="290b1-164">Device already registered</span></span> | <span data-ttu-id="290b1-165">Este dispositivo já está registrado na sua organização.</span><span class="sxs-lookup"><span data-stu-id="290b1-165">This device is already registered to your organization.</span></span> <span data-ttu-id="290b1-166">Nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="290b1-166">No further action required.</span></span> |
| <span data-ttu-id="290b1-167">Dispositivo solicitado por outra organização</span><span class="sxs-lookup"><span data-stu-id="290b1-167">Device claimed by another organization</span></span> | <span data-ttu-id="290b1-168">Este dispositivo já foi reivindicado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="290b1-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="290b1-169">Consulte seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290b1-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="290b1-170">Erro inesperado</span><span class="sxs-lookup"><span data-stu-id="290b1-170">Unexpected error</span></span> | <span data-ttu-id="290b1-171">Sua solicitação não pôde ser processada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="290b1-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="290b1-172">Entre em contato<support link>com o suporte () e forneça a ID da solicitação:<requestId></span><span class="sxs-lookup"><span data-stu-id="290b1-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
