---
title: Trabalho com relatórios
description: Os vários relatórios disponíveis no Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771880"
---
# <a name="work-with-reports"></a>Trabalho com relatórios

Área de Trabalho Gerenciada da Microsoft vários relatórios e painéis que os administradores de IT em sua organização podem usar para entender vários aspectos da população de dispositivos. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Relatórios em Microsoft Endpoint Manager

O Microsoft Endpoint Manager reúne relatórios de vários produtos em um único local para ajudá-lo a monitorar e investigar problemas com a configuração e os dispositivos da sua organização do Azure AD ("locatário"). A área de trabalho  gerenciada da Microsoft tem uma seção em Relatórios no menu principal onde você pode encontrar relatórios específicos Área de Trabalho Gerenciada da Microsoft gerenciamento dos dispositivos registrados pela Microsoft.

Esses relatórios incluem:
- **Dispositivos gerenciados**  >  **Atualizações de recursos**: este modo de exibição mostra o status geral das atualizações de recursos em seus Área de Trabalho Gerenciada da Microsoft dispositivos.
- **Dispositivos gerenciados**  >  **Office:** este modo de exibição mostra o status geral das atualizações Office em seus Área de Trabalho Gerenciada da Microsoft dispositivos.

Além disso, em vários locais Microsoft Endpoint Manager você pode filtrar relatórios de outros grupos de produtos para incluir ou excluir especificamente seus dispositivos gerenciados por Área de Trabalho Gerenciada da Microsoft. Esses relatórios integraram esse recurso de filtragem:

- [Todos os dispositivos.](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Conformidade do dispositivo](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Dispositivos não compatíveis](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Funções Área de Trabalho Gerenciada da Microsoft personalizadas garantem o acesso apenas aos relatórios Área de Trabalho Gerenciada da Microsoft dados. Para acessar outras partes do Microsoft Endpoint Manager, como **Todos** os dispositivos, consulte Controle de acesso baseado em [função com](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune . 

## <a name="endpoint-analytics"></a>Análise de ponto de extremidade
Área de Trabalho Gerenciada da Microsoft agora está integrado à [análise do Ponto de Extremidade.](/mem/analytics/overview) Esses relatórios dão informações sobre como sua organização está funcionando e a qualidade da experiência entregue aos usuários. A análise de ponto de extremidade está no menu **Relatórios** [de Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Para pivotar uma pontuação para incluir apenas dispositivos que estão  sendo gerenciados por Área de Trabalho Gerenciada da Microsoft ir para qualquer relatório, selecione a lista de opções Filtro e selecione Área de Trabalho Gerenciada da Microsoft **dispositivos**.

Se a análise de ponto de extremidade não foi configurada automaticamente para sua organização do Azure AD ("locatário") durante o registro, você pode fazer isso sozinho. Para obter mais informações, consulte [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard). Você pode registrar todos os seus dispositivos ou, se quiser  incluir apenas Área de Trabalho Gerenciada da Microsoft dispositivos, selecione os grupos de dispositivos de local de trabalho modernos para Test, First, Fast e Broad. Esses relatórios podem exigir permissões diferentes. Para obter mais informações, consulte [Permissões](/mem/analytics/overview#permissions) para garantir que você tenha funções adequadamente atribuídas.

> [!NOTE]
> Para respeitar melhor a privacidade do usuário, deve haver mais de 10 Área de Trabalho Gerenciada da Microsoft dispositivos inscritos com análise de ponto de extremidade para usar esse filtro.

 ## <a name="inventory-data"></a>Dados de inventário

Além dos outros relatórios, você pode exportar informações sobre os dispositivos gerenciados por Área de Trabalho Gerenciada da Microsoft. Na **exibição Dispositivos** da **área Dispositivos** da Microsoft Endpoint Manager, use a guia **Exportar** tudo para baixar um relatório de [inventário detalhado.](device-inventory-report.md)
