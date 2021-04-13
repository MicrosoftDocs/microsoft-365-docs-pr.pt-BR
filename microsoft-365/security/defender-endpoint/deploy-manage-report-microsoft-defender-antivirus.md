---
title: Implantar, gerenciar e relatar o Microsoft Defender Antivírus
description: Você pode implantar e gerenciar o Microsoft Defender Antivírus com o Intune, o Microsoft Endpoint Configuration Manager, a Política de Grupo, o PowerShell ou o WMI
keywords: implantar, gerenciar, atualizar, proteção, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a9cd04300e67f956b50f07c02f3dc00c515f02eb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690004"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Implantar, gerenciar e relatar o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode implantar, gerenciar e relatar o Microsoft Defender Antivírus de várias maneiras.

Como o cliente do Microsoft Defender Antivírus está instalado como parte principal do Windows 10, a implantação tradicional de um cliente para seus pontos de extremidade não se aplica.

No entanto, na maioria dos casos, você ainda precisará habilitar o serviço de proteção em seus pontos de extremidade com o Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender ou Group Policy Objects, que é descrito na tabela a seguir.

Você também verá links adicionais para:

- Gerenciando a proteção do Microsoft Defender Antivírus, incluindo o gerenciamento de atualizações de produto e proteção
- Relatórios sobre a proteção do Microsoft Defender Antivírus

> [!IMPORTANT]
> Na maioria dos casos, o Windows 10 desabilitará o Microsoft Defender Antivírus se encontrar outro produto antivírus em execução e atualizado. Você deve desabilitar ou desinstalar produtos antivírus de terceiros antes que o Microsoft Defender Antivírus funcione. Se você reabilitar ou instalar produtos antivírus de terceiros, o Windows 10 desabilitará automaticamente o Microsoft Defender Antivírus.

