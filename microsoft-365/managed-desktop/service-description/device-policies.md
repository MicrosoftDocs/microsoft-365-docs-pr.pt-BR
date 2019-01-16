---
title: Configuração de dispositivo
description: Saiba mais sobre as políticas padrão aplicadas aos dispositivos Microsoft Desktop gerenciados.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865126"
---
# <a name="device-configuration"></a>Configuração de dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo dispositivo de área de trabalho gerenciada do Microsoft está sendo provisionado, garantimos a configuração correta, otimizada para Microsoft Desktop gerenciados, está no lugar. Isso inclui um conjunto de políticas padrão que são definidos como parte do processo de inclusão. Para evitar conflitos, essas políticas não devem ser alteradas. 

Dispositivos chegarem com uma imagem da assinatura, e ingressar em domínio do Windows Azure Active Directory quando o primeiro usuário fizer logon. O dispositivo instalará automaticamente políticas necessárias e aplicativos sem qualquer intervenção de TI necessárias.

## <a name="why-mdm-over-group-policy"></a>Por que MDM sobre diretiva de grupo

Há poucos motivos para usar o gerenciamento de dispositivos móveis (MDM) em vez de diretiva de grupo:

- Segurança – MDM políticas são mais seguras do mundo moderno. Diretiva de grupo foi projetada para funcionar melhor com identidade local enquanto MDM projetado para funcionar melhor com o gerenciamento de identidades de nuvem (Azure Active Directory).
- Confiabilidade - políticas MDM fornecem mais confiável implantação da diretiva. Além disso, as configurações de MDM substituir políticas de objeto de diretiva de grupo (GPO). Começando com Windows 10, versão 1803, configurações de MDM terão prioridade sobre os valores da diretiva de grupo, que oferece suporte a clientes que estejam mudando para gerenciamento moderno. 
- Se alinhem à visão da Microsoft Desktop gerenciados - fornece monitoramento mais abrangente sobre a implantação de política e oferece suporte a abordagem baseada no grupo para alterações de diretiva de distribuição gradualmente com capacidade para pausar / continuar a implantação quando necessário.

Para obter mais informações, consulte [Gerenciamento de dispositivos móveis](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Políticas padrão

Esta tabela destaca as políticas padrão que são aplicadas a todos os dispositivos de área de trabalho do Microsoft gerenciados durante o provisionamento de dispositivo. Todos os detectados alterações não aprovadas pela equipe de operações de área de trabalho gerenciada do Microsoft aos objetos gerenciados pelo Microsoft Desktop gerenciados serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | O [Microsoft baseline de segurança](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM é configurado para todos os dispositivos de área de trabalho do Microsoft gerenciados. Essa linha de base é a configuração padrão do setor. Ele for lançado publicamente, bem testados e foi analisado por especialistas de segurança da Microsoft para manter os dispositivos de área de trabalho gerenciada do Microsoft e seguro de aplicativos no local de trabalho moderno.<br><br>Para atenuar as ameaças no cenário das ameaças de segurança-evoluem, a linha de base de segurança do Microsoft será atualizada e implantada nos dispositivos Microsoft Desktop gerenciados com cada atualização de recurso do Windows 10.<br><br>Para obter mais informações, consulte [Security baseline para Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Microsoft Desktop gerenciados recomendado de modelo de segurança | Um conjunto de alterações na linha de base de segurança recomendadas que otimizar a experiência do usuário.  Essas alterações são documentadas nos [Addendum a segurança](#security-addendum). Atualizações para o addendum política ocorrerem em conforme necessário.  
Conformidade de dispositivo | Essas diretivas são configuradas por padrão para todos os dispositivos de área de trabalho do Microsoft gerenciados. Um dispositivo é relatado como incompatíveis quando uma das seguintes condições de segurança não for atendida:<br>-Criptografia de dispositivo BitLocker habilitado, para proteger os dados em dispositivos. Para obter mais informações, consulte [Visão geral do dispositivo de disco BitLocker no Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Inicialização segura habilitada e imposto para validar as imagens do firmware em dispositivos antes que eles podem executar. Para obter mais informações, consulte [overview segura de criptografia de inicialização e o dispositivo.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Dispositivo de área de trabalho Microsoft gerenciados exige a senha para logon.
Implantação da atualização | Use o Windows Update para negócios (WUfB) para executar a implantação gradual de atualizações de software. Administradores de TI não podem modificar as configurações para as diretivas de grupo de implantação. Para obter mais informações sobre a implantação baseada em grupo, consulte [como as atualizações são manipuladas](../working-with-managed-desktop/updates.md).
Telemetria | Forneça dados de diagnóstico avançados à Microsoft sob um identificador comercial conhecido dispositivos serão definidos. Como parte do Microsoft Desktop gerenciado, os administradores de TI não podem alterar essas configurações. Para os clientes em geral regiões de regulamentação de proteção de dados (GDPR), os usuários finais podem reduzir o nível de dados de diagnóstico que são fornecidos, mas haverá uma redução no serviço. Por exemplo, o Microsoft Desktop gerenciados será não é possível coletar os dados necessários para iterar em configurações e políticas para atender melhor às necessidades de desempenho e segurança. Para obter mais informações, consulte [dados de diagnóstico de configurar o Windows em sua organização.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Addendum de segurança

 Esta seção descreve as políticas que serão implantadas como adicionais com as políticas padrão do Microsoft Desktop gerenciados. Políticas padrão são listadas nas [políticas padrão](#default-policies). Essa configuração foi projetada com serviços financeiros e altamente regulamentado setores em mente: otimização para a posição mais segura, enquanto preservam a produtividade do usuário.

 ### <a name="additional-security-policies"></a>Diretivas de segurança adicionais

 Essas diretivas são adicionadas para aumentar a segurança para setores altamente regulamentado. 
 - **Lista de permissões do aplicativo**: aplicativos devem ser confiáveis pela organização para executar em dispositivos Microsoft Desktop gerenciados. Isso oferece um ambiente bloqueado. Quaisquer aplicativos que precisam ser onboarded devem ser comunicados para a equipe de operações de área de trabalho gerenciada do Microsoft. Para obter mais informações, consulte [Windows Defender dispositivo Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Monitoramento de segurança**: Microsoft monitorará dispositivos usando [A proteção de ameaça avançado do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se uma ameaça ser detectada, Microsoft notificará o cliente, isolar o dispositivo e corrigir o problema remotamente. 

