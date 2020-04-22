---
title: 'Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para o Windows 10 Enterprise.
ms.openlocfilehash: cf4a813a6cf89029eebde8e5947caf7b3c2ea553
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636682"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Fase 3: critérios de saída da infraestrutura do Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Verifique se a infraestrutura do Windows 10 Enterprise atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Obrigatório: seus domínios do Microsoft 365 são adicionados e verificados

O locatário do Azure AD para o Office 365 e suas assinaturas do Intune são configurados com os nomes de domínio da Internet (como contoso.com), em vez de apenas um nome de domínio que inclui "onmicrosoft.com". 

Se não fizer isso, você sofrerá limitações nos métodos de autenticação que podem ser configurados. Por exemplo, a senha e a autenticação federada não podem usar o nome de domínio "onmicrosoft.com".

Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com esse requisito.

## <a name="optional-your-users-are-added-and-licensed"></a>Opcional: os usuários são adicionados e licenciados

As contas que correspondem aos usuários são adicionadas, diretamente ao locatário do Azure AD para as assinaturas do Office 365 e do Intune ou na sincronização do diretório dos Serviços de Domínio do Active Directory (AD DS) local.

Depois de adicionar os usuários, atribua licenças do Microsoft 365 Enterprise a eles, diretamente como um administrador de usuários ou global ou automaticamente usando uma associação de grupo.

Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.

## <a name="optional-diagnostics-are-enabled"></a>Opcional: os diagnósticos são habilitados

Você habilitou as configurações de dados de diagnóstico usando a Política de Grupo, o Microsoft Intune, o Editor do Registro ou no prompt de comando.

Se necessário, a [Etapa 1](windows10-prepare-your-org.md) pode ajudá-lo com essa opção.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Obrigatório para atualização in-loco: criou uma sequência de tarefas do Gerenciador de Configurações para a implantação de um sistema operacional

Para iniciar uma sequência de tarefas do Gerenciador de Configurações para realizar uma atualização in-loco em um dispositivo que executa o Windows 7 ou o Windows 8.1, você deve:

- Definir níveis de dados adequados de diagnóstico do Windows
- Verificar a preparação para atualização do Windows
- Criar uma sequência de tarefas do Gerenciador de Configurações que inclua uma coleção de dispositivos e a implantação de um sistema operacional com uma imagem do sistema operacional do Windows 10

Após a implantação, realize atualizações in-loco nos dispositivos que estiverem preparados para a atualização para o Windows. Para obter o máximo proveito do Microsoft 365 Enterprise, atualize o maior número possível de dispositivos que executam o Windows 7 e o Windows 8.1. 

Todos dispositivos que executam o Windows 10 Enterprise podem aproveitar as vantagens da solução integrada do Microsoft 365 Enterprise. Os demais dispositivos, que executam o Windows 7 ou o Windows 8.1, não podem usar tecnologias conectadas na nuvem e os recursos de segurança avançados do Windows 10 Enterprise.

Se necessário, a [Etapa 2](windows10-deploy-inplaceupgrade.md) pode ajudá-lo com esse requisito.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Obrigatório para novos dispositivos: Windows Autopilot configurado

Para usar o Windows Autopilot para implantar e personalizar o Windows 10 Enterprise um novo dispositivo, você deve:

- Definir os níveis adequados de dados de diagnóstico do Windows
- Definir os pré-requisitos para o Windows Autopilot, que incluem:
   - Registro do dispositivo e personalização da OOBE
   - Identidade visual da empresa para OOBE
   - Registro automático do MDM do Microsoft Intune
   - Conectividade de rede para os serviços de nuvem usados pelo Windows Autopilot
- Dispositivos que estão pré-instalados no Windows 10, versão 1703 ou posterior
- Selecionado o Windows Autopilot Deployment Program para sua organização

Depois de concluir a configuração do Windows Autopilot, você pode usá-lo para configurar e personalizar o Windows 10 Enterprise com a OOBE ( Configuração Inicial pelo Usuário) para:

- Novos dispositivos
- Dispositivos que já concluíram uma configuração pronta na organização. 

O Windows Autopilot configura o dispositivo e o conecta ao Azure AD.

Caso não tenha o Windows Autopilot, configure manualmente os novos dispositivos, incluindo a conexão com o Azure AD.

Se necessário, a [Etapa 3](windows10-deploy-autopilot.md) pode ajudá-lo com esse requisito.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Opcional: você está usando a Integridade do Dispositivo do Windows Analytics para monitorar seus dispositivos baseados no Windows 10 Enterprise

Você usou as informações em Monitorar a integridade de dispositivos com a Integridade do Dispositivo para detectar e corrigir problemas que afetam os usuários finais. Ao tratar rapidamente dos problemas do usuário final, é possível reduzir os custos de suporte e demonstrar aos usuários o compromisso da TI com o Windows 10 Enterprise. Isso pode ajudar a promover a adoção em toda a organização. 

Se necessário, a [Etapa 4](windows10-enable-windows-analytics.md) pode ajudá-lo com essa opção.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Obrigatório: você está usando o Windows Defender Antivirus ou uma solução antimalware

Você implantou o Windows Defender Antivirus ou sua própria solução antivírus para proteger seus dispositivos que executam o Windows 10 Enterprise contra softwares mal-intencionados. Se tiver implantado o Windows Defender Antivirus, você implementou um método de relatório, como o Microsoft Endpoint Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de antivírus.

Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-av) pode ajudá-lo com esse requisito.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Obrigatório: você está usando o Windows Defender Exploit Guard

Você implantou o Windows Defender Exploit Guard para proteger seus dispositivos que executam o Windows 10 Enterprise contra invasões e implementou um método de relatório, como o Configuration Manager ou o Microsoft Intune, para monitorar eventos e atividades de invasão.

Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-eg) pode ajudá-lo com esse requisito.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>Obrigatório: você está usando a Proteção Avançada Contra Ameaças do Microsoft Defender (Microsoft 365 Enterprise E5 apenas)

Você implantou a Proteção Avançada contra Ameaças do Microsoft Defender (ATP) para detectar, investigar e responder a ameaças avançadas contra sua rede e dispositivos que executam o Windows 10 Enterprise. 

Como opção, você integrou o Microsoft Defender ATP com outras ferramentas para expandir seus recursos.

Se necessário, a [Etapa 5](windows10-enable-security-features.md#windows10-sec-atp) pode ajudá-lo com esse requisito.

## <a name="results-and-next-steps"></a>Resultados e próximas etapas

Sua infraestrutura do Windows 10 Enterprise está pronta para ser instalada em novos dispositivos e atualizações em vigor em dispositivos executando versões anteriores do Windows, e você está usando os principais recursos de segurança do Windows 10 Enterprise.

|||
|:-------|:-----|
|![Fase 4 - Microsoft 365 Apps para empresas](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Se você está seguindo as fases para a implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase é [Microsoft 365 Apps para empresas](office365proplus-infrastructure.md). |
