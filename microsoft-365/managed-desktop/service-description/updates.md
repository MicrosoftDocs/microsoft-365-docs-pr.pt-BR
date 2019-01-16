---
title: Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft
description: Mantendo o Microsoft Desktop gerenciados atualizado é um equilíbrio entre a estabilidade e a velocidade.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864785"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Desktop gerenciados conecta todos os dispositivos a uma infraestrutura de nuvem moderna. Mantendo Windows, Office, drivers, firmware e Microsoft Store para atualizações do aplicativo de negócios atualizado é um equilíbrio entre a estabilidade e a velocidade. Toques de implantação serão usadas para garantir que o sistema operacional e políticas são implementadas de forma segura. 

## <a name="update-groups"></a>Grupos de atualização

Microsoft Desktop gerenciados usa quatro grupos do Azure AD para gerenciar atualizações:

- Teste: Dispositivos de não-produção foi projetados para validar as alterações antes de implantar as alterações entre o restante do inquilino. Dispositivos neste anel estão fora do escopo para suporte de usuário de final documentadas. 
- Primeiro: Contém os primeiros usuários de software, e dispositivos podem estar sujeitos às atualizações de pré-lançamento.
- Fast: Prioriza velocidade em relação a estabilidade. É útil para a detecção de problemas de qualidade antes que elas são oferecidas para o grupo amplo. 
- Amplo número: O último grupo ter o recurso e qualidade atualizações disponíveis. Este grupo contém a maioria dos usuários no locatário e, portanto, melhora estabilidade velocidade na implantação.

Atualizações lançadas pela Microsoft são cumulativas e podem ser classificadas como atualizações de qualidade ou recurso. Para obter mais informações, consulte [atualização do Windows: perguntas frequentes sobre](https://support.microsoft.com/help/12373/windows-update-faq). 

Como funciona a implantação de atualização:
- Microsoft Desktop gerenciados implanta uma nova atualização de recurso ou a qualidade de acordo com o agendamento especificado abaixo.
- Durante a implantação, Microsoft Desktop gerenciados monitora os sinais de falha ou interrupção (com base em sinais de telemetria e o sistema de suporte do usuário final). Se qualquer forem detectados, a implantação de todos os grupos de atuais e futuros imediatamente está pausada.
    - Exemplo: se algum problema for detectado durante a implantação de uma atualização de qualidade ao primeiro grupo, em seguida, implantações de atualização para o primeiro, Fast e amplo número serão todos pausadas até que o problema é resolvido.
    - Problemas de compatibilidade podem ser informados por um tíquete de arquivamento no portal do administrador de TI de área de trabalho gerenciada do Microsoft.
- Atualizações de qualidade e recurso estão pausadas independentemente. Pausar está em vigor para 35 dias por padrão, mas pode ser reduzido ou estendida dependendo se o problema é remediado.
- Depois que os grupos são retomados, retoma a implantação de acordo com a agenda abaixo.
- Esse processo de implantação se aplica às atualizações do recurso e a qualidade, embora varia de acordo com a linha do tempo para cada um.

<table>
<tr><th colspan="5">Configurações de implantação de atualização</th></tr>
<tr><th>Tipo de atualização</th><th>Testes</th><th>Primeiro</th><th>Rápida</th><th>Amplo</th></tr>
<tr><td>Atualizações de qualidade de sistema operacional</td><td>0 dias</td><td>0 dias</td><td>0 dias</td><td>3 dias</td></tr>
<tr><td>Atualizações de recurso de sistema operacional</td><td>0 dias</td><td>30 dias</td><td>60 dias</td><td>90 dias</td></tr>
<tr><td>Drivers/firmware</td><td colspan="4">Segue o agendamento para atualizações de qualidade</td></tr>
<tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada digitalização</td></tr>
</table>

Esses períodos de adiamento intencionalmente são projetados para garantir a segurança alta e padrões de desempenho para todos os usuários. Além disso, com base nos dados coletados em todos os dispositivos de área de trabalho do Microsoft gerenciados e o escopo variados e o impacto das atualizações, área de trabalho gerenciada do Microsoft se reserva flexibilidade para modificar a duração dos períodos adiamento acima para grupos de todo e qualquer implantação em um anúncio Base de hoc.

## <a name="windows-insider-program"></a>Programa de Insider Windows

Microsoft Desktop gerenciados não oferece suporte a dispositivos que fazem parte do programa Insider Windows. O programa Insider Windows é usado para validar o software de pré-lançamento do Windows e destina-se a dispositivos de não-missão críticos. Embora seja uma iniciativa importante da Microsoft, ele não foi projetado para implantação em larga escala em ambientes de produção. 

Todos os dispositivos encontrados com compilações Insider Windows serão colocados no grupo de testes e não ser incluídas para atualizar as contratos de nível de serviço (SLAs.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

Otimização de entrega é usada para atualizações de sistema e driver todos operando. Ele minimiza o tamanho de download do serviço Windows Update (WU) por que buscam atualizações de colegas dentro da rede corporativa.


