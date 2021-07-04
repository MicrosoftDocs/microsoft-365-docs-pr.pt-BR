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
ms.openlocfilehash: 0e2691a2f02ecee5b346fcda3335ca7e5d4becc2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288282"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Criptografia no Microsoft Dynamics 365

A Microsoft usa a tecnologia de criptografia para proteger dados do cliente no Dynamics 365 enquanto estiver em repouso em um banco de dados da Microsoft e enquanto estiver em trânsito entre dispositivos de usuário e nossos datacenters. As conexões estabelecidas entre clientes e datacenters da Microsoft são criptografadas e todos os pontos de extremidade públicos são protegidos usando TLS padrão do setor. O TLS estabelece efetivamente uma conexão de navegador a servidor com segurança aprimorada para ajudar a garantir a confidencialidade e a integridade dos dados entre desktops e datacenters. Depois que a criptografia de dados é ativada, ela não pode ser desativada. Para obter mais informações, consulte [Criptografia de dados de nível de campo](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8)).

O Dynamics 365 usa criptografia padrão Microsoft SQL Server nível de célula para um conjunto de atributos de entidade padrão que contêm informações confidenciais, como nomes de usuário e senhas de email. Esse recurso pode ajudar as organizações a atender aos requisitos de conformidade associados ao FIPS 140-2. A criptografia de dados no nível de campo é especialmente importante em cenários que aproveitam o roteador de [email](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))Microsoft Dynamics CRM , que deve armazenar nomes de usuário e senhas para habilitar a integração entre uma instância do Dynamics 365 e um serviço de email.

Todas as instâncias do Dynamics 365 usam [Microsoft SQL Server Transparent Data Encryption](/sql/relational-databases/security/encryption/transparent-data-encryption) (TDE) para executar a criptografia em tempo real de dados quando gravados em disco (em repouso). O TDE criptografa SQL Server, Banco de Dados SQL do Azure e arquivos de dados do Azure SQL Data Warehouse. Por padrão, a Microsoft armazena e gerencia as chaves de criptografia de banco de dados para suas instâncias do Dynamics 365. (As chaves usadas pelo Dynamics 365 para Finanças são geradas pela API .NET Framework Proteção de Dados.)

O recurso gerenciar chaves no Centro de Administração do Dynamics 365 oferece aos administradores a capacidade de gerenciar as chaves de criptografia de banco de dados associadas a instâncias do Dynamics 365. (As chaves de criptografia de banco de dados auto-gerenciadas só estão disponíveis na atualização de janeiro de 2017 para o Microsoft Dynamics 365 e podem não ser disponibilizadas para versões posteriores. Para obter mais informações, consulte [Manage the encryption keys for your Dynamics 365 (online) instance](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance).) O recurso de gerenciamento de chaves dá suporte a arquivos de chave de criptografia PFX e BYOK, como aqueles armazenados em um HSM. (Para obter mais informações sobre como gerar e transferir uma chave protegida por HSM pela Internet, consulte How to generate and [transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/key-vault-hsm-protected-keys).)

Para usar a opção de chave de criptografia de carregamento, você precisa da chave de criptografia pública e privada.

O recurso de gerenciamento de chaves tira a complexidade do gerenciamento de chaves de criptografia usando o Azure Key Vault para armazenar chaves de criptografia com segurança. O Azure Key Vault ajuda a proteger chaves criptográficas e segredos usados por aplicativos e serviços de nuvem. O recurso de gerenciamento de chaves não exige que você tenha uma assinatura do Azure Key Vault e, para a maioria das situações, não é necessário acessar chaves de criptografia usadas para o Dynamics 365 no cofre.