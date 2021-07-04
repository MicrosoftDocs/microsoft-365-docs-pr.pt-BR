---
title: Implantar, gerenciar e relatar Microsoft Defender Antivírus
description: Você pode implantar e gerenciar Microsoft Defender Antivírus com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo, PowerShell ou WMI
keywords: implantar, gerenciar, atualizar, proteger, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15fd70a2a60da7b0541446a98f0094c73c831d51
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289818"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implantar, gerenciar e relatar Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode implantar, gerenciar e relatar Microsoft Defender Antivírus de várias maneiras.

Como o Microsoft Defender Antivírus cliente é instalado como parte principal do Windows 10, a implantação tradicional de um cliente para seus pontos de extremidade não se aplica.

No entanto, na maioria dos casos, você ainda precisará habilitar o serviço de proteção em seus pontos de extremidade com Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender ou Objetos de Política de Grupo, que é descrito na tabela a seguir.

Você também verá links adicionais para:

- Gerenciando Microsoft Defender Antivírus proteção, incluindo o gerenciamento de atualizações de produto e proteção
- Relatórios sobre Microsoft Defender Antivírus proteção

> [!IMPORTANT]
> Na maioria dos casos, Windows 10 desabilitará Microsoft Defender Antivírus se encontrar outro produto antivírus em execução e atualizado. Você deve desabilitar ou desinstalar produtos antivírus de terceiros antes Microsoft Defender Antivírus funcionar. Se você habilitar ou instalar produtos antivírus de terceiros, Windows 10 desabilita automaticamente Microsoft Defender Antivírus.