Ferramenta|Opções de implantação (<a href="#fn2" id="ref2">2</a>)|Opções de gerenciamento (configuração em toda a rede e implantação de política ou linha de base) ([3](#fn3))|Opções de relatórios  
---|---|---|---  
Microsoft Intune|[Adicionar configurações de proteção de ponto de extremidade no Intune](/intune/endpoint-protection-configure)|[Configurar configurações de restrição de dispositivo no Intune](/intune/device-restrictions-configure)| [Usar o console do Intune para gerenciar dispositivos](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|Use a [função de sistema de site][] de ponto de Proteção de Ponto de Extremidade e habilita a Proteção de Ponto de Extremidade com [configurações personalizadas do cliente][]|Com [políticas antimalware padrão e personalizadas][] e gerenciamento [de cliente][]|Com o espaço [de trabalho e alertas][] de [email][] padrão do Configuration Manager Monitoring  
Política de Grupo e Active Directory (ingressou no domínio)|Use um Objeto de Política de Grupo para implantar alterações de configuração e garantir que o Microsoft Defender Antivírus está habilitado.|Use GPOs (Objetos de Política de Grupo) para configurar opções de atualização [para o Microsoft Defender Antivírus][] e configurar Windows Defender [recursos][]|O relatório do ponto de extremidade não está disponível com a Política de Grupo. Você pode gerar uma lista de Políticas [de Grupo para determinar se as configurações ou políticas não são aplicadas][]
PowerShell|Implante com a Política de Grupo, o Microsoft Endpoint Configuration Manager ou manualmente em pontos de extremidade individuais.|Use os cmdlets [Set-MpPreference] [e Update-MpSignature] disponíveis no módulo Defender.|Use os [cmdlets Get apropriados disponíveis no módulo Defender][]
Instrumentação de Gerenciamento do Windows|Implante com a Política de Grupo, o Microsoft Endpoint Configuration Manager ou manualmente em pontos de extremidade individuais.|Use o [método Set da classe MSFT_MpPreference e][] o método Update da classe [MSFT_MpSignature.][]|Use a [classe MSFT_MpComputerStatus][] e o método get de classes associadas no [Windows Defender WMIv2 Provider][]
Microsoft Azure|Implante o Microsoft Antimalware para o Azure no portal do Azure usando Visual Studio de máquina virtual ou usando [cmdlets do Azure PowerShell.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) Você também pode [instalar a proteção de ponto de extremidade no Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|Configurar [o Microsoft Antimalware para Máquinas Virtuais e Serviços de Nuvem com cmdlets do Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) ou [usar exemplos de código](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Use [o Microsoft Antimalware para Máquinas Virtuais e Serviços de Nuvem com cmdlets do Azure PowerShell](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) para habilitar o monitoramento. Você também pode revisar relatórios de uso no Azure [][] Active Directory para determinar atividades suspeitas, incluindo o relatório de dispositivos possivelmente infectados e configurar uma ferramenta SIEM para relatar eventos do [Microsoft Defender Antivírus][] e adicionar essa ferramenta como um aplicativo no AAD.

1. <span id="fn1" />A disponibilidade de algumas funções e recursos, especialmente relacionadas à proteção entregue na nuvem, difere entre o Microsoft Endpoint Manager (Branch Atual) e o System Center 2012 Configuration Manager. Nesta biblioteca, nos concentramos no Windows 10, no Windows Server 2016 e no Microsoft Endpoint Manager (Branch Atual). Consulte Usar a proteção fornecida na nuvem da [Microsoft no Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md) para uma tabela que descreve as principais diferenças. [(Retornar à tabela)](#ref2)
  
2.  <span id="fn2" />No Windows 10, o Microsoft Defender Antivírus é um componente disponível sem instalação ou implantação de um cliente ou serviço adicional. Ele será habilitado automaticamente quando produtos antivírus de terceiros são desinstalados ou desinstalados ( exceto no[Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)). Portanto, a implantação tradicional não é necessária. A implantação aqui se refere a garantir que o componente do Microsoft Defender Antivírus está disponível e habilitado em pontos de extremidade ou servidores. [(Retornar à tabela)](#ref2)

3. <span id="fn3" />A configuração de recursos e proteção, incluindo a configuração de atualizações de produto e proteção, são descritas na seção Configurar recursos do [Microsoft Defender Antivírus](configure-notifications-microsoft-defender-antivirus.md) nesta biblioteca. [(Retornar à tabela)](#ref2)

[Função do sistema de site de ponto de proteção de ponto de extremidade]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[políticas antimalware padrão e personalizadas]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[gerenciamento de cliente]:  /configmgr/core/clients/manage/manage-clients
[habilitar a Proteção de Ponto de Extremidade com configurações de cliente personalizadas]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
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
[Windows Defender provedor WMIv2]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Cmdlets Get disponíveis no módulo Defender]: /powershell/module/defender/
[Configurar opções de atualização para o Microsoft Defender Antivírus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Configurar Windows Defender recursos]: configure-microsoft-defender-antivirus-features.md
[Políticas de Grupo para determinar se as configurações ou políticas não são aplicadas]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Dispositivos possivelmente infectados]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Eventos do Microsoft Defender Antivírus]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
---|---
[Implantar e habilitar a proteção do Microsoft Defender Antivírus](deploy-microsoft-defender-antivirus.md) | Embora o cliente esteja instalado como parte principal do Windows 10 e a implantação tradicional não se aplique, você ainda precisará habilitar o cliente em seus pontos de extremidade com o Microsoft Endpoint Configuration Manager, Microsoft Intune ou Group Policy Objects. 
[Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md) | Há duas partes para atualizar o Microsoft Defender Antivírus: atualizando o cliente nos pontos de extremidade (atualizações do produto) e atualizando o Security intelligence (atualizações de proteção). Você pode atualizar a Inteligência de Segurança de várias maneiras, usando o Microsoft Endpoint Configuration Manager, a Política de Grupo, o PowerShell e o WMI.
[Monitorar e relatar sobre a proteção do Microsoft Defender Antivírus](report-monitor-microsoft-defender-antivirus.md) | Você pode usar o Microsoft Intune, o Microsoft Endpoint Configuration Manager, o complemento De conformidade de atualização para o Microsoft Operations Management Suite ou um produto SIEM de terceiros (consumindo logs de eventos do Windows) para monitorar o status de proteção e criar relatórios sobre a proteção do ponto de extremidade.