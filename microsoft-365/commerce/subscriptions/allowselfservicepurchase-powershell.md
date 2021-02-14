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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell

O **módulo MSCommerce** PowerShell agora está disponível na [Galeria do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery) O módulo inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendido.

Você pode usar o **módulo MSCommerce** PowerShell para:

- Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado
- Exibir uma lista de produtos aplicáveis e se a compra self-service está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo

## <a name="requirements"></a>Requisitos

Para usar o **módulo MSCommerce** PowerShell, você precisa:

- Um dispositivo Windows 10
- Permissão de administrador para o dispositivo
- Função de Administrador Global ou de Cobrança para seu locatário

## <a name="install-the-mscommerce-powershell-module"></a>Instalar o módulo MSCommerce PowerShell

Instale o **módulo MSCommerce** PowerShell em seu dispositivo Windows 10 uma vez e importe-o para cada sessão do PowerShell que iniciar. Baixe o **módulo MSCommerce** PowerShell da Galeria [do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Para instalar o **módulo MSCommerce** PowerShell com **o PowerShellGet,** execute o seguinte comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar o MSCommerce para a sessão do PowerShell

Depois de instalar o módulo em seu dispositivo Windows 10, importe-o para cada sessão do PowerShell que iniciar. Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conectar-se ao MSCommerce com suas credenciais

Para se conectar ao módulo do PowerShell com suas credenciais, execute o seguinte comando.

```powershell
Connect-MSCommerce
```

Este comando conecta a sessão atual do PowerShell a um locatário do Azure Active Directory. O comando solicita um nome de usuário e uma senha para o locatário ao qual você deseja se conectar. Se a autenticação multifa factor estiver habilitada para suas credenciais, use a opção interativa para fazer logoff.

## <a name="view-details-for-allowselfservicepurchase"></a>Exibir detalhes de AllowSelfServicePurchase

Para exibir uma descrição do valor do parâmetro **AllowSelfServicePurchase** e do status padrão, com base em sua organização, execute o seguinte comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Exibir uma lista de produtos de compra self-service e seu status

Para exibir uma lista de todos os produtos de compra self-service disponíveis e o status de cada um deles, execute o seguinte comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

A tabela a seguir lista os produtos disponíveis e seu **ProductId**.

| Produto | ProductId |
|-----------------------------|--------------|
| Power Apps por usuário | CFQ7TTC0KP0P |
| Power Automate por usuário | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Plano de Projeto 1 | CFQ7TTC0KXND |
| Plano de Projeto 3 | CFQ7TTC0KXNC |
| Plano 1 do Visio | CFQ7TTC0KXN9 |
| Plano 2 do Visio | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Exibir ou definir o status de AllowSelfServicePurchase

Depois de exibir a lista de produtos disponíveis para compra self-service, você pode exibir ou modificar a configuração de um produto específico.

Para obter a configuração de política para um produto específico, execute o seguinte comando:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Para habilitar a configuração de política para um produto específico, execute o seguinte comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Para desabilitar a configuração de política para um produto específico, execute o seguinte comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Exemplo de script para desabilitar AllowSelfServicePurchase

O exemplo a seguir o orienta sobre como importar o módulo **MSCommerce,** entrar com sua conta, obter **a ProductId** para Power Automate e desabilitar **AllowSelfServicePurchase** para esse produto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solução de problemas

### <a name="problem"></a>Problema

Você vê a seguinte mensagem de erro:

> HandleError : Falha ao recuperar a política com PolicyId 'AllowSelfServicePurchase', ErrorMessage - A conexão subjacente foi fechada: Ocorreu um erro inesperado em um envio.

Isso pode ser devido a uma versão mais antiga do Transport Layer Security (TLS). Para conectar esse serviço, você precisa usar o TLS 1.2 ou superior

### <a name="solution"></a>Solução

Atualize para o TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
