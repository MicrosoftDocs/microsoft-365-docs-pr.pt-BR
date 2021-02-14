---
title: Criptografia no Azure
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Saiba mais sobre a criptografia disponível no Azure, como a Criptografia de Disco do Azure
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a90f66ed7288d84785becbb4cd25c803ccf4fdbe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198324"
---
# <a name="encryption-in-azure"></a>Criptografia no Azure

As proteções contra a segurança no Azure, como comunicações criptografadas e processos operacionais, ajudam a manter seus dados seguros. Você também tem a flexibilidade de implementar recursos de criptografia adicionais e gerenciar suas próprias chaves criptográficas. Independentemente da configuração do cliente, a Microsoft aplica criptografia para proteger os dados do cliente no Azure. A Microsoft também permite controlar seus dados hospedados no Azure por meio de uma variedade de tecnologias avançadas para criptografar, controlar e gerenciar chaves criptográficas e controlar e auditar o acesso aos dados. Além disso, o Armazenamento do Azure fornece um conjunto abrangente de recursos de segurança que juntos permitem que os desenvolvedores criem aplicativos seguros.

O Azure oferece muitos mecanismos para proteger dados à medida que ele passa de um local para outro. A Microsoft usa o TLS para proteger os dados quando ele está viajando entre os serviços de nuvem e os clientes. Os data centers da Microsoft negociam uma conexão TLS com sistemas cliente que se conectam aos serviços do Azure. O PFS protege as conexões entre os sistemas clientes e os serviços de nuvem da Microsoft por chaves exclusivas. As conexões também usam comprimentos de chave de criptografia de 2.048 bits baseados em RSA. Essa combinação dificulta a interceptação e o acesso de dados que estão em trânsito.

