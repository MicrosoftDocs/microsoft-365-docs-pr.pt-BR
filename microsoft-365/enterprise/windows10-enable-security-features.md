---
title: Implantar recursos de segurança do Windows 10 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas de que você precisa para implantar recursos de segurança do Windows 10 Enterprise em computadores como parte do Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, segurança
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: 0f7b4ddec9c52861b4ecf4a7e86831efcce402d6
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370258"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Etapa 5: implantar recursos de segurança do Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

O Windows 10 fornece recursos de segurança para proteger usuários corporativos, interromper o ciberataques e evitar a perda de dados. 

Para saber mais sobre essas tecnologias, confira:

* [Proteção de identidade](https://docs.microsoft.com/windows/security/identity-protection/) -saiba mais sobre o Windows Hello para empresas, o Credential Guard e o controle de acesso.
* [Proteção contra ameaças](https://docs.microsoft.com/windows/threat-protection/) – saiba mais sobre a proteção avançada contra ameaças do Microsoft defender, uma plataforma unificada para proteção preventiva, detecção de pós-violação, investigação automatizada e resposta.
* [Proteção de informações](https://docs.microsoft.com/windows/security/information-protection/) – saiba mais sobre o BitLocker, a proteção de informações do Windows e outras maneiras pelas quais o Windows 10 ajuda a proteger os dados corporativos. 

Esta etapa mostra como você pode implantar, gerenciar, configurar e solucionar problemas usando estes recursos de segurança:

* [Windows Defender Antivírus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Proteção avançada contra ameaças do Microsoft defender](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus
O Windows Defender Antivirus (AV) é uma solução antimalware interna do Windows 10. Ele fornece gerenciamento de segurança e antimalware para desktops, computadores portáteis e servidores. Para obter mais informações sobre o Windows Defender AV, os requisitos mínimos e como você pode gerenciar esse recurso, consulte [Windows Defender Antivirus no Windows 10 e Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Se você não estiver usando o Windows Defender AV como cliente antivírus principal, ou se estiver usando o Microsoft defender ATP, há algumas considerações que você precisa levar em conta. Para saber mais, confira [compatibilidade de AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Implantação e gerenciamento
Para implantar e gerenciar o Windows Defender AV, siga as orientações aqui:

* [Implantar, gerenciar e relatar o AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Tópicos de referência para ferramentas de gerenciamento e configuração](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configuração
Os usuários podem configurar vários recursos. Para obter mais informações, consulte estes recursos:

* [Configurar recursos AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Tópicos de referência para ferramentas de gerenciamento e configuração](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Para ajudar a entender as opções de configuração, consulte esta lista de todas as configurações (conforme definido pela configuração da política de grupo): [usar configurações de política de grupo para configurar e gerenciar o AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Você pode usar o [Guia de avaliação de proteção AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) para ajudar a avaliar o nível de proteção e o impacto do Windows Defender AV em sua rede. Isso também pode ser útil na criação de uma configuração inicial ou como um "guia de início rápido" e é atualizado regularmente para fornecer as recomendações mais úteis para configurar e habilitar recursos para garantir o máximo de proteção.

### <a name="reporting"></a>Reporting
Você pode obter relatórios usando uma ferramenta de configuração, como o System Center Configuration Manager ou o Microsoft Intune. Você também pode obter relatórios da conformidade da atualização (OMS) ou consumir logs de eventos do Windows no seu SIEM. Se você tiver uma licença para o Microsoft defender ATP, também poderá obter relatórios sobre as detecções do Windows Defender AV e realizar a correção básica. Para obter mais informações, consulte estes recursos:
* [Implantar, gerenciar e relatar o AV do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Relatório sobre proteção antivírus do Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Visão geral do portal ATP do Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solução de problemas
Para obter informações sobre como solucionar problemas básicos de erros e códigos de eventos, consulte [revisar logs de eventos e códigos de erro para solucionar problemas com o Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Você também pode enviar problemas (como falsos positivos) usando o sistema de envio de inteligência de segurança do Windows Defender. Para saber como, confira [Enviar problemas para a Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
O Windows Defender Exploit Guard é um novo conjunto de recursos de prevenção de invasão do host para o Windows 10. Para obter mais informações sobre o Windows Defender Exploit Guard, os requisitos mínimos e como você pode gerenciar esse recurso, consulte [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Implantação, gerenciamento e configuração
Para implantar, gerenciar e configurar o Windows Defender Exploit Guard, siga as orientações aqui:
* [Proteção contra Exploit](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Proteção da superfície de ataque](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Proteção de rede](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Acesso a pastas controladas](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Você pode usar uma série de tópicos de avaliação para ajudar a avaliar o nível de proteção e o impacto do Windows Defender Exploit Guard em sua rede. Isso também pode ser útil na criação de uma configuração inicial ou como um "guia de início rápido" e os tópicos e orientações são atualizados regularmente para fornecer as recomendações mais úteis para configurar e habilitar recursos para garantir o máximo de proteção. Para obter mais informações, [avalie o Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Reporting
Você pode obter relatórios usando uma ferramenta de configuração, como o System Center Configuration Manager ou o Intune. Você também pode obter relatórios consumindo logs de eventos do Windows no SIEM. Se você tiver uma licença para o Microsoft defender ATP, também poderá obter relatórios sobre as detecções do Windows Defender AV e realizar a correção básica. Para obter mais informações, consulte estes recursos:
* [Exibir eventos do Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Visão geral do portal ATP do Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solução de problemas
Você pode executar a solução de problemas básica ou, opcionalmente, fornecer os arquivos. cab da Microsoft e enviar problemas (como falsos positivos) usando o sistema de envio de inteligência de segurança do Windows Defender. Para saber como, confira [Enviar problemas para a Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Proteção avançada contra ameaças do Microsoft defender
O Microsoft defender ATP, disponível apenas com o plano Microsoft 365 Enterprise e5, é um serviço de segurança que permite que os clientes corporativos detectem, investiguem e respondam a ameaças avançadas em suas redes. Para obter mais informações sobre o Microsoft defender ATP, os requisitos mínimos e como você pode gerenciar esse recurso, consulte:

* [Microsoft defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisitos mínimos](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Implantação, gerenciamento e configuração
Para implantar o Microsoft defender ATP, você precisará garantir que tenha a licença correta do Windows. Depois de verificar se você tem a licença certa, você precisará decidir a localização geográfica para onde seus dados serão armazenados. Depois, você pode começar a integração de pontos de extremidade ao serviço.

Para obter mais detalhes sobre essas etapas, consulte estes tópicos principais: 

* [Validar provisionamento de licenciamento e configuração completa](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Armazenamento de dados e privacidade](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Pontos de extremidade integrados e acesso de instalação](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Detectar, investigar, responder
Após a integração bem-sucedida de pontos de extremidade ao serviço, você pode começar a investigar alertas de vários painéis. Depois de analisar os alertas, você poderá executar ações de resposta nos alertas. 

Para obter mais informações sobre como fazer isso, consulte:
* [Visão geral do portal ATP do Microsoft defender](https://go.microsoft.com/fwlink/?linkid=861596)
* [Usar o portal ATP do Microsoft defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Executar ações de resposta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integrar com outros produtos e ferramentas
O Microsoft defender ATP integra e oferece suporte a vários outros produtos e ferramentas para expandir seus recursos de segurança. 

Para obter mais informações sobre as ferramentas e outros produtos, consulte:
* [Ferramentas SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Criar alertas personalizados](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Usar APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Criar relatórios do Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Solução de problemas
Você pode encontrar problemas durante a integração ou com o uso do produto. Para obter mais informações sobre como solucionar problemas, consulte:
* [Solucionando problemas de integração](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Solucionando problemas do Microsoft defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura do Windows 10 Enterprise](windows10-exit-criteria.md)
