---
title: Tecnologias de Área de Trabalho Gerenciada da Microsoft
description: Este artigo lista as tecnologias e os aplicativos usados na Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 70e4eb442f9c0e52dbf234280205dd908c135b8d
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233103"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de Área de Trabalho Gerenciada da Microsoft

Este artigo lista as tecnologias e os aplicativos usados na Área de Trabalho Gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O licenciamento do Microsoft 365 Enterprise é necessário para todos os usuários da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre os requisitos de licenciamento para o serviço, consulte [Pré-requisitos para a Área de Trabalho Gerenciada da Microsoft.](../get-ready/prerequisites.md)

Este artigo resume os componentes incluídos nas licenças Enterprise necessárias, com uma descrição de como o serviço usa cada componente com dispositivos da Área de Trabalho Gerenciada da Microsoft. Funções e responsabilidades específicas para cada área são detalhadas em toda a documentação da Área de Trabalho Gerenciada da Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 ou E5
 |
 --- | ---
Aplicativos do Microsoft 365 para empresas (64 bits) | Esses aplicativos do Office serão fornecidos com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>As versões completas de 64 bits do Microsoft Project e do Microsoft Visio não estão incluídas. No entanto, como a instalação desses aplicativos depende da instalação do Microsoft 365 Apps para empresas, a Área de Trabalho Gerenciada da Microsoft criou implantações padrão do Microsoft Intune e grupos de segurança que você pode usar para implantar esses aplicativos para usuários licenciados. Para obter mais informações, consulte [Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft.](../get-started/project-visio.md)
OneDrive |O Logor Único do Azure Active Directory está habilitado para os usuários quando eles fazem o primeiro login no OneDrive.<br><br>O Redirecionamento de Pasta Conhecida para pastas "Área de Trabalho", "Documento" e "Imagens" está incluído; habilitado e configurado pela Área de Trabalho Gerenciada da Microsoft.
Aplicativos da Loja |    O Microsoft Sway e o Power BI não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Teams não é fornecido com o dispositivo, mas é empacotado e fornecido pela Microsoft para dispositivos da Área de Trabalho Gerenciada da Microsoft. O Cliente de Proteção de Informações do Azure não é fornecido com o dispositivo, mas você pode empacotá-lo para implantação.
Aplicativos Web |  O Yammer, o Office em um navegador, o Delve, o Flow, o StaffHub, o PowerApps e o Planner não são fornecidos com o dispositivo. Os usuários podem acessar a versão web desses aplicativos com um navegador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 ou E3 com o Microsoft Defender para Ponto de Extremidade
Recomendamos que os administradores de IT configurem as configurações a seguir. Essas configurações não são incluídas ou gerenciadas como parte da Área de Trabalho Gerenciada da Microsoft.

 |
 --- | ---