Os dados podem ser protegidos em trânsito entre um aplicativo e o Azure usando criptografia [do](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)lado do cliente, HTTPS ou SMB 3.0. Você pode habilitar a criptografia para tráfego entre suas próprias máquinas virtuais (VMs) e seus usuários. Com as Redes Virtuais do [Azure,](https://azure.microsoft.com/services/virtual-network/)você pode usar o protocolo IPsec padrão do setor para criptografar o tráfego entre seu gateway VPN corporativo e o Azure, bem como entre as VMs localizadas em sua Rede Virtual.

Para dados em repouso, o Azure oferece muitas opções de criptografia, como suporte para AES-256, dando a você a flexibilidade de escolher o cenário de armazenamento de dados que melhor atenda às suas necessidades. Os dados podem ser criptografados automaticamente [](https://docs.microsoft.com/azure/storage/storage-service-encryption)quando gravados no Armazenamento do Azure usando a Criptografia de Serviço de Armazenamento e os discos de sistema operacional e de dados usados por VMs podem ser criptografados. Para saber mais, confira [Recomendações de segurança para máquinas virtuais do Windows no Azure.](https://docs.microsoft.com/azure/security/azure-security-disk-encryption) Além disso, o acesso delegado a objetos de dados no Armazenamento do Azure pode ser concedido usando [Assinaturas de Acesso Compartilhado.](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) O Azure também fornece criptografia para dados em repouso usando Criptografia de Dados Transparente para Banco de Dados [SQL do Azure e Data Warehouse.](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Para saber mais sobre criptografia no Azure, confira a visão geral da criptografia do [Azure](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) e a Criptografia de Dados [do Azure em Repouso.](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Criptografia de Disco do Azure

A Criptografia de Disco do Azure permite criptografar os discos de VM do Windows e da Infraestrutura linux como serviço (IaaS). A Criptografia de Disco do Azure aproveita o recurso BitLocker do Windows e o DM-Crypt do Linux para fornecer criptografia de nível de volume para o sistema operacional e os discos de dados. Isso também garante que todos os dados nos discos de VM sejam criptografados em repouso no armazenamento do Azure. A Criptografia de Disco do Azure é integrada ao Azure Key Vault para ajudá-lo a controlar, gerenciar e auditar o uso de chaves e segredos de criptografia.

Para saber mais, confira [Recomendações de segurança para máquinas virtuais do Windows no Azure.](https://docs.microsoft.com/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Criptografia do Serviço de Armazenamento do Azure

Com a Criptografia do Serviço de Armazenamento do [Azure,](https://docs.microsoft.com/azure/storage/storage-service-encryption)o Armazenamento do Azure criptografa automaticamente os dados antes de persisti-los no armazenamento e descriptografa os dados antes da recuperação. Os processos de criptografia, descriptografia e gerenciamento de chaves são totalmente transparentes para os usuários. A Criptografia do Serviço de Armazenamento do Azure pode ser usada para o Armazenamento de [Blob do Azure](https://azure.microsoft.com/services/storage/blobs/) e arquivos [do Azure.](https://azure.microsoft.com/services/storage/files/) Você também pode usar chaves de criptografia gerenciadas pela Microsoft com a Criptografia do Serviço de Armazenamento do Azure ou pode usar suas próprias chaves de criptografia. (Para obter informações sobre como usar suas próprias chaves, consulte Criptografia de Serviço de Armazenamento usando chaves gerenciadas [do cliente no Azure Key Vault.](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys) Para obter informações sobre como usar chaves gerenciadas pela Microsoft, consulte Criptografia de Serviço de Armazenamento [para Dados em Repouso.)](https://docs.microsoft.com/azure/storage/storage-service-encryption) Além disso, você pode automatizar o uso de criptografia. Por exemplo, você pode habilitar ou desabilitar programaticamente a Criptografia do Serviço de Armazenamento em uma conta de armazenamento usando a API REST do Provedor de Recursos de Armazenamento do [Azure,](https://msdn.microsoft.com/library/azure/mt163683.aspx)a Biblioteca de Cliente do Provedor de Recursos de Armazenamento para [.NET,](https://msdn.microsoft.com/library/azure/mt131037.aspx) [o Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)ou a CLI do [Azure.](https://docs.microsoft.com/azure/storage/storage-azure-cli)

Alguns serviços do Microsoft 365 usam o Azure para armazenar dados. Por exemplo, o SharePoint Online e o OneDrive for Business armazenam dados no armazenamento de Blobs do Azure, e o Microsoft Teams armazena dados para seu serviço de chat em tabelas, blobs e filas. Além disso, o recurso Gerenciador de Conformidade no centro de conformidade do Microsoft 365 armazena dados inseridos pelo cliente que são armazenados em formato criptografado no [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest), uma Plataforma como um Serviço (PaaS), banco de dados multi-modelo distribuído globalmente. A Criptografia do Serviço de Armazenamento do Azure criptografa os dados armazenados no armazenamento de Blob do Azure e em tabelas, e a Criptografia de Disco do Azure criptografa dados em filas, bem como discos de máquina virtual Windows e IaaS para fornecer criptografia de volume para o sistema operacional e o disco de dados. A solução garante que todos os dados nos discos da máquina virtual sejam criptografados em repouso no armazenamento do Azure. A criptografia em repouso no [Azure Db é](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) implementada usando várias tecnologias de segurança, incluindo sistemas de armazenamento de chaves seguras, redes criptografadas e APIs criptográficas.

## <a name="azure-key-vault"></a>Azure Key Vault

O gerenciamento de chaves seguras não é apenas o núcleo das práticas recomendadas de criptografia; também é essencial para proteger os dados na nuvem. [O Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) permite criptografar chaves e segredos pequenos, como senhas que usam chaves armazenadas em HSMs (módulos de segurança de hardware). O Azure Key Vault é a solução recomendada da Microsoft para gerenciar e controlar o acesso a chaves de criptografia usadas pelos serviços de nuvem. As permissões para acessar teclas podem ser atribuídas a serviços ou a usuários com contas do Azure Active Directory. O Azure Key Vault libera as organizações da necessidade de configurar, corrigir e manter HSMs e software de gerenciamento de chaves. Com o Azure Key Vault, a Microsoft nunca vê suas chaves e aplicativos não têm acesso direto a elas; você mantém o controle. Você também pode importar ou gerar chaves em HSMs. As organizações que têm uma assinatura que inclui a Proteção de Informações do Azure podem configurar seu locatário da Proteção de Informações do Azure para usar uma chave gerenciada pelo cliente (BYOK)) e registrar seu [uso.](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage) [](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)
