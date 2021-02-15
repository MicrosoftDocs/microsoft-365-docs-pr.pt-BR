---
title: Alinhamento de Descobertas Eletrônicos Avançadas com o EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O fluxo de trabalho integrado da Descoberta Eletrônica Avançada no Microsoft 365 se alinha ao processo de Descoberta Eletrônica descrito pelo EDRM (Electronic Discovery Reference Model).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841591"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Alinhamento da Descoberta Eletrônica Avançada com o Modelo de Referência de Descoberta Eletrônica

O fluxo de trabalho integrado da Descoberta Eletrônica Avançada no Microsoft 365 se alinha ao processo de Descoberta Eletrônica descrito pelo EDRM (Electronic Discovery Reference Model).

![O EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Cortesia de origem da imagem edrm.net. A imagem de origem foi disponibilizada em Creative Commons Attribution 3.0 Unported License.)

Em um nível alto, veja como a Descoberta Avançada dá suporte ao fluxo de trabalho EDRM:

- **Identificação.** Depois de identificar possíveis pessoas de interesse em uma investigação, você pode adicioná-las como custodiantes (também chamadas de responsáveis de *dados,* porque elas podem ter informações relevantes para a investigação) para um caso de Descoberta Avançada. Depois que os usuários são adicionados como custodiantes, é fácil preservar, coletar e revisar documentos custodiantes.

- **Preservação.** Para preservar e proteger dados que são relevantes para uma investigação, a Descoberta Avançada permite que você coloque uma responsabilidade legal sobre as fontes de dados associadas aos responsáveis em um caso. Você também pode colocar dados não custodial em espera. A Descoberta Eletrônica Avançada também tem um fluxo de trabalho de comunicação integrado para que você possa enviar notificações de responsabilidade legal aos responsáveis e acompanhar suas confirmações.

- **Coleção.** Depois de identificar (e preservar) as fontes de dados relevantes para a investigação, você pode usar a ferramenta de pesquisa interna na Pesquisa de Descoberta Avançada e coletar dados a vivos das fontes de dados custodial (e fontes de dados não custodial, se aplicável) que podem ser relevantes para o caso.

- **Processamento.** Depois de coletar todos os dados relevantes para o caso, a próxima etapa é processá-los para análise e revisão posteriores. Na Descoberta Avançada, os dados in-loco que você identificou na fase de coleta são copiados para um local de Armazenamento do Azure (chamado de conjunto de *revisão),* que fornece uma exibição estática dos dados da ocorrência. 

- **Revisão.** Depois que os dados são adicionados a um conjunto de revisão, você pode exibir documentos específicos e executar consultas adicionais para reduzir os dados ao que é mais relevante para o caso. Além disso, pode anotar e marcar documentos específicos.

- **Análise.** A Descoberta Avançada fornece uma ferramenta de análise integrada que ajuda você a excluir ainda mais os dados do conjunto de revisão que você determina que não são relevantes para a investigação. Além de reduzir o volume de dados relevantes, a Descoberta Antecipada também ajuda a economizar custos de revisão jurídica, o que permite organizar o conteúdo para tornar o processo de revisão mais fácil e eficiente.

- **Produção** e **apresentação.** Quando estiver pronto, você poderá exportar documentos de um conjunto de revisão para revisão jurídica. Você pode exportar documentos em seu formato nativo ou em um formato especificado por EDRM para que eles possam ser importados para aplicativos de revisão de terceiros.

## <a name="more-information"></a>Mais informações

Para começar a usar a Descoberta Avançada, confira:

- [Configurar a Descoberta Eletrônica Avançada](get-started-with-advanced-ediscovery.md)

- [Criar e gerenciar um caso de Descoberta Descoberta Avançada](create-and-manage-advanced-ediscoveryv2-case.md)