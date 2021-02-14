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
description: Este artigo contém dicas gerais e links para outros recursos que explicam como melhorar o desempenho do Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687359"
---
# <a name="tune-exchange-online-performance"></a>Ajuste o desempenho do Exchange Online

Este artigo contém dicas gerais e links para outros recursos que explicam como melhorar o desempenho do Exchange Online, especialmente antes de uma migração. Este artigo faz parte do planejamento [de rede e ajuste de desempenho do projeto do Office 365.](https://aka.ms/tune)
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Coisas a considerar para melhorar o desempenho do Exchange Online

Para aumentar a velocidade da migração e reduzir as restrições de largura de banda da sua organização para o Exchange Online, considere o seguinte:
  
- **Reduzir tamanhos de caixa de correio.** Um tamanho menor de caixa de correio melhora a velocidade de migração. 
    
- **Use os recursos de movimentação de caixa de correio com uma implantação híbrida do Exchange.** Com uma implantação híbrida do Exchange, o email offline (na forma de . Arquivos OST) não exigem re download ao migrar para o Exchange Online. Isso reduz significativamente seus requisitos de largura de banda para download. 
    
- **Agende movimentações de caixa de correio para ocorrer durante períodos de baixo tráfego da Internet e baixo uso do Exchange local.** Ao agendar movimentações, as solicitações de migração são enviadas ao proxy de replicação de caixa de correio e podem não ocorrer imediatamente. 
    
- **Use pop-outs enxutos para o Outlook na Web.** Os pop-outs enxutos fornecem versões menores e com menos memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer renderizar alguns componentes no servidor. Para obter mais informações, [consulte Usar pop-outs enxutos para reduzir a memória usada ao ler mensagens de email.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>Conselhos gerais

- Certifique-se de que a pesquisa de DNS outlook.office.com o MS-datacenter em um local de entrada lógica para o seu local.

- Pesquise o cache da caixa de correio e escolha as opções apropriadas (re. período de cache, armazenamento em cache de caixa de correio compartilhada, etc.

- Mantenha seus dados do Outlook passando conexões VPN (para um escritório central) antes que eles passe pela Internet.

- Certifique-se de que seus dados de caixa de correio aderem às limitações de pasta e itens, valores.
    
Para saber mais sobre o desempenho da migração do Exchange, confira o desempenho e as práticas recomendadas de migração do [Office 365.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
  

