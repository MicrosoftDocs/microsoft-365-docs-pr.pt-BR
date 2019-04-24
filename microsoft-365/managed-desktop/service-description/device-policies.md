---
title: Configuração do dispositivo
description: Saiba mais sobre as políticas padrão aplicadas aos dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278620"
---
# <a name="device-configuration"></a>Configuração do dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo dispositivo de área de trabalho gerenciado da Microsoft está sendo provisionado, garantimos que a configuração correta, otimizada para a área de trabalho gerenciada da Microsoft, esteja em vigor. Isso inclui um conjunto de políticas padrão definidas como parte do processo de integração. Para evitar conflitos, essas políticas não devem ser alteradas. 

Os dispositivos chegarão com uma imagem de assinatura e entrarão no domínio do Azure Active Directory quando o primeiro usuário fizer logon. O dispositivo instalará automaticamente as políticas e os aplicativos necessários, sem qualquer intervenção de ti necessária.

## <a name="why-mdm-over-group-policy"></a>Por que o MDM sobre a política de grupo

Há alguns motivos para usar o gerenciamento de dispositivo móvel (MDM) em vez da política de Grupo:

- Security-as políticas MDM são mais seguras no mundo moderno. A política de grupo foi projetada para funcionar melhor com a identidade local enquanto o MDM foi projetado para funcionar melhor com o gerenciamento de identidade na nuvem (Azure Active Directory).
- Confiabilidade-as políticas MDM oferecem implantação de política mais confiável. Além disso, as configurações de MDM substituem as políticas de GPO (objeto de diretiva de grupo). A partir do Windows 10, versão 1803, as configurações de MDM serão priorizadas sobre os valores de política de grupo, que dão suporte aos clientes que estão migrando para o gerenciamento moderno. 
- Alinhar-se com a visão da área de trabalho gerenciada da Microsoft – fornece um monitoramento mais abrangente sobre a implantação de políticas e oferece suporte à abordagem baseada em grupo para a implantação gradual de alterações de política com capacidade de pausar/retomar

Para mais informações, consulte [Gerenciamento de dispositivos móveis](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Políticas padrão

Esta tabela destaca as políticas padrão que são aplicadas a todos os dispositivos de área de trabalho gerenciada da Microsoft durante o provisionamento de dispositivos. Todas as alterações detectadas não aprovadas pela equipe de operações de área de trabalho gerenciada pela Microsoft para objetos gerenciados pelo Microsoft Managed desktop serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | A [linha de base de segurança da Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) para MDM é configurada para todos os dispositivos de área de trabalho gerenciado Essa linha de base é a configuração padrão da indústria. Ele é lançado publicamente, bem testado e revisado pelos especialistas de segurança da Microsoft para manter os dispositivos e aplicativos de área de trabalho gerenciada da Microsoft seguros no local de trabalho moderno. <br><br>Para reduzir as ameaças no panorama de ameaças à segurança em constante evolução, a linha de base de segurança da Microsoft será atualizada e implantada em dispositivos de área de trabalho gerenciada da Microsoft com cada atualização de recurso do Windows 10.<br><br>Para obter mais informações, consulte [Security Baseline for Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Modelo de segurança recomendado para área de trabalho gerenciada da Microsoft | Um conjunto de alterações recomendadas à linha de base de segurança que otimizam a experiência do usuário.  Essas alterações são documentadas no [adendo de segurança](#security-addendum). As atualizações para o adendo de política ocorrem em uma base conforme necessário.  
Conformidade do dispositivo | Essas políticas são configuradas por padrão para todos os dispositivos de área de trabalho gerenciada da Microsoft. Um dispositivo é relatado como não compatível quando uma das seguintes condições de segurança não é atendida:<br>– Criptografia de dispositivo BitLocker habilitada, para proteger dados em dispositivos. Para obter mais informações, consulte [Overview of BitLocker Device Encryption in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>– Inicialização segura habilitada e imposta, para validar imagens de firmware em dispositivos antes que eles possam ser executados. Para obter mais informações, consulte [Secure Boot and Device Encryption Overview.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-O dispositivo de área de trabalho gerenciado da Microsoft exige senha para o logon.
Implantação de atualização | Use o Windows Update for Business (WUfB) para executar a implantação gradual de atualizações de software. Os administradores de ti não podem modificar as configurações das diretivas de grupo de implantação. Para obter mais informações sobre a implantação baseada em grupo, consulte [como as atualizações são tratadas](../working-with-managed-desktop/updates.md).
Dados de diagnóstico | Os dispositivos serão definidos para fornecer dados de diagnóstico avançados à Microsoft sob um identificador comercial conhecido. Como parte da área de trabalho gerenciada da Microsoft, os administradores de ti não podem alterar essas configurações. Para clientes nas regiões RGPD (regulamentação de proteção de dados) gerais, os usuários finais podem reduzir o nível de dados de diagnóstico fornecidos, mas haverá uma redução no serviço. Por exemplo, a área de trabalho gerenciada da Microsoft não conseguirá coletar os dados necessários para iterar nas configurações e políticas para melhor atender às necessidades de desempenho e segurança. Para obter mais informações, consulte [configurar os dados de diagnóstico do Windows em sua organização.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Adendo de segurança

 Esta seção descreve as políticas que serão implantadas como adicionais às políticas padrão de área de trabalho gerenciada da Microsoft. As políticas padrão são listadas em [políticas padrão](#default-policies). Essa configuração foi projetada com serviços financeiros e setores altamente regulamentados em mente: otimizando para a postura mais segura, mantendo a produtividade do usuário.

 ### <a name="additional-security-policies"></a>Políticas de segurança adicionais

 Essas políticas são adicionadas para aumentar a segurança de setores altamente regulamentados. 
 - **Lista de permissões de aplicativo**: os aplicativos devem ser confiáveis para que a organização seja executada em dispositivos de área de trabalho gerenciada da Microsoft. Isso fornece um ambiente bloqueado. Qualquer aplicativo que precise ser integrado deve ser comunicado à equipe de operações de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Monitoramento de segurança**: a Microsoft monitorará dispositivos usando a [proteção avançada contra ameaças do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se uma ameaça for detectada, a Microsoft notificará o cliente, isolará o dispositivo e corrigirá o problema remotamente. 

