---
title: Criptografia de serviço do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: entender a criptografia de dados na camada de serviço do Microsoft Office 365.'
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211938"
---
# <a name="office-365-service-encryption"></a>Criptografia de serviço do Office 365

Além de usar o BitLocker para a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e o Microsoft Teams também usam a criptografia de serviço para criptografar os dados do cliente. A criptografia de serviço permite duas opções de gerenciamento de chave:

- A Microsoft gerencia todas as chaves criptográficas. No momento, essa opção está disponível no SharePoint Online, no OneDrive for Business, no Skype for Business e em bate-papos do Microsoft Teams. Os dados são criptografados por padrão com chaves gerenciadas pela Microsoft.

- Sua organização fornece as chaves raiz. Você gerencia essas chaves usando o Azure Key Vault. Essa opção é chamada de chave do cliente. A chave do cliente está disponível atualmente para os arquivos do Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business e Teams. Se você usar a chave do cliente, essas chaves substituirão chaves gerenciadas pela Microsoft para criptografar seus dados.

Seja qual for a opção escolhida, a criptografia de serviço oferece vários benefícios:

- Impõe a autenticação do usuário para recuperar e descriptografar dados solicitados por um usuário autorizado.

- Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.

- Aprimora a capacidade do Office 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.

Para saber como configurar a chave do cliente para o Office 365 para o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e os arquivos do Teams, consulte estes artigos:

- [Criptografia de serviço com a chave do cliente no Office 365](customer-key-overview.md)

- [Configurar a chave do cliente para o Office 365](customer-key-set-up.md)

- [Gerenciar a chave do cliente para o Office 365](customer-key-manage.md)

- [Rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Entender a chave de disponibilidade](customer-key-availability-key-understand.md)
