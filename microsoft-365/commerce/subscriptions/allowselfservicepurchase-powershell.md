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
ms.custom: ''
search.appverid:
- MET150
description: Saiba como usar o cmdlet do AllowSelfServicePurchase PowerShell para ativar ou desativar a compra de autoatendimento.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6c0bcec70eab4266674ca2a22f1b2054807a26e8
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011670"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usar o AllowSelfServicePurchase para o módulo MSCommerce PowerShell

O módulo **MSCommerce** do PowerShell agora está disponível na [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). O módulo inclui um valor de parâmetro **PolicyId** para o **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento.

Você pode usar o módulo do PowerShell do **MSCommerce** para:

- Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado
- Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo

## <a name="requirements"></a>Requisitos

Para usar o módulo **MSCommerce** do PowerShell, você precisa:

- Um dispositivo Windows 10
- Permissão de administrador para o dispositivo
- Função de administrador global ou de cobrança para seu locatário

## <a name="install-the-mscommerce-powershell-module"></a>Instalar o módulo MSCommerce do PowerShell

Você instala o módulo **MSCommerce** PowerShell no seu dispositivo Windows 10 uma vez e, em seguida, importa para cada sessão do PowerShell iniciada. Baixe o módulo **MSCommerce** PowerShell da [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Para instalar o módulo **MSCommerce** PowerShell com **PowerShellGet**, execute o seguinte comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar MSCommerce para a sessão do PowerShell

Após instalar o módulo no seu dispositivo Windows 10, importe-o para cada sessão do PowerShell iniciada. Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conectar-se ao MSCommerce com suas credenciais

Para conectar-se ao módulo do PowerShell com suas credenciais, execute o seguinte comando.

```powershell
Connect-MSCommerce
```

Este comando conecta a sessão atual do PowerShell a um locatário do Azure Active Directory. O comando solicita um nome de usuário e senha para o locatário ao qual você deseja se conectar. Se a autenticação multifator estiver habilitada para suas credenciais, use a opção interativo para fazer logon.

## <a name="view-details-for-allowselfservicepurchase"></a>Exibir detalhes de AllowSelfServicePurchase

Para exibir uma descrição do valor do parâmetro **AllowSelfServicePurchase** e o status padrão, com base na sua organização, execute o seguinte comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Exibir uma lista de produtos de compra de autoatendimento e seus status

Para exibir uma lista de todos os produtos de compra de autoatendimento disponíveis e o status de cada, execute o seguinte comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

A tabela a seguir lista os produtos disponíveis e seus **ProductID**.

| Produto | ProductId |
|-----------------------------|--------------|
| Aplicativos de energia por usuário | CFQ7TTC0KP0P |
| Automatizar a energia por usuário | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Exibir ou definir o status de AllowSelfServicePurchase

Depois de exibir a lista de produtos disponíveis para compras de autoatendimento, você pode exibir ou modificar a configuração de um produto específico.

Para obter a configuração de política para um produto específico, execute o seguinte comando:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Para habilitar a configuração de política para um produto específico, execute o seguinte comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Para desabilitar a configuração de política de um produto específico, execute o seguinte comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script de exemplo para desabilitar o AllowSelfServicePurchase

O exemplo a seguir descreve como importar o módulo **MSCommerce** , entrar com sua conta, obter o **ProductID** para automatização de energia e, em seguida, desabilitar o **AllowSelfServicePurchase** para o produto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solução de problemas

**Problema**

Você verá a seguinte mensagem de erro:

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

Isso pode ser devido a uma versão mais antiga da Transport Layer Security (TLS). Para conectar este serviço, você precisa usar o TLS 1,2 ou superior

**Solução**

Atualize para TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
