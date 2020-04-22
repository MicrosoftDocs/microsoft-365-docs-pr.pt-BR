---
title: Criptografia de serviço com a chave do cliente
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
description: Com a chave do cliente, você controla as chaves de criptografia da sua organização e, em seguida, configura o Microsoft 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft.
ms.openlocfilehash: 701dc306a81e12db7dd1062d2a840621b710abd3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635587"
---
# <a name="service-encryption-with-customer-key"></a>Criptografia de serviço com a chave do cliente

O Microsoft 365 fornece a linha de base e a criptografia no nível do volume habilitadas por meio do BitLocker e do DKM (Distributed Key Manager). O Microsoft 365 oferece uma camada adicional de criptografia no nível do aplicativo para seu conteúdo. Este conteúdo inclui dados do Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e arquivos do teams. Essa camada adicional de criptografia é chamada de criptografia de serviço.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Como a criptografia de serviço, BitLocker e chave do cliente trabalham em conjunto

A criptografia de serviço garante que o conteúdo em repouso seja criptografado na camada do aplicativo. **Seus dados são sempre criptografados em repouso no serviço do Microsoft 365 com o BitLocker e o DKM**. Para obter mais informações, consulte as informações sobre segurança, privacidade e conformidade e como o [Exchange Online protege seus segredos de email](exchange-online-secures-email-secrets.md). A chave do cliente oferece proteção adicional contra a exibição de dados por sistemas não autorizados ou pessoal e complementa a criptografia de disco BitLocker nos datacenters da Microsoft. A criptografia de serviço não é destinada a impedir que os funcionários da Microsoft acessem dados do cliente. O principal objetivo é ajudar os clientes a cumprir as obrigações normativas ou de conformidade para controlar chaves raiz. Os clientes autorizam explicitamente os serviços do O365 a usar suas chaves de criptografia para fornecer serviços de nuvem de valor adicionado, como eDiscovery, Antimalware, antispam, indexação de pesquisa, etc.

A chave do cliente é criada na criptografia de serviço e permite que você forneça e controle as chaves de criptografia. A Microsoft 365 usa essas chaves para criptografar seus dados em repouso, conforme descrito nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx). A chave do cliente ajuda você a cumprir as obrigações de conformidade, pois você controla as chaves de criptografia que o Microsoft 365 usa para criptografar e descriptografar dados.
  
A chave do cliente aprimora a capacidade de sua organização atender às exigências de requisitos de conformidade que especificam a principal organização com o provedor de serviços de nuvem. Com a chave do cliente, você fornece e controla as chaves de criptografia raiz dos seus dados do Microsoft 365 em repouso no nível do aplicativo. Como resultado, você exercerá controle sobre as chaves da sua organização. Se você decidir sair do serviço, revogar o acesso às chaves raiz da sua organização. Para todos os serviços do Microsoft 365, revogar o acesso às chaves é a primeira etapa no caminho para a exclusão de dados. Ao revogar o acesso às chaves, os dados são ilegíveis ao serviço.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>A chave do cliente criptografa dados em repouso no Office 365

Usando chaves fornecidas, a chave do cliente criptografa:

- Os arquivos do SharePoint Online, do OneDrive for Business e do teams.
- Arquivos carregados no OneDrive for Business.
- Conteúdo de caixa de correio do Exchange Online, incluindo conteúdo de corpo de email, entradas de calendário e conteúdo de anexos de email.
- Conversas de texto do Skype for Business.

No momento, não oferecemos controle de cliente das chaves de criptografia para a transmissão de reunião do Skype e carregamentos de conteúdo de reunião do Skype. Em vez disso, esse conteúdo é criptografado junto com todos os outros conteúdos no Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Chave do cliente com implantações híbridas

A chave do cliente só criptografa dados em repouso na nuvem. A chave do cliente não funciona para proteger seus arquivos e caixas de correio locais. Você pode criptografar seus dados locais usando outro método, como o BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Sobre a DEP (política de criptografia de dados)

Uma política de criptografia de dados define a hierarquia de criptografia para criptografar dados usando cada uma das chaves que você fornecer, bem como a chave de disponibilidade protegida pela Microsoft. Você cria DEPs usando cmdlets do PowerShell, que são diferentes para cada serviço e atribuem esses DEPs para criptografar dados de aplicativo. Por exemplo:

**Exchange Online e Skype for Business** Você pode criar até 50 DEPs por locatário. Você associa DEPs às suas chaves de cliente no Azure Key Vault e, em seguida, atribui DEPs às caixas de correio individuais. Ao atribuir uma DEP a uma caixa de correio:

- a caixa de correio está marcada para uma movimentação de caixa de correio. Com base em prioridades no Microsoft 365 conforme descrito aqui, [mova as solicitações no serviço Microsoft 365](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- A criptografia ocorre enquanto a caixa de correio é movida. Permitir que 72 horas para a caixa de correio sejam criptografadas com a nova DEP. Se as caixas de correio não são criptografadas após esperar 72 horas a partir do momento em que você atribuiu a DEP, entre em contato com a Microsoft.

Posteriormente, você pode atualizar a DEP ou atribuir uma DEP diferente à caixa de correio, conforme descrito em [Manage Customer key for Office 365](customer-key-manage.md). Cada caixa de correio deve ter licenças apropriadas para atribuir uma DEP. Para obter mais informações sobre licenciamento, consulte [antes de configurar a chave do cliente](customer-key-set-up.md#before-you-set-up-customer-key).

**Arquivos do SharePoint Online, do onedrive for Business e do teams** Se você estiver usando o recurso multigeográfico, poderá criar até uma DEP por geografia para sua organização. Você pode usar diferentes chaves de cliente para cada geografia. Se você não estiver usando o recurso multigeográfico, só poderá criar uma DEP por locatário. Quando você atribui a DEP, a criptografia começa automaticamente, mas pode levar algum tempo para ser concluída. Confira os detalhes na [chave configurar cliente](customer-key-set-up.md).

## <a name="leaving-the-service"></a>Sair do serviço

A chave do cliente ajuda você a cumprir as obrigações de conformidade, permitindo revogar as chaves quando você sair do serviço do Microsoft 365. Quando você revoga as chaves como parte da saída do serviço, a chave de disponibilidade é excluída, resultando na exclusão criptográfica dos dados. A exclusão criptográfica reduz o risco de remanence de dados que é importante para atender às obrigações de segurança e conformidade. Para obter informações sobre o processo de limpeza de dados e revogação de chaves, confira [revogar suas chaves e iniciar o processo de caminho de limpeza de dados](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

### <a name="encryption-ciphers-used-by-customer-key"></a>Codificações de criptografia usadas pela chave do cliente

A chave do cliente usa uma variedade de codificações de criptografia para criptografar chaves conforme mostrado nas figuras a seguir.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o Exchange Online e o Skype for Business

![Codificações de criptografia para a chave do cliente do Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Codificações de criptografia usadas para criptografar chaves para os arquivos do SharePoint Online, do OneDrive for Business e do teams

![Codificações de criptografia para a chave do cliente do SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artigos relacionados

- [Configurar a chave do cliente](customer-key-set-up.md)

- [Gerenciar chave do cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de serviço](office-365-service-encryption.md)
