---
title: Configurar a colaboração segura com o Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Saiba como configurar a colaboração de conteúdo seguro no Microsoft Teams para proteger seus dados com base em sua confidencialidade.
ms.openlocfilehash: 4f2e157025f00660e77ba3377221368e37e45445
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602068"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Configurar a colaboração segura com o Microsoft 365

Ser capaz de compartilhar facilmente as informações com as pessoas certas, impedindo o supercompartilhamento é fundamental para o sucesso de uma organização. Isso inclui ser capaz de compartilhar dados confidenciais com segurança apenas com aqueles que devem ter acesso a ele. Dependendo do projeto, isso pode incluir o compartilhamento de dados confidenciais com pessoas de fora da sua organização.

Esta guia de solução de colaboração inclui dois componentes para ajudá-lo a:
- Implantar o Microsoft Teams com o nível certo de proteção para cada projeto
- Configurar o compartilhamento externo com as configurações de segurança apropriadas para cada projeto

![Implantar o Microsoft Teams com a proteção apropriada e configurar o compartilhamento externo com as configurações de segurança apropriadas](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Se as ferramentas de colaboração de conteúdo versáteis e fáceis de usar não estiverem disponíveis, os usuários irão colaborar com os documentos por email. Esse é um método de colaboração tedioso e sujeito a erros e pode aumentar o risco de compartilhamento inadequado de informações. Se as pessoas acharem as informações de compartilhamento muito difíceis, elas podem reverter o uso de produtos de consumidor que não são controlados por ela. Isso pode representar um risco ainda maior.

Com o Microsoft 365, você pode implantar o Teams com uma variedade de configurações que ajudam a:

- Proteger sua propriedade intelectual
- Habilitar a colaboração fácil
- Criar um equilíbrio entre segurança e usabilidade que aumenta a satisfação do usuário e reduz o risco de sombreamento

A maioria das organizações tem uma variedade de informações, com graus variados de sensibilidade e graus variados de impacto nos negócios se as informações forem compartilhadas incorretamente. Dependendo da sensibilidade de uma determinada informação, talvez você queira permitir o compartilhamento com:

- Qualquer pessoa (não autenticada)
- Pessoas dentro da organização
- Pessoas específicas dentro da organização
- Pessoas específicas dentro e fora da organização

Informações como folhetos de marketing destinam-se ao compartilhamento de forma ampla fora da organização. Informações como os menus da lanchonete não são destinadas para compartilhamento externo, mas não terão impacto nos negócios se tiverem sido compartilhadas externamente. Esses tipos de informações precisam de pouca ou nenhuma proteção.

Os mesmos folhetos de marketing, enquanto em desenvolvimento, podem ser compartilhados apenas dentro da organização. Nesse caso, as configurações de compartilhamento padrão no Teams podem ser suficientes.

As informações sobre um novo produto em desenvolvimento podem ser consideradas confidenciais, mesmo dentro da organização. Um grau maior de proteção pode ser apropriado nesse caso. Você pode restringir o acesso a essas informações para membros de uma equipe específica, por exemplo. Dependendo do projeto, talvez você precise colaborar com pessoas de fora da sua organização, como uma organização de fornecedor ou parceiro.

As informações que são fundamentais para o sucesso da sua organização ou têm requisitos de segurança ou de conformidade rigorosos podem exigir níveis de proteção ainda maiores.

![Escala de risco de baixo (folheto liberado) para alto (dados comerciais confidenciais)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Para todos os cenários citados acima, você pode usar o Microsoft Teams para armazenar, compartilhar e colaborar com as informações. 

Para configurar a colaboração segura, você usa estas funcionalidades e recursos da Microsoft 365.

| Produto ou componente | Capcidade ou recurso | Licenças |
|:-------|:-----|:-------|
| Microsoft defender para Office 365 | Anexos seguros para o SPO, o OneDrive e o Microsoft Teams; Documentos seguros; Links seguros para o Teams    | Microsoft 365 E1, E3 e e5 |
| SharePoint    | Políticas de compartilhamento de arquivos e sites, permissões de compartilhamento de site, links de compartilhamento, solicitações de acesso, configurações de compartilhamento de convidado de site | Microsoft 365 E1, E3 e e5 |
| Microsoft Teams   | Acesso de convidados, equipes privadas, canais privados | Microsoft 365 E1, E3 e e5 |
| Conformidade com o Microsoft 365  | Rótulos de confidencialidade    | Microsoft 365 E3 e E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Usando o Microsoft Teams para todos os tipos de dados

Para gerenciar o acesso a informações com diferentes sensitivities, desenvolvemos [três níveis diferentes de proteção para o Microsoft Teams](configure-teams-three-tiers-protection.md). Você pode personalizar qualquer uma dessas camadas para atender melhor às necessidades ou à sua empresa. 

![Imagem em miniatura para o cartaz de arquitetura lógica do Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Esses níveis-de *linha de base*, *confidenciais* e *altamente confidenciais* aumentam gradualmente as proteções que ajudam a evitar o supercompartilhamento e o possível vazamento de informações, conforme mostrado na tabela a seguir.

|-|**Camada de linha de base**|**Camada confidencial**|**Camada altamente confidencial**|
|:--|:-----------|:------------|:-------------------|
|Equipe pública ou privada|Ambos|Private|Private|
|Compartilhamento não autenticado|Blocked|Blocked|Blocked|
|Compartilhamento de arquivos|Permitido|Permitido|Somente proprietários de equipe podem compartilhar.|
|Associação de equipe|Qualquer pessoa pode ingressar em equipes públicas.<br>Aprovação do proprietário da equipe necessária para ingressar em equipes privadas.|Aprovação do proprietário da equipe necessária para ingressar.|Aprovação do proprietário da equipe necessária para ingressar.|
|Criptografia de documentos|||Disponível com rótulo de confidencialidade|
|Compartilhamento de convidados|Permitido|Pode ser permitido ou bloqueado|Pode ser permitido ou bloqueado|
|Dispositivos não gerenciados|Sem restrição|Acesso somente Web|Blocked|

A configuração dessas camadas envolve:

- Definindo configurações no Teams para acesso de convidados e canais privados
- Definindo configurações no site do SharePoint associado de uma equipe para compartilhamento interno e de convidados, solicitações de acesso e links de compartilhamento
- Para as camadas *confidenciais* e *altamente confidenciais* , configurar rótulos de sensibilidade para classificar as equipes e controlar o compartilhamento de convidados e o acesso de dispositivos não gerenciados
- Para a camada *altamente confidencial* , configurar um rótulo de confidencialidade para criptografar os documentos aos quais ele é aplicado

Comece com a camada da linha de base e, em seguida, adicione equipes que usam as camadas *confidenciais* e *altamente confidenciais* , conforme necessário, para ajudar a proteger as informações da sua organização. Confira estes recursos para começar:

- [Configurar equipes com proteção de linha de base](configure-teams-baseline-protection.md)
- [Configurar equipes com proteção para dados altamente confidenciais](configure-teams-sensitive-protection.md)
- [Configurar equipes com proteção para dados altamente confidenciais](configure-teams-highly-sensitive-protection.md)

Se você tiver um projeto altamente confidencial que exija proteção adicional do compartilhamento, mesmo dentro da sua organização, você pode configurar uma equipe que usa seu próprio rótulo de confidencialidade para criptografar arquivos, de modo que somente os membros da equipe possam lê-los. Confira [Configurar uma equipe com isolamento de segurança](secure-teams-security-isolation.md) para obter detalhes.

### <a name="sharing-with-people-outside-your-organization"></a>Compartilhamento com pessoas de fora da sua organização

Talvez você precise [compartilhar informações de qualquer sensibilidade com pessoas de fora da sua organização](collaborate-with-people-outside-your-organization.md). Isso pode variar de compartilhar um único documento com uma única pessoa para colaborar em um projeto importante com uma organização de parceiro de grande porte ou freelanceres de todo o mundo. No Microsoft 365, esta faixa de compartilhamento externo pode ser feita facilmente e com as proteções apropriadas para ajudar a proteger suas informações confidenciais.

Esses recursos ajudarão você a começar a configurar o ambiente para colaborar com pessoas de fora da sua organização:

- [Colabore em documentos](collaborate-on-documents.md) para compartilhar arquivos individuais de pastas.
- [Colabore em um site](collaborate-in-site.md) para colaborar com convidados em um site do SharePoint.
- [Colabore como uma equipe](collaborate-as-team.md) para colaborar com convidados em uma equipe.

Dependendo da sensibilidade das informações que estão sendo compartilhadas, você pode adicionar salvaguardas para ajudar a evitar o compartilhamento. Esses recursos ajudarão você a configurar as proteções necessárias para a sua organização:

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)
- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](share-limit-accidental-exposure.md)
- [Criar um ambiente seguro de compartilhamento de convidados](create-secure-guest-sharing-environment.md)

Se você tiver um projeto importante com uma organização parceira, poderá usar o gerenciamento de qualificação do Azure para gerenciar os convidados dessa organização em uma equipe que você configurou para o projeto. Consulte [criar uma extranet B2B com convidados gerenciados](b2b-extranet.md) para obter detalhes.

## <a name="deploy-the-secure-collaboration-solution"></a>Implantar a solução de colaboração segura

Quando estiver pronto para implantar essa solução, continue com estas etapas:
1. Configure as [três camadas diferentes de proteção para o Microsoft Teams](configure-teams-three-tiers-protection.md).
2. Definir configurações para [compartilhar informações de qualquer sensibilidade com pessoas de fora da sua organização](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Confira também

[Documentação do Centro de segurança do Microsoft 365](https://docs.microsoft.com/microsoft-365/security)

[Documentação de conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance)

[Bem-vindo ao Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
