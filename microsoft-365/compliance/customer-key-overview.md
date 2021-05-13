---
title: Criptografia do serviço com a Chave de Cliente
ms.author: krowley
author: kccross
manager: laurawi
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
description: Neste artigo, você aprenderá sobre como a criptografia de serviço funciona com a Chave do Cliente Microsoft 365.
ms.openlocfilehash: 3d0c86dbca02a66547f0ade643b745ecfc8f92cd
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344765"
---
# <a name="service-encryption-with-customer-key"></a>Criptografia do serviço com a Chave de Cliente

Microsoft 365 fornece criptografia de nível de volume e linha de base habilitada por meio do BitLocker e do Distributed Key Manager (DKM). Microsoft 365 oferece uma camada adicional de criptografia para seu conteúdo. Esse conteúdo inclui dados de Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Microsoft Teams.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Como a criptografia de serviço, BitLocker e a Chave do Cliente funcionam em conjunto

Seus dados são sempre criptografados em repouso no serviço Microsoft 365 com BitLocker e DKM. Para obter mais informações, [consulte How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md). A Chave do Cliente fornece proteção extra contra a visualização de dados por sistemas ou funcionários não autorizados e complementa BitLocker criptografia de disco nos data centers da Microsoft. A criptografia de serviço não é destinada a impedir que a equipe da Microsoft acesse seus dados. Em vez disso, a Chave do Cliente ajuda você a cumprir obrigações regulatórias ou de conformidade para controlar chaves raiz. Você autoriza explicitamente Microsoft 365 serviços de criptografia a usar suas chaves de criptografia para fornecer serviços de nuvem de valor adicionado, como Descoberta eDiscovery, anti-malware, anti-spam, indexação de pesquisa e assim por diante.

A Chave do Cliente é criada com base na criptografia de serviço e permite que você forneça e controle as chaves de criptografia. Microsoft 365 então usa essas chaves para criptografar seus dados em repouso, conforme descrito nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx). A Chave do Cliente ajuda você a cumprir as obrigações de conformidade porque você controla as chaves de criptografia que Microsoft 365 usa para criptografar e descriptografar dados.
  
A Chave do Cliente aprimora a capacidade da sua organização de atender às demandas de requisitos de conformidade que especificam as principais configurações com o provedor de serviços de nuvem. Com a Chave do Cliente, você fornece e controla as chaves de criptografia raiz para seus Microsoft 365 dados em repouso no nível do aplicativo. Como resultado, você exerce o controle sobre as chaves da sua organização.

## <a name="customer-key-with-hybrid-deployments"></a>Chave do Cliente com implantações híbridas

A Chave do Cliente criptografa apenas dados em repouso na nuvem. A Chave do Cliente não funciona para proteger suas caixas de correio e arquivos locais. Você pode criptografar seus dados locais usando outro método, como BitLocker.

## <a name="about-data-encryption-policies"></a>Sobre políticas de criptografia de dados

Uma política de criptografia de dados (DEP) define a hierarquia de criptografia. Essa hierarquia é usada pelo serviço para criptografar dados usando cada uma das chaves gerenciadas e a chave de disponibilidade protegida pela Microsoft. Crie DEPs usando cmdlets do PowerShell e atribua esses DEPs para criptografar dados do aplicativo. Há três tipos de DEPs com suporte Microsoft 365 Chave do Cliente, cada tipo de política usa cmdlets diferentes e fornece cobertura para um tipo diferente de dados. Os DEPs que você pode definir incluem:

**DEP para várias cargas de Microsoft 365 de trabalho** Esses DEPs criptografam dados em várias cargas de trabalho M365 para todos os usuários dentro do locatário. Essas cargas de trabalho incluem:

- Teams de chat (chats 1:1, chats de grupo, chats de reunião e conversas de canal)
- Teams de mídia (imagens, trechos de código, mensagens de vídeo, mensagens de áudio, imagens wiki)
- Teams de chamada e reuniões armazenadas no Teams armazenamento
- Teams de chat
- Teams sugestões de chat da Cortana
- Teams de status
- Informações de usuário e sinal para Exchange Online
- Exchange Online caixas de correio que ainda não estão criptografadas por DEPs de caixa de correio
- Dados exatos do MIP (EDM) – (esquemas de arquivo de dados, pacotes de regras e sais usados para hash dos dados confidenciais).
  Para EDM e Microsoft Teams MIP exatos, o DEP de várias cargas de trabalho criptografa novos dados a partir do momento em que você atribui o DEP ao locatário. Para Exchange Online, a Chave do Cliente criptografa todos os dados existentes e novos.

Os DEPs de várias cargas de trabalho não criptografam os seguintes tipos de dados. Em vez disso, Microsoft 365 usa outros tipos de criptografia para proteger esses dados.

