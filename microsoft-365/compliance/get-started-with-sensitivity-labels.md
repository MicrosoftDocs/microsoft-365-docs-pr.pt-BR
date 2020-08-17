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
ms.openlocfilehash: 50392693b92ac660445d5966168b143c70853291
ms.sourcegitcommit: 6cf29958aff90d8bc1df0fe5fb9238d338db8237
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506326"
---
# <a name="get-started-with-sensitivity-labels"></a>Introdução ao rótulos de confidencialidade

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Para saber mais sobre quais são os rótulos de confidencialidade e como eles podem ajudá-lo a proteger os dados da sua organização, confira [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md).

Se você tiver a [Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determine se é preciso migrar os rótulos para a plataforma de rotulagem unificada e qual cliente de rotulagem usar:
- [Como posso determinar se meu locatário está na plataforma de rotulagem unificada?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Escolha qual cliente de rotulagem usar em computadores com Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Quando estiver pronto para começar a proteger os dados da sua organização usando os rótulos de confidencialidade:

1. **Crie os rótulos.** Crie e nomeie seus rótulos de confidencialidade de acordo com a taxonomia de classificação da sua organização para diferentes níveis de confidencialidade de conteúdo. Use os nomes ou termos comuns que fazem sentido para os seus usuários. Se você ainda não tiver uma taxonomia estabelecida, considere começar com nomes de rótulos como Pessoal, Público, Geral, Confidencial e Altamente Confidencial. Em seguida, você pode usar sub-rótulos para agrupar rótulos similares por categoria. Ao criar um rótulo, use o texto de dica de ferramenta para ajudar os usuários a selecionar o rótulo apropriado.
    
    Para obter orientações mais abrangentes sobre a definição de uma taxonomia de classificação, faça o download do artigo técnico "Classificação de Dados e Taxonomia de Rótulos de Confidencialidade", no [Portal de Confiança do Serviço](https://aka.ms/DataClassificationWhitepaper).

2. **Defina o que cada rótulo pode fazer.** Defina as configurações de proteção desejadas associadas a cada rótulo. Por exemplo, convém que o conteúdo de menor sensibilidade (como um rótulo "Geral") aplique apenas um cabeçalho ou rodapé, enquanto o conteúdo de maior sensibilidade (como um rótulo "Confidencial") deve ter marca d'água e criptografia.

3. **Publique os rótulos.** Quando os rótulos de confidencialidade estiverem configurados, publique-os usando uma política de rótulo. Decida quais usuários e grupos devem ter os rótulos e quais configurações de política utilizar. Um único rótulo pode ser reutilizado. Você o define uma vez e pode incluí-lo em várias políticas de rótulos atribuídas a diferentes usuários. Por exemplo, você pode fazer o piloto dos rótulos de confidencialidade atribuindo uma política de rótulo a apenas alguns usuários. Em seguida, quando você estiver pronto para implantar os rótulos em toda a organização, poderá criar uma nova política de rótulos para seus rótulos e, desta vez, especificar todos os usuários.

O fluxo básico para a implantação e a aplicação de rótulos de sensibilidade:

![Diagrama mostrando o fluxo de trabalho de rótulos de confidencialidade](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisitos de assinatura e licenciamento dos rótulos de sensibilidade

Várias assinaturas diferentes oferecem suporte aos rótulos de sensibilidade e aos requisitos de licenciamento dos usuários que dependem dos recursos que você usa.

Para visualizar as opções de licenciamento dos seus usuários para se beneficiar dos recursos de conformidade do Microsoft 365 a partir do dia 01º de abril de 2020, consulte as [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD). Para rótulos de confidencialidade, confira a seção [Proteção de informações](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) e o download relacionado em PDF ou Excel.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Permissões necessárias para criar e gerenciar rótulos dec confidencialidade

Os membros da sua equipe de conformidade que forem criar rótulos de confidencialidade precisam de permissões no Centro de conformidade do Microsoft 365, Centro de segurança do Microsoft 365 ou Centro de Conformidade e Segurança. 

Por padrão, os administradores globais de locatários têm acesso a esses centros de administração e podem conceder acesso a agentes de conformidade e a outras pessoas, sem fornecer a eles todas as permissões de um administrador de locatários. Para esse acesso delegado de administrador limitado, adicione usuários ao grupo de funções **Administrador de Dados de Conformidade**, **Administrador de Conformidade** ou **Administrador de Segurança**. 

Como alternativa às funções padrão, você pode criar um novo grupo de funções e adicionar as funções **Administrador de Rótulo de Confidencialidade** ou **Configuração da Organização** a esse grupo. Para uma função somente leitura, use **Leitor de rótulos de sensibilidade**. 

Para obter instruções sobre como adicionar usuários às funções padrão ou criar seus próprios grupos de funções, confira [Conceder aos usuários acesso ao Centro de Segurança e Conformidade do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Essas permissões são necessárias somente para criar e configurar os rótulos de confidencialidade e suas políticas de rótulos. Eles não são necessários para aplicar os rótulos em aplicativos ou serviços. Se forem necessárias permissões adicionais para as configurações específicas relacionadas aos rótulos de sensibilidade, essas permissões serão listadas nas suas respectivas instruções de documentação.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Estratégia de implementação para rótulos de sensibilidade

Uma estratégia bem-sucedida para implantar rótulos de sensibilidade para uma organização é criar uma equipe de trabalho virtual que identifique e gerencie os requisitos técnicos e de negócios, os testes de verificação, os pontos de verificação internos e as aprovações, além da implantação final para o ambiente de produção.

Usando a tabela na próxima seção, recomendamos identificar um ou dois cenários mais importantes que mostram as suas exigências de negócios mais impactantes. Após a implantação desses cenários, volte para a lista para identificar as próximas prioridades para implantação.

Você pode encontrar mais diretrizes de implantação geral na guia de aceleração de implantação e proteção de informações da Microsoft 365 disponível para download. Para obter mais informações, confira a postagem do blog, [Guia de aceleração de implantação e proteção de informações da Microsoft](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-compliance-deployment/ba-p/1403493).

## <a name="common-scenarios-for-sensitivity-labels"></a>Cenários comuns para rótulos de confidencialidade

Todos os cenários requerem que você [crie e configure rótulos de confidencialidade e suas políticas](create-sensitivity-labels.md).

|Eu quero...|Documentação|
|----------------|---------------|
|Gerenciar rótulos de confidencialidade para aplicativos do Office para que o conteúdo seja rotulado como foi criado |[Usar rótulos de confidencialidade em aplicativos do Office](sensitivity-labels-office-apps.md)|
|Permitir que os usuários rotulem e protejam arquivos de computadores com Windows usando aplicativos do Office, Explorador de Arquivos e PowerShell|[Cliente de rotulagem unificada da Proteção de Informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)|
|Criptografar documentos e emails com rótulos de confidencialidade e restringir quem pode acessá-los e como podem usar esse conteúdo |[Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](encryption-sensitivity-labels.md)|
|Habilite os rótulos de sensibilidade do Office na web, com suporte para coautoria, descoberta eletrônica, prevenção contra perda de dados — até mesmo quando os documentos são criptografados | [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Aplicar rótulos de confidencialidade automaticamente a documentos e emails | [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)|
|Usar os rótulos de confidencialidade para proteger o conteúdo do Teams e do SharePoint |[Use rótulos de sensibilidade nos Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint)](sensitivity-labels-teams-groups-sites.md)|
|Descobrir, rotular e proteger arquivos armazenados no repositório de dados locais |[Implantação do scanner da Proteção de Informações do Azure para classificar e proteger arquivos automaticamente](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Descobrir, rotular e proteger arquivos armazenados no repositório da nuvem|[Descobrir, classificar, rotular e proteger dados regulamentados e confidenciais armazenados na nuvem](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Aplicar e exibir rótulos de confidencialidade no Power BI e proteger dados ao exportar|[Proteção de dados no Power BI](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|
|Monitorar e entender como os rótulos de sensibilidade estão sendo usados na minha organização|[Conhecer seus dados - visão geral da classificação de dados](data-classification-overview.md) <br /><br /> [Exibição do uso do rótulo com análises de rótulo](label-analytics.md)|
|Estender os rótulos de confidencialidade a aplicativos e serviços de terceiros|[SDK de Proteção de Informações da Microsoft](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|

## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentação do usuário final para rótulos de confidencialidade

A documentação mais eficaz do usuário final será orientação e instruções personalizadas que você fornecerá para os nomes de etiqueta e configurações que você escolher. No entanto, você pode usar os seguintes recursos para obter instruções básicas:   

- [Aplicar rótulos de confidencialidade aos seus arquivos e email no Office](https://support.microsoft.com/pt-BR/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemas conhecidos em rótulos de confidencialidade no Office](https://support.microsoft.com/pt-BR/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Aplicar ou recomendar rótulos de confidencialidade automaticamente aos seus arquivos e emails no Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemas conhecidos com a aplicação ou recomendação de rótulos de confidencialidade automática](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Guia do usuário da proteção de informações do Azure rotulagem unificada](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


