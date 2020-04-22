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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632236"
---
# <a name="service-encryption"></a>Criptografia de serviço

Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente. A criptografia de serviço permite duas opções de gerenciamento de chave:

- A Microsoft gerencia todas as chaves criptográficas. (Essa opção está atualmente disponível no SharePoint Online, no OneDrive for Business e no Skype for Business).

- Sua organização fornece as chaves raiz. Você gerencia essas chaves usando o Azure Key Vault. Essa opção é chamada de chave do cliente. A chave do cliente está disponível atualmente para os arquivos do Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business e Teams. Se você usar a chave do cliente, essas chaves substituirão chaves gerenciadas pela Microsoft para criptografar seus dados.

A criptografia de serviço oferece vários benefícios. Por exemplo, chave de cliente:

- Fornece recursos de gerenciamento e proteção de direitos na parte superior da proteção de criptografia forte.

- Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.

- Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.

- Aprimora a capacidade do Microsoft 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.

## <a name="customer-key"></a>Chave de Cliente

Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV). Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365. Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.

Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados. Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico. Isso garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados. A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.

Para saber como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, incluindo sites de equipe e OneDrive for Business, consulte estes artigos:

- [Criptografia de serviço com a chave do cliente](customer-key-overview.md)

- [Configurar a chave do cliente](customer-key-set-up.md)

- [Gerenciar chave do cliente](customer-key-manage.md)

- [Rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Entender a chave de disponibilidade](customer-key-availability-key-understand.md)
 
