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
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094862"
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
Recomendado
 |
 --- | ---
[Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | Recomendamos que os clientes implementem o Windows Hello para Empresas para substituir senhas pela autenticação forte de dois fatores usada em dispositivos da Área de Trabalho Gerenciada da Microsoft.
[Virtualização de aplicativo](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | Os clientes podem implantar pacotes do App-V (Application Virtualization) usando o cliente de gerenciamento de aplicativos Do Intune Win32.
[Prevenção contra perda de dados do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | Os clientes são recomendáveis implementar a prevenção contra perda de dados (DLP) do Microsoft 365 para monitorar as ações que estão sendo tomadas em itens que você determinou serem confidenciais e para ajudar a evitar o compartilhamento não intencional desses itens.   

Incluído e gerenciado no serviço
 |
 --- | ---
[Criptografia de Unidade de Disco BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | A Criptografia de Unidade de Disco BitLocker é usada para criptografar todas as unidades do sistema. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Protege a integridade do sistema na sua iniciação e valida que a integridade do sistema realmente foi mantida.
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | O Windows Defender Credential Guard usa segurança baseada em virtualização para isolar segredos para que somente o software do sistema privilegiado possa acessá-los.
[Microsoft Defender para Ponto de Extremidade | Detecção e resposta do ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     As Operações de Segurança da Área de Trabalho Gerenciada da Microsoft respondem a alertas e toma medidas para remediar ameaças usando Detecção e Resposta de Ponto de Extremidade.
[Microsoft Defender para Ponto de Extremidade | Especialistas em ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | A Área de Trabalho Gerenciada da Microsoft integra-se a informações e dados de Especialistas em Ameaças por meio de notificações de ataque direcionadas. Os clientes devem fornecer consentimento adicional antes que esse serviço seja habilitado.  
[Microsoft Defender para Ponto de Extremidade | Gerenciamento de Ameaças e Vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Necessário para uso futuro no plano de serviço da Área de Trabalho Gerenciada da Microsoft.
[Microsoft Defender para Ponto de Extremidade | Redução de Superfície de Ataque](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | A Redução de superfície de ataque tem como alvo comportamentos de software arriscados que geralmente são invasores invasores.
[Microsoft Defender para Ponto de Extremidade | Exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Protege contra malware que usa explorações para infectar dispositivos e se espalhar automaticamente aplicando técnicas de mitigação de exploração a aplicativos e processos do sistema operacional.
[Microsoft Defender para Ponto de Extremidade | Proteção de rede](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | A proteção de rede expande o escopo do Microsoft Defender SmartScreen para bloquear todo o tráfego HTTP(s) de saída que tenta se conectar a fontes de baixa reputação.
[Proteção contra Adulterações do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | A Proteção contra Adulterações do Windows é usada para impedir que as configurações de segurança, como a proteção antivírus, seja alterada.
[Proteção antivírus baseada em comportamento, heurística e em tempo real do Microsoft Defender Antivírus]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Sempre em busca de ameaças de arquivo e processo que podem não ser detectadas como malware.
[Proteção entregue na nuvem do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Fornece proteção dinâmica quase instantânea e automatizada contra ameaças novas e emergentes.
[Bloquear à primeira vista do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Fornece detecção e bloqueio de novo malware quando o Windows detecta um arquivo suspeito ou desconhecido.
[Aplicativos potencialmente indesejados do Microsoft Defender AV](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Aplicativos potencialmente indesejados (PUA) são usados para bloquear aplicativos que podem fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outro software que possa ser inesperado ou indesejado.
[Windows Defender Firewall com Segurança Avançada](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | Filtragem de tráfego de rede two-way baseada em host para um dispositivo, o Windows Defender Firewall bloqueia o tráfego de rede não autorizado que flui para dentro ou para fora do dispositivo local.
[Controle de Conta de Usuário](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | O Controle de Conta de Usuário alterna para a Área de Trabalho Segura quando uma tarefa ou ação requer acesso de tipo de conta de administrador. Os usuários da Área de Trabalho Gerenciada da Microsoft têm acesso padrão ao usuário no registro. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e do Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Segurança no aplicativo na nuvem da Microsoft |  Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
Proteção de Informações do Azure P2  | Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
