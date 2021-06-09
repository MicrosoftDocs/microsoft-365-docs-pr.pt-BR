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
description: Saiba mais sobre criptografia disponível no Azure, como Azure Disk Encryption
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926249"
---
# <a name="encryption-in-azure"></a>Criptografia no Azure

As proteções tecnológicas no Azure, como comunicações criptografadas e processos operacionais, ajudam a manter seus dados seguros. Você também tem a flexibilidade de implementar recursos de criptografia adicionais e gerenciar suas próprias chaves criptográficas. Independentemente da configuração do cliente, a Microsoft aplica criptografia para proteger dados do cliente no Azure. A Microsoft também permite que você controle seus dados hospedados no Azure por meio de uma variedade de tecnologias avançadas para criptografar, controlar e gerenciar chaves criptográficas e controlar e auditar o acesso aos dados. Além disso, o Azure Armazenamento fornece um conjunto abrangente de recursos de segurança que, juntos, permitem que os desenvolvedores criem aplicativos seguros.

O Azure oferece muitos mecanismos para proteger dados à medida que ele se move de um local para outro. A Microsoft usa o TLS para proteger dados quando ele está viajando entre os serviços de nuvem e os clientes. Os data centers da Microsoft negociam uma conexão TLS com sistemas cliente que se conectam aos serviços do Azure. O Segredo de Encaminhamento Perfeito (PFS) protege as conexões entre os sistemas cliente dos clientes e os serviços de nuvem da Microsoft por chaves exclusivas. As conexões também usam comprimentos de chave de criptografia de 2.048 bits baseados em RSA. Essa combinação dificulta a interceptação e o acesso de dados em trânsito.

