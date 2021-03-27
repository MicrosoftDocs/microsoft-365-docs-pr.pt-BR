---
title: Microsoft Defender for Endpoint para clientes do Governo dos EUA
description: Saiba mais sobre os requisitos e recursos do Microsoft Defender for Endpoint para clientes do Governo dos EUA disponíveis
keywords: government, gcc, high, requirements, capabilities, defender, defender atp, mdatp, endpoint, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 320913058f1d3cab36b3a279996443c2e4ef117f
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382908"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender for Endpoint para clientes do Governo dos EUA

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

O Microsoft Defender for Endpoint para clientes do Governo dos EUA, criado no ambiente do Azure US Government, usa as mesmas tecnologias subjacentes que o Defender para Ponto de Extremidade no Azure Comercial.

Essa oferta está disponível para clientes GCC, GCC High e DoD e se baseia na mesma prevenção, detecção, investigação e correção que a versão comercial. No entanto, há algumas diferenças na disponibilidade de recursos para essa oferta.

> [!NOTE]
> Se você for um cliente GCC usando o Defender para Ponto de Extremidade no Comercial, consulte as páginas de documentação pública.

## <a name="licensing-requirements"></a>Requisitos de licença
O Microsoft Defender for Endpoint para clientes do Governo dos EUA requer uma das seguintes ofertas de licenciamento por volume da Microsoft:

### <a name="desktop-licensing"></a>Licenciamento de área de trabalho
CCG | CCG Alto | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 para GCC High | Windows 10 Enterprise E5 para DOD
| | Microsoft 365 E5 para GCC High | Microsoft 365 G5 para DOD
| | Segurança do Microsoft 365 G5 para GCC High | Segurança do Microsoft 365 G5 para DOD
Microsoft Defender para Ponto de Extremidade - GCC | Microsoft Defender para Ponto de Extremidade para GCC High | Microsoft Defender para Ponto de Extremidade para DOD

### <a name="server-licensing"></a>Licenciamento de servidor
CCG | CCG Alto | DoD
:---|:---|:---
Microsoft Defender para GCC do Endpoint Server | Microsoft Defender para Servidor de Ponto de Extremidade para GCC High | Microsoft Defender para Servidor de Ponto de Extremidade para DOD
Azure Defender para Servidores | Azure Defender for Servers - Government | Azure Defender for Servers - Government

<br />

## <a name="portal-urls"></a>Portal URLs
Veja a seguir as URLs do portal do Microsoft Defender for Endpoint para clientes do Governo dos EUA:

Tipo de cliente | Portal URL
:---|:---
CCG | https://gcc.securitycenter.microsoft.us
CCG Alto | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Versões do ponto de extremidade

### <a name="standalone-os-versions"></a>Versões autônomas do sistema operacional
As seguintes versões do sistema operacional são suportadas:

