---
title: Ajuste o desempenho do Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Este artigo contém dicas gerais e links para outros recursos que lhe dizem como melhorar o desempenho do Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909437"
---
# <a name="tune-exchange-online-performance"></a>Ajuste o desempenho do Exchange Online

Este artigo contém dicas gerais e links para outros recursos que lhe dizem como melhorar o desempenho do Exchange Online, especialmente na frente de uma migração. Este artigo faz parte do projeto [Planejamento de rede e ajuste de desempenho do Office 365.](./network-planning-and-performance.md)
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Coisas a considerar para melhorar o desempenho do Exchange Online

Para melhorar a velocidade da migração e reduzir as restrições de largura de banda da sua organização para o Exchange Online, considere o seguinte:
  
- **Reduzir tamanhos de caixa de correio.** O tamanho menor da caixa de correio melhora a velocidade de migração. 
    
- **Use os recursos de movimentação de caixa de correio com uma implantação híbrida do Exchange.** Com uma implantação híbrida do Exchange, o email offline (na forma de . Arquivos OST) não exigem re download ao migrar para o Exchange Online. Isso reduz significativamente seus requisitos de largura de banda de download. 
    
- **Agende movimentações de caixa de correio para ocorrer durante períodos de baixo tráfego da Internet e baixo uso local do Exchange.** Quando o agendamento é movimentado, as solicitações de migração são enviadas ao proxy de replicação de caixa de correio e podem não ocorrer imediatamente. 
    
- **Use pop-outs enxutos para o Outlook na Web.** Os pop-outs enxutos fornecem versões menores e menos intensas de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer renderizar alguns componentes no servidor. Para obter mais informações, [consulte Use popouts enxutos para reduzir](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)a memória usada ao ler mensagens de email .


## <a name="general-advice"></a>Consultoria geral

- Certifique-se de que a pesquisa DNS outlook.office.com o datacenter MS em um local de entrada lógico para sua localização.

- Pesquise o cache da caixa de correio e escolha as opções apropriadas (re. período de cache, cache de caixa de correio compartilhada, et cetera).

- Mantenha seus dados do Outlook de passar conexões VPN (para um escritório central) antes de passar pela Internet.

- Certifique-se de que seus dados de caixa de correio aderem às limitações de valores de pasta e item.
    
Para obter mais informações sobre o desempenho da migração do Exchange, consulte Desempenho e práticas recomendadas de migração do [Office 365.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
