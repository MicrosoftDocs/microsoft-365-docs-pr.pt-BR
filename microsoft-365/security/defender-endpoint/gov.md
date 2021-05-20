---
title: Microsoft Defender para Ponto de Extremidade para clientes do Governo dos EUA
description: Conheça o Microsoft Defender for Endpoint para os requisitos e recursos dos clientes do governo dos EUA disponíveis
keywords: governo, gcc, alto, requisitos, recursos, defender, Microsoft Defender para Endpoint, ponto final, dod
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
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572664"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender para Ponto de Extremidade para clientes do Governo dos EUA

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

O Microsoft Defender for Endpoint para clientes do governo dos EUA, construído no ambiente do governo Azure dos EUA, usa as mesmas tecnologias subjacentes que o Defender for Endpoint no Azure Commercial.

Esta oferta está disponível para clientes GCC, GCC High e DoD e é baseada na mesma prevenção, detecção, investigação e remediação da versão comercial. No entanto, existem algumas diferenças na disponibilidade de recursos para essa oferta.

> [!NOTE]
> Se você é um cliente GCC usando o Defender for Endpoint in Commercial, consulte as páginas de documentação pública.

## <a name="licensing-requirements"></a>Requisitos de licenciamento
O Microsoft Defender for Endpoint para clientes do governo dos EUA requer uma das seguintes ofertas de licenciamento de volume da Microsoft:

### <a name="desktop-licensing"></a>Licenciamento de desktop
CCG | CCG Alto | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 para GCC High | Windows 10 Enterprise E5 para DOD
| | Microsoft 365 E5 para GCC High | Microsoft 365 G5 para DOD
| | Microsoft 365 Segurança G5 para GCC Alta | Microsoft 365 Segurança G5 para DoD
Microsoft Defender for Endpoint - GCC | Microsoft Defender para Endpoint para GCC High | Microsoft Defender para Endpoint para DOD

### <a name="server-licensing"></a>Licenciamento de servidor
CCG | CCG Alto | DoD
:---|:---|:---
Microsoft Defender para endpoint server GCC | Microsoft Defender para endpoint server para GCC high | Microsoft Defender para endpoint server para DOD
Azure Defender for Servers | Azure Defender para Servidores - Governo | Azure Defender para Servidores - Governo

<br />

## <a name="portal-urls"></a>Portal URLs
A seguir, o portal Microsoft Defender for Endpoint URLs para clientes do governo dos EUA:

Tipo de cliente | Portal URL
:---|:---
CCG | https://gcc.securitycenter.microsoft.us
CCG Alto | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Versões de ponto final

### <a name="standalone-os-versions"></a>Versões de SO autônomos
As seguintes versões do SO são suportadas:

