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

Este artigo contém dicas gerais e links para outros recursos que explicam como melhorar o desempenho do Exchange Online, particularmente na frente de uma migração. Este artigo faz parte do [planejamento de rede e ajuste de desempenho para o projeto do Office 365](https://aka.ms/tune) .
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Considerações a serem consideradas para melhorar o desempenho do Exchange Online

Para melhorar a velocidade da migração e reduzir as restrições de largura de banda da sua organização para o Exchange Online, considere o seguinte:
  
- **Reduzir tamanhos de caixa de correio.** O tamanho de caixa de correio menor melhora a velocidade de migração. 
    
- **Use os recursos de movimentação de caixa de correio com uma implantação híbrida do Exchange.** Com uma implantação híbrida do Exchange, email offline (na forma de. OST) não requer o novo download ao migrar para o Exchange Online. Isso reduz significativamente os requisitos de largura de banda de download. 
    
- **Agendar movimentações de caixa de correio para ocorrer durante períodos de baixo tráfego da Internet e baixo uso do Exchange no local.** Ao agendar movimentações, as solicitações de migração são enviadas para o proxy de replicação de caixa de correio e podem não acontecer imediatamente. 
    
- **Use o Lean pop-ups para Outlook na Web.** O Lean pop-ups oferece versões menores e menos intensas de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer ao renderizar alguns componentes no servidor. Para obter mais informações, consulte [use Lean pop-ups para reduzir a memória usada ao ler mensagens de email](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Conselhos gerais

- Certifique-se de que a pesquisa de DNS para outlook.office.com Insira o MS-datacenter em um local de entrada lógica para seu local.

- Pesquisar cache de caixa de correio e escolha as opções apropriadas (re. período de cache, cache de caixa de correio compartilhada, et cetera).

- Mantenha seus dados do Outlook passando por conexões VPN (para um escritório central) antes de passar pela Internet.

- Certifique-se de que os dados da caixa de correio estão de acordo com as limitações da pasta e dos valores de item.
    
Para obter mais informações sobre o desempenho de migração do Exchange, confira [desempenho de migração e práticas recomendadas do Office 365](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
  

