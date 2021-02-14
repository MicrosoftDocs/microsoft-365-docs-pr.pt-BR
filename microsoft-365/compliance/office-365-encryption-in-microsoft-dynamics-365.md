---
title: Criptografia no Microsoft Dynamics 365
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
description: Saiba como a Microsoft usa a tecnologia de criptografia para proteger os dados do cliente no Microsoft Dynamics 365 enquanto estiver em repouso em um banco de dados da Microsoft e em trânsito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd349890fc7fc1ae7f1f7eaf07f90c22423637cf
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031407"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Criptografia no Microsoft Dynamics 365

A Microsoft usa a tecnologia de criptografia para proteger os dados do cliente no Dynamics 365 em repouso em um banco de dados da Microsoft e enquanto ele está em trânsito entre os dispositivos do usuário e nossos datacenters. As conexões estabelecidas entre clientes e datacenters da Microsoft são criptografadas, e todos os pontos de extremidade públicos são protegidos usando tLS padrão do setor. O TLS estabelece efetivamente uma conexão de navegador para servidor com segurança aprimorada para ajudar a garantir a confidencialidade e a integridade dos dados entre áreas de trabalho e datacenters. Depois que a criptografia de dados é ativada, ela não pode ser desativada. Para obter mais informações, consulte [Criptografia de dados no nível do campo.](https://msdn.microsoft.com/library/dn481562.aspx)

O Dynamics 365 usa criptografia de nível de célula padrão do Microsoft SQL Server para um conjunto de atributos de entidade padrão que contêm informações confidenciais, como nomes de usuário e senhas de email. Esse recurso pode ajudar as organizações a atender aos requisitos de conformidade associados ao FIPS 140-2. A criptografia de dados em nível de campo é especialmente importante em cenários que aproveitam o Roteador de Email do [Microsoft Dynamics CRM,](https://technet.microsoft.com/library/hh699800.aspx)que deve armazenar nomes de usuário e senhas para habilitar a integração entre uma instância do Dynamics 365 e um serviço de email. 

Todas as instâncias do Dynamics 365 usam a TDE (Criptografia de Dados Transparente) do [Microsoft SQL Server](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) para executar a criptografia em tempo real de dados quando gravados em disco (em repouso). O TDE criptografa o SQL Server, o banco de dados SQL do Azure e os arquivos de dados do Azure SQL Data Warehouse. Por padrão, a Microsoft armazena e gerencia as chaves de criptografia de banco de dados para suas instâncias do Dynamics 365. (As chaves usadas pelo Dynamics 365 for Financials são geradas pela API de Proteção de Dados do .NET Framework.) 

O recurso gerenciar chaves no Centro de Administração do Dynamics 365 oferece aos administradores a capacidade de auto-gerenciar as chaves de criptografia de banco de dados associadas a instâncias do Dynamics 365. (As chaves de criptografia de banco de dados auto-gerenciadas só estão disponíveis na atualização de janeiro de 2017 para o Microsoft Dynamics 365 e podem não estar disponíveis para versões posteriores. Para obter mais informações, consulte Gerenciar as chaves de criptografia para sua instância do [Dynamics 365 (online).](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance) O recurso de gerenciamento de chaves dá suporte a arquivos de chave de criptografia PFX e BYOK, como aqueles armazenados em um HSM. (Para obter mais informações sobre como gerar e transferir uma chave protegida por HSM pela Internet, consulte Como gerar e transferir chaves protegidas por HSM para o [Azure Key Vault.)](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys) 

Para usar a opção carregar chave de criptografia, você precisa da chave de criptografia pública e privada.

O recurso de gerenciamento de chaves tira a complexidade do gerenciamento de chaves de criptografia usando o Azure Key Vault para armazenar chaves de criptografia com segurança. O Azure Key Vault ajuda a proteger chaves criptográficas e segredos usados por aplicativos e serviços em nuvem. O recurso de gerenciamento de chaves não exige que você tenha uma assinatura do Azure Key Vault e, para a maioria das situações, não há necessidade de acessar chaves de criptografia usadas para o Dynamics 365 no cofre.
