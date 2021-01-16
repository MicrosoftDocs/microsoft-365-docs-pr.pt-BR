---
title: Apagar um dispositivo móvel no Basic Mobility and Security
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
description: Use o Basic Mobility and Security integrado para remover informações de dispositivos inscritos.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876823"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="81af9-103">Apagar um dispositivo móvel no Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="81af9-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="81af9-104">Você pode usar o Basic Mobility and Security integrado para o Microsoft 365 para remover apenas informações organizacionais ou para executar uma redefinição de fábrica para excluir todas as informações de um dispositivo móvel e restaurá-la para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="81af9-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="81af9-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="81af9-105">Before you begin</span></span>

<span data-ttu-id="81af9-106">Os dispositivos móveis podem armazenar informações organizacionais confidenciais e fornecer acesso aos recursos do Microsoft 365 da sua organização.</span><span class="sxs-lookup"><span data-stu-id="81af9-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="81af9-107">Para ajudar a proteger as informações da sua organização, você pode fazer a redefinição de fábrica ou remover dados da empresa:</span><span class="sxs-lookup"><span data-stu-id="81af9-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="81af9-108">**Redefinição de** fábrica: exclui todos os dados no dispositivo móvel de um usuário, incluindo aplicativos instalados, fotos e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="81af9-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="81af9-109">Quando a limpeza for concluída, o dispositivo será restaurado para suas configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="81af9-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="81af9-110">**Remover dados da** empresa: remove somente os dados da organização e deixa aplicativos, fotos e informações pessoais instalados no dispositivo móvel de um usuário.</span><span class="sxs-lookup"><span data-stu-id="81af9-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="81af9-111">**Quando um dispositivo é apagado (redefinição** de fábrica ou remover dados da empresa), o dispositivo é removido da lista de dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="81af9-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="81af9-112">**Redefinir** automaticamente um dispositivo: você pode configurar uma política básica de mobilidade e segurança que redefine automaticamente um dispositivo de fábrica depois que o usuário tenta inserir a senha do dispositivo várias vezes.</span><span class="sxs-lookup"><span data-stu-id="81af9-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="81af9-113">Para fazer isso, siga as etapas em [Criar políticas de segurança de dispositivos em mobilidade e segurança básicas.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="81af9-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="81af9-114">**Se você quiser saber a experiência do usuário** ao apagar o dispositivo, veja O que é o impacto do usuário e do   [dispositivo?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="81af9-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="81af9-115">Apagar um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="81af9-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="81af9-116">Vá para o [Centro de administração do Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="81af9-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="81af9-117">Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione Gerenciamento de Dispositivo **Móvel** na lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="81af9-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel Basic Mobility e Secruity":::

3. <span data-ttu-id="81af9-119">Selecione **Gerenciar dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="81af9-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="81af9-120">Selecione o dispositivo que deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="81af9-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="81af9-121">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="81af9-121">Select **Manage**.</span></span>

6. <span data-ttu-id="81af9-122">Selecione o tipo de apagamento remoto que deseja executar.</span><span class="sxs-lookup"><span data-stu-id="81af9-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="81af9-123">Para fazer uma limpeza completa e restaurar o dispositivo para suas configurações de fábrica, selecione **Redefinição de fábrica.**</span><span class="sxs-lookup"><span data-stu-id="81af9-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="81af9-124">Para fazer uma limpeza seletiva e excluir apenas informações da organização do Microsoft 365, selecione **Remover dados da empresa.**</span><span class="sxs-lookup"><span data-stu-id="81af9-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="81af9-125">Para remover o dispositivo da sua organização, selecione **Remover dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="81af9-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="81af9-126">Selecione **Sim** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="81af9-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="81af9-127">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="81af9-127">How do I know it worked?</span></span>

<span data-ttu-id="81af9-128">Você não verá mais o dispositivo móvel na lista de dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="81af9-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="81af9-129">Por que você deseja apagar um dispositivo?</span><span class="sxs-lookup"><span data-stu-id="81af9-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="81af9-130">Limpe um dispositivo por estes motivos:</span><span class="sxs-lookup"><span data-stu-id="81af9-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="81af9-131">Dispositivos móveis, como smartphones e tablets, estão se tornando mais completos o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="81af9-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="81af9-132">Isso significa que é mais fácil para os usuários armazenar informações corporativas confidenciais, como identificação pessoal ou comunicações confidenciais, e acessá-la em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="81af9-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="81af9-133">Se um desses dispositivos móveis for perdido ou roubado, apagar o dispositivo pode ajudar a impedir que as informações da sua organização acabarem em mãos erradas.</span><span class="sxs-lookup"><span data-stu-id="81af9-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="81af9-134">Quando um usuário deixa a organização com um dispositivo pessoal que está inscrito no Basic Mobility and Security, você pode ajudar a impedir que as informações organizacionais vão com esse usuário executando uma redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="81af9-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="81af9-135">Se sua organização fornece dispositivos móveis aos usuários, talvez seja necessário reatribuir dispositivos de tempos em tempos.</span><span class="sxs-lookup"><span data-stu-id="81af9-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="81af9-136">Fazer uma redefinição de fábrica em um dispositivo antes de atribuí-la a um novo usuário ajuda a garantir que qualquer informação sensível do proprietário anterior seja excluída.</span><span class="sxs-lookup"><span data-stu-id="81af9-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="81af9-137">Qual é o impacto do usuário e do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="81af9-137">What's the user and device impact?</span></span>

<span data-ttu-id="81af9-138">O apagamento é enviado imediatamente para o dispositivo móvel e o dispositivo é marcado como não compatível no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81af9-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="81af9-139">Embora todos os dados são removidos quando um dispositivo é redefinido para os padrões de fábrica, a tabela a seguir descreve qual conteúdo é removido para cada tipo de dispositivo quando um dispositivo é removido.</span><span class="sxs-lookup"><span data-stu-id="81af9-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="81af9-140">**Impace de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="81af9-140">**Content impace**</span></span>|<span data-ttu-id="81af9-141">**iOS 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="81af9-141">**iOS 10 and later**</span></span>|<span data-ttu-id="81af9-142">**Android 5 e posterior**</span><span class="sxs-lookup"><span data-stu-id="81af9-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="81af9-143">Os dados de aplicativo do Microsoft 365 serão apagados se o dispositivo estiver protegido pelas políticas de Proteção de Aplicativos do Intune.</span><span class="sxs-lookup"><span data-stu-id="81af9-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="81af9-144">Os aplicativos não são removidos.</span><span class="sxs-lookup"><span data-stu-id="81af9-144">The apps aren't removed.</span></span> <span data-ttu-id="81af9-145">Para dispositivos não protegidos por políticas de Gerenciamento de Aplicativo Móvel (MAM), o Outlook e o OneDrive não removerão dados armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="81af9-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="81af9-146">**Observação** Para aplicar políticas de proteção de aplicativos do Intune, você deve ter uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="81af9-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="81af9-147">Sim</span><span class="sxs-lookup"><span data-stu-id="81af9-147">Yes</span></span>|<span data-ttu-id="81af9-148">Sim</span><span class="sxs-lookup"><span data-stu-id="81af9-148">Yes</span></span>|
|<span data-ttu-id="81af9-149">As configurações de política aplicadas pela Mobilidade Básica e Segurança aos dispositivos não são mais impostas; os usuários podem alterar as configurações.</span><span class="sxs-lookup"><span data-stu-id="81af9-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="81af9-150">Sim</span><span class="sxs-lookup"><span data-stu-id="81af9-150">Yes</span></span>|<span data-ttu-id="81af9-151">Sim</span><span class="sxs-lookup"><span data-stu-id="81af9-151">Yes</span></span>|
|<span data-ttu-id="81af9-152">Os perfis de email criados pela Mobilidade Básica e Segurança são removidos e o email armazenado em cache no dispositivo é excluído.</span><span class="sxs-lookup"><span data-stu-id="81af9-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="81af9-153">Sim</span><span class="sxs-lookup"><span data-stu-id="81af9-153">Yes</span></span>|<span data-ttu-id="81af9-154">N/D</span><span class="sxs-lookup"><span data-stu-id="81af9-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="81af9-155">O aplicativo portal da empresa está disponível na App Store para iOS e na Play Store para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="81af9-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81af9-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="81af9-156">Related topics</span></span>

[<span data-ttu-id="81af9-157">Configurar a Mobilidade Básica e a Segurança</span><span class="sxs-lookup"><span data-stu-id="81af9-157">Set up Basic Mobility and Security</span></span>](set-up.md)