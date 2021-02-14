---
title: Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como usar o cmdlet AllowSelfServicePurchase PowerShell para ativar ou desativar a compra de autoatendente.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653708"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="c4ff5-103">Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ff5-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c4ff5-104">O **módulo MSCommerce** PowerShell agora está disponível na [Galeria do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c4ff5-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="c4ff5-105">O módulo inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendido.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="c4ff5-106">Você pode usar o **módulo MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="c4ff5-107">Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado</span><span class="sxs-lookup"><span data-stu-id="c4ff5-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="c4ff5-108">Exibir uma lista de produtos aplicáveis e se a compra self-service está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="c4ff5-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="c4ff5-109">Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="c4ff5-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="c4ff5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4ff5-110">Requirements</span></span>

<span data-ttu-id="c4ff5-111">Para usar o **módulo MSCommerce** PowerShell, você precisa:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="c4ff5-112">Um dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="c4ff5-112">A Windows 10 device</span></span>
- <span data-ttu-id="c4ff5-113">Permissão de administrador para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4ff5-113">Administrator permission for the device</span></span>
- <span data-ttu-id="c4ff5-114">Função de Administrador Global ou de Cobrança para seu locatário</span><span class="sxs-lookup"><span data-stu-id="c4ff5-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="c4ff5-115">Instalar o módulo MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ff5-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="c4ff5-116">Instale o **módulo MSCommerce** PowerShell em seu dispositivo Windows 10 uma vez e importe-o para cada sessão do PowerShell que iniciar.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="c4ff5-117">Baixe o **módulo MSCommerce** PowerShell da Galeria [do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="c4ff5-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="c4ff5-118">Para instalar o **módulo MSCommerce** PowerShell com **o PowerShellGet,** execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="c4ff5-119">Importar o MSCommerce para a sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ff5-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="c4ff5-120">Depois de instalar o módulo em seu dispositivo Windows 10, importe-o para cada sessão do PowerShell que iniciar.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="c4ff5-121">Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="c4ff5-122">Conectar-se ao MSCommerce com suas credenciais</span><span class="sxs-lookup"><span data-stu-id="c4ff5-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="c4ff5-123">Para se conectar ao módulo do PowerShell com suas credenciais, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="c4ff5-124">Este comando conecta a sessão atual do PowerShell a um locatário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="c4ff5-125">O comando solicita um nome de usuário e uma senha para o locatário ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="c4ff5-126">Se a autenticação multifa factor estiver habilitada para suas credenciais, use a opção interativa para fazer logoff.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="c4ff5-127">Exibir detalhes de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="c4ff5-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c4ff5-128">Para exibir uma descrição do valor do parâmetro **AllowSelfServicePurchase** e do status padrão, com base em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="c4ff5-129">Exibir uma lista de produtos de compra self-service e seu status</span><span class="sxs-lookup"><span data-stu-id="c4ff5-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="c4ff5-130">Para exibir uma lista de todos os produtos de compra self-service disponíveis e o status de cada um deles, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="c4ff5-131">A tabela a seguir lista os produtos disponíveis e seu **ProductId**.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="c4ff5-132">Produto</span><span class="sxs-lookup"><span data-stu-id="c4ff5-132">Product</span></span> | <span data-ttu-id="c4ff5-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="c4ff5-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="c4ff5-134">Power Apps por usuário</span><span class="sxs-lookup"><span data-stu-id="c4ff5-134">Power Apps per user</span></span> | <span data-ttu-id="c4ff5-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="c4ff5-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="c4ff5-136">Power Automate por usuário</span><span class="sxs-lookup"><span data-stu-id="c4ff5-136">Power Automate per user</span></span> | <span data-ttu-id="c4ff5-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="c4ff5-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="c4ff5-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="c4ff5-138">Power BI Pro</span></span> | <span data-ttu-id="c4ff5-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="c4ff5-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="c4ff5-140">Plano de Projeto 1</span><span class="sxs-lookup"><span data-stu-id="c4ff5-140">Project Plan 1</span></span> | <span data-ttu-id="c4ff5-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="c4ff5-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="c4ff5-142">Plano de Projeto 3</span><span class="sxs-lookup"><span data-stu-id="c4ff5-142">Project Plan 3</span></span> | <span data-ttu-id="c4ff5-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="c4ff5-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="c4ff5-144">Plano 1 do Visio</span><span class="sxs-lookup"><span data-stu-id="c4ff5-144">Visio Plan 1</span></span> | <span data-ttu-id="c4ff5-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="c4ff5-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="c4ff5-146">Plano 2 do Visio</span><span class="sxs-lookup"><span data-stu-id="c4ff5-146">Visio Plan 2</span></span> | <span data-ttu-id="c4ff5-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="c4ff5-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="c4ff5-148">Exibir ou definir o status de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="c4ff5-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="c4ff5-149">Depois de exibir a lista de produtos disponíveis para compra self-service, você pode exibir ou modificar a configuração de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="c4ff5-150">Para obter a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="c4ff5-151">Para habilitar a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="c4ff5-152">Para desabilitar a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="c4ff5-153">Exemplo de script para desabilitar AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="c4ff5-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="c4ff5-154">O exemplo a seguir o orienta sobre como importar o módulo **MSCommerce,** entrar com sua conta, obter **a ProductId** para Power Automate e desabilitar **AllowSelfServicePurchase** para esse produto.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="c4ff5-155">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="c4ff5-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="c4ff5-156">Problema</span><span class="sxs-lookup"><span data-stu-id="c4ff5-156">Problem</span></span>

<span data-ttu-id="c4ff5-157">Você vê a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="c4ff5-157">You see the following error message:</span></span>

> <span data-ttu-id="c4ff5-158">HandleError : Falha ao recuperar a política com PolicyId 'AllowSelfServicePurchase', ErrorMessage - A conexão subjacente foi fechada: Ocorreu um erro inesperado em um envio.</span><span class="sxs-lookup"><span data-stu-id="c4ff5-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="c4ff5-159">Isso pode ser devido a uma versão mais antiga do Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="c4ff5-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="c4ff5-160">Para conectar esse serviço, você precisa usar o TLS 1.2 ou superior</span><span class="sxs-lookup"><span data-stu-id="c4ff5-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="c4ff5-161">Solução</span><span class="sxs-lookup"><span data-stu-id="c4ff5-161">Solution</span></span>

<span data-ttu-id="c4ff5-162">Atualize para o TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="c4ff5-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
