---
title: Verificador de avaliação de prontidão para download
description: Verifica as configurações de dispositivo e rede, incluindo pontos de extremidade necessários
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581029"
---
# <a name="downloadable-readiness-assessment-checker"></a>Verificador de avaliação de prontidão para download

Para funcionar bem com Área de Trabalho Gerenciada da Microsoft, os dispositivos devem atender a determinados requisitos de hardware e configurações. Além disso, cada dispositivo deve ser capaz de alcançar pontos de extremidade principais. Baixe e execute essa ferramenta para obter um relatório HTML, exibir resultados e, em seguida, tomar medidas. Você precisará baixar a ferramenta e os arquivos de suporte e, em seguida, execute-a manualmente em cada dispositivo que você deseja registrar no Área de Trabalho Gerenciada da Microsoft.

Para cada verificação, a ferramenta relatará um dos três resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Aviso    | Siga as etapas na ferramenta para ter a melhor experiência com registro e usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.        |
|Não está pronto | *O registro falhará* se você não corrigir esses problemas. Siga as etapas na ferramenta para resolvê-las.        |

## <a name="obtain-the-checker"></a>Obter o checker

Baixe o arquivo .zip de https://aka.ms/mmddratoolv0 .

> [!NOTE]
> O usuário que executa a ferramenta deve ter direitos de Administrador local no dispositivo em que a está executando.

 Em seguida, execute a ferramenta seguindo estas etapas:

1. Copie o arquivo .zip para cada dispositivo que você deseja verificar.
2. Extraia todos os arquivos no download compactado.
3. Execute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Quando o prompt controle de acesso do usuário for exibido, selecione **Sim**. A ferramenta é executado e abre um relatório no navegador padrão.

Você também pode baixar e extrair o arquivo .zip  para um local compartilhado, acessarMicrosoft.MMD.DeviceReadinessAssessmentTool.exede cada dispositivo e, em seguida, execute-o localmente.


## <a name="checks"></a>Verificações

A ferramenta baixável verifica esses itens relacionados ao dispositivo e à rede:

### <a name="hardware"></a>Hardware

Os dispositivos devem atender a requisitos de hardware específicos para trabalhar com Área de Trabalho Gerenciada da Microsoft. Atualmente, somente dispositivos [aprovados](../service-description/device-list.md) específicos têm permissão para se inscrever. 

Se o dispositivo falhar em qualquer uma das verificações, ele não será compatível com Área de Trabalho Gerenciada da Microsoft.

### <a name="network-endpoints"></a>Pontos de extremidade de rede

Os dispositivos podem alcançar vários pontos [de extremidade principais](network.md) para trabalhar com Área de Trabalho Gerenciada da Microsoft.

Se a ferramenta relatar um **resultado Não** pronto, consulte o relatório detalhado para descobrir quais pontos de extremidade não eram acessíveis. Em seguida, ajuste o firewall ou outras configurações de rede para garantir que esses pontos de extremidade possam ser atingidos.

### <a name="other-settings"></a>Outras configurações

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise de wi-fi

Um **resultado de Consultoria** significa que você está usando alguns perfis wi-fi que precisam de certificados e perfis para funcionar corretamente. Para obter mais informações, [consulte Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).

#### <a name="lan-profiles"></a>Perfis de LAN

Um **resultado de Consultoria** significa que você tem LANs que precisam de certificados e perfis para funcionar corretamente. Para obter mais informações, [consulte Prepare certificates and network profiles for Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md).

#### <a name="vpn-profiles"></a>Perfis VPN

Um **resultado de Consultoria** significa que você está usando uma VPN (rede virtual privada). Crie um perfil VPN que implante certificados integrados ao Microsoft Intune. Para obter mais informações, [consulte Prepare certificates and network profiles for Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md).

#### <a name="mapped-drives"></a>Unidades mapeadas

Um **resultado de Consultoria** significa que você tem algumas unidades mapeadas, que não são recomendadas. Para obter mais informações, [consulte Preparar unidades mapeadas para Área de Trabalho Gerenciada da Microsoft](mapped-drives.md).

#### <a name="print-queues"></a>Filas de impressão

Um **resultado de Consultoria** significa que você tem algumas filas de impressão pendentes, que não são recomendadas. Uma solução é usar a impressão em nuvem. Para obter mais informações, [consulte Prepare printing resources for Área de Trabalho Gerenciada da Microsoft](printing.md).

#### <a name="proxies"></a>Proxies

Um **resultado de Consultoria** significa que você tem um servidor proxy em uso. Para obter mais informações, consulte [Configuração de rede para Área de Trabalho Gerenciada da Microsoft](network.md).

