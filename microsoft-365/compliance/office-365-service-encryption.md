---
title: Criptografia de serviço
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: entenda a resiliência de dados no Microsoft Office 365.'
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777044"
---
# <a name="service-encryption"></a>Criptografia de serviço

Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente. A criptografia de serviço permite duas opções de gerenciamento de chave:

## <a name="microsoft-managed-keys"></a>Chaves gerenciadas pela Microsoft
A Microsoft gerencia todas as chaves criptográficas, incluindo as chaves raiz para a criptografia de serviço. Atualmente, essa opção está habilitada por padrão para o Exchange Online, o SharePoint Online, o OneDrive for Business. As chaves gerenciadas pela Microsoft fornecem criptografia de serviço padrão, a menos que você decida usar a chave do cliente. Se, posteriormente, você optar por parar de usar a chave do cliente sem seguir o caminho de limpeza de dados, seus dados permanecerão criptografados usando as chaves gerenciadas pela Microsoft. Seus dados são sempre criptografados no nível padrão no mínimo. 

## <a name="customer-key"></a>Chave de Cliente
Você fornece chaves raiz usadas com a criptografia de serviço e gerencia essas chaves usando o Azure Key Vault. A Microsoft gerencia todas as outras chaves. Essa opção é chamada de chave do cliente e está disponível atualmente para o Exchange Online, o SharePoint Online e o OneDrive for Business. (Conhecido anteriormente como criptografia avançada com o BYOK. Consulte [aprimorando a transparência e o controle para clientes do Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.

A criptografia de serviço oferece vários benefícios:

- Fornece uma camada adicional de proteção na parte superior do BitLocker.

- Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do aplicativo armazenados ou processados pelo sistema operacional.

- Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.

- Aprimora a capacidade do Microsoft 365 de atender às demandas de clientes que têm requisitos de conformidade específicos relacionados à criptografia.

Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV). Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365. Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.

Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados. Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico. A remoção de dados garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados. A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.

Para saber como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, incluindo sites de equipe e OneDrive for Business, consulte estes artigos:

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Configurar a chave do cliente](customer-key-set-up.md)

- [Gerenciar chave do cliente](customer-key-manage.md)

- [Rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Entender a chave de disponibilidade](customer-key-availability-key-understand.md)

