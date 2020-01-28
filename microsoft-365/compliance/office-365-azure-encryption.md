---
title: Criptografia do Office 365 no Azure
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
description: 'Resumo: uma explicação de criptografia no Azure.'
ms.openlocfilehash: 9c493c4a60dfb050b3b628c0e37bee131e4e4db8
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558488"
---
# <a name="office-365-encryption-in-azure"></a>Criptografia do Office 365 no Azure

## <a name="introduction"></a>Introdução

Garantias tecnológicas no Azure, como comunicações criptografadas e processos operacionais, ajudam a manter seus dados seguros. Você também tem a flexibilidade para implementar recursos de criptografia adicionais e gerenciar suas próprias chaves criptográficas. Independentemente da configuração do cliente, a Microsoft aplica criptografia para proteger os dados do cliente no Azure. A Microsoft também permite que você controle seus dados hospedados no Azure por meio de uma variedade de tecnologias avançadas para criptografar, controlar e gerenciar chaves criptográficas, controlar e auditar o acesso aos dados. Além disso, o armazenamento do Azure fornece um conjunto abrangente de recursos de segurança que, juntos, permitem que os desenvolvedores criem aplicativos seguros.

O Azure oferece muitos mecanismos para proteger os dados à medida que ele se move de um local para outro. A Microsoft usa o TLS para proteger os dados quando está viajando entre os serviços de nuvem e os clientes. Os data centers da Microsoft negociam uma conexão TLS com sistemas clientes que se conectam aos serviços do Azure. O sigilo total na transferência (PFS) protege as conexões entre os sistemas clientes e os serviços de nuvem da Microsoft por chaves exclusivas. As conexões também usam comprimentos de chave de criptografia de 2.048 bits baseados em RSA. Essa combinação torna difícil para alguém interceptar e acessar os dados que estão em trânsito.

