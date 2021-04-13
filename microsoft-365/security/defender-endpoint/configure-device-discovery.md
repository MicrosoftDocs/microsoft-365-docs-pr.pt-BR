---
title: Configurar a descoberta de dispositivo
description: Saiba como configurar a descoberta de dispositivos no Microsoft 365 Defender usando a descoberta básica ou padrão
keywords: básico, padrão, configurar descoberta de ponto de extremidade, descoberta de dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 711a3188c49269b2ecedf0cccb6b27986742b048
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698408"
---
# <a name="configure-device-discovery"></a>Configurar a descoberta de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

A descoberta pode ser configurada para estar no modo padrão ou básico. Use a opção padrão para encontrar ativamente dispositivos em sua rede, o que garantirá melhor a descoberta de pontos de extremidade e fornecerá uma classificação de dispositivo mais rica. 

Você pode personalizar a lista de dispositivos usados para executar a descoberta padrão. Você pode habilitar a descoberta padrão em todos os dispositivos conectados que também suportam esse recurso (atualmente - somente dispositivos Windows 10) ou selecionar um subconjunto ou subconjunto de seus dispositivos especificando suas marcas de dispositivo. 


> [!IMPORTANT]
> Para visualizar, primeiro você precisará ativar os recursos de visualização no Centro de Segurança do Microsoft Defender.
> Em seguida, você pode acessar a configuração de descoberta de dispositivo no Centro de segurança do Microsoft 365. A lista de dispositivos não administrativos e recomendações de segurança estará disponível no Centro de Segurança do Microsoft Defender e no Centro de Segurança do Microsoft 365, enquanto os blocos do painel estarão disponíveis apenas no Centro de segurança do Microsoft 365.


Tome as seguintes etapas de configuração no Centro de segurança do Microsoft 365:

1.  Navegue **até Configurações > Descoberta de dispositivo.**
2.  Selecione o modo de descoberta a ser usado em seus dispositivos conectados. 
3.  Se você tiver selecionado para usar a descoberta padrão, selecione quais dispositivos usar para sondagem ativa: todos os dispositivos ou em um subconjunto especificando suas marcas de dispositivo.
4. Clique em **Salvar**.


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Excluir dispositivos de serem sondados ativamente na descoberta padrão
Se houver dispositivos em sua rede que não devem ser verificados ativamente (por exemplo, dispositivos usados como honeypots para outra ferramenta de segurança), você também pode definir uma lista de exclusões para impedir que eles sejam verificados. Observe que os dispositivos ainda podem ser descobertos usando o modo de descoberta básico. Esses dispositivos serão descobertos passivamente, mas não serão sondados ativamente. 

## <a name="select-networks-to-monitor"></a>Selecionar redes para monitorar
 O Microsoft Defender for Endpoint analisa uma rede e determina se é uma rede corporativa que precisa ser monitorada ou uma rede não corporativa que pode ser ignorada. As redes corporativas geralmente são escolhidas para serem monitoradas. No entanto, você pode substituir essa decisão optando por monitorar redes não corporativas onde os dispositivos conectados são encontrados. 

Você pode configurar onde a descoberta de dispositivo pode ser realizada especificando quais redes monitorar. Quando uma rede é monitorada, a descoberta de dispositivo pode ser realizada nele. 

Uma lista de redes onde a descoberta de dispositivos pode ser executada é mostrada na **página Redes Monitoradas.** 


>[!NOTE]
> Somente as 50 principais redes (de acordo com o número de dispositivos associados) estarão disponíveis na lista de rede. 


A lista de redes monitoradas é classificação com base no número total de dispositivos vistos na rede nos últimos 7 dias.


Você pode aplicar um filtro para exibir qualquer um dos seguintes estados de descoberta de rede:

- **Redes monitoradas** - Redes em que a descoberta de dispositivo é realizada.
- **Redes ignoradas** - Essa rede será ignorada e a descoberta do dispositivo não será executada nele.
- **Todos** - Redes monitoradas e ignoradas serão exibidas. 


### <a name="configure-the-network-monitor-state"></a>Configurar o estado do monitor de rede
Você controla onde ocorre a descoberta do dispositivo. Redes monitoradas são onde a descoberta de dispositivos será realizada e normalmente são redes corporativas. Você também pode optar por ignorar redes ou selecionar a classificação de descoberta inicial após modificar um estado. 

Escolher a classificação de descoberta inicial significa aplicar o estado padrão do monitor de rede feito pelo sistema. Selecionar o estado padrão do monitor de rede feito pelo sistema significa que as redes identificadas como corporativas serão monitoradas e as identificadas como não corporativas serão ignoradas automaticamente.
 
1. Selecione **Configurações > Descoberta de dispositivo.**
2. Selecione **Redes monitoradas**. 
3. Exibir a lista de redes. 
4. Selecione os três pontos ao lado do nome da rede. 
5. Escolha se deseja monitorar, ignorar ou usar a classificação de descoberta inicial. 
    
    > [!WARNING]
    >- A escolha de monitorar uma rede que não foi identificada pelo Microsoft Defender para o Ponto de Extremidade como uma rede corporativa pode causar a descoberta de dispositivo fora da rede corporativa e, portanto, pode detectar dispositivos não corporativos ou de residência. 
    > - A escolha de ignorar uma rede interromperá o monitoramento e a descoberta de dispositivos nessa rede. Os dispositivos que já foram descobertos não serão removidos do inventário, mas não serão mais atualizados e os detalhes serão mantidos até que o período de retenção de dados do Defender for Endpoint expire.
    > - Antes de optar por monitorar redes não corporativas, você deve garantir que tenha permissão para fazer isso. <br>


6. Confirme se você deseja fazer a alteração. 




## <a name="see-also"></a>Confira também
- [Visão geral da descoberta de dispositivo](device-discovery.md)
- [Perguntas frequentes sobre descoberta de dispositivos](device-discovery-faq.md)