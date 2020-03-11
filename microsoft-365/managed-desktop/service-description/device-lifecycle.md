---
title: Ciclo de vida do produto do Microsoft Managed desktop
description: Este tópico lista as especificações de dispositivo usadas na área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583168"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Ciclo de vida do produto do Microsoft Managed desktop

Os usuários finais da área de trabalho gerenciada da Microsoft garantem que eles sempre usem dispositivos que oferecem os melhores desempenho, confiabilidade, design e recursos de segurança (como suporte para recursos como o Windows Hello). Para fazer isso, a área de trabalho gerenciada da Microsoft mantém um pequeno catálogo de [dispositivos aprovados](device-list.md)continuamente atualizados. 
 
Este tópico detalha o ciclo de vida dos dispositivos à medida que são adicionados e removidos do catálogo aprovado. 

> [!NOTE]
> Neste tópico, faremos uma distinção entre um "dispositivo" e um "produto". Por "dispositivo", queremos dizer um computador individual e específico. Por exemplo, "número de série 1234", "laptop da Bill", "VM compartilhada XYZ" refere-se a dispositivos específicos. Um "produto", no entanto, refere-se a uma coleção ou família de dispositivos. Por exemplo, "fabrikam laptop", "adatum ZX450 laptop", etc. Isso é importante porque os produtos são adicionados à nossa lista ou catálogos [aprovados](device-list.md), e os dispositivos são os que são registrados na área de trabalho gerenciada da Microsoft.

## <a name="product-lifecycle"></a>Ciclo de vida do produto

 Geralmente, os produtos passam por essas fases do ciclo de vida:

