---
title: Implantar os recursos de segurança do Windows 10 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas que necessárias para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Segurança de documentação, Windows 10 Enterprise, Microsoft 365 365 da Microsoft, Microsoft 365 Enterprise,
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865319"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>Etapa 5: Implantar recursos de segurança do Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 fornece recursos para ajudar a proteger contra ameaças, ajuda você a proteger seus dispositivos e ajudar com controle de acesso. 

Para saber mais sobre essas tecnologias, consulte:
* [Proteção de acesso](https://docs.microsoft.com/windows/access-protection/) - Saiba mais sobre o acesso controle S/MIME, certificados digitais, protetor de credencial, controle de conta de usuário, virtual cartões inteligentes de, Windows Olá para negócios, o Firewall do Windows com segurança avançada e mais
* [Segurança de dispositivo](https://docs.microsoft.com/windows/device-security/) - inclui AppLocker, BitLocker, Guard do dispositivo e módulo de plataforma confiável
* [Proteção contra ameaças](https://docs.microsoft.com/windows/threat-protection/) - inclui Central de segurança do Windows Defender, a proteção de ameaça avançado do Windows Defender, Windows Defender antivírus, Windows Defender aplicativo Guard, tela do Windows Defender inteligentes e proteção de informações do Windows

Esta etapa mostra como você pode implantar, gerenciar, configurar e solucionar problemas usando estes recursos de segurança:

* [Windows Defender Antivírus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Proteção Avançada Contra Ameaças do Windows Defender](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus
Windows Defender antivírus (AV) é uma solução de antimalware incorporada no Windows 10. Ele fornece segurança e gerenciamento de antimalware para desktops, computadores portáteis e servidores. Para obter mais informações sobre o Windows Defender AV, os requisitos mínimos e como você pode gerenciar esse recurso, consulte [Antivirus do Windows Defender em 10 de Windows e Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).

Se você não estiver usando o Windows Defender AV como seu cliente principal de antivírus, ou se você também estiver usando o Windows Defender ATP, há algumas considerações que você precisará levar em conta. Para saber mais, consulte [Compatibilidade Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).

### <a name="deployment-and-management"></a>Implantação e gerenciamento
Para implantar e gerenciar o Windows Defender AV, siga as orientações aqui:

* [Implantar, gerenciar e relatar no Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Tópicos de referência para as ferramentas de gerenciamento e configuração](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>Configuração
Os usuários podem configurar um número de recursos. Para obter mais informações, consulte estes recursos:

* [Configurar recursos do Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [Tópicos de referência para as ferramentas de gerenciamento e configuração](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

Para ajudar a compreender as opções de configuração, consulte a essa lista de todas as configurações (conforme definido pelas suas configurações de diretiva de grupo): [configurações de diretiva de grupo de uso para configurar e gerenciar o Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

Você pode usar a [proteção do Windows Defender AV guia de avaliação](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) para ajudar a avaliar o nível de proteção e o impacto do Windows Defender AV em sua rede. Isso também pode ser útil na criação de uma configuração inicial, ou como um guia de início rápido' ' e é atualizado regularmente para fornecer as recomendações mais útil para configurar e ativar recursos garantir o máximo de proteção.

### <a name="reporting"></a>Relatório
Você pode obter relatórios usando uma ferramenta de configuração, como o System Center Configuration Manager ou Microsoft Intune. Você também pode obter relatórios de conformidade de atualização (OMS) ou ao consumir logs de eventos do Windows no seu SIEM. Se você tiver uma licença para o Windows Defender ATP, você também pode obter relatórios detecções de Windows Defender AV e executar remediação básica. Para obter mais informações, consulte estes recursos:
* [Implantar, gerenciar e relatar no Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Enviar relatórios sobre a proteção do Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Visão geral do Windows Defender ATP portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solução de problemas
Para informações sobre solução de problemas básicos dos códigos de erro e de eventos, consulte [os logs de eventos de revisão e códigos de erro para solucionar problemas com o Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Você também pode enviar questões (por exemplo, falsos positivos) usando o sistema de envio de inteligência de segurança do Windows Defender. Para saber como, consulte [problemas de enviar à Microsoft](https://www.microsoft.com/wdsi/filesubmission).

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender explorar Guard é um novo conjunto de recursos de prevenção de invasão de host para Windows 10. Para obter mais informações sobre o Windows Defender explorar Guard, os requisitos mínimos e como você pode gerenciar esse recurso, consulte [Windows Defender explorar Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).

### <a name="deployment-management-and-configuration"></a>Implantação, gerenciamento e configuração
Para implantar, gerenciar e configurar o Windows Defender explorar Guard, siga as orientações aqui:
* [Proteção de exploração](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [Proteção de superfície de ataque](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [Proteção de rede](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [Pasta acesso controlado](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

Você pode usar uma série de tópicos de avaliação para ajudar a avaliar o nível de proteção e o impacto do Windows Defender explorar Guard em sua rede. Isso também pode ser útil na criação de uma configuração inicial, ou como um guia de início rápido' ' e os tópicos e diretrizes são atualizados regularmente para fornecer as recomendações mais útil para configurar e ativar recursos garantir o máximo de proteção. Para obter mais informações, [Avalie Windows Defender explorar Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).

### <a name="reporting"></a>Relatório
Você pode obter relatórios usando uma ferramenta de configuração, como o System Center Configuration Manager ou Intune. Você também pode obter relatórios ao consumir logs de eventos do Windows no seu SIEM. Se você tiver uma licença para o Windows Defender ATP, você também pode obter relatórios detecções de Windows Defender AV e executar remediação básica. Para obter mais informações, consulte estes recursos:
* [Visualizar eventos do Windows Defender explorar Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Visão geral do Windows Defender ATP portal](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>Solução de problemas
Você pode executar a solução de problemas básicos ou opcionalmente fornecer à Microsoft arquivos. cab e enviar questões (por exemplo, falsos positivos) usando o sistema de envio de inteligência de segurança do Windows Defender. Para saber como, consulte [problemas de enviar à Microsoft](https://www.microsoft.com/wdsi/filesubmission).


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Proteção Avançada Contra Ameaças do Windows Defender
ATP do Windows Defender, disponível apenas com o plano de Microsoft 365 Enterprise E5, é um serviço de segurança que permite aos clientes enterprise detectar, investigar e responder a ameaças avançadas em suas redes. Para obter mais informações sobre o Windows Defender ATP, os requisitos mínimos e como você pode gerenciar esse recurso, consulte:

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [Requisitos mínimos](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>Implantação, gerenciamento e configuração
Para implantar o Windows Defender ATP, você precisará garantir que você tem o direito de licença do Windows. Depois de verificar se você tem a licença de direita, você precisará decidir a localização geográfica para onde os dados serão armazenados. Depois disso, você pode iniciar a inclusão de pontos de extremidade ao serviço.

Para obter mais detalhes sobre essas etapas, consulte estes tópicos principais: 

* [Validar o provisionamento de licenciamento e conclua o conjunto de backup](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [Privacidade e armazenamento de dados](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [Pontos de extremidade onboard e acesso de instalação](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>Detectar, investigue, responder
Após com êxito inclusão pontos de extremidade ao serviço, você pode iniciar investigando alertas a partir de vários painéis. Depois que você tiver investigados alertas, você pode executar ações de resposta em alertas. 

Para obter mais informações sobre como fazer essas, consulte:
* [Visão geral do Windows Defender ATP portal](https://go.microsoft.com/fwlink/?linkid=861596)
* [Usar o portal do Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [Execute as ações de resposta](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>Integração com outros produtos e ferramentas
Windows Defender ATP integra e oferece suporte a vários outros produtos e ferramentas para expandir seus recursos de segurança. 

Para obter mais informações sobre as ferramentas e outros produtos, consulte:
* [Ferramentas SIEM](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [Criar alertas personalizadas](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Usar APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Criar relatórios do Power BI](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>Solução de problemas
Você pode encontrar problemas enquanto você inclusão ou usando o produto. Para obter mais informações sobre como solucionar problemas, consulte:
* [Solucionando problemas de inclusão](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [O Windows Defender ATP de solução de problemas](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída de infraestrutura do Windows 10 Enterprise](windows10-exit-criteria.md)
