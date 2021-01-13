---
title: Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft
description: Manter a Área de Trabalho Gerenciada da Microsoft atualizada é um equilíbrio de velocidade e estabilidade.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 53a21c4126e59861200df405ffe365b2ccef08f8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840284"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

A Área de Trabalho Gerenciada da Microsoft conecta todos os dispositivos a uma infraestrutura moderna baseada em nuvem. Manter o Windows, o Office, os drivers, o firmware e os aplicativos da Microsoft Store para Empresas atualizados é um equilíbrio de velocidade e estabilidade. Os grupos de implantação serão usados para garantir que as atualizações e políticas do sistema operacional sejam implantadas de maneira segura. Para obter mais informações, consulte o vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

As atualizações lançadas pela Microsoft são cumulativas e são categorizadas como atualizações de qualidade ou recurso.
Para obter mais informações, consulte [o Windows Update para Empresas: tipos de atualização.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Atualizar grupos

A Área de Trabalho Gerenciada da Microsoft usa quatro grupos do Azure AD para gerenciar atualizações:

- **Teste:** usado para validar alterações de política da Área de Trabalho Gerenciada da Microsoft, atualizações do sistema operacional, atualizações de recursos e outras alterações feitas pelo locatário. Não deve haver nenhum usuário colocado no grupo de teste. O grupo de teste está isento de quaisquer contratos de nível de serviço estabelecidos e suporte ao usuário. Esse grupo está disponível para uso para validar a compatibilidade de aplicativos com novas políticas ou alterações no sistema operacional.  
- **Primeiro:** contém dispositivos e desenvolvedores de software inseríveis que podem estar sujeitos a atualizações de pré-lançamento. Os dispositivos nesse grupo podem ter paralisações se houver cenários que não foram cobertos durante o teste no anel de teste.
- **Rápido:** prioriza a velocidade em vez da estabilidade. Útil para detectar problemas de qualidade antes que eles sejam oferecidos ao grupo Amplo. Esse grupo serve como uma próxima camada de validação, mas normalmente é mais estável do que os grupos Test e First. 
- **Amplo:** último grupo a ter atualizações de recursos e qualidade disponíveis. Esse grupo contém a maioria dos usuários no locatário e, portanto, favorece a estabilidade em relação à velocidade na implantação. Os testes de aplicativos devem ser feitos aqui, pois o ambiente é mais estável. 

> [!NOTE]
> Se você precisar mover um usuário para um grupo de atualização diferente, envie uma solicitação de suporte. Consulte [Suporte para Área de Trabalho Gerenciada da Microsoft](support.md) para obter mais informações sobre como enviar solicitações de suporte. Se você mover um usuário por conta própria, a movimentação será revertida.

Para obter mais funções e responsabilidades de informações com esses grupos de implantação, consulte Funções e responsabilidades da Área de [Trabalho Gerenciada da Microsoft](../intro/roles-and-responsibilities.md)

Como funciona a implantação de atualização:
- A Área de Trabalho Gerenciada da Microsoft implanta um novo recurso ou atualização de qualidade de acordo com o cronograma especificado na tabela.
- Durante a implantação, a Área de Trabalho Gerenciada da Microsoft monitora sinais de falha ou interrupção (com base nos dados de diagnóstico e no sistema de suporte do usuário). Se algum for detectado, a implantação para todos os grupos atuais e futuros será pausada imediatamente.
    - Exemplo: se um problema for descoberto durante a implantação de uma atualização de qualidade no primeiro grupo, atualizar as implantações para First, Fast e Broad será pausado até que o problema seja resolvido.
    - Os problemas de compatibilidade podem ser relatados apresentando um tíquete no portal do Administrador da Área de Trabalho Gerenciada da Microsoft.
- As atualizações de recursos e qualidade são pausadas independentemente. A pausa está em vigor por 35 dias por padrão, mas pode ser reduzida ou estendida dependendo se o problema foi remediado.
- Depois que os grupos não sãopausados, a implantação é retomada de acordo com o cronograma na tabela.
- Esse processo de implantação se aplica a atualizações de recursos e qualidade, embora a linha do tempo varie para cada uma delas.




<table>
    <tr><th colspan="5">Atualizar configurações de implantação</th></tr>
    <tr><th>Tipo de atualização</th><th>Testar</th><th>Primeiro</th><th>Rápida</th><th>Amplas</th></tr>
    <tr><td>Atualizações de qualidade para o sistema operacional</td><td>0 dias</td><td>0 dias</td><td>0 dias</td><td>3 dias</td></tr>
    <tr><td>Atualizações de recursos para o sistema operacional</td><td>0 dias</td><td>30 dias</td><td>60 dias</td><td>90 dias</td></tr>
    <tr><td>Drivers/firmware</td><td colspan="4">Segue o cronograma de atualizações de qualidade</td></tr>
    <tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada verificação</td></tr>
    <tr><td>Microsoft 365 Apps para empresas</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Saiba Mais</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Saiba Mais</a></td></tr>
</table>

>[!NOTE]
>Esses períodos de adiamento foram projetados intencionalmente para garantir padrões de alta segurança e desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos da Área de Trabalho Gerenciada da Microsoft e no escopo e impacto variáveis das atualizações, a Área de Trabalho Gerenciada da Microsoft reserva flexibilidade para modificar o comprimento dos períodos de adiamento acima para qualquer e todos os grupos de implantação de forma ad hoc.
>
>A Área de Trabalho Gerenciada da Microsoft realiza uma avaliação independente de cada versão de recursos do Windows para avaliar sua necessidade e utilidade para seus locatários gerenciados. Consequentemente, a Área de Trabalho Gerenciada da Microsoft pode ou não implantar todas as atualizações de recursos do Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

A Área de Trabalho Gerenciada da Microsoft não dá suporte a dispositivos que fazem parte do programa Windows Insider. O programa Windows Insider é usado para validar o software do Windows de pré-lançamento e destina-se a dispositivos que não são essenciais. Embora seja uma iniciativa importante da Microsoft, ela não se destina a ampla implantação em ambientes de produção. 

Todos os dispositivos encontrados com builds do Windows Insider podem ser colocados no grupo de teste e estarão isentos dos contratos de nível de serviço de atualização e do suporte do usuário da Área de Trabalho Gerenciada da Microsoft.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

Usamos a [Otimização de Entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) para todas as atualizações de driver e sistema operacional. Esse recurso minimiza o tamanho de download do serviço Windows Update buscando atualizações de pares dentro da rede corporativa.


