---
title: Saiba mais sobre as barreiras de informações no Microsoft 365
description: Use barreiras de informações para garantir a conformidade de comunicação usando o Microsoft Teams em sua organização.
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
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051873"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Saiba mais sobre as barreiras de informações no Microsoft 365

Os serviços de nuvem da Microsoft incluem poderosos recursos de colaboração e comunicação. Mas suponha que você queira restringir a comunicação e a colaboração entre dois grupos para evitar que um conflito de interesse ocorra em sua organização. Ou talvez você queira restringir a comunicação e a colaboração entre determinadas pessoas dentro da sua organização para proteger informações internas. O Microsoft 365 permite comunicação e colaboração entre grupos e organizações, portanto, há uma maneira de restringir a comunicação e a colaboração entre grupos específicos de usuários quando necessário? Com barreiras de informações, você pode!

O Microsoft Teams, o SharePoint Online e o OneDrive for Business suportam barreiras de informações. Supondo [](#required-licenses-and-permissions) que sua assinatura inclua barreiras de informações, um administrador de conformidade ou barreiras de informações pode definir políticas para permitir ou impedir comunicações entre grupos de usuários no Microsoft Teams. As políticas de barreira de informações podem ser usadas para situações como estas:

- O usuário no grupo de comerciantes de dia não deve se comunicar ou compartilhar arquivos com a equipe de marketing
- Os funcionários financeiros que trabalham em informações confidenciais da empresa não devem se comunicar ou compartilhar arquivos com determinados grupos em sua organização
- Uma equipe interna com material de segredo comercial não deve chamar ou conversar online com pessoas em determinados grupos em sua organização
- Uma equipe de pesquisa só deve chamar ou conversar online com uma equipe de desenvolvimento de produtos
- Um site para o grupo de comerciantes de dia não deve ser compartilhado ou acessado por qualquer pessoa fora do grupo de operadores de dia

> [!IMPORTANT]
> Barreiras de informações ***só oferece suporte** a restrições _ de duas vias. Restrições de uma maneira, como o marketing, podem se comunicar e colaborar com operadores de dia, mas os operadores de dia não podem se comunicar e colaborar com marketing _* não tem _suporte_**.

Para todos esses cenários de exemplo (e muito mais), as políticas de barreira de informações podem ser definidas para impedir ou permitir comunicações e colaboração no Microsoft Teams, SharePoint Online e OneDrive. Essas políticas podem impedir que as pessoas telefonem ou conversem com aqueles que não devem ou permitem que as pessoas se comuniquem apenas com grupos específicos no Microsoft Teams. Com políticas de barreira de informações em vigor, sempre que os usuários cobertos por essas políticas tentarem se comunicar e colaborar com outras pessoas no Microsoft Teams, as verificações do SharePoint Online ou do OneDrive são feitas para impedir (ou permitir) a comunicação e a colaboração (conforme definido pelas políticas de barreira de informações).

Para saber mais sobre a experiência do usuário com barreiras de informações, consulte:

- [Barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barreiras de informações no SharePoint Online](/sharepoint/information-barriers)
- [Barreiras de informações no OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Atualmente, as barreiras de informações não se aplicam às comunicações de email. Além disso, as barreiras de informações são independentes dos limites [de conformidade.](set-up-compliance-boundaries.md)<p> Antes de definir e aplicar políticas de barreira de informações, certifique-se de que sua organização não tenha políticas de livro de endereços do [Exchange](/exchange/address-books/address-book-policies/address-book-policies) em vigor. (As barreiras de informações se baseiam nas políticas do livro de endereços.)

## <a name="what-happens-with-information-barriers"></a>O que acontece com barreiras de informações

Quando as políticas de barreira de informações estão em uso, as pessoas que não devem se comunicar ou compartilhar arquivos com outros usuários específicos não poderão encontrar, selecionar, conversar ou chamar esses usuários. Com barreiras de informações, verificações são realizadas para impedir a comunicação e a colaboração não autorizadas. 

As barreiras de informações se aplicam ao Microsoft Teams (chats e canais), Ao SharePoint Online e ao OneDrive. No Microsoft Teams, as políticas de barreira de informações determinam e impedem os seguintes tipos de comunicações não autorizadas:

- Pesquisando itens que um usuário pode acessar
- Adicionar um novo membro à equipe
- Iniciar uma sessão de chat com alguém
- Iniciar um chat em grupo
- Convide alguém para participar de uma reunião
- Compartilhamento de uma pasta
- Fazendo uma chamada
- Compartilhando um arquivo com outro usuário
- Acesso ao arquivo por meio do link de compartilhamento

Se as pessoas envolvidas estão incluídas em uma política de barreira de informações para impedir a atividade, elas não poderão continuar. Além disso, potencialmente, todos os incluídos em uma política de barreira de informações podem ser impedidos de se comunicar com outras pessoas no Microsoft Teams. Quando as pessoas afetadas pelas políticas de barreira de informações fazem parte da mesma equipe ou chat em grupo, elas podem ser removidas dessas sessões de chat e a comunicação posterior com o grupo pode não ser permitida.

Para saber mais sobre a experiência do usuário com barreiras de informações, consulte [barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

No SharePoint Online e no OneDrive, as políticas de barreira de informações determinam e impedem os seguintes tipos de colaborações não autorizadas:

- Adicionar um membro a um site
- Acessando site ou conteúdo por um usuário
- Compartilhamento de site ou conteúdo com outro usuário
- Pesquisar um site

Para saber mais sobre a experiência do usuário com barreiras de informações, consulte [barreiras de informações no SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

As barreiras de informações estão sendo implantadas agora e estão incluídas em assinaturas, como:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Conformidade Avançada do Office 365
- Microsoft 365 Compliance E5/A5
- Gerenciamento de riscos do Microsoft 365 Insider

Para obter mais informações, consulte Diretrizes de licenciamento do [Microsoft 365 para conformidade & segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Para [definir ou editar políticas de barreira de](information-barriers-policies.md)informações, você deve ter uma das seguintes funções:

- Administrador global do Microsoft 365
- Administrador global do Office 365
- Administrador de conformidade
- Gerenciamento de Conformidade do IB

(Para saber mais sobre funções e permissões, consulte [Permissions in the Office 365 Security & Compliance Center](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).)

Você deve estar familiarizado com os cmdlets do PowerShell para definir, validar ou editar políticas de barreira de informações. Embora forneçamos vários exemplos de cmdlets do PowerShell no artigo [how-to](information-barriers-policies.md), você precisará saber outros detalhes, como parâmetros, para sua organização.

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre as barreiras de informações no Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Saiba mais sobre as barreiras de informações no SharePoint Online](/sharepoint/information-barriers)
- [Saiba mais sobre as barreiras de informações no OneDrive](/onedrive/information-barriers)
- [Consulte os atributos que podem ser usados para políticas de barreira de informações](information-barriers-attributes.md)
- [Definir políticas para barreiras de informações](information-barriers-policies.md)
- [Editar (ou remover) políticas de barreira de informações](information-barriers-edit-segments-policies.md)