Versão do SISTEMA OPERACIONAL | CCG | CCG Alto | DoD
:---|:---|:---|:---
Windows 10, versão 20H2 (com [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 2004 (com [KB4586853](https://support.microsoft.com/help/4586853)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1909 (com [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1903 (com [KB4586819](https://support.microsoft.com/help/4586819)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1809 (com [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1803 (com [KB4598245](https://support.microsoft.com/help/4598245)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 10, versão 1709 | ![Não](images/svg/check-no.svg)<br />Nota: Não será suportado | ![Sim ](images/svg/check-yes.svg) com [KB4499147](https://support.microsoft.com/help/4499147)<br />Nota: [Preterido,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)por favor atualize | ![Não](images/svg/check-no.svg)<br />Nota: Não será suportado
Windows 10, versão 1703 e anterior | ![Não](images/svg/check-no.svg)<br />Nota: Não será suportado | ![Não](images/svg/check-no.svg)<br />Nota: Não será suportado | ![Não](images/svg/check-no.svg)<br />Nota: Não será suportado
Windows Servidor 2019 (com [KB4586839](https://support.microsoft.com/help/4586839)) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2016 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 8 Pro | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 7 Enterprise SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows 7 Pro SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Linux | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
macOS | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Android | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia
iOS | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia

> [!NOTE]
> Quando um patch é especificado, ele deve ser implantado antes do onboarding do dispositivo, a fim de configurar o Defender para Endpoint para o ambiente correto.

> [!NOTE]
> Tentando embarcar Windows dispositivos com mais de Windows 10 ou Windows Server 2019 usando [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)? Você precisará escolher "Azure US Government" em "Azure Cloud" se usar o [assistente de configuração](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard), ou se usar uma [linha de comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) ou um [script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) - definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" para 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Versões do SISTEMA OPERACIONAL ao usar o Azure Defender para servidores
As seguintes versões do SO são suportadas ao usar [o Azure Defender for Servers](/azure/security-center/security-center-wdatp):

Versão do SISTEMA OPERACIONAL | CCG | CCG Alto | DoD
:---|:---|:---|:---
Windows Server 2019 | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Windows Server 2016 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Configurações de conectividade necessárias
Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.

A planilha a seguir lista os serviços e seus URLs associados à qual sua rede deve ser capaz de se conectar. Verifique se não há regras de filtragem de firewall ou rede que neguem o acesso a esses URLs ou criem uma regra *de perdoeamento* especificamente para eles.

Lista de planilhas de domínios | Descrição
:-----|:-----
![Imagem do polegar para microsoft defender para planilha de URLs endpoint](images/mdatp-urls.png)<br/> | Planilha de registros de DNS específicos para locais de serviço, localizações geográficas e SO. <br /><br />[Baixe a planilha aqui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Para obter mais informações, consulte [Configurar as configurações de proxy do dispositivo e conectividade com a Internet](configure-proxy-internet.md).

> [!NOTE]
> A planilha também contém URLs comerciais, certifique-se de verificar as guias "US Gov".
> 
> Ao filtrar, procure os registros rotulados como "US Gov" e sua nuvem específica sob a coluna de geografia.

### <a name="service-backend-ip-ranges"></a>Intervalos de IP de backend de serviço

Se seus dispositivos de rede não suportarem regras baseadas em DNS, use faixas IP em vez disso.

O Defender for Endpoint para clientes do governo dos EUA é construído no ambiente do governo dos EUA, implantado nas seguintes regiões:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

Você pode encontrar as faixas ip do Azure em [faixas ip azure e tags de serviço – Nuvem do Governo dos EUA](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Como uma solução baseada em nuvem, as faixas de endereço IP podem mudar. Recomenda-se que você mude para regras baseadas em DNS.

<br />

## <a name="api"></a>API
Em vez das URIs públicas listadas em nossa [documentação de API,](apis-intro.md)você precisará usar as seguintes URIs:

Tipo de ponto final | CCG | GCC DoD de alta &
:---|:---|:---
Logon | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defensor da API endpoint | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Paridade de recursos com comercial
Defender for Endpoint para clientes do governo dos EUA não tem paridade completa com a oferta comercial. Embora nosso objetivo seja entregar todos os recursos comerciais e funcionalidades aos nossos clientes do governo dos EUA, existem algumas capacidades ainda não disponíveis que queremos destacar.

Estas são as lacunas conhecidas:

Nome do recurso | CCG | CCG Alto | DoD
:---|:---|:---|:---
Gestão e APIs: API de streaming | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Filtragem de conteúdo da Web | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Integrações: Azure Sentinel | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) Alertas <br /> ![Não](images/svg/check-no.svg) Incidentes & dados brutos: Em desenvolvimento | ![Sim](images/svg/check-yes.svg) Alertas <br /> ![Não](images/svg/check-no.svg) Incidentes & dados brutos: Em desenvolvimento
Integrações: Microsoft Cloud App Security | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Integrações: Microsoft Compliance Manager | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Integrações: Microsoft Defender for Identity | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Integrações: Microsoft Endpoint DLP | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Integrações: Microsoft Intune | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg) | ![Sim](images/svg/check-yes.svg)
Integrações: Microsoft Power Automate & Aplicativos Lógicos do Azure | ![Sim](images/svg/check-yes.svg) | ![Não](images/svg/check-no.svg) Em desenvolvimento | ![Não](images/svg/check-no.svg) Em desenvolvimento
Especialistas em Ameaças da Microsoft | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia | ![Não](images/svg/check-no.svg) Em backlog de engenharia
