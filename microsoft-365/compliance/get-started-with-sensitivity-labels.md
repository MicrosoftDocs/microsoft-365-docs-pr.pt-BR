---
title: Introdução ao rótulos de confidencialidade
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Pronto para começar a implementar rótulos de confidencialidade para ajudar a proteger os dados da sua organização, mas não sabe por onde começar? Leia algumas orientações práticas para ajudá-lo em sua jornada de rotulagem.
ms.openlocfilehash: efb0d8401cca8fd0e8c2450a5d35788015f37dad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073169"
---
# <a name="get-started-with-sensitivity-labels"></a>Introdução ao rótulos de confidencialidade

Para saber mais sobre quais são os rótulos de confidencialidade e como eles podem ajudá-lo a proteger os dados da sua organização, confira [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md).

Se você tiver a [Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine se é preciso migrar os rótulos para a plataforma de rotulagem unificada e qual cliente de rotulagem usar:
- [Como posso determinar se meu locatário está na plataforma de rotulagem unificada?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Escolher qual cliente de rotulagem usar em computadores com Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Quando estiver pronto para começar a proteger os dados da sua organização usando os rótulos de confidencialidade:

1. **Crie os rótulos.** Crie e nomeie seus rótulos de confidencialidade de acordo com a taxonomia de classificação da sua organização para diferentes níveis de confidencialidade de conteúdo. Use os nomes ou termos comuns que fazem sentido para os seus usuários. Se você ainda não tiver uma taxonomia estabelecida, considere começar com nomes de rótulos como Pessoal, Público, Geral, Confidencial e Altamente Confidencial. Em seguida, você pode usar sub-rótulos para agrupar rótulos similares por categoria. Ao criar um rótulo, use o texto de dica de ferramenta para ajudar os usuários a selecionar o rótulo apropriado.

2. **Defina o que cada rótulo pode fazer.** Defina as configurações de proteção desejadas associadas a cada rótulo. Por exemplo, você pode querer que um conteúdo de menor confidencialidade (como um rótulo “Geral”) tenha apenas um cabeçalho ou rodapé aplicado, enquanto um conteúdo de maior confidencialidade (como um rótulo “Confidencial”) deve ter uma marca d’água, criptografia e proteção de ponto de extremidade aplicado a ele.

3. **Publique os rótulos.** Quando os rótulos de confidencialidade estiverem configurados, publique-os usando uma política de rótulo. Decida quais usuários e grupos devem ter os rótulos e quais configurações de política utilizar. Um único rótulo pode ser reutilizado; você o define uma vez e, em seguida, você pode incluí-lo em várias políticas de rótulo atribuídas a diferentes usuários. Por exemplo, você pode fazer o piloto dos rótulos de confidencialidade atribuindo uma política de rótulo a apenas alguns usuários. Em seguida, quando você estiver pronto para implantar os rótulos em toda a organização, poderá criar uma nova política de rótulos para seus rótulos e, desta vez, especificar todos os usuários.

O fluxo básico para que o administrador, o usuário e os aplicativos do Office façam com que os rótulos de confidencialidade funcionem:

![Diagrama mostrando o fluxo de trabalho de rótulos de confidencialidade](../media/Sensitivity-label-flow.png)

## <a name="common-scenarios-for-sensitivity-labels"></a>Cenários comuns para rótulos de confidencialidade

Use a seguinte documentação para oferecer suporte à implantação de rótulo de confidencialidade:

|Eu quero...|Documentação|
|----------------|---------------|
|Criar e publicar rótulos de confidencialidade que ajudarão a proteger os dados da minha organização|[Criar e configurar rótulos de confidencialidade e suas políticas](create-sensitivity-labels.md)|
|Criptografar documentos e emails com rótulos de confidencialidade e restrinja quem pode acessá-los e como podem usar esse conteúdo |[Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](encryption-sensitivity-labels.md)|
|Habilitar recursos de colaboração no SharePoint (e OneDrive) para documentos rotulados com criptografia | [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)](sensitivity-labels-sharepoint-onedrive-files.md)
|Gerenciar rótulos de confidencialidade para aplicativos do Office para que o conteúdo seja rotulado como foi criado |[Usar rótulos de confidencialidade em aplicativos do Office](sensitivity-labels-office-apps.md)|
|Aplicar automaticamente os rótulos de confidencialidade ou recomendar rótulos aos usuários quando o conteúdo for criado | [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)|
|Usar os rótulos de confidencialidade para proteger o conteúdo do Teams e do SharePoint |[Usar etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)](sensitivity-labels-teams-groups-sites.md)|
|Descobrir, rotular e proteger arquivos armazenados no repositório de dados locais |[Implantação do scanner da Proteção de Informações do Azure para classificar e proteger arquivos automaticamente](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Descobrir, rotular e proteger arquivos armazenados em armazenamentos de dados na nuvem |[Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Visualizar como os rótulos de confidencialidade estão sendo usados para relatar o status de implantação e ajustar a configuração de rótulo|[Exibição do uso do rótulo com análises de rótulo](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentação do usuário final para rótulos de confidencialidade

- [Aplicar rótulos de confidencialidade aos seus arquivos e email no Office](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemas conhecidos em rótulos de confidencialidade no Office](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar ou recomendar rótulos de confidencialidade automaticamente aos seus arquivos e emails no Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)

- [Problemas conhecidos com a aplicação ou recomendação de rótulos de confidencialidade automática](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)


