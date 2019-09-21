---
title: Visão geral das barreiras de informações
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use as barreiras de informação para garantir a conformidade de comunicação usando o Microsoft Teams em sua organização.
ms.openlocfilehash: c4a9213e74129126da0cbc41b7bc210a10b34db2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072728"
---
# <a name="information-barriers"></a>Barreiras de informações

## <a name="overview"></a>Visão geral

Os serviços de nuvem da Microsoft incluem recursos avançados de comunicação e colaboração. Mas suponha que você deseja restringir as comunicações entre dois grupos para evitar um conflito de interesse de ocorrer em sua organização. Ou, talvez você queira restringir as comunicações entre determinadas pessoas dentro da sua organização para proteger informações internas. A Microsoft 365 permite a comunicação e a colaboração entre grupos e organizações, portanto, há uma maneira de restringir as comunicações entre grupos específicos de usuários quando necessário? Com as barreiras de informação, você pode! 

As barreiras de informação estão sendo lançadas agora, começando com o Microsoft Teams. Supondo que sua [assinatura](#required-licenses-and-permissions) inclua barreiras de informação, um administrador de conformidade ou barreiras de informações pode definir políticas para permitir ou impedir a comunicação entre grupos de usuários no Microsoft Teams. As políticas de barreira de informações podem ser usadas para situações como estas:

- Um dia dos traders não pode ligar para alguém na equipe de marketing
- O pessoal financeiro que trabalha em informações confidenciais da empresa não pode receber chamadas de determinados grupos dentro de sua organização
- Uma equipe interna com material secreto comercial não pode ligar ou bater papo com pessoas de determinados grupos de sua organização
- Uma equipe de pesquisa pode apenas ligar ou conversar online com uma equipe de desenvolvimento de produtos

Para todos esses cenários de exemplo (e mais), as políticas de barreira de informações podem ser definidas para impedir ou permitir comunicações no Microsoft Teams. Essas políticas podem impedir que as pessoas chamem ou chat com as que elas não deveriam ou permitir que as pessoas se comuniquem somente com grupos específicos no Microsoft Teams. Com as políticas de barreira de informações em vigor, sempre que os usuários que estão cobertos por essas políticas tentarem se comunicar com outras pessoas no Microsoft Teams, as verificações são realizadas para impedir (ou permitir) a comunicação (conforme definido pelas políticas de barreira de informações). Para saber mais sobre a experiência do usuário com barreiras de informações, confira [barreiras de informações no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> Atualmente, as barreiras de informação não se aplicam às comunicações por email ou ao compartilhamento de arquivos por meio do SharePoint Online ou do OneDrive. Além disso, as barreiras de informação são independentes dos [limites de conformidade](tagging-and-assessment-in-advanced-ediscovery.md).<p>Antes de definir e aplicar as políticas de barreira de informações, certifique-se de que sua organização não tenha [diretivas de catálogo de endereços do Exchange](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) em vigor. (As barreiras de informação são baseadas nas políticas do catálogo de endereços.) 

## <a name="what-happens-with-information-barriers"></a>O que acontece com as barreiras de informação

Quando as políticas de barreira de informações estão vigentes, as pessoas que não devem se comunicar com outros usuários específicos não poderão localizar, selecionar, bater papo ou chamar esses usuários. Com as barreiras de informação, os cheques estão vigentes para impedir a comunicação não autorizada.

Inicialmente, as barreiras de informações se aplicam apenas a chat e canais do Microsoft Teams. No Microsoft Teams, as políticas de barreira de informações determinam e impedem os seguintes tipos de comunicações não autorizadas:
- Procurando um usuário
- Adicionar um membro a uma equipe
- Iniciar uma sessão de chat com alguém
- Iniciar um chat de grupo
- Convidar alguém para participar de uma reunião
- Compartilhar uma tela
- Fazendo uma chamada 

Se as pessoas envolvidas estiverem incluídas em uma política de barreira de informações para impedir a atividade, elas não poderão continuar. Além disso, possivelmente, todos incluídos em uma política de barreira de informações podem ser impedidos de se comunicar com outras pessoas no Microsoft Teams. Quando as pessoas afetadas por políticas de barreira de informações fazem parte do mesmo bate-papo de grupo ou equipe, elas podem ser removidas dessas sessões de chat e a comunicação adicional com o grupo pode não ser permitida.

Para saber mais sobre a experiência do usuário com barreiras de informações, confira [barreiras de informações no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

As barreiras de informação estão sendo lançadas agora e estão incluídas em assinaturas, como:

- Microsoft 365 E5
- Office 365 e5
- Conformidade Avançada do Office 365
- Conformidade e proteção de informações do Microsoft 365 e5

Para obter mais detalhes, consulte [soluções de conformidade](https://products.office.com/business/security-and-compliance/compliance-solutions).

Para [definir ou editar as políticas de barreira de informações](information-barriers-policies.md), você deve ter uma das seguintes funções:

- Administrador global do Microsoft 365
- Administrador global do Office 365
- Administrador de conformidade
- Gerenciamento de conformidade IB (esta é uma nova função!)

(Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade & segurança do Office 365](../security/office-365-security/protect-against-threats.md).)

Você deve estar familiarizado com os cmdlets do PowerShell para definir, validar ou editar as políticas de barreira de informações. Embora forneçamos vários exemplos de cmdlets do PowerShell no [artigo de instruções](information-barriers-policies.md), você precisará saber detalhes adicionais, como parâmetros, para sua organização.

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre as barreiras de informação no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [Ver os atributos que podem ser usados para políticas de barreira de informações](information-barriers-attributes.md)

- [Definir políticas para barreiras de informações](information-barriers-policies.md)

- [Editar (ou remover) políticas de barreira de informações](information-barriers-edit-segments-policies.md.md) 