Os dados podem ser protegidos em trânsito entre um aplicativo e o Azure usando a [criptografia do lado do cliente](https://docs.microsoft.com/azure/storage/storage-client-side-encryption), HTTPS ou SMB 3,0. Você pode habilitar a criptografia para o tráfego entre suas próprias máquinas virtuais (VMs) e seus usuários. Com as [redes virtuais do Azure](https://azure.microsoft.com/services/virtual-network/), você pode usar o protocolo IPsec padrão da indústria para criptografar o tráfego entre o gateway VPN corporativo e o Azure, bem como entre as VMs localizadas na sua rede virtual.

Para dados em repouso, o Azure oferece muitas opções de criptografia, como o suporte para AES-256, oferecendo a flexibilidade para escolher o cenário de armazenamento de dados que melhor atende às suas necessidades. Os dados podem ser criptografados automaticamente quando gravados no armazenamento do Azure usando a [criptografia de serviço de armazenamento](https://docs.microsoft.com/azure/storage/storage-service-encryption), e os discos de sistema operacional e de dados usados por VMS podem ser criptografados. Para obter mais informações, consulte [recomendações de segurança para máquinas virtuais do Windows no Azure](https://docs.microsoft.com/azure/security/azure-security-disk-encryption). Além disso, o acesso delegado a objetos de dados no armazenamento do Azure pode ser concedido usando [assinaturas de acesso compartilhado](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1). O Azure também fornece criptografia para dados em repouso usando [a criptografia de dados transparente para o banco de dados SQL e o data warehouse do Azure](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Para obter mais informações sobre criptografia no Azure, confira [visão geral de criptografia do](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) Azure e [criptografia de dados do Azure-em repouso](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest).

## <a name="azure-disk-encryption"></a>Criptografia de disco do Azure

A criptografia de disco do Azure permite que você criptografe seus discos VM do Windows e do Linux como um serviço (IaaS). A criptografia de disco do Azure aproveita o recurso BitLocker do Windows e o recurso de DM criptografado do Linux para fornecer a criptografia no nível do volume para o sistema operacional e os discos de dados. Também garante que todos os dados nos discos da VM sejam criptografados em repouso no armazenamento do Azure. A criptografia de disco do Azure é integrada ao Azure Key Vault para ajudá-lo a controlar, gerenciar e auditar o uso das chaves e dos segredos de criptografia.

Para obter mais informações, consulte [recomendações de segurança para máquinas virtuais do Windows no Azure](https://docs.microsoft.com/azure/security/azure-security-disk-encryption).

## <a name="azure-storage-service-encryption"></a>Criptografia de serviço de armazenamento do Azure

Com a [criptografia de serviço de armazenamento do Azure](https://docs.microsoft.com/azure/storage/storage-service-encryption), o armazenamento do Azure criptografa automaticamente os dados antes de mantê-los para armazenamento e descriptografa os dados antes da recuperação. Os processos de criptografia, descriptografia e gerenciamento de chaves são totalmente transparentes aos usuários. A criptografia do serviço de armazenamento do Azure pode ser usada para o [armazenamento de blob do Azure](https://azure.microsoft.com/services/storage/blobs/) e [arquivos do Azure](https://azure.microsoft.com/services/storage/files/). Você também pode usar chaves de criptografia gerenciadas pela Microsoft com a criptografia de serviço de armazenamento do Azure ou pode usar suas próprias chaves de criptografia. (Para obter informações sobre como usar suas próprias chaves, confira [criptografia de serviço de armazenamento usando chaves gerenciadas pelo cliente no Azure Key Vault](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys). Para obter informações sobre como usar chaves gerenciadas pela Microsoft, confira [criptografia de serviço de armazenamento para dados em repouso](https://docs.microsoft.com/azure/storage/storage-service-encryption). Além disso, você pode automatizar o uso de criptografia. Por exemplo, você pode habilitar ou desabilitar a criptografia de serviço de armazenamento por meio de programação em uma conta de armazenamento usando a [API REST do provedor de recursos de armazenamento do Azure](https://msdn.microsoft.com/library/azure/mt163683.aspx), a [biblioteca de cliente do provedor de recursos de armazenamento para .net](https://msdn.microsoft.com/library/azure/mt131037.aspx), o [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)ou a [CLI do Azure](https://docs.microsoft.com/azure/storage/storage-azure-cli).

Alguns serviços do Office 365 usam o Azure para armazenar dados. Por exemplo, dados de repositório do SharePoint Online e do OneDrive for Business no armazenamento de blob do Azure e o Microsoft Teams armazena dados para seu serviço de chat em tabelas, BLOBs e filas. Além disso, o recurso de Pontuação de conformidade no centro de conformidade da Microsoft 365 armazena os dados inseridos pelo cliente, que são armazenados no formato criptografado no banco de dados [do Azure Cosmos](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest), uma plataforma como um serviço (PaaS), um banco de dados com vários modelos globalmente distribuído. A criptografia do serviço de armazenamento do Azure criptografa os dados armazenados no armazenamento de blob do Azure e em tabelas, e a criptografia de disco do Azure criptografa dados em filas, bem como discos de máquina virtual do Windows e IaaS para fornecer criptografia de volume para o sistema operacional e o disco de dados. A solução garante que todos os dados nos discos da máquina virtual sejam criptografados em repouso no armazenamento do Azure. [A criptografia em repouso no Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) é implementada usando várias tecnologias de segurança, incluindo sistemas de armazenamento de chave segura, redes criptografadas e APIs criptografadas.

## <a name="azure-key-vault"></a>Azure Key Vault

O gerenciamento de chave segura não é apenas essencial para as práticas recomendadas de criptografia; também é essencial para proteger os dados na nuvem. O [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) permite que você criptografe chaves e pequenos segredos, como senhas que usam chaves armazenadas em módulos de segurança de hardware (HSMs). O Azure Key Vault é a solução recomendada pela Microsoft para gerenciar e controlar o acesso a chaves de criptografia usadas pelos serviços de nuvem. Permissões para acessar chaves podem ser atribuídas a serviços ou a usuários com contas do Active Directory do Azure. O Azure Key Vault alivia as organizações que precisam configurar, corrigir e manter softwares de gerenciamento de chaves e HSMs. Com o Azure Key Vault, a Microsoft nunca vê suas chaves e os aplicativos não têm acesso direto a eles; Você mantém o controle. Você também pode importar ou gerar chaves em HSMs. As organizações que possuem uma assinatura que inclui a proteção de informações do Azure podem configurar o locatário de proteção de informações do Azure para usar uma chave gerenciada pelo cliente, [traga sua chave](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (BYOK)) e [Registre seu uso](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage).
