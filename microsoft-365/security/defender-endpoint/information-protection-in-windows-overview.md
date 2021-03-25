---
title: Proteção de informações na visão geral do Windows
ms.reviewer: ''
description: Saiba como funciona a proteção de informações no Windows para identificar e proteger informações confidenciais
keywords: information, protection, dlp, data, loss, prevention, protect
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 733f86ed48b9cc7a68fb0cd346c7b15fdcc3ce65
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187500"
---
# <a name="information-protection-in-windows-overview"></a>Proteção de informações na visão geral do Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

A proteção de informações é uma parte integrante do pacote do Microsoft 365 Enterprise, fornecendo proteção inteligente para manter dados confidenciais seguros enquanto habilita a produtividade no local de trabalho.


>[!TIP]
> Leia nossa postagem no blog sobre como o Microsoft Defender ATP se integra à Proteção de Informações da Microsoft para descobrir, proteger e monitorar dados confidenciais [em dispositivos Windows.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)

O Defender for Endpoint aplica os seguintes métodos para descobrir, classificar e proteger dados:

- **Descoberta de dados** - Identificar dados confidenciais em dispositivos Windows em risco
- **Classificação de** dados - Classifique automaticamente os dados com base em políticas comuns de Proteção de Informações da Microsoft (MIP) gerenciadas no Centro de Conformidade & Segurança do Office 365. A classificação automática permite proteger dados confidenciais, mesmo que o usuário final não os tenha classificado manualmente.


## <a name="data-discovery-and-data-classification"></a>Descoberta de dados e classificação de dados

O Defender for Endpoint descobre automaticamente arquivos com rótulos de sensibilidade e arquivos que contêm tipos de informações confidenciais.

Rótulos de sensibilidade classificam e ajudam a proteger conteúdos confidenciais.

Os tipos de informações confidenciais na implementação de prevenção contra perda de dados (DLP) do Office 365 estão em duas categorias:

- Padrão
- Personalizado

Os tipos de informações confidenciais padrão incluem informações como números de contas bancárias, números de previdência social ou IDs nacionais. Para obter mais informações, consulte [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).

Tipos personalizados são aqueles que você define e é projetado para proteger um tipo diferente de informações confidenciais (por exemplo, IDs de funcionários ou números de projeto). Para obter mais informações, [consulte Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).

Quando um arquivo é criado ou editado em um dispositivo Windows, o Defender for Endpoint verifica o conteúdo para avaliar se ele contém informações confidenciais.

Ative a integração da Proteção de Informações do Azure para que, quando um arquivo que contenha informações confidenciais seja descoberto pelo Defender para o Ponto de Extremidade, embora rótulos ou tipos de informações, ele seja automaticamente encaminhado para a Proteção de Informações do Azure a partir do dispositivo.

![Imagem da página de configurações com a Proteção de Informações do Azure](images/atp-settings-aip.png)

Os sinais relatados podem ser exibidos no painel Proteção de Informações do Azure – Descoberta de dados.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Proteção de Informações do Azure - Painel de descoberta de dados

Este painel apresenta uma informação resumida de descoberta dos dados descobertos pelo Defender for Endpoint e pela Proteção de Informações do Azure. Os dados do Defender para Ponto de Extremidade são marcados com Tipo de Local - Ponto de Extremidade.

![Imagem da Proteção de Informações do Azure - Descoberta de dados](images/azure-data-discovery.png)

Observe que a coluna Risco de Dispositivo à direita, esse risco de dispositivo é derivado diretamente do Defender para Ponto de Extremidade, indicando o nível de risco do dispositivo de segurança onde o arquivo foi descoberto, com base nas ameaças de segurança ativas detectadas pelo Defender para Ponto de Extremidade.

Clique em um dispositivo para exibir uma lista de arquivos observados neste dispositivo, com seus rótulos de sensibilidade e tipos de informações.

>[!NOTE]
>Permita que aproximadamente 15 a 20 minutos para a Descoberta do Painel de Proteção de Informações do Azure reflitam arquivos descobertos.

## <a name="log-analytics"></a>Análise de Log

A descoberta de dados baseada no Defender for Endpoint também está disponível no [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), onde você pode realizar consultas complexas sobre os dados brutos.

Para obter mais informações sobre a análise da Proteção de Informações do Azure, consulte [Relatório Central para a Proteção de Informações do Azure.](https://docs.microsoft.com/azure/information-protection/reports-aip)

Abra o Azure Log Analytics no portal do Azure e abra um construtor de consultas (padrão ou clássico).

Para exibir dados do Defender para o Ponto de Extremidade, execute uma consulta que contém:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Pré-requisitos:**

- Os clientes devem ter uma assinatura para a Proteção de Informações do Azure.
- Habilitar a integração da Proteção de Informações do Azure no Centro de Segurança do Microsoft Defender:
    - Vá para **Configurações no** Centro de Segurança do Microsoft Defender, clique em **Configurações Avançadas** em **Geral**.



