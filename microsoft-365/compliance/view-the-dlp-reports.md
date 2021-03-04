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
description: Use os relatórios de DLP no Office 365 para exibir o número de jogos de política de DLP, substituições ou falsos positivos e ver se eles estão em tendência para cima ou para baixo com o tempo.
ms.openlocfilehash: eb281f4d912a9e21716d7f9859564a02f9c23401
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423824"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Exibir os relatórios de prevenção contra perda de dados

Depois de criar suas políticas de prevenção contra perda de dados (DLP), você vai querer verificar se elas estão funcionando conforme você pretendia e ajudá-lo a permanecer em conformidade. Com os relatórios de DLP no Centro &amp; de Conformidade e Segurança, você pode exibir rapidamente:
  
- **A política DLP corresponde** Este relatório mostra a contagem de combinações de política de DLP ao longo do tempo. Você pode filtrar o relatório por data, local, política ou ação. Você pode usar este relatório para: 
    
  - Ajuste ou refine suas políticas de DLP conforme você as executar no modo de teste. Você pode exibir a regra específica que corresponderá ao conteúdo.
    
  - Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.
    
  - Descobrir processos empresariais que violam as políticas DLP da organização.
    
  - Entenda qualquer impacto comercial das políticas de DLP vendo quais ações estão sendo aplicadas ao conteúdo.
    
  - Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.
    
  - Exibir uma lista dos principais usuários e repetir usuários que estão contribuindo para incidentes em sua organização.
    
  - Exibir uma lista dos principais tipos de informações confidenciais em sua organização.
    
- **Incidentes DLP** Este relatório também mostra as combinações de política ao longo do tempo, como o relatório de corresponde à política. No entanto, o relatório de corresponde à política mostra as combinações em um nível de regra; por exemplo, se um email correspondeu a três regras diferentes, o relatório de corresponder à política mostrará três itens de linha diferentes. Por outro lado, o relatório de incidentes mostra as combinações em um nível de item; por exemplo, se um email corresponder a três regras diferentes, o relatório de incidentes mostrará um único item de linha para esse conteúdo. 
    
  Como as contagens de relatório são agregadas de forma diferente, o relatório de combinações de política é melhor para identificar as combinações com regras específicas e ajustar as políticas DLP de ajuste fino. O relatório de incidentes é melhor para identificar partes específicas de conteúdo que são problemáticas para suas políticas de DLP.
    
- **DLP falsos positivos e substituições** Se sua política de DLP permitir que os usuários a substituam ou reportem um falso positivo, este relatório mostrará uma contagem dessas instâncias ao longo do tempo. Você pode filtrar o relatório por data, local ou política. Você pode usar este relatório para: 
    
  - Ajuste ou refine suas políticas de DLP vendo quais políticas incorrem em um alto número de falsos positivos.
    
  - Exibir as justificativas enviadas pelos usuários quando resolverem uma dica de política substituindo a política.
    
  - Descubra onde as políticas de DLP conflitam com processos comerciais válidos incorrendo em um alto número de substituições de usuários.
    
Todos os relatórios de DLP podem mostrar dados do período de quatro meses mais recente. Os dados mais recentes podem levar até 24 horas para aparecerem nos relatórios.
  
Você pode encontrar esses relatórios no Painel de Relatórios do Centro &amp; de Conformidade \>  \> **e Segurança.**
  
![Relatório de corresponde à política de DLP](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Exibir a justificativa enviada por um usuário para uma substituição

Se sua política de DLP permitir que os usuários a substituam, você poderá usar o relatório falso positivo e substituir para exibir o texto enviado pelos usuários na dica de política.
  
![Campo Justification em detalhes do relatório de falso positivo e substituição de DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Tomar medidas sobre insights e recomendações

Os relatórios podem mostrar insights e recomendações em que você pode clicar no ícone de aviso vermelho para ver detalhes sobre possíveis problemas e realizar uma possível ação corretiva.
  
![Clicando em um ícone de insights para ver detalhes e ações a ser tomadas](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Permissões para relatórios DLP

Para exibir relatórios de DLP no Centro de Conformidade & segurança, você precisa ter o:

- **Função leitor de** segurança no centro de administração do Exchange. Por padrão, essa função é atribuída aos grupos de função Gerenciamento da Organização e Leitor de Segurança no Centro de administração do Exchange.

- **Função de Gerenciamento de Conformidade de DLP** somente exibição no Centro de Conformidade & Segurança. Por padrão, essa função é atribuída aos grupos de função Administrador de Conformidade, Gerenciamento da Organização, Administrador de Segurança e Leitor de Segurança no Centro de Conformidade & Segurança.

- **Função Somente exibição Destinatários** no Centro de administração do Exchange. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade, Gerenciamento da Organização e gerenciamento View-Only Organização no centro de administração do Exchange.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Encontre os cmdlets para os relatórios DLP

Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:
  
1. [Conectar-se ao Centro &amp; de Conformidade de Segurança usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. Use qualquer um desses [ &amp; cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409) do Centro de Conformidade de Segurança
    
No entanto, os relatórios DLP precisam extrair dados do Office 365, incluindo o Exchange Online. Por esse motivo, os cmdlets para os relatórios DLP estão disponíveis no Powershell do Exchange Online, não no Centro de &amp; Conformidade de Segurança do Powershell. Portanto, para usar os cmdlets para os relatórios DLP, você precisa:
  
1. [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Usar qualquer um destes cmdlets para os relatórios DLP:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

