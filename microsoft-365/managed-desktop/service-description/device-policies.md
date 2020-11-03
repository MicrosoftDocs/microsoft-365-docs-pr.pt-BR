---
title: Configuração do dispositivo
description: Saiba mais sobre as políticas padrão aplicadas aos dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5533284d4a3f55a51b3017a64e4c353b4ec71352
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846223"
---
# <a name="device-configuration"></a>Configuração do dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo dispositivo de área de trabalho gerenciada da Microsoft está sendo configurado, garantimos que ele tenha a configuração correta otimizada para a área de trabalho gerenciada da Microsoft. Isso inclui um conjunto de políticas padrão definidas como parte do processo de integração. Essas políticas são oferecidas usando o gerenciamento de dispositivo móvel (MDM) sempre que possível. Para mais informações, consulte [Gerenciamento de dispositivos móveis](https://docs.microsoft.com/windows/client-management/mdm/). 

>[!NOTE]
>Para evitar conflitos, não altere essas políticas.

Os dispositivos chegarão com uma imagem de assinatura e ingressarão no domínio do Azure Active Directory quando o primeiro usuário entrar. O dispositivo instalará automaticamente as políticas e os aplicativos necessários, sem qualquer intervenção da equipe de ti.

## <a name="default-policies"></a>Políticas padrão

Esta tabela destaca as políticas padrão que são aplicadas a todos os dispositivos de área de trabalho gerenciada da Microsoft durante o provisionamento de dispositivos. Todas as alterações detectadas não aprovadas pela equipe de operações de área de trabalho gerenciada pela Microsoft para objetos gerenciados pelo Microsoft Managed desktop serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | A [linha de base de segurança da Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM é configurada para todos os dispositivos de área de trabalho gerenciado Essa linha de base é a configuração padrão da indústria. Ele é lançado publicamente, bem testado e revisado pelos especialistas de segurança da Microsoft para manter os dispositivos e aplicativos de área de trabalho gerenciada da Microsoft seguros no local de trabalho moderno. <br><br>Para reduzir as ameaças no panorama de ameaças à segurança em constante evolução, a linha de base de segurança da Microsoft será atualizada e implantada em dispositivos de área de trabalho gerenciada da Microsoft com cada atualização de recurso do Windows 10.<br><br>Para obter mais informações, consulte [linhas de base de segurança do Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines).
Modelo de segurança recomendado para área de trabalho gerenciada da Microsoft | Um conjunto de alterações recomendadas à linha de base de segurança que otimizam a experiência do usuário.  Essas alterações são documentadas no [adendo de segurança](#security-addendum). As atualizações para o adendo de política ocorrem em uma base conforme necessário.  
Implantação de atualização | Use o Windows Update para empresas para executar a implantação gradual de atualizações de software. Os administradores de ti não podem modificar as configurações das diretivas de grupo de implantação. Para obter mais informações sobre a implantação baseada em grupo, consulte [como as atualizações são tratadas na área de trabalho gerenciada da Microsoft](updates.md).
Conexões limitadas | Por padrão, as atualizações em conexões limitadas (como redes LTE) estão desativadas, embora cada usuário possa ativar o recurso de forma independente em **configurações > atualizações > opções avançadas**. Se você deseja permitir que todos os usuários habilitem atualizações em conexões limitadas, [envie uma solicitação de alteração](../working-with-managed-desktop/admin-support.md), o que ativará essa configuração para todos os dispositivos.
| Conformidade do dispositivo | Essas políticas são configuradas para todos os dispositivos de área de trabalho gerenciada da Microsoft. Um dispositivo é relatado como não compatível quando ele se desfere da configuração de segurança necessária.

## <a name="windows-diagnostic-data"></a>Dados de diagnóstico do Windows

 Os dispositivos serão definidos para fornecer dados de diagnóstico avançados à Microsoft sob um identificador comercial conhecido. Como parte da área de trabalho gerenciada da Microsoft, os administradores de ti não podem alterar essas configurações. Para clientes nas regiões RGPD (regulamentação de proteção de dados) gerais, os usuários podem reduzir o nível de dados de diagnóstico fornecidos, mas haverá uma redução no serviço. Por exemplo, a área de trabalho gerenciada da Microsoft não conseguirá coletar os dados necessários para iterar nas configurações e políticas para melhor atender às necessidades de desempenho e segurança. Para obter mais informações, consulte [configurar os dados de diagnóstico do Windows em sua organização.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Adendo de segurança

 Esta seção descreve as políticas que serão implantadas além das políticas padrão de área de trabalho gerenciada da Microsoft listada em [políticas padrão](#default-policies). Essa configuração foi projetada com serviços financeiros e setores altamente regulamentados em mente, otimizando o máximo de segurança enquanto mantém a produtividade do usuário.

 ### <a name="additional-security-policies"></a>Políticas de segurança adicionais

 Essas políticas são adicionadas para aumentar a segurança de setores altamente regulamentados. 
 - **Monitoramento de segurança** : a Microsoft monitorará dispositivos usando [o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se uma ameaça for detectada, a Microsoft irá notificar o cliente, isolar o dispositivo e retificar o problema remotamente. 
 - **Disable PowerShell v2** : a Microsoft removeu o PowerShell V2 em agosto de 2017. Este recurso foi desabilitado em todos os dispositivos de área de trabalho gerenciada da Microsoft. Para obter mais informações sobre essa alteração, consulte [Windows PowerShell 2,0 Preterition](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
