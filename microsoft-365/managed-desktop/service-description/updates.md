---
title: Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft
description: Manter atualizado o desktop gerenciado da Microsoft é um equilíbrio de velocidade e estabilidade.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1349b58bdd6243b05323f14197e0ad92c1fc0d7b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289490"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

A área de trabalho gerenciada da Microsoft conecta todos os dispositivos a uma infraestrutura moderna baseada em nuvem. Manter atualizado o Windows, o Office, os drivers, o firmware e a Microsoft Store para aplicativos de negócios é um equilíbrio de velocidade e estabilidade. Os grupos de implantação serão usados para garantir que as atualizações e as políticas do sistema operacional sejam distribuídas de forma segura. Para saber mais sobre isso, confira o [processo de mudança e liberação da área de trabalho gerenciada da Microsoft em](https://www.microsoft.com/videoplayer/embed/RE4mWqP)vídeo.

As atualizações lançadas pela Microsoft são cumulativas e são categorizadas como qualidade ou atualizações de recursos.
Para obter mais informações, consulte [Windows Update for Business: Update Types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Atualizar grupos

O Microsoft Managed desktop usa quatro grupos do Azure AD para gerenciar atualizações:

- **Teste**: usado para validar as alterações da política de área de trabalho gerenciada da Microsoft, atualizações do sistema operacional, atualizações de recursos e outras alterações enviadas para o locatário. Não deve haver nenhum usuário colocado no grupo de teste. O grupo de teste é isento de qualquer contrato de nível de serviço estabelecido e suporte ao usuário. Esse grupo está disponível para ser usado para validar a compatibilidade de aplicativos com novas alterações de política ou sistema operacional.  
- **Primeiro**: contém os pioneiros e dispositivos de software que podem estar sujeitos às atualizações de pré-lançamento. Os dispositivos desse grupo podem sofrer interrupções se houver cenários que não foram cobertos durante o teste no anel de teste.
- **Rápido**: prioriza a velocidade em relação à estabilidade. Útil para detectar problemas de qualidade antes que sejam oferecidos ao grupo amplo. Esse grupo serve como uma próxima camada de validação, mas geralmente é mais estável do que o teste e os primeiros grupos. 
- **Amplo**: o último grupo deve ter as atualizações de recursos e qualidade disponíveis. Esse grupo contém a maioria dos usuários no locatário e, portanto, favorece a estabilidade sobre a velocidade na implantação. O teste de aplicativos deve ser feito aqui, pois o ambiente é mais estável. 

> [!NOTE]
> Se você precisar mover um usuário para um grupo de atualização diferente, envie uma solicitação de suporte. Consulte [suporte para a área de trabalho gerenciada da Microsoft](support.md) para obter mais informações sobre como enviar solicitações de suporte. Se você mesmo mover um usuário, a movimentação será revertida.

Para saber mais sobre funções e responsabilidades com esses grupos de implantação, confira [funções e responsabilidades de área de trabalho gerenciada da Microsoft](../intro/roles-and-responsibilities.md)

Como funciona a implantação da atualização:
- O Microsoft Managed desktop implanta um novo recurso ou uma atualização de qualidade de acordo com o agendamento especificado abaixo.
- Durante a implantação, o Microsoft Managed desktop monitora sinais de falha ou interrupção (com base nos dados de diagnóstico e no sistema de suporte do usuário). Se algum for detectado, a implantação de todos os grupos atuais e futuros será pausada imediatamente.
    - Exemplo: se um problema for descoberto durante a implantação de uma atualização de qualidade para o primeiro grupo, então atualize as implantações para o primeiro, o mais rápido e o amplo será pausado até que o problema seja resolvido.
    - Problemas de compatibilidade podem ser relatados pelo arquivamento de um tíquete no portal de administração de área de trabalho gerenciada da Microsoft.
- As atualizações de recursos e qualidade são pausadas de forma independente. A pausa está em vigor por um ou mais 35 dias por padrão, mas pode ser reduzida ou estendida, dependendo se o problema foi corrigido.
- Após a pausa dos grupos, a implantação é retomada de acordo com o cronograma abaixo.
- Esse processo de implantação se aplica às atualizações de recursos e qualidade, embora a linha do tempo varie para cada.




<table>
<tr><th colspan="5">Atualizar configurações de implantação</th></tr>
<tr><th>Tipo de atualização</th><th>Testar</th><th>Primeiro</th><th>Rápida</th><th>Amplas</th></tr>
<tr><td>Atualizações de qualidade do sistema operacional</td><td>0 dias</td><td>0 dias</td><td>0 dias</td><td>3 dias</td></tr>
<tr><td>Atualizações de recursos para o sistema operacional</td><td>0 dias</td><td>30 dias</td><td>60 dias</td><td>90 dias</td></tr>
<tr><td>Drivers/firmware</td><td colspan="4">Segue o agendamento de atualizações de qualidade</td></tr>
<tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada verificação</td></tr>
<tr><td>Microsoft 365 Apps para Grandes Empresas</td><td colspan="4">Acompanha o canal atual do Office
</table>

Para obter mais informações sobre o canal atual para o Microsoft 365 Apps for Enterprise, consulte [Overview of Update Channels for microsoft 365 apps](https://docs.microsoft.com/deployoffice/overview-update-channels).

>[!NOTE]
>Esses períodos de adiamento foram intencionalmente projetados para garantir altos padrões de segurança e desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos de área de trabalho gerenciada da Microsoft e no escopo variável e no impacto das atualizações, a área de trabalho gerenciada da Microsoft reserva a flexibilidade para modificar o tamanho dos períodos de adiamento acima para qualquer e todos os grupos de implantação em uma base ad hoc.
>
>O Microsoft Managed desktop conduz uma avaliação independente de cada versão de recurso do Windows para avaliar sua necessidade e utilidade para seus locatários gerenciados. Consequentemente, a área de trabalho gerenciada da Microsoft pode ou não implantar todas as atualizações de recursos do Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

A área de trabalho gerenciada da Microsoft não suporta dispositivos que fazem parte do programa Windows Insider. O programa Windows Insider é usado para validar o software de pré-lançamento do Windows e destina-se a dispositivos que não são essenciais. Embora esta seja uma importante iniciativa da Microsoft, ela não se destina à implantação abrangente em ambientes de produção. 

Todos os dispositivos encontrados com as compilações do Windows Insider podem ser colocados no grupo de teste e serão isentos de contratos de nível de serviço de atualização e suporte ao usuário da área de trabalho gerenciada da Microsoft.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

Usamos a [otimização de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) para todas as atualizações de sistema operacional e driver. Isso minimiza o tamanho do download do serviço do Windows Update procurando as atualizações de pares dentro da rede corporativa.


