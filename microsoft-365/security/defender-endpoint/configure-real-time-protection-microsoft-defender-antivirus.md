---
title: Habilitar e configurar recursos de proteção do Microsoft Defender Antivírus
description: Habilitar e configurar recursos de proteção em tempo real do Microsoft Defender Antivírus, como monitoramento de comportamento, heurística e aprendizado de máquina
keywords: antivírus, proteção em tempo real, rtp, aprendizado de máquina, monitoramento de comportamento, heurística
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 7fa4f90282bf87c1def1917037e090b213cad3db
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689785"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Habilitar e configurar a proteção always-on do Microsoft Defender Antivírus na Política de Grupo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

A proteção always-on consiste em proteção em tempo real, monitoramento de comportamento e heurística para identificar malware com base em atividades suspeitas e mal-intencionadas conhecidas.

Essas atividades incluem eventos, como processos que fazem alterações incomuns em arquivos existentes, modificação ou criação de chaves de registro de inicialização automática e locais de inicialização (também conhecidos como pontos de extensibilidade de início automático ou ASEPs) e outras alterações no sistema de arquivos ou na estrutura de arquivos.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Habilitar e configurar a proteção always-on na Política de Grupo

Você pode usar **o Editor de Política de Grupo Local** para habilitar e configurar as configurações de proteção always-on do Microsoft Defender Antivírus.

Para habilitar e configurar a proteção always-on:

1. Abra **o Editor de Política de Grupo Local.** Para fazer isso:  

    1. Na caixa de pesquisa da barra de tarefas do Windows 10, digite **gpedit**.
    
    1. Em **Melhor combinação,** clique em **Editar política de grupo** para iniciar o Editor de Política de Grupo **Local.**
    
       ![Resultado da pesquisa da barra de tarefas GPEdit](images/gpedit-search.png)

2. No painel esquerdo do Editor de Política de  **Grupo Local**, expanda a árvore para Configuração do Computador Modelos  >  **Administrativos**  >  **componentes do Windows** Microsoft Defender  >  **Antivírus**. 

3. Configure as configurações da política de serviço antimalware do Microsoft Defender Antivírus. Para fazer isso:  

    1. No painel de detalhes do **Microsoft Defender Antivírus** à direita, clique duas vezes na configuração de política conforme especificado na tabela a seguir:

       | Setting | Descrição | Configuração padrão |
       |-----------------------------|------------------------|-------------------------------|
       | Permitir que o serviço antimalware seja inicializado com prioridade normal | Você pode reduzir a prioridade do mecanismo do Microsoft Defender Antivírus, que pode ser útil em implantações leves em que você deseja ter o mais enxuto possível de um processo de inicialização. Isso pode afetar a proteção no ponto de extremidade. | Habilitado
       | Permitir que o serviço antimalware permaneça em execução sempre | Se as atualizações de proteção foram desabilitadas, você pode definir o Microsoft Defender Antivírus para ainda ser executado. Isso reduz a proteção no ponto de extremidade. | Desabilitada |
    
    1. Configure a configuração conforme apropriado e clique em **OK**.
    
    1. Repita as etapas anteriores para cada configuração na tabela.

