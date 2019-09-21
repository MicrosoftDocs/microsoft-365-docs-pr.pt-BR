---
title: Proteger informações
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: página de aterrissagem para proteção de informações
ms.openlocfilehash: 77b4332ae4c5450f7464af660e3cda82ddbe18a5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073404"
---
# <a name="protect-information"></a>Proteger informações

O Microsoft 365 e o Office 365 incluem recursos que podem ser aplicados a tipos específicos de dados para proteger as informações.


|**Funcionalidade**|**Mais informações**|
|:-----|:-----|
|[Rótulos de confidencialidade](sensitivity-labels.md) <br/> |Com rótulos de confidencialidade, você pode classificar e ajudar a proteger o conteúdo confidencial. As opções de proteção incluem rótulos, marcas d' água e criptografia. Os rótulos de confidencialidade usam a proteção de informações do Azure. Se você estiver usando os rótulos de proteção de informações do Azure, por ora, recomendamos que você evite criar novos rótulos em outros centros de Administração até concluir a migração. Confira [migração de proteção de informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels). <br/> Os [Rótulos de retenção](retention-policies.md) são diferentes dos rótulos de confidencialidade. Os rótulos de retenção ajudam você a reter ou excluir o conteúdo com base em políticas definidas por você. Essas organizações ajudam a cumprir as normas do setor e as políticas internas.|
|[Prevenção contra perda de dados](data-loss-prevention-policies.md) DLP  <br/> |Com as políticas de DLP, você pode identificar, monitorar e proteger automaticamente as informações confidenciais no Office 365. As políticas de prevenção contra perda de dados podem usar rótulos de confidencialidade e tipos de informações confidenciais para identificar informações confidenciais. <br/> |
|[Tipos de informações confidenciais](what-the-sensitive-information-types-look-for.md) <br/> |O Microsoft 365 inclui muitos tipos de informações confidenciais que estão prontos para serem usados em políticas de DLP e para classificação automática com rótulos de confidencialidade e retenção. Os tipos de informações confidenciais também podem ser usados com o [Verificador de proteção de informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) para classificar e proteger arquivos no local. Os tipos de informações confidenciais definem como o processo automatizado reconhece tipos de informações específicos, como números de serviço de integridade e números de cartão de crédito.   <br/> |
|[Criptografia de mensagem do Office 365](ome.md) OME  <br/> |Com a criptografia de mensagem do Office 365, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A criptografia de mensagem do Office 365 funciona com o Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagens de email ajuda a garantir que somente os destinatários pretendidos possam exibir o conteúdo da mensagem. <br/> |
|[Proteção de Informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |A proteção de informações do Azure (às vezes referida como AIP) ajuda uma organização a classificar, rotular e, opcionalmente, proteger documentos e emails. Os administradores podem aplicar rótulos automaticamente definindo regras e condições. Os usuários podem aplicar rótulos manualmente a arquivos e email. Você também pode fornecer aos usuários recomendações sobre quando aplicar rótulos.<br/> Se você estiver usando rótulos de confidencialidade ou criptografia de mensagem do Office, já está usando recursos de classificação e proteção. Se você ainda não migrou os rótulos de proteção de informações do Azure para o Office 365, continue a gerenciá-los na proteção de informações do Azure.  <br/>Você pode executar o [Verificador de proteção de informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) no local para classificar e proteger arquivos no Windows Server, em compartilhamentos de rede e em bibliotecas e sites do SharePoint Server. Isso pode ser uma primeira etapa para identificar dados para migrar para o Office 365.
|Proteção de informações do Azure com chave de criptografia gerenciada pelo cliente <br/> |Algumas organizações têm uma necessidade de negócios ou requisito de conformidade para manter o controle de uma chave de criptografia. Isso não é comum. A proteção de informações do Azure permite que as organizações tragam sua chave (BYOK) para o serviço. Para obter mais informações, consulte [trazer sua própria chave (BYOK) para a proteção de informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions). Outra opção mais complexa é oferecida para os clientes que têm a necessidade de manter uma chave de criptografia no local, chamado de manter sua própria chave (HYOK).  Para saber mais, confira [reter sua própria chave (HYOK) para a proteção de informações do Azure](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions). <br/> |
    

