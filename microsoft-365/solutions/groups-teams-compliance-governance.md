---
title: Opções de conformidade para o Microsoft 365 grupos, equipes e colaboração do SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba mais sobre as opções de conformidade para o Microsoft 365 grupos, equipes e colaboração do SharePoint.
ms.openlocfilehash: cc8f7391b03cc65ba66cca6cf010137e3843ab05
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662469"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opções de conformidade para o Microsoft 365 grupos, equipes e colaboração do SharePoint

O Microsoft 365 oferece um pacote completo de ferramentas para manter a conformidade à medida que os usuários colaboram. Revise essas opções e considere como elas são mapeadas para suas necessidades de negócios, a sensibilidade dos seus dados e o escopo das pessoas com as quais os usuários precisam colaborar.

A tabela a seguir fornece uma referência rápida para os controles de conformidade disponíveis no Microsoft 365. Mais informações são fornecidas nas seções a seguir.

|Categoria|Descrição|Referência|
|:-------|:----------|:--------|
|Retenção de informações|||
||Manter o conteúdo de grupos e de email do SharePoint|[Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Reter chat e mensagens|[Saiba mais sobre as políticas de retenção do Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Classificação de informações|||
||Classificar grupos e equipes|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Classificar automaticamente conteúdo confidencial|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Criptografar conteúdo confidencial|[Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Proteção de informações|||
||Evitar a perda de informações confidenciais|[Visão geral da prevenção contra perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Proteger informações confidenciais no chat.|[Prevenção de perda de dados e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||Definir as informações confidenciais da sua organização|[Tipos personalizados de informações confidenciais](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Segmentação de usuário|||
||Restringir a comunicação entre segmentos de usuário|[Barreiras de informações](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Retenção de informações

As políticas de retenção estão disponíveis para reter ou excluir itens usados para colaboração em grupos e equipes, incluindo arquivos, mensagens e emails. As políticas podem ser definidas para reter e excluir, apenas para reter ou excluir. As informações cobertas por uma política de retenção são protegidas caso o grupo ou equipe expire ou seja excluído.

A configuração de uma política de retenção para o Microsoft 365 groups abrange a caixa de correio do grupo e o site e os arquivos do SharePoint associados.

- [Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Políticas de retenção para o Teams retêm mensagens de chat e canal. Enquanto as mensagens de chat e canal são armazenadas nas caixas de correio do Exchange, elas não são afetadas pelas políticas de retenção do Exchange. Você deve definir suas políticas de retenção para aplicar a chats de equipes e mensagens de canal de equipe:

- [Saiba mais sobre as políticas de retenção do Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Políticas de retenção no Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)

Uma única política de retenção pode ser configurada para aplicar a grupos de mensagens do Microsoft 365, bate-papo em equipe e canal do teams. 

Recursos adicionais:

- [Saiba mais sobre políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Marcas de retenção e políticas de retenção](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) no Exchange

## <a name="information-classification"></a>Classificação de informações

Você pode usar rótulos de confidencialidade para controlar o acesso de convidados, a privacidade de grupo e a equipe e o acesso por dispositivos não gerenciados para grupos e equipes. Aplicando o rótulo, essas configurações são automaticamente configuradas conforme especificado pelas configurações de rótulo.

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Você pode configurar o Microsoft 365 para aplicar automaticamente rótulos de confidencialidade a arquivos e emails com base nos critérios que você especificar, incluindo a detecção de tipos de informações confidenciais ou correspondência de padrões com classificadores ferroviárias.

- [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Você pode usar rótulos de confidencialidade para criptografar arquivos, permitindo apenas aqueles com permissões para descriptografá-los e lê-los.

- [Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Configurar uma equipe com isolamento de segurança](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Recursos adicionais:

- [Saiba mais sobre rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Proteção de informações

As políticas de DLP podem impedir o compartilhamento acidental de informações confidenciais entre o SharePoint, o Exchange e o Microsoft Teams. Você pode criar políticas que especificam ações a serem tomadas (como bloqueio de acesso) com base em um conjunto de regras.

- [Visão geral da prevenção contra perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

A DLP no Teams pode ajudar a proteger informações confidenciais em mensagens de chat e de canal da equipe, excluindo mensagens que contenham informações confidenciais.

- [Prevenção de perda de dados e Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Se você tiver informações confidenciais exclusivas para sua organização, como nomes de código de projeto, você pode criar seus próprios tipos de informações confidenciais e aplicá-las às políticas de DLP para proteger o conteúdo em grupos, equipes e SharePoint.

- [Tipos personalizados de informações confidenciais](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Segmentação de usuário

Com as barreiras de informações, você pode segmentar seus dados e usuários para restringir a comunicação indesejada e a colaboração entre grupos e evitar conflitos de interesse em sua organização. As barreiras de informações permitem que você crie políticas para permitir ou impedir a colaboração de arquivos, chat, chamadas ou convites de reunião entre grupos de pessoas em sua organização.

- [Barreiras de informações](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Barreiras de informação no Microsoft Teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Usar barreiras de informações com o SharePoint](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Tópicos relacionados

[Segurança e conformidade para o Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Proteger informações](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


