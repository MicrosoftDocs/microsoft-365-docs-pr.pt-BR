---
title: Exibir os relatórios de prevenção contra perda de dados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Use os relatórios de DLP no Office 365 para exibir o número de políticas de DLP, substituições ou falsos positivos e veja se elas estão mais ou menos tendências ao longo do tempo.
ms.openlocfilehash: 1ddcd60dc9314779ade2f7ceae02d336f902e483
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818991"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Exibir os relatórios de prevenção contra perda de dados

Depois de criar suas políticas de prevenção contra perda de dados (DLP), verifique se elas estão funcionando conforme o esperado e se estão ajudando a manter a conformidade. Com os relatórios de DLP no Centro de Conformidade &amp; de Segurança, você pode exibir rapidamente:
  
- **DLP policy matches** Este relatório mostra a contagem de combinações de política de DLP ao longo do tempo. Você pode filtrar o relatório por data, local, política ou ação. Você pode usar esse relatório para: 
    
  - Ajuste ou refine suas políticas de DLP conforme você as executar no modo de teste. Você pode exibir a regra específica que corresponder ao conteúdo.
    
  - Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.
    
  - Descobrir processos empresariais que violam as políticas DLP da organização.
    
  - Entenda qualquer impacto comercial das políticas de DLP ao ver quais ações estão sendo aplicadas ao conteúdo.
    
  - Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.
    
  - Exibir uma lista dos principais usuários e repetir usuários que estão contribuindo para incidentes em sua organização.
    
  - Exibir uma lista dos principais tipos de informações confidenciais em sua organização.
    
- **Incidentes de DLP** Esse relatório também mostra as diretivas que coincidem com o tempo, como o relatório de diretivas. No entanto, o relatório de diretivas que corresponde mostra as combinações em um nível de regra; por exemplo, se um email corresponde a três regras diferentes, o relatório de diretivas corresponde a três itens de linha diferentes. Por outro lado, o relatório de incidentes mostra as combinações em um nível de item; por exemplo, se um email corresponder a três regras diferentes, o relatório de incidentes mostrará um único item de linha para esse conteúdo. 
    
  Como as contagens de relatório são agregadas de forma diferente, o relatório de políticas corresponde melhor para identificar as combinações com regras específicas e ajustar as políticas DLP. O relatório de incidentes é melhor para identificar partes específicas do conteúdo que são problemáticas para suas políticas de DLP.
    
- **Substituições e falsos positivos de DLP** Se sua política de DLP permitir que os usuários a substituam ou re reportem um falso positivo, esse relatório mostrará uma contagem dessas instâncias ao longo do tempo. Você pode filtrar o relatório por data, local ou política. Você pode usar esse relatório para: 
    
  - Ajuste ou refine suas políticas de DLP ao ver quais políticas incorrem em um alto número de falsos positivos.
    
  - Veja as justificativas enviadas pelos usuários quando eles resolvem uma dica de política substituindo a política.
    
  - Descubra onde as políticas de DLP estão em conflito com processos empresariais válidos, incorrendo em um grande número de substituições de usuário.
    
Todos os relatórios de DLP podem mostrar dados do período de quatro meses mais recente. Os dados mais recentes podem levar até 24 horas para aparecer nos relatórios.
  
Você pode encontrar esses relatórios no Painel de Relatórios &amp; do Centro de Conformidade \>  \> **de Segurança.**
  
![Relatório de combinações de política de DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Exibir a justificativa enviada por um usuário para uma substituição

Se sua política DLP permitir que os usuários a substituam, você poderá usar o falso positivo e substituir o relatório para exibir o texto enviado pelos usuários na dica de política.
  
![Campo justification in details of the DLP false positive and override report](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas sobre informações e recomendações

Os relatórios podem mostrar insights e recomendações em que você pode clicar no ícone de aviso vermelho para ver detalhes sobre possíveis problemas e tomar uma possível ação corretiva.
  
![Clicar em um ícone do Insights para ver detalhes e ações a tomar](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Permissões para relatórios DLP

Para exibir relatórios de DLP no Centro de Conformidade & segurança, você deve ter o:

- **Função leitor de** segurança no Centro de administração do Exchange. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Leitor de Segurança no Centro de administração do Exchange.

- **Função de Gerenciamento de Conformidade de DLP somente** para exibição no Centro de Conformidade & Segurança. Por padrão, essa função é atribuída aos grupos de funções Administrador de Conformidade, Gerenciamento da Organização, Administrador de Segurança e Leitor de Segurança no Centro de Conformidade & Segurança.

- **Função Somente Exibição de Destinatários** no Centro de administração do Exchange. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade, Gerenciamento da Organização View-Only Gerenciamento da Organização no Centro de administração do Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Encontrar os cmdlets para os relatórios de DLP

Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:
  
1. [Conectar-se ao Centro &amp; de Conformidade de Segurança usando o PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Usar qualquer um desses [ &amp; cmdlets do Centro de Conformidade de Segurança](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
No entanto, os relatórios DLP precisam extrair dados do Office 365, incluindo o Exchange Online. Por esse motivo, os cmdlets para os relatórios de DLP estão disponíveis no Powershell do Exchange Online, não no Powershell do Centro de Conformidade &amp; de Segurança. Portanto, para usar os cmdlets para os relatórios DLP, você precisa:
  
1. [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Usar qualquer um destes cmdlets para os relatórios DLP:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

