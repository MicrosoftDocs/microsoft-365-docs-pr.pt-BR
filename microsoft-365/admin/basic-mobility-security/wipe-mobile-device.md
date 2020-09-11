---
title: Apagar um dispositivo móvel em mobilidade básica e segurança
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Usar mobilidade básica e segurança interna para remover informações de dispositivos registrados.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429945"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="64b63-103">Apagar um dispositivo móvel em mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="64b63-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="64b63-104">Você pode usar a mobilidade básica e a segurança interna do Microsoft 365 para remover apenas as informações organizacionais ou executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-las às configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="64b63-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="64b63-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="64b63-105">Before you begin</span></span>

<span data-ttu-id="64b63-106">Os dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos do Microsoft 365 da sua organização.</span><span class="sxs-lookup"><span data-stu-id="64b63-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="64b63-107">Para ajudar a proteger as informações da sua organização, você pode reconfigurar fábrica ou remover dados da empresa:</span><span class="sxs-lookup"><span data-stu-id="64b63-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="64b63-108">**Redefinição de fábrica**: exclui todos os dados do dispositivo móvel de um usuário, incluindo aplicativos instalados, Fotos e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="64b63-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="64b63-109">Quando o apagamento é concluído, o dispositivo é restaurado para suas configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="64b63-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="64b63-110">**Remover dados da empresa**: remove apenas os dados da organização e deixa aplicativos instalados, Fotos e informações pessoais no dispositivo móvel de um usuário.</span><span class="sxs-lookup"><span data-stu-id="64b63-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="64b63-111">**Quando um dispositivo é apagado (reinicialização de fábrica ou remover dados da empresa)**, o dispositivo é removido da lista de dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="64b63-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="64b63-112">**Redefinir automaticamente um dispositivo**: você pode configurar uma política de segurança e mobilidade básica que redefine automaticamente um dispositivo depois que o usuário tenta inserir a senha do dispositivo por um número específico de vezes.</span><span class="sxs-lookup"><span data-stu-id="64b63-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="64b63-113">Para fazer isso, siga as etapas em [criar políticas de segurança de dispositivo em mobilidade básica e segurança](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64b63-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="64b63-114">**Se você quiser saber a experiência do usuário** ao apagar o dispositivo, confira o  [que é o impacto do usuário e do dispositivo?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="64b63-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="64b63-115">Apagar um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="64b63-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="64b63-116">Vá para o [centro de administração do Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="64b63-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="64b63-117">Digite gerenciamento de dispositivo móvel no campo de pesquisa e selecione **Gerenciamento de dispositivo móvel** na lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="64b63-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Mobilidade básica e opção de gerenciamento de dispositivo móvel do secruity":::

3. <span data-ttu-id="64b63-119">Selecione **gerenciar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="64b63-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="64b63-120">Selecione o dispositivo que deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="64b63-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="64b63-121">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="64b63-121">Select **Manage**.</span></span>

6. <span data-ttu-id="64b63-122">Selecione o tipo de apagamento remoto que deseja executar.</span><span class="sxs-lookup"><span data-stu-id="64b63-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="64b63-123">Para fazer um apagamento completo e restaurar o dispositivo para suas configurações de fábrica, selecione **redefinição de fábrica**.</span><span class="sxs-lookup"><span data-stu-id="64b63-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="64b63-124">Para fazer uma limpeza seletiva e excluir apenas as informações da organização 365 da Microsoft, selecione **remover dados da empresa**.</span><span class="sxs-lookup"><span data-stu-id="64b63-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="64b63-125">Para remover o dispositivo da sua organização, selecione **remover dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="64b63-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="64b63-126">Selecione **Sim** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="64b63-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="64b63-127">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="64b63-127">How do I know it worked?</span></span>

