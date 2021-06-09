---
title: Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Intune
description: Saiba como gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune
keywords: pós-migração, gerenciar, operações, manutenção, utilização, intune, Microsoft Defender para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: a8c5f5e04c629eb82a7e6f63f92d61030c544de4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841901"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Recomendamos o [uso Microsoft Endpoint Manager](/mem), que inclui o Microsoft Intune (Intune) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). [Saiba mais sobre Endpoint Manager](/mem/endpoint-manager-overview).

Este artigo descreve como encontrar suas configurações do Microsoft Defender para Ponto de Extremidade no Intune e lista várias tarefas que você pode executar.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Encontre suas configurações do Microsoft Defender para Ponto de Extremidade no Intune

> [!IMPORTANT]
> Você deve ser um administrador global ou administrador de serviço no Intune para definir as configurações descritas neste artigo. Para saber mais, confira **[Tipos de administradores (Intune)](/mem/intune/fundamentals/users-add#types-of-administrators)**.

1. Vá para o portal do Azure ( [https://portal.azure.com](https://portal.azure.com) ) e entre.

2. Em **Serviços do Azure,** escolha **Intune**.

3. No painel de navegação à esquerda, **escolha** Configuração do dispositivo e, em **Gerenciar,** escolha **Perfis**.

4. Selecione um perfil existente ou crie um novo.

> [!TIP]
> Precisa de ajuda? Consulte **[Usando o Microsoft Defender para Ponto de Extremidade com o Intune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Configurar o Microsoft Defender para Ponto de Extremidade com o Intune

A tabela a seguir lista várias tarefas que você pode executar para configurar o Microsoft Defender para Ponto de Extremidade com o Intune. Não é preciso configurar tudo de uma vez. escolha uma tarefa, leia os recursos correspondentes e prossiga.

|Tarefa  |Recursos para saber mais  |
|---------|---------|
|**Gerenciar os dispositivos da sua organização usando o Intune** para proteger esses dispositivos e dados armazenados neles     |[Proteger dispositivos com o Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Integrar o Microsoft Defender para Ponto de Extremidade com o Intune** como uma solução de Defesa contra Ameaças Móveis <br/>*(para dispositivos Android e dispositivos que executam Windows 10 ou posteriores)*   |[Impor a conformidade para o Microsoft Defender para Ponto de Extremidade com Acesso Condicional no Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Usar o Acesso Condicional** para controlar os dispositivos e aplicativos que podem se conectar aos seus recursos de email e empresa |[Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Configurar Microsoft Defender Antivírus configurações usando** o provedor de serviços de configuração de política ([CSP de política](/windows/client-management/mdm/policy-configuration-service-provider)) |[Restrições de dispositivo: Microsoft Defender Antivírus](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP de política - Microsoft Defender para Ponto de Extremidade](/windows/client-management/mdm/policy-csp-defender)  | 
|**Se necessário, especifique exclusões para Microsoft Defender Antivírus** <br/><br/>*Geralmente, você não deve precisar aplicar exclusões. Microsoft Defender Antivírus inclui várias exclusões automáticas com base em comportamentos conhecidos do sistema operacional e arquivos de gerenciamento típicos, como aqueles usados no gerenciamento empresarial, gerenciamento de banco de dados e outros cenários corporativos.* |[Recomendações de verificação de vírus para Enterprise computadores que estão executando versões com suporte de Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Restrições de dispositivo: Microsoft Defender Antivírus exclusões para Windows 10 dispositivos](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Configurar Microsoft Defender Antivírus exclusões no Windows Server 2016 ou 2019](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Configure suas regras de redução** de superfície de ataque para direcionar comportamentos de software que geralmente são abusadas por invasores<br/><br/>*Configure suas regras de redução de superfície de ataque no modo [de](/microsoft-365/security/defender-endpoint/audit-windows-defender) auditoria inicialmente (por pelo menos uma semana e até dois meses). Você pode monitorar o status usando Power BI ([obter nosso modelo](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) e definir essas regras para o modo ativo quando estiver pronto.* |[Modo de auditoria no Microsoft Defender para Ponto de Extremidade ](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Proteção do ponto de extremidade: Redução de superfície de ataque](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Saiba mais sobre regras de redução de superfície de ataque](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Postagem Community blog de tecnologia: Desmistificando regras de redução de superfície de ataque - Parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Configure sua filtragem de rede para** bloquear conexões de saída de qualquer aplicativo para endereços IP ou domínios com baixa reputação  <br/><br/>*A filtragem de rede também é chamada de proteção [de rede.](/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Certifique-se de Windows 10 dispositivos com as atualizações mais recentes da plataforma [antimalware](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) instaladas.*|[Proteção de ponto de extremidade: Filtragem de rede](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Revisar eventos de proteção de rede Windows Visualizador de Eventos](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <br/><br/>*[O acesso controlado a](/microsoft-365/security/defender-endpoint/controlled-folders) pastas também é conhecido como proteção antiransomware.*  |[Proteção de ponto de extremidade: Acesso controlado a pastas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar o acesso controlado a pastas no Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Configurar a proteção de exploração** para proteger os dispositivos da sua organização contra malware que usa explorações para propagar e infectar outros dispositivos <br/><br/> *[A proteção de](/microsoft-365/security/defender-endpoint/exploit-protection) exploração também é conhecida como Exploit Guard.* |[Proteção de ponto de extremidade: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Habilitar a proteção de exploração no Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Configure Microsoft Defender SmartScreen** proteção contra sites mal-intencionados e arquivos na Internet. <br/><br/> *Microsoft Edge deve ser instalado nos dispositivos da sua organização. Para proteção nos navegadores Google Chrome e FireFox, configure exploit protection.*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Restrições de dispositivo: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Configurações de política para gerenciar o SmartScreen no Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Configure Microsoft Defender Firewall** bloquear o tráfego de rede não autorizado fluindo para dentro ou para fora dos dispositivos da sua organização  |[Proteção de ponto de extremidade: Microsoft Defender Firewall](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall com Segurança Avançada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Configure a criptografia e BitLocker** para proteger informações sobre os dispositivos da sua organização que executam Windows |[Proteção do ponto de extremidade: Windows Criptografia](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker para Windows 10 dispositivos](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Configurar o Microsoft Defender Credential Guard** para proteger contra ataques de roubo de credenciais |Para Windows 10, Windows Server 2016 e Windows Server 2019, consulte [Endpoint protection: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Para Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 e Windows Server 2012 R2, consulte Mitigando ataques de passagem do hash (PtH) e Outros roubos de [credenciais, versões 1](https://www.microsoft.com/download/details.aspx?id=36036) e 2  |
|**Configurar o Controle de Aplicativos** do Microsoft Defender para escolher se deve auditar ou confiar em aplicativos nos dispositivos da sua organização <br/><br/>*O Controle de Aplicativos do Microsoft Defender também é conhecido como [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview).*|[Implantar políticas de Controle de Aplicativos do Microsoft Defender usando Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Proteção de ponto de extremidade: Controle de aplicativo do Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**Configurar o controle de dispositivo e o acesso a periféricos USB** para ajudar a evitar que ameaças em periféricos não autorizados a comprometer seus dispositivos |[Controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para o Ponto de Extremidade e o Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Configure seu Central de Segurança do Microsoft Defender

Se você ainda não fez **isso,** configure seu Central de Segurança do Microsoft Defender ( ) para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da [https://securitycenter.windows.com](https://securitycenter.windows.com) sua organização. 

Você também pode configurar se e quais recursos os usuários finais podem ver no Central de Segurança do Microsoft Defender.

- [Visão geral do Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Central de Segurança do Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obter uma visão geral do Gerenciamento de Ameaças e Vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de Central de Segurança do Microsoft Defender de operações de segurança](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
