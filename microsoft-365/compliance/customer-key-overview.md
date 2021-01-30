---
title: Criptografia do serviço com a Chave de Cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre como a criptografia de serviço funciona com a chave do cliente no Microsoft 365.
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058484"
---
# <a name="service-encryption-with-customer-key"></a>Criptografia do serviço com a Chave de Cliente

O Microsoft 365 fornece criptografia de nível de volume e linha de base habilitada por meio do BitLocker e do Distributed Key Manager (DKM). O Microsoft 365 oferece uma camada adicional de criptografia na camada do aplicativo para seu conteúdo. Esse conteúdo inclui dados do Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e arquivos do Teams. Essa camada adicionada de criptografia é chamada de criptografia de serviço.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Como a criptografia de serviço, o BitLocker e a Chave do Cliente funcionam juntos

A criptografia de serviço garante que o conteúdo em repouso seja criptografado na camada de serviço. **Seus dados são sempre criptografados em repouso no serviço do Microsoft 365 com BitLocker e DKM.** Para obter mais informações, consulte "Informações de segurança, privacidade e conformidade" e como o Exchange Online protegerá [seus segredos de email.](exchange-online-secures-email-secrets.md) A Chave do Cliente oferece proteção adicional contra a exibição de dados por sistemas ou funcionários não autorizados e complementa a criptografia de disco BitLocker em datacenters da Microsoft. A criptografia de serviço não foi feita para impedir que a equipe da Microsoft acesse os dados do cliente. O objetivo principal é ajudar os clientes a cumprir as obrigações regulatórias ou de conformidade para controlar as chaves raiz. Os clientes autorizam explicitamente os serviços do O365 a usarem suas chaves de criptografia para fornecer serviços de nuvem de valor agregado, como Descobertas e Descobertas, anti-malware, anti-spam, indexação de pesquisa etc.

A Chave do Cliente é criada com base na criptografia de serviço e permite que você forneça e controle as chaves de criptografia. Em seguida, o Microsoft 365 usa essas chaves para criptografar seus dados em repouso, conforme descrito nos Termos do [Online Services (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) A Chave do Cliente ajuda você a cumprir as obrigações de conformidade porque você controla as chaves de criptografia que o Microsoft 365 usa para criptografar e descriptografar dados.
  
A Chave do Cliente aprimora a capacidade da sua organização de atender às demandas de requisitos de conformidade que especificam as principais organizações com o provedor de serviços de nuvem. Com a Chave do Cliente, você fornece e controla as chaves de criptografia raiz dos dados em repouso do Microsoft 365 no nível do aplicativo. Como resultado, você exerce controle sobre as chaves da sua organização. Se você decidir sair do serviço, revoga o acesso às chaves raiz da sua organização. Para todos os serviços do Microsoft 365, revogar o acesso às chaves é a primeira etapa no caminho para a exclusão de dados. Ao revogar o acesso às chaves, os dados são ilegíveis para o serviço.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Chave do cliente criptografa dados em repouso no Office 365

Usando chaves fornecidas, a Chave do Cliente criptografa:

- Arquivos do SharePoint Online, do OneDrive for Business e do Teams.
- Arquivos carregados no OneDrive for Business.
- Conteúdo da caixa de correio do Exchange Online, incluindo conteúdo do corpo do email, entradas de calendário e o conteúdo em anexos de email.
- Conversas de texto do Skype for Business.

Atualmente, não oferecemos controle de cliente das chaves de criptografia para carregamentos de conteúdo de Transmissão de Reunião do Skype e Reunião do Skype. Em vez disso, esse conteúdo é criptografado junto com todos os outros conteúdos do Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Chave do cliente com implantações híbridas

A Chave do Cliente criptografa apenas os dados em repouso na nuvem. A Chave do Cliente não funciona para proteger suas caixas de correio e arquivos locais. Você pode criptografar seus dados locais usando outro método, como o BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Sobre a política de criptografia de dados (DEP)

Uma política de criptografia de dados define a hierarquia de criptografia para criptografar dados usando cada uma das chaves que você fornecer, bem como a chave de disponibilidade protegida pela Microsoft. Você cria DEPs usando cmdlets do PowerShell, que são diferentes para cada serviço, e atribui esses DEPs para criptografar dados de aplicativo. Por exemplo:

**Exchange Online e Skype for Business** Você pode criar até 50 DEPs por locatário. Você associa DEPs às suas Chaves do Cliente no Azure Key Vault e, em seguida, atribui DEPs a caixas de correio individuais. Quando você atribui um DEP a uma caixa de correio:

- a caixa de correio está marcada para uma movimentação de caixa de correio. Com base nas prioridades no Microsoft 365, conforme descrito aqui, [mover solicitações no serviço microsoft 365](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- A criptografia ocorre enquanto a caixa de correio é movida. Deixe 72 horas para que a caixa de correio seja criptografada com a nova DEP. Se as caixas de correio não são criptografadas após aguardar 72 horas a partir do momento em que você atribuiu a DEP, entre em contato com a Microsoft.

Posteriormente, você pode atualizar a DEP ou atribuir uma DEP diferente à caixa de correio, conforme descrito em Gerenciar chave do cliente para [o Office 365.](customer-key-manage.md) Cada caixa de correio deve ter licenças apropriadas para atribuir uma DEP. Para obter mais informações sobre licenciamento, consulte [Antes de configurar a Chave do Cliente.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> A DEP pode ser aplicada a uma caixa de correio compartilhada, caixa de correio de pasta pública e caixa de correio de grupo do Microsoft 365 para locatários que atendem ao requisito de licenciamento para caixas de correio de usuário, mesmo que alguns desses tipos de caixa de correio não possam ser uma licença atribuída (caixa de correio de pasta pública e caixa de correio de grupo do Microsoft 365) ou precisem de uma licença para aumentar o armazenamento (caixa de correio compartilhada).

**Arquivos do SharePoint Online, OneDrive for Business e Teams** Se você estiver usando o recurso multi-geo, poderá criar até um DEP por geo para sua organização. Você pode usar chaves de cliente diferentes para cada área geográfica. Se você não estiver usando o recurso multi-geo, só poderá criar uma DEP por locatário. Quando você atribui a DEP, a criptografia começa automaticamente, mas pode levar algum tempo para ser concluída. Consulte os detalhes em [Set up Customer Key](customer-key-set-up.md).

## <a name="leaving-the-service"></a>Sair do serviço

A Chave do Cliente ajuda você a cumprir as obrigações de conformidade, permitindo que você revoque suas chaves quando deixar o serviço do Microsoft 365. Quando você revoga suas chaves como parte da saída do serviço, a chave de disponibilidade é excluída, resultando na exclusão criptográfica de seus dados. A exclusão criptográfica reduz o risco de remanenciamento de dados, o que é importante para atender às obrigações de segurança e conformidade. Para obter informações sobre o processo de limpeza de dados e a revogação de chave, consulte Revogar suas chaves e iniciar o processo [de limpeza de dados.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Codificações de criptografia usadas pela Chave do Cliente

A Chave do Cliente usa uma variedade de codificações de criptografia para criptografar chaves, conforme mostrado nas figuras a seguir.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o Exchange Online e o Skype for Business

![Codificações de criptografia para a Chave de Cliente do Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Codificações de criptografia usadas para criptografar chaves para arquivos do SharePoint Online, OneDrive for Business e Teams

![Codificações de criptografia para a Chave de Cliente do SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artigos relacionados

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de Serviço](office-365-service-encryption.md)
