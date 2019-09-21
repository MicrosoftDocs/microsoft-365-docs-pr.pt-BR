---
title: Criptografia de serviço do Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: entenda a resiliência de dados no Microsoft Office 365.'
ms.openlocfilehash: 385bb936de2c0cfcb478f0b20d2f7367d5b55ff4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073446"
---
# <a name="office-365-service-encryption"></a>Criptografia de serviço do Office 365

Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente. A criptografia de serviço permite duas opções de gerenciamento de chave:
- A Microsoft gerencia todas as chaves criptográficas. (Essa opção está atualmente disponível no SharePoint Online, no OneDrive for Business e no Skype for Business. No momento, ele está no mapa do Exchange Online.)
- O cliente fornece as chaves raiz usadas com a criptografia de serviço e o cliente gerencia essas chaves usando o Azure Key Vault. A Microsoft gerencia todas as outras chaves. Essa opção é chamada de chave do cliente e está disponível atualmente para o Exchange Online, o SharePoint Online e o OneDrive for Business. (Conhecido anteriormente como criptografia avançada com o BYOK. Consulte [aprimorando a transparência e o controle para clientes do Office 365](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.

A criptografia de serviço oferece vários benefícios. Por exemplo, ele:
- fornece recursos de gerenciamento e proteção de direitos na parte superior da proteção de criptografia forte.
- inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.
- fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.
- aprimora a capacidade do Office 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.

## <a name="customer-key"></a>Chave do Cliente
Usando a chave do cliente, você pode gerar suas próprias chaves criptográficas usando um HSM local ou o Azure Key Vault. Independentemente de como a chave é gerada, os clientes usam o Azure Key Vault para controlar e gerenciar as chaves criptográficas usadas pelo Office 365. Depois que as chaves são armazenadas no Azure Key Vault, elas podem ser atribuídas a cargas de trabalho, como o Exchange Online e o SharePoint Online e usadas como a raiz do chaveiro usado para criptografar seus arquivos e dados de caixa de correio.
Um dos outros benefícios do uso da chave do cliente é controlar a capacidade da Microsoft de processar os dados do cliente. Esse recurso existe para que um cliente que deseja remover dados do Office 365 (como quando um cliente finaliza o serviço com a Microsoft ou remove uma parte dos dados armazenados na nuvem) pode fazer isso e usar a chave do cliente como um controle técnico para garantir que ninguém , incluindo a Microsoft, pode acessar ou processar os dados. Isso é adicional (e um complemento) ao recurso de lockbox do cliente que pode ser usado para controlar o acesso aos dados do cliente pela equipe da Microsoft.

Para saber como configurar a chave do cliente para o Office 365 para o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business, consulte [controle dos dados no Office 365 usando a chave do cliente](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Para obter informações adicionais, consulte a [chave do cliente para perguntas frequentes sobre o Office 365](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)e [gerencie e controle seus dados para ajudar a atender às necessidades de conformidade com a chave do cliente](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).