Versão do sistema operacional | CCG | CCG Alto | DoD
:---|:---|:---|:---
Windows 10, versão 20H2 (com [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 2004 (com [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1909 (com [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1903 (com [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1809 (com [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1803 (com [KB4598245](https://support.microsoft.com/help/4598245)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1709 | ![Não](images/svg/check-no.svg)<br />Observação: não haverá suporte | ![Sim ](images/svg/check-yes.svg) com [KB4499147](https://support.microsoft.com/help/4499147)<br />Observação: [preterido,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)atualize | ![Não](images/svg/check-no.svg)<br />Observação: não haverá suporte
Windows 10, versão 1703 e anterior | ![Não](images/svg/check-no.svg)<br />Observação: não haverá suporte | ![Não](images/svg/check-no.svg)<br />Observação: não haverá suporte | ![Não](images/svg/check-no.svg)<br />Observação: não haverá suporte
Windows Server 2019 (com [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2016 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 8 Pro | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Linux | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo
macOS | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo | ![Sim](images/svg/check-yes.svg) Na visualização<br />Consulte observação abaixo
Android | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
iOS | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia

> [!NOTE]
> Quando um patch é especificado, ele deve ser implantado antes da integração do dispositivo para configurar o Defender para o Ponto de Extremidade no ambiente correto.

> [!NOTE]
> Tentar a integração de dispositivos Windows mais antigos do que o Windows 10 ou o Windows Server 2019 usando [o Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)? Você precisará escolher "Azure US Government" em "Nuvem do Azure" se [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) estiver usando o assistente de instalação [ou](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)se estiver usando uma linha de comando ou um [script,](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.

> [!NOTE]
> Você precisará da versão 101.25.72 e superior para Linux e versão 101.25.69 e superior para macOS. Durante a visualização, essas versões só podem ser aproveitadas no canal "Insider Fast". Consulte [Configure the Linux software repository](linux-install-manually.md#configure-the-linux-software-repository) or Set the channel name [(macOS)](mac-updates.md#set-the-channel-name) for instructions.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versões do sistema operacional ao usar o Azure Defender para Servidores
As seguintes versões do sistema operacional são suportadas ao usar [o Azure Defender para Servidores](https://docs.microsoft.com/azure/security-center/security-center-wdatp):

Versão do sistema operacional | CCG | CCG Alto | DoD
:---|:---|:---|:---
Windows Server 2016 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Configurações de conectividade necessárias
Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.

A planilha baixável a seguir lista os serviços e suas URLs associadas às quais sua rede deve ser capaz de se conectar. Verifique se não há regras de filtragem de rede ou firewall que negam o acesso a essas URLs ou criem uma regra *de* autorização especificamente para elas.

Planilha de lista de domínios | Descrição
:-----|:-----
![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/> | Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional. <br /><br />[Baixe a planilha aqui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Para obter mais informações, consulte [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

> [!NOTE]
> A planilha também contém URLs comerciais, verifique as guias "US Gov".
> 
> Ao filtrar, procure os registros rotulados como "US Gov" e sua nuvem específica na coluna geografia.

### <a name="service-backend-ip-ranges"></a>Intervalos de IP de back-end de serviço

Se seus dispositivos de rede não suportam regras baseadas em DNS, use intervalos IP.

O Defender for Endpoint para clientes do Governo dos EUA é criado no ambiente do Azure US Government, implantado nas seguintes regiões:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Você pode encontrar os intervalos de IP do Azure em Intervalos de IP do Azure e Marcas de Serviço [– Nuvem governamental dos EUA.](https://www.microsoft.com/download/details.aspx?id=57063)

> [!NOTE]
> Como uma solução baseada em nuvem, os intervalos de endereços IP podem mudar. É recomendável mover para regras baseadas em DNS.

<br />

## <a name="api"></a>API
Em vez das URIs públicas listadas em nossa documentação [de API,](apis-intro.md)você precisará usar os seguintes URIs:

Tipo de ponto de extremidade | CCG | GCC High & DoD
:---|:---|:---
Logon | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
API do Defender para Ponto de Extremidade | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Paridade de recursos com comercial
O Defender for Endpoint para clientes do Governo dos EUA não tem paridade completa com a oferta comercial. Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades para nossos clientes do Governo dos EUA, há alguns recursos ainda não disponíveis que queremos destacar.

Estas são as lacunas conhecidas a partir de março de 2021:

Nome do recurso | CCG | CCG Alto | DoD
:---|:---|:---|:---
Investigação e correção automatizadas: Resposta ao vivo | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Investigação e correção automatizadas: resposta aos alertas do Office 365 | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Notificações por e-mail | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Laboratório de avaliação | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Gerenciamento e APIs: Relatório de conformidade e saúde do dispositivo | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Gerenciamento e APIs: integração com produtos de terceiros | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Gerenciamento e APIs: API de streaming | ![Sim](images/svg/check-yes.svg) | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento
Gerenciamento e APIs: Relatório de proteção contra ameaças | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Gerenciamento de ameaças e vulnerabilidades | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Análise de ameaças | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Filtragem de conteúdo da Web | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento
Integrações: Azure Sentinel | ![Sim](images/svg/check-yes.svg) | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento
Integrações: Microsoft Cloud App Security | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Integrações: Microsoft Compliance Manager | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Integrações: Microsoft Defender for Identity | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Integrações: Microsoft Defender para Office 365 | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Integrações: DLP do Ponto de Extremidade da Microsoft | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
Integrações: Microsoft Intune | ![Sim](images/svg/check-yes.svg) | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento
Integrações: Microsoft Power Automate & Aplicativos lógicos do Azure | ![Sim](images/svg/check-yes.svg) | ![Não](images/svg/check-no.svg) No desenvolvimento | ![Não](images/svg/check-no.svg) No desenvolvimento
Integrações: Skype for Business /Teams | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Especialistas em Ameaças da Microsoft | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia | ![Não](images/svg/check-no.svg) No backlog de engenharia
