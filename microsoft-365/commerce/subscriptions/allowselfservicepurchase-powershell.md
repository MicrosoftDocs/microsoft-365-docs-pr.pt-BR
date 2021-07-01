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
ms.openlocfilehash: fbba7f4385684a8a34f9feebc28a27e8e867bacb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227470"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Use AllowSelfServicePurchase para o módulo MSCommerce PowerShell

O **módulo MSCommerce** PowerShell agora está disponível na [Galeria do PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery) O módulo inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendiço.

Você pode usar o **módulo MSCommerce** PowerShell para:

- Exibir o estado padrão do **valor do parâmetro AllowSelfServicePurchase** — quer ele seja habilitado ou desabilitado
- Exibir uma lista de produtos aplicáveis e se a compra de autoatendados está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo

## <a name="requirements"></a>Requisitos

Para usar o **módulo MSCommerce** PowerShell, você precisa:

- Um Windows 10 de segurança
- PowerShell 5 ou abaixo. Atualmente, o PowerShell 6.x/7.x não tem suporte com esse módulo.
- Permissão de administrador para o dispositivo
- Função de administrador global ou cobrança para seu locatário

## <a name="install-the-mscommerce-powershell-module"></a>Instalar o módulo MSCommerce PowerShell

Você instala o **módulo MSCommerce** PowerShell em seu dispositivo Windows 10 uma vez e, em seguida, importa-o para cada sessão do PowerShell que você iniciar. Baixe o **módulo MSCommerce** PowerShell da [Galeria do PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Para instalar o **módulo MSCommerce** PowerShell com **o PowerShellGet,** execute o seguinte comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar MSCommerce para a sessão do PowerShell

Depois de instalar o módulo em seu Windows 10, importe-o para cada sessão do PowerShell que você iniciar. Para importá-lo para uma sessão do PowerShell, execute o seguinte comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conexão para MSCommerce com suas credenciais

Para se conectar ao módulo do PowerShell com suas credenciais, execute o seguinte comando.

```powershell
Connect-MSCommerce
```

Este comando conecta a sessão atual do PowerShell a um Azure Active Directory locatário. O comando solicita um nome de usuário e senha para o locatário ao qual você deseja se conectar. Se a autenticação multifative estiver habilitada para suas credenciais, use a opção interativa para fazer logoff.

## <a name="view-details-for-allowselfservicepurchase"></a>Exibir detalhes para AllowSelfServicePurchase

Para exibir uma descrição **do valor do parâmetro AllowSelfServicePurchase** e do status padrão, com base em sua organização, execute o seguinte comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Exibir uma lista de produtos de compra de autoatendados e seu status

Para exibir uma lista de todos os produtos de compra de autoatendados disponíveis e o status de cada um, execute o seguinte comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

A tabela a seguir lista os produtos disponíveis e **seus ProductId**.

| Produto | ProductId |
|-----------------------------|--------------|
| Power Apps por usuário | CFQ7TTC0KP0P |
| Power Automate por usuário | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (autônomo) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plano 1 | CFQ7TTC0KXND |
| Project Plano 3 | CFQ7TTC0KXNC |
| Visio Plano 1 | CFQ7TTC0KXN9 |
| Visio Plano 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Exibir ou definir o status de AllowSelfServicePurchase

Depois de exibir a lista de produtos disponíveis para compra de autoatendados, você pode exibir ou modificar a configuração de um produto específico.

Para obter a configuração de política de um produto específico, execute o seguinte comando:

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

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script de exemplo para desabilitar AllowSelfServicePurchase

O exemplo a seguir explica como importar o **módulo MSCommerce,** entrar com sua conta, obter **ProductId** para Power Automate e desabilitar **AllowSelfServicePurchase** para esse produto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solução de Problemas

### <a name="problem"></a>Problema

Você vê a seguinte mensagem de erro:

> HandleError : Falha ao recuperar a política com PolicyId 'AllowSelfServicePurchase', ErrorMessage - A conexão subjacente foi fechada: ocorreu um erro inesperado em um envio.

Isso pode ser devido a uma versão mais antiga do TLS (Transport Layer Security). Para conectar esse serviço, você precisa usar o TLS 1.2 ou superior

### <a name="solution"></a>Solução

Atualizar para o TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>Conteúdo relacionado

[Gerenciar compras self-service (Admin)](manage-self-service-purchases-admins.md) (artigo)

[Perguntas frequentes sobre compra de autoatendam](self-service-purchase-faq.yml) (artigo)
