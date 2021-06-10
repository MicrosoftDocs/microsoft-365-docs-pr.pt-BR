---
title: Configuração do dispositivo
description: Saiba mais sobre as políticas padrão aplicadas a Área de Trabalho Gerenciada da Microsoft dispositivos.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920487"
---
# <a name="device-configuration"></a>Configuração do dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo Área de Trabalho Gerenciada da Microsoft está sendo definido, garantimos que ele tenha a configuração correta otimizada para Área de Trabalho Gerenciada da Microsoft. Essa configuração inclui um conjunto de políticas padrão definidas como parte do processo de integração. Essas políticas são entregues usando o Gerenciamento de Dispositivo Móvel (MDM) sempre que possível. Para obter mais informações, consulte [Mobile Device Management](/windows/client-management/mdm/). 

>[!NOTE]
>Para evitar conflitos, não altere essas políticas.

Os dispositivos chegarão com uma imagem de assinatura e ingressarão no domínio Azure Active Directory quando o primeiro usuário entrar. O dispositivo instalará automaticamente as políticas e aplicativos necessários sem qualquer intervenção de sua equipe de TI.

## <a name="default-policies"></a>Políticas padrão

Esta tabela realça as políticas padrão que são aplicadas a todos os dispositivos Área de Trabalho Gerenciada da Microsoft durante o provisionamento de dispositivos. Todas as alterações detectadas não aprovadas pelo Área de Trabalho Gerenciada da Microsoft Operations Team para objetos gerenciados por Área de Trabalho Gerenciada da Microsoft serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | [A linha de base de](/windows/device-security/windows-security-baselines) segurança da Microsoft para MDM está configurada para todos os Área de Trabalho Gerenciada da Microsoft dispositivos. Essa linha de base é a configuração padrão do setor. Ele é lançado publicamente, bem testado e foi revisado por especialistas em segurança da Microsoft para manter Área de Trabalho Gerenciada da Microsoft dispositivos e aplicativos seguros no local de trabalho moderno. <br><br>Para atenuar as ameaças no cenário de ameaças de segurança em constante evolução, a linha de base de segurança da Microsoft será atualizada e implantada em dispositivos Área de Trabalho Gerenciada da Microsoft com cada atualização Windows 10 de recursos.<br><br>Para obter mais informações, [consulte Windows de segurança](/windows/security/threat-protection/windows-security-baselines).
Área de Trabalho Gerenciada da Microsoft modelo de segurança recomendado | Um conjunto de alterações recomendadas na linha de base de segurança que otimizam a experiência do usuário.  Essas alterações são documentadas [no Security Addendum](#security-addendum). As atualizações para o complemento de política ocorrem conforme necessário.  
Atualizar implantação | Use Windows Update for Business para executar a implantação gradual de atualizações de software. Os administradores de IT não podem modificar as configurações das políticas de grupo de implantação. Para obter mais informações sobre a implantação baseada em grupo, consulte [How updates are handled in Área de Trabalho Gerenciada da Microsoft](updates.md).
Conexões com medida | Por padrão, as atualizações sobre conexões com metros (como redes LTE) são desligadas, embora cada usuário possa ativar esse recurso independentemente no Configurações > Atualizações > **Opções avançadas.** Se você quiser permitir que todos os usuários habilitam atualizações por conexões com [metros,](../working-with-managed-desktop/admin-support.md)envie uma solicitação de alteração , que ativará essa configuração para todos os dispositivos.
| Conformidade do dispositivo | Essas políticas são configuradas para todos os Área de Trabalho Gerenciada da Microsoft dispositivos. Um dispositivo é relatado como não compatível quando ele deriva de nossa configuração de segurança necessária.

## <a name="windows-diagnostic-data"></a>Windows dados de diagnóstico

 Os dispositivos serão definidos para fornecer dados de diagnóstico aprimorados à Microsoft sob um identificador comercial conhecido. Como parte do Área de Trabalho Gerenciada da Microsoft, os administradores de IT não podem alterar essas configurações. Para clientes em regiões de RGPD (Regulamento Geral de Proteção de Dados), os usuários podem reduzir o nível de dados de diagnóstico fornecidos, mas haverá uma redução no serviço. Por exemplo, Área de Trabalho Gerenciada da Microsoft não será possível coletar os dados necessários para iterar em configurações e políticas para atender melhor às necessidades de desempenho e segurança. Para obter mais informações, consulte [Configure Windows dados de diagnóstico em sua organização.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Complemento de segurança

 Esta seção descreve as políticas que serão implantadas além das políticas de Área de Trabalho Gerenciada da Microsoft padrão listadas em [Políticas padrão.](#default-policies) Essa configuração foi projetada com serviços financeiros e setores altamente regulamentados em mente, otimizando para a maior segurança, mantendo a produtividade do usuário.

 ### <a name="additional-security-policies"></a>Políticas de segurança adicionais

 Essas políticas são adicionadas para aumentar a segurança para setores altamente regulamentados. 
 - **Monitoramento de segurança:** a Microsoft monitorará dispositivos usando [o Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Se uma ameaça for detectada, a Microsoft notificará o cliente, isolará o dispositivo e corrigirá o problema remotamente. 
 - **Desabilitar o PowerShell V2**: a Microsoft removeu o PowerShell V2 em agosto de 2017. Esse recurso foi desabilitado em todos os Área de Trabalho Gerenciada da Microsoft dispositivos. Para obter mais informações sobre essa alteração, [consulte Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).