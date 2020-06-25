---
title: Configurar recursos de criptografia de nova mensagem
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Aprenda sobre os novos recursos de criptografia das mensagens do Office 365 que permitem a comunicação protegida por e-mail com pessoas dentro e fora da organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d6e37da7456cfbb0b7cbf8d986b54615aca60f0
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819181"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="9b724-103">Configurar recursos de criptografia de nova mensagem</span><span class="sxs-lookup"><span data-stu-id="9b724-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="9b724-104">Os novos recursos de criptografia de mensagens do Office 365 (OME) permitem que as organizações compartilhem emails protegidos com qualquer pessoa em qualquer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b724-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="9b724-105">Os usuários podem trocar mensagens protegidas com outras organizações do Microsoft 365, bem como os não clientes que usam Outlook.com, Gmail e outros serviços de email.</span><span class="sxs-lookup"><span data-stu-id="9b724-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="9b724-106">Siga as etapas abaixo para garantir que os novos recursos do OME estejam disponíveis na sua organização.</span><span class="sxs-lookup"><span data-stu-id="9b724-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="9b724-107">Verifique se o Azure Rights Management está ativo</span><span class="sxs-lookup"><span data-stu-id="9b724-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="9b724-108">Os novos recursos da OME aproveitam os recursos de proteção no[Azure RMS (Azure Rights Management Services)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), e a tecnologia usada pela[Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) para proteger emails e documentos por meio de controles de criptografia e acesso.</span><span class="sxs-lookup"><span data-stu-id="9b724-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="9b724-109">O único pré-requisito para usar os novos recursos de OME que o [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) deve ser ativado no locatário da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9b724-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="9b724-110">Caso esteja, o Microsoft 365 ativa automaticamente os novos recursos de OME e você não precisa fazer nada.</span><span class="sxs-lookup"><span data-stu-id="9b724-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="9b724-111">O Azure RMS também é ativado automaticamente para a maioria dos planos qualificados, portanto, provavelmente você não precise fazer nada.</span><span class="sxs-lookup"><span data-stu-id="9b724-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="9b724-112">Para saber mais confira [Ativar o Gerenciamento de Direitos do Azure](https://docs.microsoft.com/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="9b724-112">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9b724-113">Se você usa o AD RMS (Active Directory Rights Management Services) com o Exchange Online, [é preciso migrar para a Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) antes de poder usar os novos recursos do OME.</span><span class="sxs-lookup"><span data-stu-id="9b724-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="9b724-114">OME não é compatível com AD RMS.</span><span class="sxs-lookup"><span data-stu-id="9b724-114">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="9b724-115">Para saber mais, veja:</span><span class="sxs-lookup"><span data-stu-id="9b724-115">For more information, see:</span></span>

- <span data-ttu-id="9b724-116">[Quais assinaturas eu preciso para usar os novos recursos do OME? ](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para verificar se o seu plano de assinatura inclui a proteção de informações do Azure (que inclui a funcionalidade do Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="9b724-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="9b724-117">[Proteção de Informações do Azure](https://azure.microsoft.com/services/information-protection/) para saber mais sobre como adquirir uma assinatura qualificada.</span><span class="sxs-lookup"><span data-stu-id="9b724-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="9b724-118">Ativar manualmente o Gerenciamento de Direitos do Azure</span><span class="sxs-lookup"><span data-stu-id="9b724-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="9b724-119">Se você tiver desabilitado o Azure RMS, ou se ele não tiver sido ativado automaticamente por algum motivo, você poderá ativá-lo manualmente no:</span><span class="sxs-lookup"><span data-stu-id="9b724-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="9b724-120">**Centro de administração do Microsoft 365** Confira [: Como ativar o Azure Rights Management no centro de administração](https://docs.microsoft.com/azure/information-protection/activate-office365) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="9b724-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="9b724-121">**Portal do Azure**: [Confira como ativar o Azure Rights Management no portal do Azure](https://docs.microsoft.com/azure/information-protection/activate-azure) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="9b724-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="9b724-122">Configurar o gerenciamento de sua chave do locatário de proteção de informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9b724-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="9b724-123">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="9b724-123">This is an optional step.</span></span> <span data-ttu-id="9b724-124">Permitir que a Microsoft gerencie a chave raiz da proteção de informações do Azure é a configuração padrão e a melhor prática recomendada para a maioria das organizações.</span><span class="sxs-lookup"><span data-stu-id="9b724-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="9b724-125">Se esse for o caso, você não precisa fazer nada.</span><span class="sxs-lookup"><span data-stu-id="9b724-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="9b724-126">Há muitos motivos, por exemplo, os requisitos de conformidade, que podem exigir a geração e o gerenciamento de sua própria chave raiz (também conhecida como (BYOK)).</span><span class="sxs-lookup"><span data-stu-id="9b724-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="9b724-127">Se esse for o caso, recomendamos que você conclua as etapas necessárias antes de configurar os novos recursos do OME.</span><span class="sxs-lookup"><span data-stu-id="9b724-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="9b724-128">Confira o artigo [Como planejar e implementar a chave locatário de proteção de informações do Azure](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9b724-128">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="9b724-129">Verificar a nova configuração do OME no PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9b724-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="9b724-130">Você pode verificar se o locatário do Microsoft 365 está configurado corretamente para usar os novos recursos do OME no[Exchange Online do PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="9b724-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="9b724-131">[Conecte-se ao Exchange Online do PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando uma conta com permissões de administrador global em seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b724-131">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="9b724-132">Execute o cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b724-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="9b724-133">Você deverá ver um valor de $True para o parâmetro AzureRMSLicensingEnabled, que indica que o OME está configurado em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9b724-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="9b724-134">Caso contrário, use Set-IRMConfiguration para definir o valor de AzureRMSLicensingEnabled como $True para habilitar o OME.</span><span class="sxs-lookup"><span data-stu-id="9b724-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="9b724-135">Execute o cmdlet Test-IRMConfiguration usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b724-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="9b724-136">**Exemplo**:</span><span class="sxs-lookup"><span data-stu-id="9b724-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="9b724-137">Fornecer um email de remetente é opcional, mas força o sistema a executar verificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="9b724-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="9b724-138">Use o endereço de email de qualquer usuário em seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b724-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="9b724-139">Seus resultados devem ser semelhantes a:</span><span class="sxs-lookup"><span data-stu-id="9b724-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="9b724-140">O nome da sua organização substituirá *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="9b724-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="9b724-141">Os nomes dos modelos padrão podem ser diferentes daqueles exibidos acima.</span><span class="sxs-lookup"><span data-stu-id="9b724-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="9b724-142">Confira [Configurando e Gerenciando modelos para a proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9b724-142">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="9b724-143">Execute o cmdlet Remove-PSSession para se desconectar do serviço de gerenciamento de direitos.</span><span class="sxs-lookup"><span data-stu-id="9b724-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="9b724-144">Próximas etapas: definir regras de fluxo de emails para usar novos recursos do OME</span><span class="sxs-lookup"><span data-stu-id="9b724-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="9b724-145">Se houver regras de fluxo de email configuradas anteriormente para criptografar emails na sua organização, você precisará atualizar as regras existentes para usar os novos recursos do OME.</span><span class="sxs-lookup"><span data-stu-id="9b724-145">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="9b724-146">Para novas implantações, você precisa criar novas regras de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="9b724-146">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9b724-147">Se você não atualizar as regras de fluxo de email existentes, os usuários continuarão a receber emails criptografados que usam o formato de anexo HTML anterior, em vez da nova experiência contínua do OME.</span><span class="sxs-lookup"><span data-stu-id="9b724-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="9b724-148">As regras de fluxo de email determinam em quais condições as mensagens de email devem ser criptografadas, bem como as condições para a remoção dessa criptografia.</span><span class="sxs-lookup"><span data-stu-id="9b724-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="9b724-149">Quando você define uma ação para uma regra, todas as mensagens que correspondem às condições da regra são criptografadas quando são enviadas.</span><span class="sxs-lookup"><span data-stu-id="9b724-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="9b724-150">Para ver as etapas sobre como criar regras de fluxo, confira [Definir regras de fluxo de e-mail para criptografar mensagens de e-mail no Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="9b724-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="9b724-151">Para atualizar regras existentes para usar os novos recursos do OME:</span><span class="sxs-lookup"><span data-stu-id="9b724-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="9b724-152">No Centro de administração do Microsoft 365, selecione **Centros de administração > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="9b724-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="9b724-153">No Centro de administração do Exchange, acesse **Fluxo de email > Regras**.</span><span class="sxs-lookup"><span data-stu-id="9b724-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="9b724-154">Para cada regra, no \*\* siga este procedimento\*\*:</span><span class="sxs-lookup"><span data-stu-id="9b724-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="9b724-155">Selecione **Modificar a segurança de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="9b724-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="9b724-156">Selecione **Aplicar a Criptografia e os Direitos de Mensagem do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="9b724-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="9b724-157">Selecione um modelo RMS na lista.</span><span class="sxs-lookup"><span data-stu-id="9b724-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="9b724-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9b724-158">Select **Save**.</span></span>
    - <span data-ttu-id="9b724-159">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b724-159">Select **OK**.</span></span>
