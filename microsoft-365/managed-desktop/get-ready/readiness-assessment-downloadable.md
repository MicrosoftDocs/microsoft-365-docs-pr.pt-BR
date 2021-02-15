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
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921925"
---
# <a name="downloadable-readiness-assessment-checker"></a>Verificador de avaliação de prontidão para download

Para funcionar bem com a Área de Trabalho Gerenciada da Microsoft, os dispositivos devem atender a determinados requisitos de hardware e configurações. Além disso, cada dispositivo deve ser capaz de alcançar pontos de extremidade principais. Baixe e execute essa ferramenta para obter um relatório HTML, exibir resultados e executar uma ação. Você precisará baixar a ferramenta e os arquivos de suporte e, em seguida, execute-a manualmente em cada dispositivo que você deseja registrar na Área de Trabalho Gerenciada da Microsoft.

Para cada verificação, a ferramenta relatará um dos três resultados possíveis:


|Resultado  |Significado  |
|---------|---------|
|Pronto     | Nenhuma ação é necessária antes de concluir o registro.        |
|Aviso    | Siga as etapas na ferramenta para a melhor experiência com o registro e para os usuários. Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.        |
|Não está pronto | *O registro falhará* se você não corrigir esses problemas. Siga as etapas na ferramenta para resolvê-las.        |

## <a name="obtain-the-checker"></a>Obter o checker

Baixe o arquivo .zip de https://aka.ms/mmddratoolv0 .

> [!NOTE]
> O usuário que executa a ferramenta deve ter direitos de Administrador local no dispositivo em que ele a está executando.

 Em seguida, execute a ferramenta seguindo estas etapas:

1. Copie o arquivo .zip baixado para cada dispositivo que você deseja verificar.
2. Extraia todos os arquivos no download compactado.
3. Execute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Quando o prompt controle de acesso do usuário for exibido, selecione **Sim**. A ferramenta é executado e abre um relatório no navegador padrão.

Você também pode baixar e extrair o arquivo  .zip para um local compartilhado, acessarMicrosoft.MMD.DeviceReadinessAssessmentTool.exede cada dispositivo e, em seguida, executar localmente.


## <a name="checks"></a>Verificações

A ferramenta baixável verifica estes itens relacionados à rede e dispositivo:

### <a name="hardware"></a>Hardware

Os dispositivos devem atender a requisitos de hardware específicos para trabalhar com a Área de Trabalho Gerenciada da Microsoft. Atualmente, somente dispositivos [aprovados específicos](../service-description/device-list.md) têm permissão para se inscrever. 

Se o dispositivo falhar em qualquer uma das verificações, ele não será compatível com a Área de Trabalho Gerenciada da Microsoft.

### <a name="network-endpoints"></a>Pontos de extremidade de rede

Os dispositivos podem alcançar vários pontos [de extremidade](network.md) principais para trabalhar com a Área de Trabalho Gerenciada da Microsoft.

Se a ferramenta relatar **um resultado Não** pronto, consulte o relatório detalhado para descobrir quais pontos de extremidade não estavam acessíveis. Em seguida, ajuste o firewall ou outras configurações de rede para garantir que esses pontos de extremidade possam ser alcançados.

### <a name="other-settings"></a>Outras configurações

#### <a name="enterprise-wi-fi-profiles"></a>Perfis de wi-fi corporativos

Um **resultado de** Consultoria significa que você está usando alguns perfis de wi-fi que precisam de certificados e perfis para funcionar corretamente. Para obter mais informações, [consulte Implantar certificados e perfil de Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>Perfis de LAN

Um **resultado de Consultoria** significa que você tem LANs que precisam de certificados e perfis para funcionar corretamente. Para obter mais informações, consulte [Preparar certificados e perfis de rede para a Área de Trabalho Gerenciada da Microsoft.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>Perfis VPN

Um **resultado de** consultoria significa que você está usando uma rede virtual privada (VPN). Crie um perfil vpn que implante certificados integrados ao Microsoft Intune. Para obter mais informações, consulte [Preparar certificados e perfis de rede para a Área de Trabalho Gerenciada da Microsoft.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Unidades mapeadas

Um **resultado de** consultoria significa que você tem algumas unidades mapeadas, que não são recomendadas. Para obter mais informações, consulte [Preparar unidades mapeadas para a Área de Trabalho Gerenciada da Microsoft.](mapped-drives.md)

#### <a name="print-queues"></a>Imprimir filas

Um **resultado de** consultoria significa que você tem algumas filas de impressão pendentes, que não são recomendadas. Uma solução é usar a impressão na nuvem. Para obter mais informações, consulte [Preparar recursos de impressão para a Área de Trabalho Gerenciada da Microsoft.](printing.md)

#### <a name="proxies"></a>Proxies

Um **resultado de** consultoria significa que você tem um servidor proxy em uso. Para obter mais informações, consulte [Configuração de rede da Área de Trabalho Gerenciada da Microsoft.](network.md)

