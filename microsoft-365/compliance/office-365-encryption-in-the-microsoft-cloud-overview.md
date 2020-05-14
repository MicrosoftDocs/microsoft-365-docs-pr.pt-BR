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

Os dados do cliente nos serviços de nuvem corporativa da Microsoft são protegidos por uma variedade de tecnologias e processos, incluindo várias formas de criptografia. (Os dados do cliente neste documento incluem o conteúdo da caixa de correio do Exchange Online, o corpo do email, as entradas de calendário e o conteúdo de anexos de email e, se aplicável, conteúdo do Skype for Business), o conteúdo do site do SharePoint Online e os arquivos armazenados em sites e os arquivos carregados no OneDrive for Business ou Skype for Business. A Microsoft usa vários métodos de criptografia, protocolos e codificações em seus produtos e serviços para ajudar a fornecer um caminho seguro para que os dados do cliente viaje entre nossos serviços de nuvem e para ajudar a proteger a confidencialidade dos dados do cliente armazenados em nossos serviços de nuvem. A Microsoft usa alguns dos protocolos de criptografia mais fortes e mais seguros disponíveis para fornecer barreiras contra o acesso não autorizado aos dados do cliente. O gerenciamento de chave adequado também é um elemento essencial das práticas recomendadas de criptografia e o Microsoft Works para garantir que todas as chaves de criptografia gerenciadas pela Microsoft estejam devidamente protegidas.

Independentemente da configuração do cliente, os dados do cliente armazenados nos serviços de nuvem corporativa da Microsoft são protegidos usando uma ou mais formas de criptografia. (A validação da nossa política de criptografia e sua aplicação é verificada independentemente por vários auditores terceirizados e os relatórios dessas auditorias estão disponíveis no [portal de confiança do serviço](https://aka.ms/stp).)

A Microsoft fornece tecnologias do lado do serviço que criptografam os dados do cliente em repouso e em trânsito. Por exemplo, para dados de clientes em repouso, o Microsoft Azure usa o [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) e o [DM criptografado](https://en.wikipedia.org/wiki/Dm-crypt), e o Microsoft 365 usa BitLocker, [criptografia de serviço de armazenamento do Azure](https://docs.microsoft.com/azure/), [Gerenciamento de chave distribuída](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) e criptografia de serviço Microsoft 365. Para os dados do cliente em trânsito, o Azure, o Office 365, o suporte comercial da Microsoft, o Microsoft Dynamics 365, o Microsoft Power BI e o Visual Studio Team Services usam protocolos de transporte seguro padrão do setor, como IPsec (segurança de protocolo Internet) e TLS (Transport Layer Security), entre o Microsoft datacenters e os dispositivos de usuário e os datacenters da Microsoft

Além do nível de linha de base da segurança de criptografia fornecido pela Microsoft, nossos serviços em nuvem também incluem opções de criptografia adicionais que podem ser gerenciadas. Por exemplo, você pode habilitar a criptografia para o tráfego entre suas VMs (máquinas virtuais) do Azure e seus usuários. Com as [redes virtuais do Azure](https://azure.microsoft.com/services/virtual-network/), você pode usar o protocolo IPsec padrão da indústria para criptografar o tráfego entre o gateway VPN corporativo e o Azure, bem como entre as VMs localizadas na sua rede virtual. Além disso, os [novos recursos de criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md) permitem que você envie emails criptografados para qualquer pessoa.

De acordo com o padrão de segurança operacional de infraestrutura de chave pública, que é um componente da [política de segurança da Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), a Microsoft aproveita os recursos de criptografia incluídos no sistema operacional Windows para certificados e mecanismos de autenticação, que inclui o uso de módulos criptográficos que atendem aos [padrões](https://csrc.nist.gov/publications/PubsFIPS.html) FIPS 140-2 padrão do governo dos EUA. (Os números de certificados do NIST relevantes para a Microsoft podem ser encontrados emhttps://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> Observação Para acessar a política de segurança da Microsoft como um recurso, você deve entrar usando sua conta corporativa ou de estudante. Se você ainda não tem uma assinatura, [é possível inscrever-se em uma avaliação gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

O FIPS 140-2 é um padrão projetado especificamente para validar módulos de produto que implementam criptografia em vez de usar os produtos que os utilizam. Módulos criptográficos que são implementados em um serviço podem ser certificados como atender aos requisitos de intensidade de hash, gerenciamento de chave e semelhantes. Sempre que os recursos criptográficos são empregados para proteger a confidencialidade, integridade ou disponibilidade dos dados nos serviços de nuvem da Microsoft, os módulos e codificações usados atendem ao padrão FIPS 140-2.

A Microsoft certifica os módulos de criptografia subjacente usados em nossos serviços em nuvem com cada nova versão do sistema operacional Windows:

- Governo dos EUA do Azure e Azure
- Dynamics 365 e Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense

A criptografia de dados do cliente em repouso é fornecida por várias tecnologias do lado do serviço, incluindo BitLocker, DKM, criptografia do serviço de armazenamento do Azure e criptografia de serviço no Exchange Online, Skype for Business, OneDrive for Business e SharePoint Online. A criptografia de serviço do Office 365 inclui uma opção para usar chaves de criptografia gerenciadas pelo cliente armazenadas no Azure Key Vault. Essa opção de chave gerenciada pelo cliente, chamada de [chave do cliente](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview), está disponível para o Exchange Online, o SharePoint Online, o Skype for Business e o onedrive for Business.

Para dados do cliente em trânsito, todos os servidores do Office 365 negociam sessões seguras usando TLS por padrão com máquinas clientes para proteger os dados do cliente.  Isso se aplica a protocolos em qualquer dispositivo usado por clientes, como o Skype for Business, o Outlook e o Outlook na Web, clientes móveis e navegadores da Web.

(Todos os servidores voltados para o cliente negociam para TLS 1,2 por padrão, mas também suportamos a negociação para um padrão mais baixo, se necessário.)

## <a name="related-links"></a>Links relacionados

- [Criptografia no Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) para Criptografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Criptografia de serviço do Office 365](office-365-service-encryption.md)
- [Criptografia do Office 365 para o Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Criptografia de dados em trânsito](office-365-encryption-for-data-in-transit.md)
- [Recursos de criptografia de gerenciamento de cliente](office-365-customer-managed-encryption-features.md)
- [Riscos e proteções de criptografia](office-365-encryption-risks-and-protections.md)
- [Criptografia no Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
