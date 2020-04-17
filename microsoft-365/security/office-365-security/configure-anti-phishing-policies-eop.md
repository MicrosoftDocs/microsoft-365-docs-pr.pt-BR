---
title: Configurar a política anti-phishing padrão no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a modificar as configurações antifalsificação disponíveis na política anti-phishing padrão nas organizações do Office 365 com caixas de correio do Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537528"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="24ad0-103">Configurar a política anti-phishing padrão no EOP</span><span class="sxs-lookup"><span data-stu-id="24ad0-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="24ad0-104">As organizações do Office 365 com caixas de correio do Exchange Online e do proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online têm uma política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="24ad0-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="24ad0-105">Esta política contém um número limitado de recursos anti-falsificação habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="24ad0-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="24ad0-106">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="24ad0-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="24ad0-107">As organizações do Office 365 com caixas de correio do Exchange Online podem modificar a política anti-phishing padrão no centro de conformidade & segurança do Office 365 ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="24ad0-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="24ad0-108">As organizações autônomas do EOP sem caixas de correio do Exchange Online não podem modificar a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="24ad0-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="24ad0-109">Para obter informações sobre como criar e modificar as políticas de anti-phishing mais avançadas da ATP que estão disponíveis na proteção avançada contra ameaças do Office 365, consulte [Configure ATP anti-phishing Policies in office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="24ad0-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="24ad0-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="24ad0-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="24ad0-111">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="24ad0-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="24ad0-112">Para ir diretamente para a página **anti-phishing** , use <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="24ad0-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="24ad0-113">Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="24ad0-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="24ad0-114">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="24ad0-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="24ad0-115">Para adicionar, modificar e excluir políticas anti-phishing, você precisa ser membro dos grupos de função de gerenciamento da **organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="24ad0-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="24ad0-116">Para acesso somente leitura às políticas anti-phishing, você precisa ser membro do grupo de função **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="24ad0-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="24ad0-117">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de conformidade e Segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="24ad0-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="24ad0-118">Para nossas configurações recomendadas para a política anti-phishing padrão, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="24ad0-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="24ad0-119">Aguarde até 30 minutos para que a política atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="24ad0-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="24ad0-120">Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email no Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="24ad0-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="24ad0-121">Usar o centro de conformidade de & de segurança para modificar a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="24ad0-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="24ad0-122">A política anti-phishing padrão é chamada de padrão do Office365 antiphish e não aparece na lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="24ad0-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="24ad0-123">Para modificar a política anti-phishing padrão, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="24ad0-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="24ad0-124">No centro de conformidade & segurança, vá para **anti-phishing**de **política** \> de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="24ad0-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="24ad0-125">Na página **anti-phishing** , clique em **política padrão**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="24ad0-126">A página **editar sua política padrão do Office365 antiphishing** é exibida.</span><span class="sxs-lookup"><span data-stu-id="24ad0-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="24ad0-127">Na seção **spoof** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="24ad0-128">Observe que essas configurações são idênticas às configurações de spoof que estão disponíveis nas políticas anti-phishing do ATP.</span><span class="sxs-lookup"><span data-stu-id="24ad0-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="24ad0-129">**Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado.</span><span class="sxs-lookup"><span data-stu-id="24ad0-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="24ad0-130">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="24ad0-131">Para obter mais informações, consulte [Configure spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="24ad0-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="24ad0-132">Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Office 365; em vez disso, habilite a filtragem avançada de conectores.</span><span class="sxs-lookup"><span data-stu-id="24ad0-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="24ad0-133">Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="24ad0-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="24ad0-134">**Habilitar o recurso de remetente não autenticado**: Adiciona um ponto de interrogação à foto do remetente se a mensagem falhar nas verificações de autenticação de email.</span><span class="sxs-lookup"><span data-stu-id="24ad0-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="24ad0-135">Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="24ad0-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="24ad0-136">O valor padrão é **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-136">The default value is **On**.</span></span> <span data-ttu-id="24ad0-137">Para desativá-la, deslize o botão de alternância para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="24ad0-138">**Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:</span><span class="sxs-lookup"><span data-stu-id="24ad0-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="24ad0-139">**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:</span><span class="sxs-lookup"><span data-stu-id="24ad0-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="24ad0-140">**Mover mensagem para as pastas de lixo eletrônico dos destinatários** (esse é o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="24ad0-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="24ad0-141">**Colocar a mensagem em quarentena**</span><span class="sxs-lookup"><span data-stu-id="24ad0-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="24ad0-142">**Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.</span><span class="sxs-lookup"><span data-stu-id="24ad0-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="24ad0-143">Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.</span><span class="sxs-lookup"><span data-stu-id="24ad0-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="24ad0-144">Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:</span><span class="sxs-lookup"><span data-stu-id="24ad0-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="24ad0-145">**Habilitar proteção contra falsificação**</span><span class="sxs-lookup"><span data-stu-id="24ad0-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="24ad0-146">**Habilitar o recurso de remetente não autenticado**</span><span class="sxs-lookup"><span data-stu-id="24ad0-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="24ad0-147">Quando tiver terminado, clique em **salvar** em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="24ad0-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="24ad0-148">Novamente na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="24ad0-149">Usar o centro de conformidade de & de segurança para exibir a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="24ad0-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="24ad0-150">No centro de conformidade & segurança e vá para **política** \> de **Gerenciamento** \> de ameaças de anti-phishing do **ATP**.</span><span class="sxs-lookup"><span data-stu-id="24ad0-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="24ad0-151">Clique em **política padrão** para exibir a política anti-phishing padrão.</span><span class="sxs-lookup"><span data-stu-id="24ad0-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="24ad0-152">Usar o PowerShell do Exchange Online para configurar a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="24ad0-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="24ad0-153">Usar o PowerShell para exibir a política anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="24ad0-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="24ad0-154">Para exibir a política anti-phishing padrão, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="24ad0-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="24ad0-155">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="24ad0-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="24ad0-156">Usar o PowerShell para modificar a política de anti-phishing padrão</span><span class="sxs-lookup"><span data-stu-id="24ad0-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="24ad0-157">Para modificar a política anti-phishing padrão, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="24ad0-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="24ad0-158">Este exemplo altera a ação para mensagens falsificadas que falham verificações de autenticação para quarentena.</span><span class="sxs-lookup"><span data-stu-id="24ad0-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="24ad0-159">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="24ad0-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="24ad0-160">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="24ad0-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="24ad0-161">Para verificar se você configurou com êxito a política anti-phishing padrão, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="24ad0-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="24ad0-162">No centro de conformidade & segurança, vá para **Threat management** \> **política** \> de gerenciamento de ameaças **anti-phishing** \> clique em **política padrão** e exiba os detalhes no submenu.</span><span class="sxs-lookup"><span data-stu-id="24ad0-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="24ad0-163">No PowerShell do Exchange Online, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="24ad0-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