<span data-ttu-id="64b63-128">Você não vê mais o dispositivo móvel na lista de dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="64b63-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="64b63-129">Por que você gostaria de apagar um dispositivo?</span><span class="sxs-lookup"><span data-stu-id="64b63-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="64b63-130">Limpe um dispositivo por estes motivos:</span><span class="sxs-lookup"><span data-stu-id="64b63-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="64b63-131">Dispositivos móveis como smartphones e tablets estão ficando mais repletos de tempo todo.</span><span class="sxs-lookup"><span data-stu-id="64b63-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="64b63-132">Isso significa que é mais fácil para os usuários armazenarem informações confidenciais corporativas, como a identificação pessoal ou comunicações confidenciais e o acesso em trânsito.</span><span class="sxs-lookup"><span data-stu-id="64b63-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="64b63-133">Se um desses dispositivos móveis for perdido ou roubado, a limpeza do dispositivo poderá ajudar a impedir que as informações da sua organização sejam terminadas nas mãos erradas.</span><span class="sxs-lookup"><span data-stu-id="64b63-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="64b63-134">Quando um usuário deixa a organização com um dispositivo pessoal que está inscrito em mobilidade básica e segurança, você pode ajudar a evitar que as informações organizacionais entrem em um usuário executando uma redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="64b63-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="64b63-135">Se sua organização fornece dispositivos móveis aos usuários, talvez seja necessário reatribuir dispositivos de tempos em tempos.</span><span class="sxs-lookup"><span data-stu-id="64b63-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="64b63-136">Fazer uma redefinição de fábrica em um dispositivo antes de atribuí-lo a um novo usuário ajuda a garantir que qualquer informação confidencial do proprietário anterior seja excluída.</span><span class="sxs-lookup"><span data-stu-id="64b63-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="64b63-137">Qual é o impacto do usuário e do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="64b63-137">What's the user and device impact?</span></span>

<span data-ttu-id="64b63-138">O apagamento é enviado imediatamente para o dispositivo móvel e o dispositivo é marcado como não compatível no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64b63-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="64b63-139">Embora todos os dados sejam removidos quando um dispositivo é redefinido para os padrões de fábrica, a tabela a seguir descreve qual conteúdo é removido para cada tipo de dispositivo quando um dispositivo é removido quando você remove os dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="64b63-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="64b63-140">**Ritmo do conteúdo**</span><span class="sxs-lookup"><span data-stu-id="64b63-140">**Content impace**</span></span>|<span data-ttu-id="64b63-141">**iOS 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="64b63-141">**iOS 10 and later**</span></span>|<span data-ttu-id="64b63-142">**Android 5 e posterior**</span><span class="sxs-lookup"><span data-stu-id="64b63-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64b63-143">Os dados do aplicativo Microsoft 365 serão apagados se o dispositivo estiver protegido pelas políticas de proteção de aplicativos do Intune.</span><span class="sxs-lookup"><span data-stu-id="64b63-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="64b63-144">Os aplicativos não são removidos.</span><span class="sxs-lookup"><span data-stu-id="64b63-144">The apps aren't removed.</span></span> <span data-ttu-id="64b63-145">Para dispositivos não protegidos por políticas de gerenciamento de aplicativo móvel (MAM), o Outlook e o OneDrive não removerão os dados armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="64b63-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="64b63-146">**Observação** Para aplicar as políticas de proteção de aplicativos do Intune, você deve ter uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="64b63-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="64b63-147">Sim</span><span class="sxs-lookup"><span data-stu-id="64b63-147">Yes</span></span>|<span data-ttu-id="64b63-148">Sim</span><span class="sxs-lookup"><span data-stu-id="64b63-148">Yes</span></span>|
|<span data-ttu-id="64b63-149">As configurações de política aplicadas pela mobilidade básica e segurança para dispositivos não são mais impostas; os usuários podem alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="64b63-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="64b63-150">Sim</span><span class="sxs-lookup"><span data-stu-id="64b63-150">Yes</span></span>|<span data-ttu-id="64b63-151">Sim</span><span class="sxs-lookup"><span data-stu-id="64b63-151">Yes</span></span>|
|<span data-ttu-id="64b63-152">Os perfis de email criados pela mobilidade básica e segurança são removidos e o email em cache no dispositivo é excluído.</span><span class="sxs-lookup"><span data-stu-id="64b63-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="64b63-153">Sim</span><span class="sxs-lookup"><span data-stu-id="64b63-153">Yes</span></span>|<span data-ttu-id="64b63-154">N/D</span><span class="sxs-lookup"><span data-stu-id="64b63-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="64b63-155">O aplicativo do portal da empresa está disponível na App Store para iOS e no repositório de reprodução para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="64b63-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64b63-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="64b63-156">Related topics</span></span>

[<span data-ttu-id="64b63-157">Configurar a Mobilidade Básica e a Segurança</span><span class="sxs-lookup"><span data-stu-id="64b63-157">Set up Basic Mobility and Security</span></span>](set-up.md)