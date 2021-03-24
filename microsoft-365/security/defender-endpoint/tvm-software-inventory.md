---
title: Inventário de software no gerenciamento de ameaças e vulnerabilidades
description: A página de inventário de software para o gerenciamento de ameaças e vulnerabilidades do Microsoft Defender ATP mostra quantas deficiências e vulnerabilidades foram detectadas no software.
keywords: gerenciamento de ameaças e vulnerabilidades, microsoft defender atp, inventário de software do microsoft defender atp, gerenciamento de vulnerabilidades de ameaças & m & datp, inventário de software de gerenciamento de vulnerabilidades do mdatp, inventário de software de tvm mdatp, inventário de software de tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a161cfcad301c6e5cac2c7398b5c13559b27698d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053837"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a>Inventário de software - gerenciamento de ameaças e vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

O inventário de software no gerenciamento de ameaças e vulnerabilidades é uma lista de softwares conhecidos em sua organização com enumerações de [plataformas comuns (CPE)](https://nvd.nist.gov/products/cpe)oficiais. Os produtos de software sem uma CPE oficial não têm vulnerabilidades publicadas. Ele também inclui detalhes como o nome do fornecedor, número de pontos fracos, ameaças e número de dispositivos expostos.

## <a name="how-it-works"></a>Como funciona

No campo da descoberta, estamos aproveitando o mesmo conjunto de sinais que é responsável pela avaliação de detecção e vulnerabilidade no Microsoft Defender para recursos de detecção e resposta de ponto de [extremidade.](overview-endpoint-detection-response.md)

Como é em tempo real, em questão de minutos, você verá informações de vulnerabilidade à medida que elas são descobertas. O mecanismo captura automaticamente informações de vários feeds de segurança. Na verdade, você verá se um software específico está conectado a uma campanha de ameaça ao vivo. Ele também fornece um link para um relatório de Análise de Ameaças assim que ele está disponível.

## <a name="navigate-to-the-software-inventory-page"></a>Navegue até a página Inventário de software

Acesse a página Inventário de software selecionando **Inventário de software** no menu de navegação de gerenciamento de ameaças e vulnerabilidades no Centro de Segurança do Microsoft [Defender.](portal-overview.md)

Exibir software em dispositivos específicos nas páginas de dispositivos individuais da lista [de dispositivos](machines-view-overview.md).

>[!NOTE]
>Se você procurar software usando a pesquisa global do Microsoft Defender for Endpoint, certifique-se de colocar um sublinhado em vez de um espaço. Por exemplo, para os melhores resultados de pesquisa, você escreveria "windows_10" em vez de "Windows 10".

## <a name="software-inventory-overview"></a>Visão geral do inventário de software

A **página inventário** de software é aberta com uma lista de softwares instalados em sua rede, incluindo o nome do fornecedor, as fraquezas encontradas, as ameaças associadas a eles, dispositivos expostos, impacto na pontuação de exposição e marcas.

Você pode filtrar a exibição de lista com base em pontos fracos encontrados no software, ameaças associadas a eles e marcas como se o software atingiu o fim do suporte.

![Exemplo da página inicial do inventário de software.](images/tvm-software-inventory.png)

Selecione o software que você deseja investigar. Um painel de sobrevoo será aberto com uma exibição mais compacta das informações na página. Você pode mergulhar mais profundamente na investigação e selecionar **Abrir página de software** ou sinalizar quaisquer inconsistências técnicas selecionando Report **inexatidão**.

### <a name="software-that-isnt-supported"></a>Software que não tem suporte

Softwares que não são suportados atualmente por ameaças & gerenciamento de vulnerabilidades podem estar presentes na página Inventário de software. Como não há suporte, apenas dados limitados estarão disponíveis. Filtrar por software sem suporte com a opção "Não disponível" na seção "Fraqueza".

![Filtro de software sem suporte.](images/tvm-unsupported-software-filter.png)

O seguinte indica que não há suporte para um software:

- O campo Pontos Fracos mostra "Não disponível"
- O campo Dispositivos Expostos mostra um traço
- Texto informacional adicionado no painel lateral e na página de software
- A página de software não terá as recomendações de segurança, vulnerabilidades descobertas ou seções de linha do tempo do evento

Atualmente, os produtos sem um CPE não são mostrados na página de inventário de software, somente no inventário de software no nível do dispositivo.

## <a name="software-inventory-on-devices"></a>Inventário de software em dispositivos

No painel de navegação do Centro de Segurança do Microsoft Defender, vá para a lista **[Dispositivos](machines-view-overview.md)**. Selecione o nome de um dispositivo para abrir a página do dispositivo (como Computador1) e selecione a guia Inventário de **software** para ver uma lista de todos os softwares conhecidos presentes no dispositivo. Selecione uma entrada de software específica para abrir o sobrevoo com mais informações.

O software pode estar visível no nível do dispositivo, mesmo que não tenha suporte no momento pelo gerenciamento de ameaças e vulnerabilidades. No entanto, apenas dados limitados estarão disponíveis. Você saberá se o software não tem suporte porque ele dirá "Não disponível" na coluna "Fraqueza".

Software sem CPE também pode aparecer no inventário de software específico deste dispositivo.

### <a name="software-evidence"></a>Evidências de software

Consulte evidências de onde detectamos um software específico em um dispositivo do Registro, disco ou ambos. Você pode encontrá-lo em qualquer dispositivo no inventário de software do dispositivo.

Selecione um nome de software para abrir o sobrevoo e procure a seção chamada "Evidência de Software".

![Exemplo de evidência de software do Windows 10 da lista de dispositivos, mostrando o caminho do registro de evidências de software.](images/tvm-software-evidence.png)

## <a name="software-pages"></a>Páginas de software

Você pode exibir páginas de software de algumas maneiras diferentes:

- Página de inventário de software > Selecione um nome de software > selecione **Abrir página de software** no flyout
- [Página de recomendações](tvm-security-recommendation.md) de segurança > Selecione uma recomendação > Selecione **Abrir software** no sobrevoo
- [Página de](threat-and-vuln-mgt-event-timeline.md) linha do tempo do evento > Selecione um evento > Selecione o nome do software hiperlink (como Visual Studio 2017) na seção chamada "Componente relacionado" no flyout

 Uma página completa aparecerá com todos os detalhes de um software específico e as seguintes informações:

- Painel lateral com informações do fornecedor, prevalência do software na organização (incluindo o número de dispositivos em que ele está instalado e dispositivos expostos que não são remendados), se e exploração está disponível e impacto na pontuação de exposição.
- Visualizações de dados mostrando o número de vulnerabilidades e configurações inconfigurações e gravidade. Além disso, gráficos com o número de dispositivos expostos.
- Guias mostrando informações como:
    - Recomendações de segurança correspondentes para as fraquezas e vulnerabilidades identificadas.
    - CVEs nomeadas de vulnerabilidades descobertas.
    - Dispositivos que têm o software instalado (juntamente com o nome do dispositivo, domínio, sistema operacional e muito mais).
    - Lista de versões de software (incluindo o número de dispositivos em que a versão está instalada, o número de vulnerabilidades descobertas e os nomes dos dispositivos instalados).

    ![Página de exemplo de software Visual Studio 2017 com detalhes de software, pontos fracos, dispositivos expostos e muito mais.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a>Imprecisão de relatório

Reporte um falso positivo quando vir qualquer informação vagas, impreciso ou incompleta. Você também pode relatar as recomendações de segurança que já foram remediadas.

1. Abra o sobrevoo de software na página Inventário de software.
2. Selecione **Relatório impreciso**.
3. No painel submenu, selecione a categoria impreciso no menu suspenso, preencha seu endereço de email e detalhes sobre a imprecisão.
4. Selecione **Enviar**. Seus comentários são enviados imediatamente para os especialistas em gerenciamento de ameaças e vulnerabilidades.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral do gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
- [Linha do tempo do evento](threat-and-vuln-mgt-event-timeline.md)
- [Exibir e organizar a lista do Microsoft Defender for Endpoint Devices](machines-view-overview.md)
