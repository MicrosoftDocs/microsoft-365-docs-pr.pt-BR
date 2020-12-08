---
title: Trabalho com relatórios
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585323"
---
# <a name="work-with-reports"></a>Trabalho com relatórios

O Microsoft Managed Desktop fornece vários relatórios e painéis que os administradores de ti da sua organização podem usar para entender vários aspectos da população de dispositivos.Você encontrará relatórios em dois locais: no [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e no [centro de administração do Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Relatórios no Microsoft Endpoint Manager

O console do Microsoft Endpoint Manager reúne relatórios de vários produtos em um único local para ajudá-lo a monitorar e investigar problemas com a configuração e os dispositivos de sua organização do Azure AD ("locatário"). A área de trabalho gerenciada da Microsoft tem uma seção em **relatórios** no menu principal, onde você pode encontrar relatórios específicos para o gerenciamento de dispositivos que você registrou na área de trabalho gerenciada da Microsoft.

Além disso, em vários locais no Microsoft Endpoint Manager, você pode filtrar relatórios de outros grupos de produtos para incluir ou excluir especificamente os dispositivos gerenciados pela área de trabalho gerenciada da Microsoft. Esses relatórios integraram esse recurso de filtragem:

- **Todos os dispositivos**
- **Conformidade do dispositivo**
- **Dispositivos não compatíveis**

> [!NOTE]
> As funções personalizadas da área de trabalho gerenciada da Microsoft garantem acesso somente aos relatórios da área de trabalho gerenciada Para acessar outras partes do Microsoft Endpoint Manager, como **todos os dispositivos**, confira [controle de acesso baseado em função com o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Relatórios no centro de administração do Microsoft 365

Você pode encontrar relatórios do Microsoft Managed desktop insights abrindo o [centro de administração do microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)e, em seguida, navegando para **relatórios** e selecionando **área de trabalho gerenciada da Microsoft**. Você também pode seguir o link direto para esses relatórios na guia **área de trabalho gerenciada da Microsoft** na home page do [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Esses relatórios incluem: 

- [Insights de uso](usage-insights.md) -este modo de exibição fornece métricas de uso para seus dispositivos de área de trabalho gerenciada da Microsoft.
- [Insights de confiabilidade](reliability-insights.md) -este modo de exibição fornece um resumo de integridade dos dispositivos gerenciados.
- [Insights de bateria](battery-insights.md) -este modo de exibição mostra informações sobre o consumo de energia de aplicativos e a vida da bateria projetada para dispositivos no seu ambiente.
- [Atualização de segurança do Windows](security-update-insights.md) -este modo de exibição mostra informações sobre o status das atualizações de segurança para os dispositivos de área de trabalho gerenciado da Microsoft.

 ## <a name="inventory-data"></a>Dados de inventário

Além dos outros relatórios, você pode exportar informações sobre os dispositivos gerenciados pela área de trabalho gerenciada da Microsoft. No modo de exibição **dispositivos** da área **dispositivos** do Microsoft Endpoint Manager, use a guia **Exportar tudo** para [baixar um relatório detalhado de inventário](device-inventory-report.md).