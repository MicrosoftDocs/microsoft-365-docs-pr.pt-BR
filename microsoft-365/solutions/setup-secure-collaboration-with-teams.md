---
title: Configure a colaboração segura com o Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Saiba como configurar a colaboração de conteúdo seguro no Teams para proteger seus dados com base em sua sensibilidade.
ms.openlocfilehash: f65657125fef8b8cf7e4e229d70d8fe211153392
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613579"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Configure a colaboração segura com o Microsoft 365

Ser capaz de compartilhar facilmente informações com as pessoas certas enquanto impede o compartilhamento em excesso é fundamental para o sucesso de uma organização. Isso inclui a capacidade de compartilhar dados confidenciais com segurança apenas com aqueles que devem ter acesso a eles. Dependendo do projeto, isso pode incluir o compartilhamento de dados confidenciais com pessoas de fora da sua organização.

Este guia de solução de colaboração inclui dois componentes para ajudá-lo:
- Implantar o Microsoft Teams com o nível certo de proteção para cada projeto
- Definir o compartilhamento externo com as configurações de segurança apropriadas para cada projeto

![Implantar o Teams com proteção apropriada e configurar o compartilhamento externo com as configurações de segurança apropriadas](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Se ferramentas de colaboração de conteúdo versáteis e fáceis de usar não estão disponíveis, os usuários geralmente colaboram enviando documentos por email. Esse é um método de colaboração tedioso e propenso a erros e pode aumentar o risco de compartilhamento inadequado de informações. Se as pessoas acham muito difícil compartilhar informações, elas podem reverter para o uso de produtos de consumidor que não são governados por IT. Isso pode representar um risco ainda maior.

Com o Microsoft 365, você pode implantar o Teams com uma variedade de configurações que ajudam:

- Proteger sua propriedade intelectual
- Habilitar a colaboração fácil
- Criar um equilíbrio entre segurança e usabilidade que aumente a satisfação do usuário e reduz o risco de sombra de IT

A maioria das organizações tem uma variedade de informações, com graus variáveis de sensibilidade e graus variáveis de impacto nos negócios se as informações são compartilhadas inadequadamente. Dependendo da sensibilidade de uma determinada informação, talvez você queira permitir o compartilhamento com:

- Qualquer pessoa (não autenticada)
- Pessoas dentro da organização
- Pessoas específicas dentro da organização
- Pessoas específicas dentro e fora da organização

Informações como folhetos de marketing são destinadas a compartilhar amplamente fora da organização. Informações como menus de cafeteria não são destinadas ao compartilhamento externo, mas não terão impacto comercial se eles foram compartilhados externamente. Esses tipos de informações precisam de pouca ou nenhuma proteção.

Esses mesmos folhetos de marketing, durante o desenvolvimento, podem ser compartilhados apenas dentro da organização. Nesse caso, as configurações de compartilhamento padrão no Teams podem ser suficientes.

As informações sobre um novo produto que está em desenvolvimento podem ser consideradas confidenciais, mesmo dentro da organização. Um grau maior de proteção pode ser apropriado nesse caso. Você pode restringir o acesso a essas informações a membros de uma equipe específica, por exemplo. Dependendo do projeto, talvez seja necessário colaborar com pessoas de fora da sua organização, como um fornecedor ou uma organização parceira.

As informações essenciais para o sucesso da sua organização ou que têm requisitos rigorosos de segurança ou conformidade podem exigir níveis ainda maiores de proteção.

![Escala de risco de baixo (folheto lançado) para alto (dados comerciais confidenciais)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Para todos os cenários mencionados acima, você pode usar equipes no Microsoft Teams para armazenar, compartilhar e colaborar nas informações. 

Para configurar a colaboração segura, use esses recursos e recursos do Microsoft 365.

| Produto ou componente | Capcidade ou recurso | Licenciamento |
|:-------|:-----|:-------|
| Microsoft Defender para Office 365 | Anexos seguros para SPO, OneDrive e Teams; Documentos seguros; Links seguros para o Teams    | Microsoft 365 E1, E3 e E5 |
| SharePoint    | Políticas de compartilhamento de sites e arquivos, permissões de compartilhamento de site, links de compartilhamento, solicitações do Access, configurações de compartilhamento de convidados do site | Microsoft 365 E1, E3 e E5 |
| Microsoft Teams   | Acesso de convidados, equipes privadas, canais privados | Microsoft 365 E1, E3 e E5 |
| Conformidade com o Microsoft 365  | Rótulos de confidencialidade    | Microsoft 365 E3 e E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Usar o Teams para todos os tipos de dados

Para gerenciar o acesso a informações com diferentes sensibilidades, desenvolvemos três camadas diferentes de [proteção para o Teams.](configure-teams-three-tiers-protection.md) Você pode personalizar qualquer uma dessas camadas para atender melhor às necessidades ou à sua empresa. 

![Imagem em miniatura para o cartaz de arquitetura lógica do Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Essas camadas - *linha* de base *,* sensível e altamente confidenciais *-* aumentam gradualmente as proteções que ajudam a evitar o compartilhamento em excesso e o potencial vazamento de informações, conforme mostrado na tabela a seguir.

|-|**Camada de linha de base**|**Camada sensível**|**Camada altamente sensível**|
|:--|:-----------|:------------|:-------------------|
|Equipe pública ou privada|Ambos|Private|Private|
|Compartilhamento não autenticado|Blocked|Blocked|Blocked|
|Compartilhamento de arquivos|Permitido|Permitido|Somente os proprietários da equipe podem compartilhar.|
|Associação de equipe|Qualquer pessoa pode ingressar em equipes públicas.<br>Aprovação do proprietário da equipe necessária para ingressar em equipes privadas.|Aprovação do proprietário da equipe necessária para ingressar.|Aprovação do proprietário da equipe necessária para ingressar.|
|Criptografia de documentos|||Disponível com rótulo de sensibilidade|
|Compartilhamento de convidados|Permitido|Pode ser permitido ou bloqueado|Pode ser permitido ou bloqueado|
|Dispositivos não-manageados|Sem restrições|Acesso somente web|Blocked|

A configuração dessas camadas envolve:

- Definindo configurações no Teams para acesso de convidados e canais privados
- Definindo configurações no site do SharePoint associado de uma equipe para compartilhamento interno e de convidados, solicitações de acesso e links de compartilhamento
- Para as  *camadas altamente* confidenciais e altamente confidenciais, configurar rótulos de sensibilidade para classificar as equipes e controlar o compartilhamento de convidados e o acesso de dispositivos não controlados
- Para a *camada altamente* sensível, configurar um rótulo de sensibilidade para criptografar os documentos aos quais ele é aplicado

Comece com a camada de linha de  base  e, em seguida, adicione equipes que usem as camadas confidenciais e altamente confidenciais conforme necessário para ajudar a proteger as informações em sua organização. Consulte estes recursos para começar:

- [Configurar equipes com proteção de linha de base](configure-teams-baseline-protection.md)
- [Configurar equipes com proteção para dados altamente confidenciais](configure-teams-sensitive-protection.md)
- [Configurar equipes com proteção para dados altamente confidenciais](configure-teams-highly-sensitive-protection.md)

Se você tiver um projeto altamente sensível que exija proteção adicional contra o compartilhamento mesmo dentro de sua organização, poderá configurar uma equipe que usa seu próprio rótulo de sensibilidade para criptografar arquivos para que somente os membros da equipe possam lê-los. Consulte [Configurar uma equipe com isolamento de segurança](secure-teams-security-isolation.md) para obter detalhes.

### <a name="sharing-with-people-outside-your-organization"></a>Compartilhar com pessoas de fora da sua organização

Talvez seja necessário compartilhar [informações de qualquer sensibilidade com pessoas de fora da sua organização.](collaborate-with-people-outside-your-organization.md) Isso pode variar desde o compartilhamento de um único documento com uma única pessoa até a colaboração em um projeto importante com uma grande organização parceira ou grupos de todo o mundo. No Microsoft 365, esse intervalo de compartilhamento externo pode ser feito facilmente e com as proteções apropriadas para ajudar a proteger suas informações confidenciais.

Esses recursos ajudarão você a começar a configurar seu ambiente para colaborar com pessoas de fora da sua organização:

- [Colabore em](collaborate-on-documents.md) documentos para compartilhar arquivos individuais de pastas.
- [Colabore em um site](collaborate-in-site.md) para colaborar com convidados em um site do SharePoint.
- [Colabore como uma](collaborate-as-team.md) equipe para colaborar com convidados em uma equipe.

Dependendo da sensibilidade das informações que estão sendo compartilhadas, você pode adicionar proteções para ajudar a evitar o compartilhamento em excesso. Esses recursos ajudarão você a configurar as proteções que você precisa para sua organização:

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](best-practices-anonymous-sharing.md)
- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](share-limit-accidental-exposure.md)
- [Criar um ambiente seguro de compartilhamento de convidados](create-secure-guest-sharing-environment.md)

Se você tiver um projeto importante com uma organização parceira, poderá usar o Gerenciamento de Direitos do Azure para gerenciar os convidados dessa organização em uma equipe configurada para o projeto. Consulte [Criar uma extranet B2B com convidados gerenciados](b2b-extranet.md) para obter detalhes.

## <a name="deploy-the-secure-collaboration-solution"></a>Implantar a solução de colaboração segura

Quando você estiver pronto para implantar essa solução, continue com estas etapas:
1. Configure as [três camadas diferentes de proteção para o Teams.](configure-teams-three-tiers-protection.md)
2. Definir configurações para [compartilhar informações de qualquer sensibilidade com pessoas de fora da sua organização.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Confira também

[Documentação do Centro de segurança do Microsoft 365](https://docs.microsoft.com/microsoft-365/security)

[Documentação de conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance)

[Bem-vindo ao Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
