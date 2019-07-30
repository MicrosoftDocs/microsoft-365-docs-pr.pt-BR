---
title: Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft
description: Manter a área de trabalho gerenciada da Microsoft atualizada é um equilíbrio de velocidade e estabilidade.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924864"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

A área de trabalho gerenciada da Microsoft conecta todos os dispositivos a uma infraestrutura moderna baseada em nuvem. Manter atualizado o Windows, o Office, os drivers, o firmware e a Microsoft Store para atualizações de aplicativos comerciais é um equilíbrio de velocidade e estabilidade. OS grupos de implantação serão usados para garantir que o sistema operacional e as políticas sejam implantados de forma segura. 

As atualizações lançadas pela Microsoft são cumulativas e são categorizadas como qualidade ou atualizações de recursos.
Para obter mais informações, consulte [Windows Update for Business: Update Types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Atualizar grupos

O Microsoft Managed desktop usa quatro grupos do Azure AD para gerenciar atualizações:

- **Teste**: usado para validar as alterações da política de área de trabalho gerenciada da Microsoft, atualizações de sistema operacional, atualizações de recursos e outras alterações enviadas para o locatário. Não deve haver usuários finais no grupo de teste. O grupo de teste é isento de qualquer SLA estabelecido e suporte ao usuário final. Esse grupo está disponível para ser usado para validar a compatibilidade de aplicativos com novas alterações de política ou sistema operacional.  
- **Primeiro**: contém os pioneiros e dispositivos de software que podem estar sujeitos às atualizações de pré-lançamento. Os dispositivos desse grupo podem sofrer interrupções se houver cenários que não foram cobertos durante o teste no anel de teste.
- **Rápido**: prioriza a velocidade em relação à estabilidade. Útil para detectar problemas de qualidade antes que sejam oferecidos ao grupo amplo. Esse grupo serve como uma próxima camada de validação, mas geralmente é mais estável do que o teste e os primeiros grupos. 
- **Amplo**: o último grupo deve ter as atualizações de recursos e qualidade disponíveis. Esse grupo contém a maioria dos usuários no locatário e, portanto, favorece a estabilidade sobre a velocidade na implantação. O teste de aplicativos deve ser feito aqui, pois o ambiente é mais estável. 

Para saber mais sobre funções e responsabilidades com esses grupos de implantação, confira [funções e responsabilidades de área de trabalho gerenciada da Microsoft](../intro/roles-and-responsibilities.md)

Como funciona a implantação da atualização:
- O Microsoft Managed desktop implanta um novo recurso ou uma atualização de qualidade de acordo com o agendamento especificado abaixo.
- Durante a implantação, o Microsoft Managed desktop monitora sinais de falha ou interrupção (com base nos sinais de dados de diagnóstico e no sistema de suporte ao usuário final). Se algum for detectado, a implantação de todos os grupos atuais e futuros será pausada imediatamente.
    - Exemplo: se um problema for descoberto durante a implantação de uma atualização de qualidade para o primeiro grupo, então atualize as implantações para o primeiro, o mais rápido e o amplo será pausado até que o problema seja resolvido.
    - Problemas de compatibilidade podem ser relatados pelo arquivamento de um tíquete no portal de administração de ti da área de trabalho gerenciada da Microsoft
- As atualizações de recursos e qualidade são pausadas de forma independente. A pausa está em vigor por um ou mais 35 dias por padrão, mas pode ser reduzida ou estendida, dependendo se o problema foi corrigido.
- Após a pausa dos grupos, a implantação é retomada de acordo com o cronograma abaixo.
- Esse processo de implantação se aplica às atualizações de recursos e qualidade, embora a linha do tempo varie para cada.

<table>
<tr><th colspan="5">Atualizar configurações de implantação</th></tr>
<tr><th>Tipo de atualização</th><th>Testes</th><th>Primeiro</th><th>Rápida</th><th>Amplas</th></tr>
<tr><td>Atualizações de qualidade do sistema operacional</td><td>0 dias</td><td>0 dias</td><td>0 dias</td><td>3 dias</td></tr>
<tr><td>Atualizações de recursos para o sistema operacional</td><td>0 dias</td><td>30 dias</td><td>60 dias</td><td>90 dias</td></tr>
<tr><td>Drivers/firmware</td><td colspan="4">Segue o agendamento de atualizações de qualidade</td></tr>
<tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada verificação</td></tr>
</table>

>[!NOTE]
>Esses períodos de adiamento foram intencionalmente projetados para garantir altos padrões de segurança e desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos de área de trabalho gerenciada da Microsoft e no escopo variável e no impacto das atualizações, a área de trabalho gerenciada da Microsoft reserva flexibilidade para modificar o tamanho dos períodos de adiamento acima para todos os grupos de implantação em um anúncio hoc.
>
>O Microsoft Managed desktop conduz uma avaliação independente de cada versão de recurso do Windows para avaliar sua necessidade e utilidade para seus locatários gerenciados. Consequentemente, a área de trabalho gerenciada da Microsoft pode ou não implantar todas as atualizações de recursos do Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

A área de trabalho gerenciada da Microsoft não suporta dispositivos que fazem parte do programa Windows Insider. O programa Windows Insider é usado para validar o software de pré-lançamento do Windows e é destinado a dispositivos que não são de missão crítica. Embora esta seja uma importante iniciativa da Microsoft, ela não se destina à implantação abrangente em ambientes de produção. 

Todos os dispositivos encontrados com as compilações do Windows Insider podem ser colocados no grupo de teste e serão isentos de contratos de nível de serviço de atualização (SLAs) e suporte ao usuário final da área de trabalho gerenciada da Microsoft.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

A otimização de entrega é usada para todas as atualizações de sistema operacional e driver. Ele minimiza o tamanho do download do serviço Windows Update procurando atualizações de colegas dentro da rede corporativa.


