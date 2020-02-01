---
title: Criptografia do Office 365 no Microsoft Dynamics 365
f1.keywords:
- NOCSH
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
description: 'Resumo: entender a criptografia no Microsoft Dynamics 365.'
ms.openlocfilehash: 288f739182f8419cf7fbbfb6dfd7ad0a2c7838a5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597848"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Criptografia do Office 365 no Microsoft Dynamics 365

A Microsoft usa a tecnologia de criptografia para proteger os dados do cliente no Dynamics 365 enquanto estiver em repouso em um banco de dados da Microsoft e enquanto estiver em trânsito entre os dispositivos do usuário e nossos data centers. As conexões estabelecidas entre os clientes e os datacenters da Microsoft são criptografadas, e todos os pontos de extremidade públicos são protegidos usando TLS padrão da indústria. O TLS efetivamente estabelece uma conexão de navegador para servidor de segurança avançada para ajudar a garantir a confidencialidade e a integridade dos dados entre desktops e datacenters. Depois que a criptografia de dados é ativada, ela não pode ser desativada. Para obter mais informações, consulte [Field-level Data Encryption](https://msdn.microsoft.com/library/dn481562.aspx).

O Dynamics 365 usa a criptografia de nível de célula padrão do Microsoft SQL Server para um conjunto de atributos de entidade padrão que contêm informações confidenciais, como nomes de usuário e senhas de email. Esse recurso pode ajudar as organizações a cumprir os requisitos de conformidade associados ao FIPS 140-2. A criptografia de dados em nível de campo é especialmente importante em cenários que aproveitam o [roteador de email do Microsoft Dynamics CRM](https://technet.microsoft.com/library/hh699800.aspx), que deve armazenar nomes de usuário e senhas para habilitar a integração entre uma instância do Dynamics 365 e um serviço de email. 

Todas as instâncias do Dynamics 365 usam [o Microsoft SQL Server Transparent Data Encryption](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) para executar a criptografia de dados em tempo real quando gravadas em disco (em repouso). O TDE criptografa o SQL Server, o banco de dados SQL do Azure e os arquivos de dados do Azure SQL data warehouse. Por padrão, a Microsoft armazena e gerencia as chaves de criptografia do banco de dados para suas instâncias do Dynamics 365. (As chaves usadas pelo Dynamics 365 para finanças são geradas pela API de proteção de dados do .NET Framework.) 

O recurso gerenciar chaves no centro de administração do Dynamics 365 oferece aos administradores a capacidade de gerenciar automaticamente as chaves de criptografia de banco de dados associadas às instâncias do Dynamics 365. (As chaves de criptografia de banco de dados autogerenciadas só estão disponíveis na atualização de janeiro de 2017 para o Microsoft Dynamics 365 e podem não ser disponibilizadas para versões posteriores. Para obter mais informações, consulte [gerenciar as chaves de criptografia para sua instância do Dynamics 365 (online)](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance). O recurso de gerenciamento de chaves oferece suporte a arquivos de chave de criptografia PFX e BYOK, como os armazenados em um HSM. (Para obter mais informações sobre a geração e a transferência de uma chave protegida por HSM pela Internet, consulte [como gerar e transferir chaves protegidas por HSM para o Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys).) 

Para usar a opção de chave de criptografia de upload, você precisará da chave de criptografia pública e privada.

O recurso de gerenciamento de chaves retira a complexidade do gerenciamento de chaves de criptografia usando o Azure Key Vault para armazenar com segurança as chaves de criptografia. O Azure Key Vault ajuda a proteger chaves criptográficas e segredos usados por aplicativos e serviços de nuvem. O recurso de gerenciamento de chaves não exige que você tenha uma assinatura do Azure Key Vault e, na maioria das situações, não é necessário acessar as chaves de criptografia usadas para o Dynamics 365 no cofre.