Os dados podem ser protegidos em trânsito entre um aplicativo e o Azure usando [criptografia](/azure/storage/storage-client-side-encryption)do lado do cliente, HTTPS ou SMB 3.0. Você pode habilitar a criptografia para tráfego entre suas próprias máquinas virtuais (VMs) e seus usuários. Com as Redes Virtuais do [Azure,](https://azure.microsoft.com/services/virtual-network/)você pode usar o protocolo IPsec padrão do setor para criptografar o tráfego entre o gateway VPN corporativo e o Azure, bem como entre as VMs localizadas em sua Rede Virtual.

Para dados em repouso, o Azure oferece muitas opções de criptografia, como suporte para o AES-256, dando a você a flexibilidade de escolher o cenário de armazenamento de dados que melhor atende às suas necessidades. Os dados podem ser criptografados automaticamente quando gravados no Azure Armazenamento usando Armazenamento [Criptografia](/azure/storage/storage-service-encryption)de Serviço, e os discos de sistema operacional e de dados usados por VMs podem ser criptografados. Para obter mais informações, consulte [Recomendações de segurança para Windows virtuais no Azure](/azure/security/azure-security-disk-encryption). Além disso, o acesso delegado a objetos de dados no Azure Armazenamento pode ser concedido usando [Assinaturas de](/azure/storage/storage-dotnet-shared-access-signature-part-1)Acesso Compartilhado . O Azure também fornece criptografia para dados em repouso usando [Transparent Data Encryption para Banco de Dados SQL do Azure e Data Warehouse.](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Para obter mais informações sobre criptografia no Azure, consulte Visão geral da criptografia do [Azure](/azure/security/security-azure-encryption-overview) e Criptografia de Dados [do Azure-at-Rest.](/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption permite criptografar os discos de VM do Windows e do Linux como serviço (IaaS). Azure Disk Encryption aproveita o recurso BitLocker do Windows e o recurso DM-Crypt do Linux para fornecer criptografia de nível de volume para o sistema operacional e os discos de dados. Ele também garante que todos os dados nos discos VM sejam criptografados em repouso no armazenamento do Azure. Azure Disk Encryption é integrado ao Azure Key Vault para ajudá-lo a controlar, gerenciar e auditar o uso das chaves e segredos de criptografia.

Para obter mais informações, consulte [Recomendações de segurança para Windows virtuais no Azure](/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Criptografia de serviço Armazenamento Azure

Com a Criptografia de Serviço do [Azure Armazenamento](/azure/storage/storage-service-encryption), o Azure Armazenamento criptografa automaticamente os dados antes de persisti-los no armazenamento e descriptografa dados antes da recuperação. Os processos de criptografia, descriptografia e gerenciamento de chaves são totalmente transparentes para os usuários. A criptografia Armazenamento de serviço do Azure pode ser usada para arquivos [do Azure Blob Armazenamento](https://azure.microsoft.com/services/storage/blobs/) e [arquivos do Azure.](https://azure.microsoft.com/services/storage/files/) Você também pode usar chaves de criptografia gerenciadas pela Microsoft com o Azure Armazenamento Service Encryption ou pode usar suas próprias chaves de criptografia. (Para obter informações sobre como usar suas próprias chaves, consulte [Armazenamento Service Encryption using customer managed keys in Azure Key Vault](/azure/storage/common/storage-service-encryption-customer-managed-keys). Para obter informações sobre como usar chaves gerenciadas pela Microsoft, [consulte Armazenamento Service Encryption for Data at Rest](/azure/storage/storage-service-encryption).) Além disso, você pode automatizar o uso de criptografia. Por exemplo, você pode habilitar ou desabilitar programaticamente Armazenamento Criptografia de Serviço em uma conta de armazenamento usando a API REST do Provedor de Recursos do [Azure Armazenamento,](/rest/api/storagerp/)a Biblioteca de Cliente do Provedor de Recursos do [Armazenamento para .NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell](/powershell/azureps-cmdlets-docs)ou a CLI do [Azure](/azure/storage/storage-azure-cli).

Alguns Microsoft 365 usam o Azure para armazenar dados. Por exemplo, SharePoint Online e OneDrive for Business armazenam dados no armazenamento do Blob do Azure e o Microsoft Teams armazena dados para seu serviço de chat em tabelas, blobs e filas. Além disso, o recurso Gerenciador de Conformidade no centro de conformidade do Microsoft 365 armazena dados inseridos pelo cliente que são armazenados em formato criptografado no [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), uma Plataforma como Serviço (PaaS), banco de dados distribuído globalmente e multi-modelo. A Criptografia de Serviço do Azure Armazenamento criptografa dados armazenados no armazenamento do Blob do Azure e em tabelas, e o Azure Disk Encryption criptografa dados em filas, bem como discos de máquina virtual Windows e IaaS para fornecer criptografia de volume para o sistema operacional e o disco de dados. A solução garante que todos os dados nos discos da máquina virtual sejam criptografados em repouso no armazenamento do Azure. A criptografia em repouso no [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) é implementada usando várias tecnologias de segurança, incluindo sistemas de armazenamento de chaves seguras, redes criptografadas e APIs criptográficas.

## <a name="azure-key-vault"></a>Azure Key Vault

O gerenciamento de chaves seguras não é apenas fundamental para as práticas recomendadas de criptografia; também é essencial para proteger dados na nuvem. [O Azure Key Vault](/azure/key-vault/key-vault-whatis) permite criptografar chaves e pequenos segredos, como senhas que usam chaves armazenadas em HSMs (módulos de segurança de hardware). O Azure Key Vault é a solução recomendada da Microsoft para gerenciar e controlar o acesso às chaves de criptografia usadas pelos serviços de nuvem. As permissões para acessar chaves podem ser atribuídas aos serviços ou aos usuários com Azure Active Directory contas. O Azure Key Vault alivia as organizações da necessidade de configurar, corrigir e manter HSMs e software de gerenciamento de chaves. Com o Azure Key Vault, a Microsoft nunca vê suas chaves e aplicativos não têm acesso direto a elas; você mantém o controle. Você também pode importar ou gerar chaves em HSMs. As organizações que têm uma assinatura que inclui a Proteção de Informações do Azure podem configurar seu locatário da Proteção de Informações do Azure para usar uma chave gerenciada pelo cliente [Traga](/information-protection/plan-design/byok-price-restrictions) sua própria chave (BYOK)) e registrar seu [uso](/information-protection/deploy-use/log-analyze-usage).