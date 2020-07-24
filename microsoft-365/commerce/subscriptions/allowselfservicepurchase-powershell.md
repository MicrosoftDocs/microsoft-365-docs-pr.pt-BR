---
title: Usar o AllowSelfServicePurchase para o módulo MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como usar o cmdlet do AllowSelfServicePurchase PowerShell para ativar ou desativar a compra de autoatendimento.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b35b62a97f8dc269be5db232e163391a8ce50658
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391537"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="7a587-103">Usar o AllowSelfServicePurchase para o módulo MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a587-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="7a587-104">O módulo **MSCommerce** do PowerShell agora está disponível na [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="7a587-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="7a587-105">O módulo inclui um valor de parâmetro **PolicyId** para o **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="7a587-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="7a587-106">Você pode usar o módulo do PowerShell do **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="7a587-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="7a587-107">Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado</span><span class="sxs-lookup"><span data-stu-id="7a587-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="7a587-108">Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="7a587-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="7a587-109">Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="7a587-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="7a587-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a587-110">Requirements</span></span>

<span data-ttu-id="7a587-111">Para usar o módulo **MSCommerce** do PowerShell, você precisa:</span><span class="sxs-lookup"><span data-stu-id="7a587-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="7a587-112">Um dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="7a587-112">A Windows 10 device</span></span>
- <span data-ttu-id="7a587-113">Permissão de administrador para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="7a587-113">Administrator permission for the device</span></span>
- <span data-ttu-id="7a587-114">Função de administrador global ou de cobrança para seu locatário</span><span class="sxs-lookup"><span data-stu-id="7a587-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="7a587-115">Instalar o módulo MSCommerce do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a587-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="7a587-116">Você instala o módulo **MSCommerce** PowerShell no seu dispositivo Windows 10 uma vez e, em seguida, importa para cada sessão do PowerShell iniciada.</span><span class="sxs-lookup"><span data-stu-id="7a587-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="7a587-117">Baixe o módulo **MSCommerce** PowerShell da [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="7a587-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="7a587-118">Para instalar o módulo **MSCommerce** PowerShell com **PowerShellGet**, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="7a587-119">Importar MSCommerce para a sessão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a587-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="7a587-120">Após instalar o módulo no seu dispositivo Windows 10, importe-o para cada sessão do PowerShell iniciada.</span><span class="sxs-lookup"><span data-stu-id="7a587-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="7a587-121">Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="7a587-122">Conectar-se ao MSCommerce com suas credenciais</span><span class="sxs-lookup"><span data-stu-id="7a587-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="7a587-123">Para conectar-se ao módulo do PowerShell com suas credenciais, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="7a587-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="7a587-124">Este comando conecta a sessão atual do PowerShell a um locatário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7a587-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="7a587-125">O comando solicita um nome de usuário e senha para o locatário ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="7a587-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="7a587-126">Se a autenticação multifator estiver habilitada para suas credenciais, use a opção interativo para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="7a587-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="7a587-127">Exibir detalhes de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="7a587-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="7a587-128">Para exibir uma descrição do valor do parâmetro **AllowSelfServicePurchase** e o status padrão, com base na sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="7a587-129">Exibir uma lista de produtos de compra de autoatendimento e seus status</span><span class="sxs-lookup"><span data-stu-id="7a587-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="7a587-130">Para exibir uma lista de todos os produtos de compra de autoatendimento disponíveis e o status de cada, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="7a587-131">A tabela a seguir lista os produtos disponíveis e seus **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="7a587-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="7a587-132">Produto</span><span class="sxs-lookup"><span data-stu-id="7a587-132">Product</span></span> | <span data-ttu-id="7a587-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="7a587-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="7a587-134">Aplicativos de energia por usuário</span><span class="sxs-lookup"><span data-stu-id="7a587-134">Power Apps per user</span></span> | <span data-ttu-id="7a587-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="7a587-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="7a587-136">Automatizar a energia por usuário</span><span class="sxs-lookup"><span data-stu-id="7a587-136">Power Automate per user</span></span> | <span data-ttu-id="7a587-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="7a587-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="7a587-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="7a587-138">Power BI Pro</span></span> | <span data-ttu-id="7a587-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="7a587-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="7a587-140">Exibir ou definir o status de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="7a587-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="7a587-141">Depois de exibir a lista de produtos disponíveis para compras de autoatendimento, você pode exibir ou modificar a configuração de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="7a587-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="7a587-142">Para obter a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="7a587-143">Para habilitar a configuração de política para um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="7a587-144">Para desabilitar a configuração de política de um produto específico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a587-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="7a587-145">Script de exemplo para desabilitar o AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="7a587-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="7a587-146">O exemplo a seguir descreve como importar o módulo **MSCommerce** , entrar com sua conta, obter o **ProductID** para automatização de energia e, em seguida, desabilitar o **AllowSelfServicePurchase** para o produto.</span><span class="sxs-lookup"><span data-stu-id="7a587-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="7a587-147">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="7a587-147">Troubleshooting</span></span>

<span data-ttu-id="7a587-148">**Problema**</span><span class="sxs-lookup"><span data-stu-id="7a587-148">**Problem**</span></span>

<span data-ttu-id="7a587-149">Você verá a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="7a587-149">You see the following error message:</span></span>

> <span data-ttu-id="7a587-150">HandleError: falha ao recuperar política com PolicyId ' AllowSelfServicePurchase ', ErrorMessage-a conexão subjacente foi fechada: ocorreu um erro inesperado em um envio.</span><span class="sxs-lookup"><span data-stu-id="7a587-150">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="7a587-151">Isso pode ser devido a uma versão mais antiga da Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="7a587-151">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="7a587-152">Para conectar este serviço, você precisa usar o TLS 1,2 ou superior</span><span class="sxs-lookup"><span data-stu-id="7a587-152">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="7a587-153">**Solução**</span><span class="sxs-lookup"><span data-stu-id="7a587-153">**Solution**</span></span>

<span data-ttu-id="7a587-154">Atualize para TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="7a587-154">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
