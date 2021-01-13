---
title: Configuração do dispositivo
description: Saiba mais sobre as políticas padrão aplicadas aos dispositivos da Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840320"
---
# <a name="device-configuration"></a>Configuração do dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando um novo dispositivo de Área de Trabalho Gerenciada da Microsoft está sendo definido, garantimos que ele tenha a configuração correta otimizada para a Área de Trabalho Gerenciada da Microsoft. Essa configuração inclui um conjunto de políticas padrão definidas como parte do processo de integração. Essas políticas são fornecidas usando o Gerenciamento de Dispositivo Móvel (MDM) sempre que possível. Para obter mais informações, consulte [Gerenciamento de Dispositivo Móvel.](https://docs.microsoft.com/windows/client-management/mdm/) 

>[!NOTE]
>Para evitar conflitos, não altere essas políticas.

Os dispositivos chegarão com uma imagem de assinatura e ingressarão no domínio do Azure Active Directory quando o primeiro usuário entrar. O dispositivo instalará automaticamente as políticas e aplicativos necessários sem intervenção da equipe de TI.

## <a name="default-policies"></a>Políticas padrão

Esta tabela destaca as políticas padrão que são aplicadas a todos os dispositivos da Área de Trabalho Gerenciada da Microsoft durante o provisionamento de dispositivos. Todas as alterações detectadas não aprovadas pela Equipe de Operações de Área de Trabalho Gerenciada da Microsoft para objetos gerenciados pela Área de Trabalho Gerenciada da Microsoft serão revertidas.

Política | Descrição
--- | ---
Linha de base de segurança | [A linha de base de](https://docs.microsoft.com/windows/device-security/windows-security-baselines) segurança da Microsoft para MDM está configurada para todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. Esta linha de base é a configuração padrão do setor. Ele foi lançado publicamente, bem testado e revisado por especialistas em segurança da Microsoft para manter os dispositivos e aplicativos da Área de Trabalho Gerenciada da Microsoft seguros no local de trabalho moderno. <br><br>Para reduzir as ameaças no cenário de ameaças de segurança em constante evolução, a linha de base de segurança da Microsoft será atualizada e implantada em dispositivos da Área de Trabalho Gerenciada da Microsoft com cada atualização de recursos do Windows 10.<br><br>Para obter mais informações, consulte linhas [de base de segurança do Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)
Modelo de segurança recomendado da Área de Trabalho Gerenciada da Microsoft | Um conjunto de alterações recomendadas na linha de base de segurança que otimizam a experiência do usuário.  Essas alterações estão documentadas [no Adendo de Segurança.](#security-addendum) As atualizações do adendo de política ocorrem conforme necessário.  
Atualizar implantação | Use o Windows Update para empresas para executar a implantação gradual de atualizações de software. Os administradores de IT não podem modificar as configurações das políticas de grupo de implantação. Para obter mais informações sobre a implantação baseada em grupo, consulte Como as [atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft.](updates.md)
Conexões monitoradas | Por padrão, as atualizações em conexões medida (como redes LTE) são desligadas, embora cada usuário possa ativar esse recurso independentemente em Configurações > Atualizações > Opções **avançadas.** Se você quiser permitir que todos os usuários habilitam atualizações em conexões [metros,](../working-with-managed-desktop/admin-support.md)envie uma solicitação de alteração, que ativará essa configuração para todos os dispositivos.
| Conformidade do dispositivo | Essas políticas são configuradas para todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. Um dispositivo é relatado como não compatível quando se descondente com a configuração de segurança necessária.

## <a name="windows-diagnostic-data"></a>Dados de diagnóstico do Windows

 Os dispositivos serão definidos para fornecer dados de diagnóstico aprimorados à Microsoft em um identificador comercial conhecido. Como parte da Área de Trabalho Gerenciada da Microsoft, os administradores de IT não podem alterar essas configurações. Para clientes em regiões do RGPD (Regulamento Geral sobre a Proteção de Dados), os usuários podem reduzir o nível de dados de diagnóstico fornecido, mas haverá uma redução no serviço. Por exemplo, a Área de Trabalho Gerenciada da Microsoft não poderá coletar os dados necessários para iterar configurações e políticas para atender melhor às necessidades de desempenho e segurança. Para obter mais informações, [consulte Configurar dados de diagnóstico do Windows em sua organização.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Adendo de segurança

 Esta seção descreve as políticas que serão implantadas além das políticas padrão da Área de Trabalho Gerenciada da Microsoft listadas nas [políticas padrão.](#default-policies) Essa configuração foi projetada com serviços financeiros e setores altamente regulamentados em mente, otimizando para a segurança mais alta, mantendo a produtividade do usuário.

 ### <a name="additional-security-policies"></a>Políticas de segurança adicionais

 Essas políticas são adicionadas para aumentar a segurança de setores altamente regulamentados. 
 - **Monitoramento de segurança:** a Microsoft monitorará dispositivos [usando o Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Se uma ameaça for detectada, a Microsoft notificará o cliente, isolará o dispositivo e corrigirá o problema remotamente. 
 - **Desabilitar o PowerShell V2**: a Microsoft removeu o PowerShell V2 em agosto de 2017. Esse recurso foi desabilitado em todos os dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre essa alteração, consulte a preteração do [Windows PowerShell 2.0.](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)