4. Configure as configurações da política de proteção em tempo real do Microsoft Defender Antivírus. Para fazer isso:

    1. No painel de detalhes do **Microsoft Defender Antivírus,** clique duas vezes em **Proteção em Tempo Real.** Ou, na árvore **do Microsoft Defender Antivírus** no painel esquerdo, clique em **Proteção em Tempo Real.**
    
    1. No painel **Detalhes da Proteção** em Tempo Real à direita, clique duas vezes na configuração de política, conforme especificado na tabela a seguir:  

       | Setting | Descrição | Configuração padrão |
       |-----------------------------|------------------------|-------------------------------|
       | Ativar o monitoramento de comportamento | O mecanismo AV monitorará processos de arquivo, alterações de arquivo e registro e outros eventos em seus pontos de extremidade para atividades mal-intencionadas suspeitas e conhecidas. | Habilitado |
       | Examinar todos os arquivos e anexos baixados | Arquivos baixados e anexos são verificados automaticamente. Isso funciona além do filtro Windows Defender SmartScreen, que verifica arquivos antes e durante o download. | Habilitado |
       | Monitorar atividades de arquivo e programa em seu computador | O mecanismo do Microsoft Defender Antivírus observa quaisquer alterações de arquivo (gravações de arquivo, como movimentações, cópias ou modificações) e atividade geral do programa (programas abertos ou em execução e que fazem com que outros programas sejam executados). | Habilitado |
       | Ativar notificações de gravação de volume bruto | As informações sobre gravações de volume bruto serão analisadas pelo monitoramento de comportamento. | Habilitado |
       | Ativar a verificação de processo sempre que a proteção em tempo real estiver habilitada | Você pode habilitar independentemente o mecanismo do Microsoft Defender Antivírus para examinar os processos em execução em busca de modificações ou comportamentos suspeitos. Isso é útil se você desabilitou temporariamente a proteção em tempo real e deseja verificar automaticamente os processos iniciados enquanto ele estava desabilitado. | Habilitado |
       | Definir o tamanho máximo de arquivos e anexos baixados a serem verificados | Você pode definir o tamanho em kilobytes. | Habilitado |
       | Configurar a substituição de configuração local para ativar o monitoramento de comportamento | Configure uma substituição local para a configuração do monitoramento de comportamento. Essa configuração só pode ser definida pela Política de Grupo. Se você habilitar essa configuração, a configuração de preferência local terá prioridade sobre a Política de Grupo. Se você desabilitar ou não definir essa configuração, a Política de Grupo terá prioridade sobre a configuração de preferência local.| Habilitado |
       | Configurar a substituição de configuração local para verificação de todos os arquivos e anexos baixados | Configure uma substituição local para a configuração da verificação de todos os arquivos e anexos baixados. Essa configuração só pode ser definida pela Política de Grupo. Se você habilitar essa configuração, a configuração de preferência local terá prioridade sobre a Política de Grupo. Se você desabilitar ou não definir essa configuração, a Política de Grupo terá prioridade sobre a configuração de preferência local.| Habilitado |
       | Configurar a substituição de configuração local para monitoramento de atividade de arquivo e programa no computador | Configure uma substituição local para a configuração do monitoramento de atividades de arquivo e programa em seu computador. Essa configuração só pode ser definida pela Política de Grupo. Se você habilitar essa configuração, a configuração de preferência local terá prioridade sobre a Política de Grupo. Se você desabilitar ou não definir essa configuração, a Política de Grupo terá prioridade sobre a configuração de preferência local.| Habilitado |
       | Configurar a substituição de configuração local para ativar a proteção em tempo real | Configure uma substituição local para a configuração ativar a proteção em tempo real. Essa configuração só pode ser definida pela Política de Grupo. Se você habilitar essa configuração, a configuração de preferência local terá prioridade sobre a Política de Grupo. Se você desabilitar ou não definir essa configuração, a Política de Grupo terá prioridade sobre a configuração de preferência local.| Habilitado |
       | Configurar a substituição de configuração local para monitoramento para atividade de arquivo de entrada e saída | Configure uma substituição local para a configuração do monitoramento para a atividade de arquivo de entrada e saída. Essa configuração só pode ser definida pela Política de Grupo. Se você habilitar essa configuração, a configuração de preferência local terá prioridade sobre a Política de Grupo. Se você desabilitar ou não definir essa configuração, a Política de Grupo terá prioridade sobre a configuração de preferência local. | Habilitado |
       | Configurar o monitoramento para a atividade de arquivo e programa de entrada e saída | Especifique se o monitoramento deve ocorrer na entrada, saída, ambas ou nenhuma direção. Isso é relevante para instalações do Windows Server em que você definiu servidores específicos ou Funções de Servidor que veem grandes quantidades de alterações de arquivo em apenas uma direção e você deseja melhorar o desempenho da rede. Os pontos de extremidade (e servidores) totalmente atualizados em uma rede verão pouco impacto no desempenho independentemente do número ou direção das alterações de arquivo. | Habilitado (ambas as direções) |

    1. Configure a configuração conforme apropriado e clique em **OK**.
    
    1. Repita as etapas anteriores para cada configuração na tabela.

5. Configure a configuração da política de verificação do Microsoft Defender Antivírus. Para fazer isso:  

    1. Na árvore **do Microsoft Defender Antivírus** no painel esquerdo, clique em **Verificar**.
    
       ![Opções de Verificação antivírus do Microsoft Defender](images/gpedit-windows-defender-antivirus-scan.png)

    1. No painel **Verificar** detalhes à direita, clique duas vezes na configuração de política conforme especificado na tabela a seguir:

       | Setting | Descrição | Configuração padrão |
       |-----------------------------|------------------------|-------------------------------|    
       | Ativar heurística | A proteção heurística desabilitará ou bloqueará atividades suspeitas imediatamente antes que o mecanismo do Microsoft Defender Antivírus seja solicitado a detectar a atividade. | Habilitado |

    1. Configure a configuração conforme apropriado e clique em **OK**.
    
6. Feche **o Editor de Política de Grupo Local.**


## <a name="disable-real-time-protection-in-group-policy"></a>Desabilitar a proteção em tempo real na Política de Grupo

> [!WARNING]
> Desabilitar a proteção em tempo real reduz drasticamente a proteção em seus pontos de extremidade e não é recomendado.

O principal recurso de proteção em tempo real é habilitado por padrão, mas você pode desabilitá-lo usando o Editor de Política de **Grupo Local.**

Para desabilitar a proteção em tempo real na política de grupo:

1. Abra **o Editor de Política de Grupo Local.**

   1. Na caixa de pesquisa da barra de tarefas do Windows 10, digite **gpedit**.
   
   1. Em **Melhor combinação,** clique em **Editar política de grupo** para iniciar o Editor de Política de Grupo **Local.**

2.  No painel esquerdo do Editor de Política de Grupo **Local,** expanda a árvore para Configuração do Computador Modelos  >  **Administrativos componentes** do  >    >  **Windows Microsoft Defender Antivírus** Proteção em tempo  >  **real**.

3. No painel **Detalhes da Proteção** em Tempo Real à direita, clique duas vezes em Desativar a proteção em tempo **real**.

   ![Desativar a proteção em tempo real](images/gpedit-turn-off-real-time-protection.png)

4. Na janela **Desativar proteção em tempo real,** de definir a opção como **Habilitado**.

   ![Desativar a proteção em tempo real habilitada](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Clique em **OK**.

6. Feche **o Editor de Política de Grupo Local.**

## <a name="related-articles"></a>Artigos relacionados

- [Configurar proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)