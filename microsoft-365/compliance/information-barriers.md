---
title: Saiba mais sobre barreiras de informações no Microsoft 365
description: Use barreiras de informações para garantir a conformidade da comunicação usando o Microsoft Teams em sua organização.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ef09fbf7a517950ae182472e4b4d5ef896d65e5
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126538"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Saiba mais sobre barreiras de informações no Microsoft 365

Os serviços de nuvem da Microsoft incluem poderosos recursos de comunicação e colaboração. Mas suponha que você queira restringir a comunicação e a colaboração entre dois grupos para evitar que um conflito de interesses ocorra em sua organização. Ou talvez você queira restringir a comunicação e a colaboração entre determinadas pessoas dentro da sua organização para proteger as informações internas. O Microsoft 365 permite a comunicação e a colaboração entre grupos e organizações, portanto, existe uma maneira de restringir a comunicação e a colaboração entre grupos específicos de usuários quando necessário? Com barreiras de informações, você pode!

O Microsoft Teams, o SharePoint Online e o OneDrive for Business suportam barreiras de informações. Supondo [que sua assinatura](#required-licenses-and-permissions) inclua barreiras de informações, um administrador de conformidade ou barreiras de informações pode definir políticas para permitir ou impedir comunicações entre grupos de usuários no Microsoft Teams. As políticas de barreira de informações podem ser usadas para situações como estas:

- O usuário no grupo de comerciantes do dia não deve se comunicar ou compartilhar arquivos com a equipe de marketing
- A equipe de finanças que trabalha com informações confidenciais da empresa não deve se comunicar ou compartilhar arquivos com determinados grupos dentro da organização
- Uma equipe interna com material de segredos comerciais não deve ligar ou conversar online com pessoas de determinados grupos dentro da organização
- Uma equipe de pesquisa só deve ligar ou conversar online com uma equipe de desenvolvimento de produtos
- Um site para o grupo de comerciantes de dia não deve ser compartilhado ou acessado por qualquer pessoa fora do grupo de comerciantes de dia

> [!IMPORTANT]
> Barreiras de informações ***só oferece suporte a** restrições de duas vias. Restrições de uma via, como marketing, podem se comunicar e colaborar com comerciantes de dia, mas os comerciantes de dia não podem se comunicar e colaborar com marketing _*_não é suportado_**.

Para todos esses cenários de exemplo (e muito mais), as políticas de barreira de informações podem ser definidas para impedir ou permitir comunicações e colaboração no Microsoft Teams, SharePoint Online e OneDrive. Essas políticas podem impedir que as pessoas ligarem ou conversarem com aqueles que não deveriam ou permitir que as pessoas se comuniquem apenas com grupos específicos no Microsoft Teams. Com as políticas de barreira de informações em vigor, sempre que os usuários cobertos por essas políticas tentarem se comunicar e colaborar com outras pessoas no Microsoft Teams, as verificações do SharePoint Online ou do OneDrive são feitas para impedir (ou permitir) a comunicação e a colaboração (conforme definido pelas políticas de barreira de informações).

Para saber mais sobre a experiência do usuário com barreiras de informações, consulte:

- [Barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barreiras de informações no SharePoint Online](/sharepoint/information-barriers)
- [Barreiras de informações no OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Atualmente, as barreiras de informações não se aplicam às comunicações por email. Além disso, as barreiras de informações são independentes dos limites [de conformidade.](set-up-compliance-boundaries.md)<p> Antes de definir e aplicar políticas de barreira de informações, certifique-se de que sua organização não tenha políticas de agenda do [Exchange](/exchange/address-books/address-book-policies/address-book-policies) em vigor. (As barreiras de informações são baseadas em políticas do livro de endereços.)

## <a name="what-happens-with-information-barriers"></a>O que acontece com barreiras de informações

Quando as políticas de barreira de informações estão em uso, as pessoas que não devem se comunicar ou compartilhar arquivos com outros usuários específicos não poderão encontrar, selecionar, conversar ou ligar para esses usuários. Com barreiras de informações, as verificações são realizadas para evitar a comunicação e a colaboração não autorizadas. 

As barreiras de informações se aplica ao Microsoft Teams (chats e canais), SharePoint Online e OneDrive. No Microsoft Teams, as políticas de barreira de informações determinam e impedem os seguintes tipos de comunicações não autorizadas:

- Pesquisar um usuário
- Adicionar um membro a uma equipe
- Iniciando uma sessão de chat com alguém
- Iniciando um chat em grupo
- Convidar alguém para ingressar em uma reunião
- Compartilhando uma tela
- Fazendo uma chamada
- Compartilhando um arquivo com outro usuário
- Acesso ao arquivo por meio do link de compartilhamento

Se as pessoas envolvidas estão incluídas em uma política de barreira de informações para impedir a atividade, elas não poderão continuar. Além disso, potencialmente, todas as pessoas incluídas em uma política de barreira de informações podem ser impedidas de se comunicar com outras pessoas no Microsoft Teams. Quando as pessoas afetadas por políticas de barreira de informações fazem parte da mesma equipe ou chat em grupo, elas podem ser removidas dessas sessões de chat e a comunicação posterior com o grupo pode não ser permitida.

Para saber mais sobre a experiência do usuário com barreiras de informações, confira as [barreiras de informações no Microsoft Teams.](/MicrosoftTeams/information-barriers-in-teams)

No SharePoint Online e no OneDrive, as políticas de barreira de informações determinam e impedem os seguintes tipos de colaborações não autorizadas:

- Adicionando um membro a um site
- Acessando site ou conteúdo por um usuário
- Compartilhar site ou conteúdo com outro usuário
- Pesquisar um site

Para saber mais sobre a experiência do usuário com barreiras de informações, confira [barreiras de informações no SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Barreiras de informações estão sendo implantadas agora e estão incluídas em assinaturas, como:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Conformidade Avançada do Office 365
- Microsoft 365 Compliance E5/A5
- Gerenciamento de riscos do Microsoft 365 Insider

Para saber mais, confira as [diretrizes de licenciamento do Microsoft 365 para segurança & conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Para [definir ou editar políticas de barreira de](information-barriers-policies.md)informações, você deve ter uma das seguintes funções atribuídas:

- Administrador global do Microsoft 365
- Administrador global do Office 365
- Administrador de conformidade
- Gerenciamento de Conformidade do IB

(Para saber mais sobre funções e permissões, confira Permissões no Centro de Conformidade e Segurança [& do Office 365.)](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Você deve estar familiarizado com os cmdlets do PowerShell para definir, validar ou editar políticas de barreira de informações. Embora forneçamos vários exemplos de cmdlets do PowerShell no artigo de como fazer [isso,](information-barriers-policies.md)você precisará saber outros detalhes, como parâmetros, para sua organização.

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Saiba mais sobre barreiras de informações no SharePoint Online](/sharepoint/information-barriers)
- [Saiba mais sobre barreiras de informações no OneDrive](/onedrive/information-barriers)
- [Ver os atributos que podem ser usados para políticas de barreira de informações](information-barriers-attributes.md)
- [Definir políticas para barreiras de informações](information-barriers-policies.md)
- [Editar (ou remover) políticas de barreira de informações](information-barriers-edit-segments-policies.md)