- SharePoint e OneDrive for Business dados.
- Microsoft Teams arquivos e algumas Teams de chamada e reuniões salvas no OneDrive for Business e SharePoint Online são criptografados usando o DEP SharePoint Online.
- Outras Microsoft 365 cargas de trabalho, como Yammer e Planner que não são suportadas atualmente pela Chave do Cliente.
- Teams Eventos ao vivo e&A em eventos ao vivo. Para Teams, esse cenário é o único que não é criptografado pela Chave do Cliente usando DEP de várias cargas de trabalho.

Você pode criar vários DEPs por locatário, mas atribuir apenas um DEP por vez. Quando você atribui o DEP, a criptografia começa automaticamente, mas leva algum tempo para ser concluída, dependendo do tamanho do locatário.

**DEPs para Exchange Online caixas de correio** Os DEPs de Caixa de Correio fornecem um controle mais preciso sobre caixas de correio individuais dentro Exchange Online. Use DEPs de caixa de correio para criptografar dados armazenados em caixas de correio EXO de diferentes tipos, como UserMailbox, MailUser, Group, PublicFolder e Shared mailboxes. Você pode ter até 50 DEPs ativos por locatário e atribuir esses DEPs a caixas de correio individuais. Você pode atribuir um DEP a várias caixas de correio.

Por padrão, suas caixas de correio são criptografadas usando chaves gerenciadas pela Microsoft. Ao atribuir um DEP de Chave de Cliente a uma caixa de correio:

- Se a caixa de correio for criptografada usando uma DEP de várias cargas de trabalho, o serviço reegrava a caixa de correio usando a nova DEP de caixa de correio, desde que um usuário ou uma operação do sistema acesse os dados da caixa de correio.

- Se a caixa de correio já estiver criptografada usando chaves gerenciadas pela Microsoft, o serviço redeselha a caixa de correio usando a nova DEP de caixa de correio, desde que um usuário ou uma operação do sistema acesse os dados da caixa de correio.

- Se a caixa de correio ainda não estiver criptografada usando criptografia padrão, o serviço marcará a caixa de correio para uma movimentação. A criptografia ocorre depois que a movimentação é concluída. As movimentações de caixa de correio são governadas com base nas prioridades definidas para todas as Microsoft 365. Para obter mais informações, consulte [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service). Se as caixas de correio não são criptografadas dentro do tempo especificado, contate a Microsoft.

Mais tarde, você pode atualizar o DEP ou atribuir um DEP diferente à caixa de correio conforme descrito em [Gerenciar Chave](customer-key-manage.md)do Cliente para Office 365 . Cada caixa de correio deve ter licenças apropriadas para receber uma DEP. Para obter mais informações sobre licenciamento, consulte [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).

Os DEPs podem ser atribuídos a uma caixa de correio compartilhada, caixa de correio de pasta pública e Microsoft 365 de grupo para locatários que atendem ao requisito de licenciamento para caixas de correio de usuário. Você não precisa de licenças separadas para caixas de correio não específicas do usuário para atribuir o DEP de Chave do Cliente.

Para DEPs de Chave de Cliente que você atribui a caixas de correio individuais, você pode solicitar que a Microsoft limpe DEPs específicos ao sair do serviço. Para obter informações sobre o processo de limpeza de dados e revogação de chave, consulte [Revogar](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)suas chaves e iniciar o processo de caminho de limpeza de dados .

Quando você revoga o acesso às chaves como parte da saída do serviço, a chave de disponibilidade é excluída, resultando na exclusão criptográfica de seus dados. A exclusão criptográfica reduz o risco de remanência de dados, o que é importante para atender às obrigações de segurança e conformidade.

**DEP para SharePoint Online e OneDrive for Business** Essa DEP é usada para criptografar o conteúdo armazenado no SPO e OneDrive for Business, incluindo Microsoft Teams arquivos armazenados no SPO. Se você estiver usando o recurso multi-geo, poderá criar um DEP por geo para sua organização. Se você não estiver usando o recurso multi-geo, poderá criar apenas um DEP por locatário. Consulte os detalhes em [Set up Customer Key](customer-key-set-up.md).

### <a name="encryption-ciphers-used-by-customer-key"></a>Codificações de criptografia usadas pela Chave do Cliente

A Chave do Cliente usa várias codificações de criptografia para criptografar chaves, conforme mostrado nas figuras a seguir.

A hierarquia de chaves usada para DEPs que criptografam dados para várias Microsoft 365 cargas de trabalho é semelhante à hierarquia usada para DEPs para caixas de correio Exchange Online individuais. A única diferença é que a Chave de Caixa de Correio é substituída pela chave de carga Microsoft 365 carga de trabalho correspondente.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Codificações de criptografia usadas para criptografar chaves para Exchange Online e Skype for Business

![Codificações de criptografia para Exchange Online Chave do Cliente](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Codificações de criptografia usadas para criptografar chaves para SharePoint online, OneDrive for Business e Teams arquivos

![Codificações de criptografia para SharePoint Chave do Cliente Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artigos relacionados

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Sistema de Proteção de Dados do Cliente](customer-lockbox-requests.md)

- [Criptografia de Serviço](office-365-service-encryption.md)