Ferramenta|Opções de implantação (<a href="#fn2" id="ref2">2</a>)|Opções de gerenciamento (configuração em toda a rede e implantação de política ou linha de base) ([3](#fn3))|Opções de relatórios  
---|---|---|---  
Microsoft Intune|[Adicionar configurações de proteção de ponto de extremidade no Intune](/intune/endpoint-protection-configure)|[Configurar configurações de restrição de dispositivo no Intune](/intune/device-restrictions-configure)| [Usar o console do Intune para gerenciar dispositivos](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Use a [função Endpoint Protection do sistema de site de][] ponto e [habilita Endpoint Protection com configurações personalizadas do cliente][]|Com [políticas antimalware padrão e personalizadas][] e gerenciamento [de cliente][]|Com o espaço [de trabalho e alertas][] de [email][] padrão do Configuration Manager Monitoring  
Política de Grupo e Active Directory (ingressou no domínio)|Use um Objeto de Política de Grupo para implantar alterações de configuração e garantir Microsoft Defender Antivírus está habilitado.|Use GPOs (Objetos de Política de Grupo) para [Configurar opções][] de atualização para Microsoft Defender Antivírus e Configurar [Windows Defender recursos][]|O relatório do ponto de extremidade não está disponível com a Política de Grupo. Você pode gerar uma lista de Políticas [de Grupo para determinar se as configurações ou políticas não são aplicadas][]
Windows PowerShell|Implantar com a Política de Grupo, Microsoft Endpoint Configuration Manager ou manualmente em pontos de extremidade individuais.|Use os cmdlets [Set-MpPreference] [e Update-MpSignature] disponíveis no módulo Defender.|Use os [cmdlets Get apropriados disponíveis no módulo Defender][]
Windows Instrumentação de Gerenciamento|Implantar com a Política de Grupo, Microsoft Endpoint Configuration Manager ou manualmente em pontos de extremidade individuais.|Use o [método Set da classe MSFT_MpPreference e][] o método Update da classe [MSFT_MpSignature.][]|Use a [classe MSFT_MpComputerStatus][] e o método get de classes associadas no [Windows Defender WMIv2 Provider][]
Microsoft Azure|Implante Microsoft Antimalware para o Azure no portal do Azure, usando Visual Studio configuração de máquina virtual ou usando [cmdlets Azure PowerShell .](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Você também pode [instalar a proteção de ponto de extremidade no Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Configurar [Microsoft Antimalware para Máquinas Virtuais e Serviços de Nuvem com Azure PowerShell cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) ou usar [exemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Use [Microsoft Antimalware para Máquinas Virtuais e Serviços de Nuvem com Azure PowerShell cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) para habilitar o monitoramento. Você também pode revisar relatórios de uso no Azure Active Directory [][] para determinar atividades suspeitas, incluindo o [][] relatório dispositivos possivelmente infectados e configurar uma ferramenta SIEM para relatar eventos Microsoft Defender Antivírus e adicionar essa ferramenta como um aplicativo no AAD.

1. <span id="fn1" />A disponibilidade de algumas funções e recursos, especialmente relacionadas à proteção entregue na nuvem, difere entre Microsoft Endpoint Manager (Branch Atual) e System Center 2012 Configuration Manager. Nesta biblioteca, nos concentramos em Windows 10, Windows Server 2016 e Microsoft Endpoint Manager (Branch Atual). Consulte [Usar a proteção fornecida na](cloud-protection-microsoft-defender-antivirus.md) nuvem da Microsoft Microsoft Defender Antivírus para uma tabela que descreve as principais diferenças. [(Retornar à tabela)](#ref2)
  
2. <span id="fn2" />Em Windows 10, Microsoft Defender Antivírus é um componente disponível sem instalação ou implantação de um cliente ou serviço adicional. Ele será habilitado automaticamente quando produtos antivírus de[terceiros](microsoft-defender-antivirus-on-windows-server.md)são desinstalados ou desinstalados ( exceto em Windows Server 2016 ). Portanto, a implantação tradicional não é necessária. A implantação aqui se refere a garantir que o componente Microsoft Defender Antivírus está disponível e habilitado em pontos de extremidade ou servidores. [(Retornar à tabela)](#ref2)

3. <span id="fn3" />A configuração de recursos e proteção, incluindo a configuração de atualizações de produto e proteção, são descritas na seção Configurar Microsoft Defender Antivírus [recursos](configure-notifications-microsoft-defender-antivirus.md) nesta biblioteca. [(Retornar à tabela)](#ref2)

[Endpoint Protection função de sistema de site de ponto]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[políticas antimalware padrão e personalizadas]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[gerenciamento de cliente]:  /configmgr/core/clients/manage/manage-clients
[habilitar Endpoint Protection com configurações de cliente personalizadas]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Espaço de trabalho de Monitoramento do Configuration Manager]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[alertas de email]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Método Set da classe MSFT_MpPreference]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Método Update da classe MSFT_MpSignature]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender Provedor WMIv2]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Cmdlets Get disponíveis no módulo Defender]: /powershell/module/defender/
[Configurar opções de atualização para Microsoft Defender Antivírus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Configurar Windows Defender recursos]: configure-microsoft-defender-antivirus-features.md
[Políticas de Grupo para determinar se as configurações ou políticas não são aplicadas]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Dispositivos possivelmente infectados]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender Antivírus eventos]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
---|---
[Implantar e habilitar Microsoft Defender Antivírus proteção](deploy-microsoft-defender-antivirus.md) | Embora o cliente esteja instalado como parte principal do Windows 10 e a implantação tradicional não se aplique, você ainda precisará habilitar o cliente em seus pontos de extremidade com Microsoft Endpoint Configuration Manager, Microsoft Intune ou Objetos de Política de Grupo. 
[Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md) | Há duas partes para atualizar Microsoft Defender Antivírus: atualizar o cliente nos pontos de extremidade (atualizações do produto) e atualizar a Inteligência de Segurança (atualizações de proteção). Você pode atualizar a Inteligência de Segurança de várias maneiras, usando Microsoft Endpoint Configuration Manager, Política de Grupo, PowerShell e WMI.
[Monitorar e relatar sobre Microsoft Defender Antivírus proteção](report-monitor-microsoft-defender-antivirus.md) | Você pode usar Microsoft Intune, Microsoft Endpoint Configuration Manager, o complemento Conformidade de Atualização para o Microsoft Operations Management Suite ou um produto SIEM de terceiros (consumindo logs de eventos Windows) para monitorar o status da proteção e criar relatórios sobre a proteção do ponto de extremidade.