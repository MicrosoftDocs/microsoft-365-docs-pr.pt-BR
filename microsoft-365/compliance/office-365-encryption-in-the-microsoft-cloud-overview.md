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
ms.openlocfilehash: a8e184fbe722de674db6f9bcc47e2ab5aa0723d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926210"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Criptografia no Microsoft Cloud

Os dados do cliente nos serviços de nuvem empresarial da Microsoft são protegidos por várias tecnologias e processos, incluindo várias formas de criptografia. (Os dados do cliente neste documento incluem conteúdo de caixa de correio do Exchange Online, corpo de email, entradas de calendário e o conteúdo de anexos de email e, se aplicável, conteúdo do Skype for Business), conteúdo do site do SharePoint Online e os arquivos armazenados em sites e arquivos carregados no OneDrive for Business ou no Skype for Business.) A Microsoft usa vários métodos de criptografia, protocolos e codificações em seus produtos e serviços para ajudar a fornecer um caminho seguro para os dados do cliente percorrerem nossos serviços de nuvem e para ajudar a proteger a confidencialidade dos dados do cliente armazenados em nossos serviços de nuvem. A Microsoft usa alguns dos protocolos de criptografia mais fortes e seguros disponíveis para fornecer barreiras contra o acesso não autorizado aos dados do cliente. O gerenciamento de chaves apropriado também é um elemento essencial das práticas recomendadas de criptografia, e a Microsoft funciona para garantir que todas as chaves de criptografia gerenciadas pela Microsoft sejam protegidas corretamente.

Os dados do cliente armazenados nos serviços de nuvem empresarial da Microsoft são protegidos usando uma ou mais formas de criptografia. (A validação de nossa política de criptografia e sua imposição é verificada independentemente por vários auditores de terceiros, e os relatórios dessas auditorias estão disponíveis no Portal de Confiança do [Serviço](https://aka.ms/stp).)

A Microsoft fornece tecnologias do lado do serviço que criptografam dados do cliente em repouso e em trânsito. Por exemplo, para dados do cliente em repouso, o Microsoft Azure usa [o BitLocker](/windows/device-security/bitlocker/bitlocker-overview) e [o DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)e o Microsoft 365 usa o BitLocker, a Criptografia do Serviço de Armazenamento [do Azure,](/azure/)o [DKM](./exchange-online-secures-email-secrets.md) (Gerenciador de Chaves Distribuídas) e a criptografia de serviço do Microsoft 365. Para dados do cliente em trânsito, o Azure, o Office 365, o Suporte Comercial da Microsoft, o Microsoft Dynamics 365, o Microsoft Power BI e o Visual Studio Team Services usam protocolos de transporte seguros padrão do setor, como o IPsec (Segurança do Protocolo da Internet) e o TLS (Transport Layer Security), entre datacenters da Microsoft e entre dispositivos de usuário e datacenters da Microsoft.

Além do nível de linha de base de segurança criptográfica fornecida pela Microsoft, nossos serviços de nuvem também incluem opções de criptografia que você pode gerenciar. Por exemplo, você pode habilitar a criptografia para tráfego entre suas máquinas virtuais do Azure (VMs) e seus usuários. Com [as Redes Virtuais do Azure,](https://azure.microsoft.com/services/virtual-network/)você pode usar o protocolo IPsec padrão do setor para criptografar o tráfego entre o gateway VPN corporativo e o Azure. Você também pode criptografar o tráfego entre as VMs em sua rede virtual. Além disso, os novos recursos de Criptografia de Mensagens do [Office 365](set-up-new-message-encryption-capabilities.md) permitem que você envie emails criptografados para qualquer pessoa.

Seguindo o Padrão de Segurança Operacional da Infraestrutura de Chave Pública, que é um componente da Política de Segurança da [Microsoft,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)a Microsoft usa os recursos criptográficos incluídos no sistema operacional Windows para certificados e mecanismos de autenticação. Esses mecanismos incluem o uso de módulos criptográficos que atendem ao padrão FIPS [(Federal Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 do governo dos EUA. Você pode pesquisar os números de certificado NIST relevantes para a Microsoft usando o CMVP do Programa de Validação [de Módulo Criptográfico](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search).

> [OBSERVAÇÃO] Para acessar a Política de Segurança da Microsoft como recurso, você deve entrar usando sua conta de trabalho ou de estudante. Se você ainda não tiver uma assinatura, [poderá inscrever-se para uma avaliação gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

O FIPS 140-2 é um padrão projetado especificamente para validar módulos de produto que implementam criptografia em vez dos produtos que os usam. Os módulos criptográficos implementados dentro de um serviço podem ser certificados como atender aos requisitos de força de hash, gerenciamento de chaves e outros produtos. Os módulos criptográficos e as codificações usadas para proteger a confidencialidade, integridade ou disponibilidade de dados nos serviços de nuvem da Microsoft atendem ao padrão FIPS 140-2.

A Microsoft certifica os módulos criptográficos subjacentes usados em nossos serviços de nuvem a cada nova versão do sistema operacional Windows:

- Governo dos EUA do Azure e do Azure
- Dynamics 365 e Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense

A criptografia de dados do cliente em repouso é fornecida por várias tecnologias do lado do serviço, incluindo BitLocker, DKM, Criptografia de Serviço de Armazenamento do Azure e criptografia de serviço no Exchange Online, Skype for Business, OneDrive for Business e SharePoint Online. A criptografia de serviço do Office 365 inclui uma opção para usar chaves de criptografia gerenciadas pelo cliente armazenadas no Azure Key Vault. Essa opção de chave gerenciada pelo cliente, chamada [Chave](./customer-key-overview.md)do Cliente, está disponível para Exchange Online, SharePoint Online, Skype for Business e OneDrive for Business.

Para dados do cliente em trânsito, todos os servidores do Office 365 negociam sessões seguras usando TLS por padrão com máquinas cliente para proteger dados do cliente. Por exemplo, o Office 365 negociará sessões seguras para Skype for Business, Outlook e Outlook na Web, clientes móveis e navegadores da Web.

(Todos os servidores voltados para o cliente negociam com o TLS 1.2 por padrão.)

## <a name="related-links"></a>Links relacionados

- [Criptografia no Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) para Criptografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Criptografia de serviço do Office 365](office-365-service-encryption.md)
- [Criptografia do Office 365 para Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](./n/compliance/assurance/assurance-encryption-for-microsoft-365-services)
- [Criptografia de dados em trânsito](/compliance/assurance/assurance-encryption-in-transit)
- [Recursos de criptografia de gerenciamento de cliente](office-365-customer-managed-encryption-features.md)
- [Riscos e proteções de criptografia](office-365-encryption-risks-and-protections.md)
- [Criptografia no Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)