- [Versão e avaliação do produto](#product-release-and-evaluation)
- [Período de disponibilidade principal do produto](#product-primary-availability-period)
- [Período de cortesia do produto](#product-grace-period)
- [Descontinuação de produto](#product-retirement)


Esta ilustração mostra a sequência inteira:

![linha do tempo do ciclo de vida: Iniciando com a disponibilidade geral do produto, a "disponibilidade principal" dura dois anos. Durante esse período, a janela de certificação termina e em algum momento o dispositivo é integrado. No final da disponibilidade principal, o produto é arquivado e o "período de carência" de três anos é iniciado. A partir do momento em que o dispositivo é integrado, ele tem um período de 3 anos de uso até que seja removido do gerenciamento. No final do período de carência, removemos o produto do catálogo.](../../media/non-dark1-edits.PNG)

Os produtos permanecem no catálogo por até 24 meses, mas os <em>dispositivos</em> permanecem sob gerenciamento por 3 anos com base em suas datas de registro individuais. Efetivamente, cada produto tem três datas importantes, mas cada dispositivo tem apenas um. Para produtos, todas as três datas são calculadas com base na <em>data de aprovação</em>e, portanto, publicamos essas datas após a aprovação, de modo que você possa sempre olhar em frente e planejar adequadamente para o ciclo de vida inteiro do produto.

Esta tabela mostra as datas de exemplo de um produto teórico:


|Produto  |Data de aprovação  |Fim da disponibilidade principal  |Fim da elegibilidade  |
|---------|---------|---------|---------|
|Laptop da Fabrikam    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Laptop adatum   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Esta tabela mostra datas de exemplo para *dispositivos*teóricos:


|ID do dispositivo  |Data de registro  |Data de aposentadoria  |
|---------|---------|---------|
|#123412 de laptop     |  2/3/2018       |  2/3/2021       |
|#321513 de área de trabalho     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Versão e avaliação do produto

O ciclo de vida do produto é iniciado quando um fabricante lança o produto publicamente:

![linha do tempo do ciclo de vida mostrando o período de lançamento e avaliação](../../media/non-dark3-edits.PNG)

Durante esse estágio, a equipe de engenharia de área de trabalho gerenciada da Microsoft faz a avaliação e a certificação de um produto. A equipe avalia itens como confiabilidade e desempenho com o Windows, conformidade com uma linha de base de hardware, informações do mercado e disponibilidade de estoque e canal, entre outras coisas. Esse processo geralmente leva aproximadamente 6 semanas.
  
A área de trabalho gerenciada da Microsoft só avaliará dispositivos de certificação nos primeiros 6 meses de disponibilidade. Isso garante que estamos sempre concentrando nossos esforços na última geração de hardware.
 
No final desta fase, a área de trabalho gerenciada da Microsoft adiciona o produto à [lista aprovada](device-list.md), liberando com eficiência o produto para as registradoras do cliente. Independentemente da data em que um dispositivo é certificado, sua **data de aprovação** é de back-data para a data de disponibilidade geral do produto. 


## <a name="product-primary-availability-period"></a>Período de disponibilidade principal do produto

Esse período é o principal da disponibilidade do produto:

![linha do tempo do ciclo de vida mostrando a disponibilidade principal](../../media/non-dark4-edits.PNG)

Todos os dispositivos registrados durante esse período recebem o total de três anos de suporte da área de trabalho gerenciada da Microsoft (conforme mostrado na linha do tempo azul). Este período dura até uma data de término definida como 24 meses a partir da data de disponibilidade geral.

Você pode pensar nesse período com o "registro aberto" efetivamente, para maximizar o valor da área de trabalho gerenciada da Microsoft, você deve direcionar os modelos de compras e os produtos selecionados para se enquadram neste período. Como um pequeno exemplo, um cliente deve evitar a liquidação em um período de distribuição de dois anos usando um produto que esteja no mês final da disponibilidade principal – a maioria desses dispositivos não receberá os três anos de gerenciamento de área de trabalho gerenciada da Microsoft (consulte [período de cortesia](#product-grace-period) para obter mais informações).  

## <a name="product-grace-period"></a>Período de cortesia do produto

O período de cortesia do produto é um período de três anos após a disponibilidade principal. Esta fase permite que você registre dispositivos que são de uma família de produtos com suporte, mas ainda confirmam as promessas da área de trabalho gerenciada da Microsoft sobre o desempenho moderno de hardware e dispositivos. Esta fase é ideal para clientes que fizeram decisões de compras antes de saber sobre a área de trabalho gerenciada da Microsoft. 

Se você comprou recentemente vários dispositivos aprovados antes de se inscrever com a área de trabalho gerenciada da Microsoft, ainda poderá registrá-los, mas não receberá um total de três anos de gerenciamento. Em vez disso, eles ficarão fora de conformidade na data de aposentadoria, independentemente de quando eles estiverem registrados. Nos bastidores, a área de trabalho gerenciada da Microsoft tratará esses dispositivos como se estivessem registrados no último dia da disponibilidade principal. Nesta ilustração, você pode ver esse cenário observando que o dispositivo azul e verde termina no mesmo dia, apesar da diferença de um ano no registro:


![linha do tempo do ciclo de vida mostrando período de carência](../../media/non-dark2-edits.PNG)

O exemplo de laptop da Fabrikam da tabela anterior ilustra essa situação: 

|Produto  |Data de aprovação  |Fim da disponibilidade principal  |Fim da elegibilidade  |
|---------|---------|---------|---------|
|Laptop da Fabrikam    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Como cliente, você pode registrar os laptops da Fabrikam o caminho até 6/1/2022 – no entanto, eles serão tratados como se você os tivesse registrado no 6/1/2019. Se você inscrever um laptop da Fabrikam em 6/1/2021, obterá apenas um ano de gerenciamento. Essa política permite extrair ciclos de vida parciais de produtos que tinham suporte anteriormente, em vez de ter que adquirir novos dispositivos prematuramente. 

Por fim, durante esta fase, o dispositivo é removido da [lista de dispositivos](device-list.md) e movido para a lista de [dispositivos arquivados](archived-device-list.md).


## <a name="product-retirement"></a>Descontinuação de produto

A aposentadoria do produto é a fase final do ciclo de vida. Nesta fase, nenhum dispositivo novo desse tipo de produto pode ser inscrito na área de trabalho gerenciada da Microsoft e, por definição, todos os dispositivos existentes agora estão fora do termo de três anos permitido. Durante esse período, a área de trabalho gerenciada da Microsoft removerá totalmente o dispositivo da lista pública. Também é durante esta fase, em que, se você ainda não tiver adquirido as substituições, começará a ver os serviços reduzidos à medida que o Microsoft Managed desktop começar a aumentar a velocidade dos dispositivos que estão fora de conformidade. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivos que estão fora de conformidade

Um dispositivo está fora de conformidade quando a janela permitida para o gerenciamento de área de trabalho gerenciada da Microsoft tiver decorrido. Isso ocorre quando o dispositivo alcança três anos de gerenciamento ou quando esse tipo de produto é removido do catálogo de dispositivos, o que ocorrer primeiro. Você deve sempre direcionar seus ciclos de compras de forma que novos dispositivos sejam implantados antes de os dispositivos atuais ficar fora de conformidade.

A equipe de área de trabalho gerenciada da Microsoft sabe que os ciclos de compras são longos e planejados em relação aos orçamentos de longa duração. Para garantir que você esteja sempre ciente do estado de sua população de dispositivos, fornecemos um [site](https://aka.ms/mmdportal) que lista todos os dispositivos sob gerenciamento, sua idade e um status que indica sua conformidade. Isso significa que você sempre tem as últimas informações sobre a idade do dispositivo e pode usar o relatório em qualquer ciclo de planejamento de compras. 







