---
title: Arquivar dados de terceiros no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Os administradores podem importar dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos para caixas de correio em sua organização do Office 365. Isso permite que você arquive dados de Facebook, Twitter e outras fontes de dados de terceiros no Office 365. Em seguida, você pode usar e aplicar recursos de conformidade do Office 365 (como retenção legal, eDiscovery, arquivamento in-loco e políticas de retenção) para dados de terceiros.
ms.openlocfilehash: 1e4cc8fc322b4e7e447cc053bd1b0a74ffe40aeb
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38684758"
---
# <a name="archive-third-party-data-in-office-365"></a>Arquivar dados de terceiros no Office 365

O Office 365 permite que os administradores importem e arquivem dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos, para caixas de correio em sua organização do Office 365. Exemplos de fontes de dados de terceiros que podem ser importadas para o Office 365 incluem os seguintes serviços: 
  
- **Social:** Facebook, LinkedIn, Twitter e Yammer 
    
- **Mensagens instantâneas:** Yahoo Messenger, GoogleTalk e Cisco Jabber 
    
- **Colaboração de documentos:** Caixa e DropBox 
    
- **Setores verticais:** Gerenciamento de relacionamento com o cliente (como o Salesforce e os serviços financeiros (como Bloomberg e Thomson Reuters) 
    
- **SMS/mensagens de texto:** Rim 
    
Após a importação dos dados de terceiros, é possível aplicar recursos de conformidade do Office 365, como retenção de litígio, eDiscovery, arquivamento in-loco, auditoria, [conformidade de comunicação](communication-compliance.md)e políticas de retenção do Office 365 – a esses dados. Por exemplo, quando uma caixa de correio é colocada em retenção de litígio, os dados de terceiros são preservados. Você pode pesquisar dados de terceiros usando as ferramentas de descoberta eletrônica da Microsoft. Ou você pode aplicar políticas de arquivamento e retenção a dados de terceiros, da mesma forma que você pode para os dados da Microsoft. Em suma, o arquivamento de dados de terceiros no Office 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.

Há duas maneiras de importar e arquivar dados de terceiros no Office 365:

- **Use um conector de dados de terceiros no centro de conformidade de & de segurança:** Use um conector de dados personalizado que está disponível no centro de conformidade e segurança & no Office 365. Após configurar e configurar o conector, ele se conecta à fonte de dados de terceiros, converte o conteúdo de um item em um formato de mensagem de email e, em seguida, importa o item para uma caixa de correio no Office 365. No momento, você pode implementar conectores para importar e arquivar dados de páginas de negócios do Facebook, contas do Twitter corporativos, o Instant Bloomberg e o LinkedIn. Para obter instruções passo a passo para configurar um conector, consulte:
   
   - **Facebook:** [usar um exemplo de conector para arquivar dados do Facebook no Office 365](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter:** [usar um exemplo de conector para arquivar dados do Twitter no Office 365](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn:** [configurar um conector para arquivar dados do LinkedIn no Office 365](archive-linkedin-data.md)

   - **Bloomberg instantâneo:** [configurar um conector para arquivar dados de Bloomberg instantâneos no Office 365](archive-instant-bloomberg-data.md)

- **Trabalhar com um parceiro da Microsoft:** Sua organização trabalha com um parceiro da Microsoft que fornecerá um conector personalizado que será configurado para extrair itens da fonte de dados de terceiros regularmente e, em seguida, se conectar à nuvem da Microsoft por uma API de terceiros e importá-los para o Office 365. O conector de parceiro também converte o conteúdo de um item da fonte de dados de terceiros em uma mensagem de email e, em seguida, importa-os para uma caixa de correio no Office 365. Para obter uma lista de parceiros com os quais você pode trabalhar e o processo passo a passo desse método, confira [trabalhar com um parceiro para arquivar dados de terceiros no Office 365](work-with-partner-to-archive-third-party-data.md).
