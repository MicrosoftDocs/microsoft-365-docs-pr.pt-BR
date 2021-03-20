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
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917677"
---
# <a name="work-with-reports"></a>Trabalho com relatórios

A Área de Trabalho Gerenciada da Microsoft fornece vários relatórios e painéis que os administradores de IT em sua organização podem usar para entender vários aspectos da população de dispositivos.Você encontrará relatórios em dois locais: no [Microsoft Endpoint Manager](https://endpoint.microsoft.com) e no Centro de Administração [do Microsoft 365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Relatórios no Microsoft Endpoint Manager

O console do Microsoft Endpoint Manager reúne relatórios de vários produtos em um único local para ajudá-lo a monitorar e investigar problemas com a configuração e os dispositivos da sua organização do Azure AD ("locatário"). A área de trabalho  gerenciada da Microsoft tem uma seção em Relatórios no menu principal onde você pode encontrar relatórios específicos do gerenciamento da Área de Trabalho Gerenciada da Microsoft dos dispositivos registrados.

Esses relatórios incluem:
- **Dispositivos gerenciados**  >  **Atualizações de recursos**: este modo de exibição mostra o status geral das atualizações de recursos em seus dispositivos da Área de Trabalho Gerenciada da Microsoft.
- **Dispositivos gerenciados**  >  **Atualizações do Office**: este modo de exibição mostra o status geral das atualizações do Office em seus dispositivos da Área de Trabalho Gerenciada da Microsoft.

Além disso, em vários locais em todo o Microsoft Endpoint Manager, você pode filtrar relatórios de outros grupos de produtos para incluir ou excluir especificamente seus dispositivos gerenciados pela Área de Trabalho Gerenciada da Microsoft. Esses relatórios integraram esse recurso de filtragem:

- [Todos os dispositivos](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Conformidade do dispositivo](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos não compatíveis](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Funções personalizadas da Área de Trabalho Gerenciada da Microsoft garantem acesso apenas aos relatórios da Área de Trabalho Gerenciada da Microsoft. Para acessar outras partes do Microsoft Endpoint Manager, como **Todos** os dispositivos, consulte Controle de acesso baseado em função [com o Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Relatórios no Centro de Administração do Microsoft 365

Você pode encontrar relatórios de insights da Área de Trabalho Gerenciada da Microsoft  abrindo o Centro de Administração do [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)e navegando para Relatórios e selecionando a Área de Trabalho **Gerenciada da Microsoft.** Você também pode seguir o link direto para esses relatórios da guia Área de Trabalho Gerenciada da **Microsoft** na página inicial [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Esses relatórios incluem: 

- [Insights de uso](usage-insights.md) - Essa exibição fornece métricas de uso para seus dispositivos da Área de Trabalho Gerenciada da Microsoft.
- [Insights de confiabilidade](reliability-insights.md) - Essa exibição fornece um resumo de saúde de seus dispositivos gerenciados.
- [Percepções sobre a](battery-insights.md) bateria - Esta exibição mostra informações sobre o consumo de energia de aplicativos e a duração da bateria projetada para dispositivos em seu ambiente.
- [Insights de atualização de segurança do Windows](security-update-insights.md) - Essa exibição mostra informações sobre o status das atualizações de segurança para seus dispositivos da Área de Trabalho Gerenciada da Microsoft.

 ## <a name="inventory-data"></a>Dados de inventário

Além dos outros relatórios, você pode exportar informações sobre os dispositivos gerenciados pela Área de Trabalho Gerenciada da Microsoft. Na **exibição Dispositivos** da área **Dispositivos** do Microsoft Endpoint Manager, use a guia **Exportar** tudo para baixar um [relatório de inventário detalhado.](device-inventory-report.md)