Windows Hello para Empresas | Você deve implementar o Windows Hello para Empresas para substituir senhas por autenticação forte de dois fatores para dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [o Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Virtualização de aplicativo | Você pode implantar pacotes do App-V (Application Virtualization) usando o cliente de gerenciamento de aplicativos Win32 do Intune. Para obter mais informações, consulte [Application Virtualization](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference).
Prevenção contra perda de dados do Microsoft 365 | Você deve implementar a prevenção contra perda de dados do Microsoft 365 para monitorar as ações que estão sendo tomadas em itens que você determinou serem confidenciais e para ajudar a evitar o compartilhamento não intencional desses itens. Para saber mais, confira a prevenção contra perda de dados [do Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)


Recursos incluídos e gerenciados como parte da Área de Trabalho Gerenciada da Microsoft:

 |
 --- | ---
Criptografia de Unidade de Disco BitLocker | A Criptografia de Unidade de Disco BitLocker é usada para criptografar todas as unidades do sistema. Para obter mais informações, consulte [Criptografia de Unidade de Disco BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Protege a integridade do sistema na inicialização e valida que a integridade do sistema realmente foi mantida. Para obter mais informações, consulte [o Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | O Windows Defender Credential Guard usa segurança baseada em virtualização para isolar segredos para que somente o software do sistema privilegiado possa acessá-los. Para obter mais informações, consulte [o Windows Defender System Guard.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender para Ponto de Extremidade - Detecção e Resposta de Ponto de Extremidade | As Operações de Segurança da Área de Trabalho Gerenciada da Microsoft respondem a alertas e toma medidas para remediar ameaças usando Detecção e Resposta de Ponto de Extremidade. Para obter mais informações, consulte Microsoft Defender para Ponto de Extremidade - Detecção e Resposta [de Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender para Ponto de Extremidade - Especialistas em Ameaças | A Área de Trabalho Gerenciada da Microsoft integra-se a informações e dados de Especialistas em Ameaças por meio de notificações de ataque direcionadas. Você terá que dar consentimento adicional antes que esse serviço seja habilitado. Para obter mais informações, [consulte o Microsoft Defender para Ponto de Extremidade - Especialistas em Ameaças.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender para Ponto de Extremidade - Gerenciamento de Ameaças e Vulnerabilidades | Necessário para uso futuro no plano de serviço da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte Microsoft Defender para Ponto de Extremidade - Gerenciamento de Ameaças [e Vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender para Ponto de Extremidade - Redução de Superfície de Ataque | A Redução de superfície de ataque tem como alvo comportamentos de software arriscados que geralmente são invasores invasores. Para obter mais informações, consulte [Microsoft Defender para Ponto de Extremidade - Redução de Superfície de Ataque.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender para Ponto de Extremidade - Exploit Protection | Protege contra malware que usa explorações para infectar dispositivos e se espalhar automaticamente aplicando técnicas de mitigação de exploração a aplicativos e processos do sistema operacional. Para obter mais informações, [consulte Microsoft Defender for Endpoint - Exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).
Microsoft Defender para Ponto de Extremidade - Proteção de Rede | A proteção de rede expande o escopo do Microsoft Defender SmartScreen para bloquear todo o tráfego HTTP e HTTPS de saída que tenta se conectar a fontes de baixa reputação. Para obter mais informações, [consulte Microsoft Defender para Ponto de Extremidade - Proteção de Rede.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Proteção contra Adulterações do Microsoft Defender | A Proteção contra Adulterações do Windows é usada para impedir que as configurações de segurança, como a proteção antivírus, seja alterada. Para obter mais informações, consulte [a Proteção contra Adulterações do Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Proteção antivírus baseada em comportamento, heurística e em tempo real do Microsoft Defender Antivírus | Sempre em busca de ameaças de arquivo e processo que podem não ser detectadas como malware. Para obter mais informações, consulte a proteção antivírus baseada em [comportamento do Microsoft Defender Antivírus, heurística]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)e em tempo real.
Proteção entregue na nuvem do Microsoft Defender Antivírus | Fornece proteção dinâmica quase instantânea e automatizada contra ameaças novas e emergentes. Para obter mais informações, consulte Proteção entregue na nuvem do [Microsoft Defender Antivírus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Bloquear à primeira vista" | Fornece detecção e bloqueio de novo malware quando o Windows detecta um arquivo suspeito ou desconhecido. Para obter mais informações, consulte [o Microsoft Defender Block à primeira vista.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Aplicativos potencialmente indesejados do Microsoft Defender AV | Aplicativos potencialmente indesejados são usados para bloquear aplicativos que podem fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outro software que possa ser inesperado ou indesejado. Para obter mais informações, [consulte Microsoft Defender AV Aplicativos potencialmente indesejados.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall com Segurança Avançada | Filtragem de tráfego de rede two-way baseada em host para um dispositivo, o Windows Defender Firewall bloqueia o tráfego de rede não autorizado que flui para dentro ou para fora do dispositivo local. Para obter mais informações, consulte [o Windows Defender Firewall com Segurança Avançada.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Controle de Conta de Usuário | O Controle de Conta de Usuário alterna para a Área de Trabalho Segura quando uma tarefa ou ação requer o acesso do tipo de conta de administrador. Os usuários da Área de Trabalho Gerenciada da Microsoft têm acesso padrão ao usuário no registro. Para obter mais informações, consulte [Controle de Conta de Usuário.](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e do Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Microsoft Cloud App Security |  Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
Proteção de Informações do Azure P2  | Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
