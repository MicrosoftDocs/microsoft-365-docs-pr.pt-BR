---
title: Criptografia no Microsoft Cloud
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
description: Neste artigo, leia uma visão geral das várias formas de criptografia usadas para manter os dados do cliente seguros na nuvem da Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214269"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Criptografia no Microsoft Cloud

Os dados do cliente nos serviços de nuvem corporativos da Microsoft são protegidos por uma variedade de tecnologias e processos, incluindo várias formas de criptografia. (Os dados do cliente neste documento incluem o conteúdo da caixa de correio do Exchange Online, o corpo do email, as entradas de calendário e o conteúdo de anexos de email e, se aplicável, o conteúdo do site do Skype for Business), o conteúdo do site do SharePoint Online e os arquivos armazenados nos sites e arquivos carregados no OneDrive for Business ou no Skype for Business.) A Microsoft usa vários métodos, protocolos e codificações de criptografia em seus produtos e serviços para ajudar a fornecer um caminho seguro para os dados do cliente percorrerem nossos serviços de nuvem e para ajudar a proteger a confidencialidade dos dados do cliente armazenados em nossos serviços de nuvem. A Microsoft usa alguns dos protocolos de criptografia mais seguros e fortes disponíveis para fornecer barreiras contra o acesso não autorizado aos dados do cliente. O gerenciamento adequado de chaves também é um elemento essencial das práticas recomendadas de criptografia, e a Microsoft trabalha para garantir que todas as chaves de criptografia gerenciadas pela Microsoft sejam protegidas corretamente.

Independentemente da configuração do cliente, os dados do cliente armazenados nos serviços de nuvem empresarial da Microsoft são protegidos usando uma ou mais formas de criptografia. (A validação de nossa política de criptografia e sua imposição é verificada independentemente por vários auditores de terceiros, e os relatórios dessas auditorias estão disponíveis no Portal de Confiança [do](https://aka.ms/stp)Serviço.

A Microsoft fornece tecnologias do lado do serviço que criptografam dados do cliente em repouso e em trânsito. Por exemplo, para dados de cliente em repouso, o Microsoft Azure usa [o BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) e o [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)e o Microsoft 365 usa o BitLocker, a Criptografia do Serviço de Armazenamento do [Azure,](https://docs.microsoft.com/azure/)o Gerenciador de Chaves [Distribuídas](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) e a criptografia de serviço do Microsoft 365. Para dados do cliente em trânsito, o Azure, o Office 365, o Suporte Comercial da Microsoft, o Microsoft Dynamics 365, o Microsoft Power BI e o Visual Studio Team Services usam protocolos de transporte seguros padrão do setor, como iPsec (Internet Protocol Security) e TLS (Transport Layer Security), entre datacenters da Microsoft e entre dispositivos de usuário e datacenters da Microsoft.

Além do nível de linha de base de segurança criptográfica fornecido pela Microsoft, nossos serviços de nuvem também incluem opções de criptografia adicionais que você pode gerenciar. Por exemplo, você pode habilitar a criptografia para tráfego entre suas máquinas virtuais (VMs) do Azure e seus usuários. Com as Redes Virtuais do [Azure,](https://azure.microsoft.com/services/virtual-network/)você pode usar o protocolo IPsec padrão do setor para criptografar o tráfego entre seu gateway VPN corporativo e o Azure, bem como entre as VMs localizadas em sua Rede Virtual. Além disso, os novos recursos de Criptografia de Mensagem do [Office 365](set-up-new-message-encryption-capabilities.md) permitem que você envie emails criptografados para qualquer pessoa.

De acordo com o Padrão de Segurança Operacional da Infraestrutura de Chave Pública, que é um componente da Política de Segurança da [Microsoft,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)a Microsoft aproveita os recursos criptográficos incluídos no sistema operacional Windows para certificados e mecanismos de autenticação, que incluem o uso de módulos criptográficos que atendem ao padrão FIPS 140-2 do governo dos EUA. [](https://csrc.nist.gov/publications/PubsFIPS.html) (Os números de certificado NIST relevantes para a Microsoft podem ser encontrados em https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [OBSERVAÇÃO] Para acessar a Política de Segurança da Microsoft como um recurso, você deve entrar usando sua conta comercial ou de estudante. Se você ainda não tiver uma assinatura, poderá se inscrever para uma [avaliação gratuita.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

O FIPS 140-2 é um padrão projetado especificamente para validar módulos de produtos que implementam criptografia em vez dos produtos que os utilizam. Os módulos criptográficos implementados em um serviço podem ser certificados para atender aos requisitos de força de hash, gerenciamento de chaves e outros recursos. Sempre que os recursos criptográficos são empregados para proteger a confidencialidade, a integridade ou a disponibilidade de dados nos serviços de nuvem da Microsoft, os módulos e codificações usados atendem ao padrão FIPS 140-2.

A Microsoft certifica os módulos criptográficos subjacentes usados em nossos serviços de nuvem com cada nova versão do sistema operacional Windows:

- Azure e Azure U.S. Government
- Dynamics 365 e Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense

A criptografia de dados em repouso do cliente é fornecida por várias tecnologias do lado do serviço, incluindo BitLocker, DKM, Criptografia de Serviço de Armazenamento do Azure e criptografia de serviço no Exchange Online, Skype for Business, OneDrive for Business e SharePoint Online. A criptografia de serviço do Office 365 inclui uma opção para usar chaves de criptografia gerenciadas pelo cliente armazenadas no Azure Key Vault. Essa opção de chave gerenciada pelo cliente, chamada de Chave do [Cliente,](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)está disponível para Exchange Online, SharePoint Online, Skype for Business e OneDrive for Business.

Para dados do cliente em trânsito, todos os servidores do Office 365 negociam sessões seguras usando o TLS por padrão com máquinas cliente para proteger os dados do cliente.  Isso se aplica a protocolos em qualquer dispositivo usado por clientes, como o Skype for Business, o Outlook e o Outlook na Web, clientes móveis e navegadores da Web.

(Todos os servidores voltados para o cliente negociam com o TLS 1.2 por padrão, mas também damos suporte à negociação para um padrão inferior, se necessário.)

## <a name="related-links"></a>Links relacionados

- [Criptografia no Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) para Criptografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Criptografia de serviço do Office 365](office-365-service-encryption.md)
- [Criptografia do Office 365 para Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Criptografia de dados em trânsito](office-365-encryption-for-data-in-transit.md)
- [Recursos de criptografia de gerenciamento de cliente](office-365-customer-managed-encryption-features.md)
- [Riscos e proteções de criptografia](office-365-encryption-risks-and-protections.md)
- [Criptografia no Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
