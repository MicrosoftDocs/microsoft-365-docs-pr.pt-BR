---
title: Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft
description: Mantendo o Microsoft Desktop gerenciados atualizado é um equilíbrio entre a estabilidade e a velocidade.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864785"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Desktop gerenciados conecta todos os dispositivos a uma infraestrutura de nuvem moderna. Mantendo Windows, Office, drivers, firmware e Microsoft Store para atualizações do aplicativo de negócios atualizado é um equilíbrio entre a estabilidade e a velocidade. Toques de implantação serão usadas para garantir que o sistema operacional e políticas são implementadas de forma segura. 

## <a name="update-rings"></a>Toques de atualização

Microsoft Desktop gerenciados usa quatro grupos do Azure AD para gerenciar atualizações:

- Teste: Teste a opção ligar somente foi projetada para teste e validação de alterações feitas no locatário do cliente.  
- Primeira: Primeiro deve ser um toque de teste inicial com usuários experientes do tech limitado que estão dispostos a instalar o software no início e estar sujeitos a algumas atualizações de pré-lançamento.
- Fast: A opção ligar fast é onde podemos esperaria um grande conjunto de usuários.  O objetivo para esse anel é manter os dispositivos atualizadas e protegidas com um ritmo rápido de entrega de software.  
- Amplo: A opção ligar lenta é um balanced rolo conservadora atualizações de qualidade e recurso.  Atualizações de qualidade ainda são entregues rapidamente ritmo, mas não imediatamente. 

As atualizações no sistema anel são classificadas como qualidade ou atualizações de recursos:
- Atualizações de qualidade incluem segurança, critical e as atualizações de driver.  Estes são geralmente mensais atualizações. 
- Atualizações de recurso contêm não apenas segurança e revisões de qualidade, mas também recurso significativo adições e alterações; eles são liberados semestralmente. 

Como funciona o promoção de anel:
- Microsoft Desktop gerenciados implanta uma nova atualização de recurso ou a qualidade de acordo com o agendamento especificado abaixo.
- Durante a implantação, Microsoft Desktop gerenciados monitora de sinais de falha ou outra interrupção (via sinais de telemetria e nosso sistema de suporte do usuário final); Se qualquer forem detectados, a implantação para todos os toques atuais e futuros imediatamente está pausada.
    - Exemplo: se algum problema for detectado durante a implantação de uma atualização de qualidade para a opção ligar primeira, em seguida, em primeiro lugar, Fast e amplo número serão todos pausados até que o problema é resolvido.
    - Problemas de compatibilidade podem ser informados por um tíquete de arquivamento no portal do administrador de TI de área de trabalho gerenciada do Microsoft.
- Atualizações de qualidade e recurso estão pausadas independentemente.  Pausar está em vigor para 35 dias por padrão, mas pode ser reduzido ou estendida dependendo se o problema é remediado.
- Depois que o tocar estiverem retomado, retoma a implantação de acordo com a agenda abaixo.
- Esse processo promoção se aplica às atualizações do recurso e a qualidade, embora varia de acordo com a linha do tempo para cada um.

<table>
<tr><th colspan="5">Toques e configurações de adiamento</th></tr>
<tr><th>Tipo de atualização</th><th>Toque de teste</th><th>Primeiro</th><th>Rápida</th><th>Amplo</th></tr>
<tr><td>Atualizações de qualidade de sistema operacional</td><td>0 dias</td><td>0 dias</td><td>1 dia</td><td>5 dias</td></tr>
<tr><td>Atualizações de recurso de sistema operacional</td><td>Canal semi-estruturados anual (público alvo) + 0 dias</td><td>Canal semi-estruturados anual (público alvo) + 30 dias</td><td>Canal semi-estruturados anual (público alvo) + 60 dias</td><td>Canal semi-estruturados anual + 30 dias</td></tr>
<tr><td>Drivers/firmware</td><td colspan="4">Segue o agendamento para atualizações de qualidade</td></tr>
<tr><td>Definição de antivírus</td><td colspan="4">Atualizado com cada digitalização</td></tr>
<tr><td>Clique do Office Pro Plus para executar</td><td colspan="4">Alinhado com o canal semi-estruturados anual</td></tr>
</table>


## <a name="windows-insider-program"></a>Programa de Insider Windows

Microsoft Desktop gerenciados não oferece suporte a dispositivos que fazem parte do programa Insider Windows. Este programa é usado para validar o software de pré-lançamento do Windows e destina-se a dispositivos de não-missão críticos. Embora seja uma iniciativa importante da Microsoft, ele não foi projetado para implantação em larga escala em ambientes de produção. 

Todos os dispositivos encontrados com compilações Insider Windows serão colocados no anel teste e não ser incluídas para atualização SLAs.

## <a name="bandwidth-management"></a>Gerenciamento de largura de banda

Otimização de entrega é usada para atualizações de sistema e driver todos operando. Ele minimiza o tamanho de download do serviço Windows Update (WU) por que buscam atualizações de colegas dentro da rede corporativa.


