---
title: Use AllowSelfServicePurchase para o módulo MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Saiba como usar o cmdlet AllowSelfServicePurchase PowerShell para ativar ou desativar a compra de autoatendiço.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333369"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="b855b-103">Use AllowSelfServicePurchase para o módulo MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="b855b-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="b855b-104">O **módulo MSCommerce** PowerShell agora está disponível na [Galeria do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="b855b-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="b855b-105">O módulo inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendiço.</span><span class="sxs-lookup"><span data-stu-id="b855b-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="b855b-106">Você pode usar o **módulo MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="b855b-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="b855b-107">Exibir o estado padrão do **valor do parâmetro AllowSelfServicePurchase** — quer ele seja habilitado ou desabilitado</span><span class="sxs-lookup"><span data-stu-id="b855b-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="b855b-108">Exibir uma lista de produtos aplicáveis e se a compra de autoatendados está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="b855b-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="b855b-109">Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="b855b-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="b855b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b855b-110">Requirements</span></span>

<span data-ttu-id="b855b-111">Para usar o **módulo MSCommerce** PowerShell, você precisa:</span><span class="sxs-lookup"><span data-stu-id="b855b-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="b855b-112">Um dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="b855b-112">A Windows 10 device</span></span>
- <span data-ttu-id="b855b-113">Permissão de administrador para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="b855b-113">Administrator permission for the device</span></span>
- <span data-ttu-id="b855b-114">Função de administrador global ou cobrança para seu locatário</span><span class="sxs-lookup"><span data-stu-id="b855b-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="b855b-115">Instalar o módulo MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="b855b-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="b855b-116">Instale o **módulo MSCommerce** PowerShell em seu dispositivo Windows 10 uma vez e importe-o para cada sessão do PowerShell que você iniciar.</span><span class="sxs-lookup"><span data-stu-id="b855b-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="b855b-117">Baixe o **módulo MSCommerce** PowerShell da [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="b855b-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="b855b-118">Para instalar o **módulo MSCommerce** PowerShell com **o PowerShellGet,** execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="b855b-119">Importar MSCommerce para a sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b855b-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="b855b-120">Depois de instalar o módulo em seu dispositivo Windows 10, importe-o para cada sessão do PowerShell que você iniciar.</span><span class="sxs-lookup"><span data-stu-id="b855b-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="b855b-121">Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="b855b-122">Conectar-se ao MSCommerce com suas credenciais</span><span class="sxs-lookup"><span data-stu-id="b855b-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="b855b-123">Para se conectar ao módulo do PowerShell com suas credenciais, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="b855b-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="b855b-124">Esse comando conecta a sessão atual do PowerShell a um locatário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b855b-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="b855b-125">O comando solicita um nome de usuário e senha para o locatário ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="b855b-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="b855b-126">Se a autenticação multifative estiver habilitada para suas credenciais, use a opção interativa para fazer logoff.</span><span class="sxs-lookup"><span data-stu-id="b855b-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="b855b-127">Exibir detalhes para AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b855b-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="b855b-128">Para exibir uma descrição **do valor do parâmetro AllowSelfServicePurchase** e do status padrão, com base em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="b855b-129">Exibir uma lista de produtos de compra de autoatendados e seu status</span><span class="sxs-lookup"><span data-stu-id="b855b-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="b855b-130">Para exibir uma lista de todos os produtos de compra de autoatendados disponíveis e o status de cada um, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="b855b-131">A tabela a seguir lista os produtos disponíveis e **seus ProductId**.</span><span class="sxs-lookup"><span data-stu-id="b855b-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="b855b-132">Produto</span><span class="sxs-lookup"><span data-stu-id="b855b-132">Product</span></span> | <span data-ttu-id="b855b-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="b855b-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="b855b-134">Power Apps por usuário</span><span class="sxs-lookup"><span data-stu-id="b855b-134">Power Apps per user</span></span> | <span data-ttu-id="b855b-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="b855b-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="b855b-136">Power Automate por usuário</span><span class="sxs-lookup"><span data-stu-id="b855b-136">Power Automate per user</span></span> | <span data-ttu-id="b855b-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="b855b-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="b855b-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="b855b-138">Power Automate RPA</span></span> | <span data-ttu-id="b855b-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="b855b-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="b855b-140">Power BI Premium (autônomo)</span><span class="sxs-lookup"><span data-stu-id="b855b-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="b855b-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="b855b-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="b855b-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="b855b-142">Power BI Pro</span></span> | <span data-ttu-id="b855b-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="b855b-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="b855b-144">Plano de Projeto 1</span><span class="sxs-lookup"><span data-stu-id="b855b-144">Project Plan 1</span></span> | <span data-ttu-id="b855b-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="b855b-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="b855b-146">Plano de Projeto 3</span><span class="sxs-lookup"><span data-stu-id="b855b-146">Project Plan 3</span></span> | <span data-ttu-id="b855b-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="b855b-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="b855b-148">Plano 1 do Visio</span><span class="sxs-lookup"><span data-stu-id="b855b-148">Visio Plan 1</span></span> | <span data-ttu-id="b855b-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="b855b-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="b855b-150">Plano 2 do Visio</span><span class="sxs-lookup"><span data-stu-id="b855b-150">Visio Plan 2</span></span> | <span data-ttu-id="b855b-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="b855b-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="b855b-152">Exibir ou definir o status de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b855b-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="b855b-153">Depois de exibir a lista de produtos disponíveis para compra de autoatendados, você pode exibir ou modificar a configuração de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="b855b-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="b855b-154">Para obter a configuração de política de um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="b855b-155">Para habilitar a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="b855b-156">Para desabilitar a configuração de política de um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b855b-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="b855b-157">Script de exemplo para desabilitar AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b855b-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="b855b-158">O exemplo a seguir orienta como importar o módulo **MSCommerce,** entrar com sua conta, obter **ProductId** para Power Automate e desabilitar **AllowSelfServicePurchase** para esse produto.</span><span class="sxs-lookup"><span data-stu-id="b855b-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="b855b-159">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b855b-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="b855b-160">Problema</span><span class="sxs-lookup"><span data-stu-id="b855b-160">Problem</span></span>

<span data-ttu-id="b855b-161">Você vê a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="b855b-161">You see the following error message:</span></span>

> <span data-ttu-id="b855b-162">HandleError : Falha ao recuperar a política com PolicyId 'AllowSelfServicePurchase', ErrorMessage - A conexão subjacente foi fechada: ocorreu um erro inesperado em um envio.</span><span class="sxs-lookup"><span data-stu-id="b855b-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="b855b-163">Isso pode ser devido a uma versão mais antiga do TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="b855b-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="b855b-164">Para conectar esse serviço, você precisa usar o TLS 1.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="b855b-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="b855b-165">Solução</span><span class="sxs-lookup"><span data-stu-id="b855b-165">Solution</span></span>

<span data-ttu-id="b855b-166">Atualize para o TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="b855b-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
