---
title: Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft
description: Manter a área de trabalho gerenciada da Microsoft atualizada é um equilíbrio de velocidade e estabilidade.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0dad909ce9e17f993de64ba39b08f388c71abb89
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278640"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

A área de trabalho gerenciada da Microsoft conecta todos os dispositivos a uma infraestrutura moderna baseada em nuvem. Manter atualizado o Windows, o Office, os drivers, o firmware e a Microsoft Store para atualizações de aplicativos comerciais é um equilíbrio de velocidade e estabilidade. OS grupos de implantação serão usados para garantir que o sistema operacional e as políticas sejam implantados de forma segura. 

As atualizações lançadas pela Microsoft são cumulativas e podem ser categorizadas como qualidade ou atualizações de recursos.
Para obter mais informações, consulte [Windows Update for Business: Update Types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Atualizar grupos

O Microsoft Managed desktop usa quatro grupos do Azure AD para gerenciar atualizações:

- **Teste**: usado para validar as alterações da política de área de trabalho gerenciada da Microsoft, atualizações de sistema operacional, atualizações de recursos e outras alterações enviadas para o locatário. Não deve haver usuários finais no grupo de teste. O grupo de teste é isento de qualquer SLA estabelecido e suporte ao usuário final. Esse grupo está disponível para ser usado para validar a compatibilidade de aplicativos com novas alterações de política ou sistema operacional.  
- **Primeiro**: contém os pioneiros e dispositivos de software que podem estar sujeitos às atualizações de pré-lançamento. Os dispositivos desse grupo podem sofrer interrupções se houver cenários que não foram cobertos durante o teste no anel de teste.
- **Rápido**: prioriza a velocidade em relação à estabilidade. Útil para detectar problemas de qualidade antes que sejam oferecidos ao grupo amplo. Esse grupo serve como uma próxima camada de validação, mas geralmente é mais estável do que o teste e os primeiros grupos. 
- **Amplo**: o último grupo deve ter as atualizações de recursos e qualidade disponíveis. Esse grupo contém a maioria dos usuários no locatário e, portanto, favorece a estabilidade sobre a velocidade na implantação. O teste de aplicativos deve ser feito aqui, pois o ambiente é mais estável. 

Para saber mais sobre funções e responsabilidades com esses grupos de implantação, confira [funções e responsabilidades de área de trabalho gerenciaDa da Microsoft](../intro/roles-and-responsibilities.md)

Como funciona a implantação da atualização:
- O Microsoft Managed desktop implanta um novo recurso ou uma atualização de qualidade de acordo com o agendamento especificado abaixo.
- Durante a implantação, o Microsoft Managed desktop monitora sinais de falha ou interrupção (com base nos sinais de dados de diagnóstico e no sistema de suporte ao usuário final). Se algum for detectado, a implantação de todos os grupos atuais e futuros será pausada imediatamente.
    - Exemplo: se um problema for descoberto durante a implantação de uma atualização de qualidade para o primeiro grupo, então atualize as implantações para o primeiro, o mais rápido e o amplo será pausado até que o problema seja resolvido.
    - Problemas de compatibilidade podem ser relatados pelo arquivamento de um tíquete no portal de administração de ti do Microsoft Managed desktop.
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

Esses períodos de adiamento foram intencionalmente projetados para garantir altos padrões de segurança e desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos de área de trabalho gerenciada da Microsoft e no escopo variável e no impacto das atualizações, a área de trabalho gerenciada da Microsoft reserva flexibilidade para modificar o tamanho dos períodos de adiamento acima para todos os grupos de implantação em um anúncio hoc.

## <a name="windows-insider-program"></a>Programa Windows inSider

A área de trabalho gerenciada da Microsoft não suporta dispositivos que fazem parte do programa Windows inSider. O programa Windows inSider é usado para validar o software de pré-lançamento do Windows e destina-se a dispositivos não-essenciais. Embora esta seja uma importante iniciativa da Microsoft, ela não se destina à implantação abrangente em ambientes de produção. 

Todos os dispositivos encontrados com as compilações do Windows inSider serão colocados no grupo de teste e não serão incluídos para atualizar os contratos de nível de serviço (SLAs).

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

A otimização de entrega é usada para todas as atualizações de sistema operacional e driver. Ele minimiza o tamanho do download do serviço Windows Update (WU) procurando atualizações de pares dentro da rede corporativa.


