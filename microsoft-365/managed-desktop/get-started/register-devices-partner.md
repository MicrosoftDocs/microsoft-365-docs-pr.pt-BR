---
title: Etapas para registrar dispositivos de parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445585"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="436af-104">Etapas para registrar dispositivos de parceiros</span><span class="sxs-lookup"><span data-stu-id="436af-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="436af-105">Este tópico descreve as etapas para parceiros seguirem para registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="436af-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="436af-106">O processo de registro de dispositivos por conta própria está documentado em [Registrar dispositivos na Área de Trabalho Gerenciada da Microsoft.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="436af-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="436af-107">Preparar para registro</span><span class="sxs-lookup"><span data-stu-id="436af-107">Prepare for registration</span></span> 
<span data-ttu-id="436af-108">Antes de concluir o registro de um cliente, você deve primeiro estabelecer um relacionamento com ele no [Partner Center](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="436af-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="436af-109">Consulte a [documentação de consentimento](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obter mais detalhes sobre esse processo.</span><span class="sxs-lookup"><span data-stu-id="436af-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="436af-110">Qualquer parceiro CSP pode adicionar dispositivos em nome de qualquer cliente, desde que o cliente consenta.</span><span class="sxs-lookup"><span data-stu-id="436af-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="436af-111">Você também pode saber mais sobre as relações de parceiros e permissões do Piloto Automático na ajuda [do Partner Center.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="436af-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="436af-112">Esta documentação é somente para Parceiros e OEMs.</span><span class="sxs-lookup"><span data-stu-id="436af-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="436af-113">O processo de auto-registro é documentado em [Registrar dispositivos na Área de Trabalho Gerenciada da Microsoft.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="436af-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="436af-114">Registrar dispositivos usando o Partner Center</span><span class="sxs-lookup"><span data-stu-id="436af-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="436af-115">Depois de estabelecer o relacionamento com seus clientes, você pode aproveitar o Partner Center para adicionar dispositivos ao Autopilot para qualquer um dos clientes com os que você tem uma relação seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="436af-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="436af-116">Navegue até [o Partner Center](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="436af-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="436af-117">Selecione **Clientes** no menu Partner Center e selecione o cliente cujos dispositivos você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="436af-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="436af-118">Na página de detalhes do cliente, selecione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="436af-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="436af-119">Em **Aplicar perfis** a dispositivos, selecione **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="436af-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="436af-120">Insira **Microsoft365Managed_Autopilot** nome do grupo e selecione **Procurar** para carregar a lista do cliente (no formato de arquivo .csv) para o Partner Center.</span><span class="sxs-lookup"><span data-stu-id="436af-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="436af-121">O Nome do Grupo deve corresponder **Microsoft365Managed_Autopilot,** incluindo maiúsculas e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="436af-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="436af-122">Isso permitirá que os dispositivos recém-registrados sejam atribuídos ao perfil do Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="436af-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="436af-123">Você deve ter recebido esse arquivo .csv com a compra do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="436af-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="436af-124">Se você não recebeu um arquivo .csv, pode criar um sozinho seguindo as etapas em Adicionar dispositivos [ao Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="436af-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="436af-125">O Windows PowerShell script é diferente do usado para o portal de Administração da [Área de Trabalho Gerenciada da Microsoft.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="436af-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="436af-126">Os parceiros devem usar [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para registrar dispositivos para dispositivos da Área de Trabalho Gerenciada da Microsoft no Partner Center.</span><span class="sxs-lookup"><span data-stu-id="436af-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="436af-127">Se você receber uma mensagem de erro ao tentar carregar o arquivo .csv, verifique o formato do arquivo.</span><span class="sxs-lookup"><span data-stu-id="436af-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="436af-128">Certifique-se de que a ordem de coluna corresponde ao descrito em Use Windows Autopilot profiles in new devices to customize [a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span><span class="sxs-lookup"><span data-stu-id="436af-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="436af-129">Você também pode usar o arquivo .csv de exemplo fornecido no link ao lado de **Adicionar dispositivos** para criar uma lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="436af-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="436af-130">Para obter mais informações sobre o Autopilot em cenários de parceiros, consulte [Adicionar dispositivos à conta de um cliente](/partner-center/autopilot#add-devices-to-a-customers-account).</span><span class="sxs-lookup"><span data-stu-id="436af-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="436af-131">Registrar dispositivos usando a API OEM</span><span class="sxs-lookup"><span data-stu-id="436af-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="436af-132">Antes de concluir o registro de um cliente, você deve primeiro estabelecer um relacionamento com ele.</span><span class="sxs-lookup"><span data-stu-id="436af-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="436af-133">Você deve ter um link exclusivo para fornecer aos seus respectivos clientes.</span><span class="sxs-lookup"><span data-stu-id="436af-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="436af-134">Consulte [Como estabelecer relação OEM](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span><span class="sxs-lookup"><span data-stu-id="436af-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="436af-135">Depois de estabelecer a relação, você pode começar a registrar dispositivos para clientes usando a marca de **grupo Microsoft365Managed_Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="436af-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="436af-136">O nome do grupo deve corresponder **Microsoft365Managed_Autopilot,** incluindo maiúsculas e caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="436af-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="436af-137">Isso permitirá que os dispositivos recém-registrados sejam atribuídos ao perfil do Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="436af-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>