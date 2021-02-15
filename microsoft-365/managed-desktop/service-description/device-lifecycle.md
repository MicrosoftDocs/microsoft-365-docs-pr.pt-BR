---
title: Ciclo de vida do produto da Área de Trabalho Gerenciada da Microsoft
description: Este artigo lista as especificações de dispositivo usadas na Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841194"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Ciclo de vida do produto da Área de Trabalho Gerenciada da Microsoft

A Área de Trabalho Gerenciada da Microsoft beneficia os usuários, garantindo que eles sempre usem dispositivos que ofereçam o melhor desempenho, confiabilidade, design e recursos de segurança (como suporte para recursos como o Windows Hello). Para fazer isso, a Área de Trabalho Gerenciada da Microsoft mantém um pequeno catálogo de dispositivos aprovados [continuamente atualizados.](device-list.md) 
 
Este artigo detalha o ciclo de vida dos dispositivos à medida que eles são adicionados e removidos do catálogo aprovado. 

> [!NOTE]
> Neste tópico, faremos uma distinção entre um "dispositivo" e um "produto". Por "dispositivo", queremos dizer um computador específico e individual. Por exemplo, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" referem-se a dispositivos específicos. Um "produto", no entanto, se refere a uma coleção ou família de dispositivos. Por exemplo, "Laptop Fabrikam", "Adatum ZX450 Laptop", etc. Isso é importante porque os produtos são adicionados à nossa lista aprovada [ou](device-list.md)catálogo, e os dispositivos são o que são inscritos na Área de Trabalho Gerenciada da Microsoft.

## <a name="product-lifecycle"></a>Ciclo de vida do produto

 Geralmente, os produtos passam por essas fases do ciclo de vida:

- [Versão e avaliação do produto](#product-release-and-evaluation)
- [Período de disponibilidade principal do produto](#product-primary-availability-period)
- [Período de carência do produto](#product-grace-period)
- [Baixa do produto](#product-retirement)


Esta ilustração mostra toda a sequência:

![linha do tempo do ciclo de vida: começando com a disponibilidade geral do produto, a "disponibilidade principal" dura dois anos. Durante esse tempo, a janela de certificação termina e, em algum momento, o dispositivo é onboarded. No final da disponibilidade principal, o produto é arquivado e o "período de carência" de três anos começa. A partir de quando o dispositivo é onboarded, ele tem um período de 3 anos de uso até ser removido do gerenciamento. No final do período de carência, removemos o produto do catálogo.](../../media/non-dark1-edits.PNG)

Os produtos permanecem no catálogo por até <em></em> 24 meses, mas os dispositivos permanecem sob gerenciamento por três anos com base em suas datas de registro individuais. Efetivamente, cada produto tem três datas importantes, mas cada dispositivo tem apenas uma. Para produtos, todas essas três datas <em></em>são calculadas com base na data de aprovação e, portanto, publicamos essas datas após a aprovação para que você possa sempre olhar para frente e planejar adequadamente todo o ciclo de vida do produto.

Esta tabela mostra datas de exemplo para um produto bruto:


|Produto  |Data aprovada  |Fim da disponibilidade principal  |Fim da qualificação  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Esta tabela mostra datas de exemplo para dispositivos *negativos:*


|ID do dispositivo  |Data do registro  |Data da reforma  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Área de #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Versão e avaliação do produto

O ciclo de vida do produto começa quando um fabricante lança publicamente o produto:

![linha do tempo do ciclo de vida mostrando o período de versão e avaliação](../../media/non-dark3-edits.PNG)

Durante esse estágio, a equipe de engenharia da Área de Trabalho Gerenciada da Microsoft faz sua avaliação e certificação de um produto. A equipe avalia itens como confiabilidade e desempenho com o Windows, conformidade com uma linha de base de hardware, opiniões de mercado e preparação de estoque e canal, entre outras coisas. Esse processo normalmente leva aproximadamente seis semanas.
  
A Área de Trabalho Gerenciada da Microsoft avaliará apenas os dispositivos para certificação nos primeiros seis meses de disponibilidade. Essa política garante que estamos sempre concentrando nossos esforços na geração mais recente de hardware.
 
No final desta fase, a Área de Trabalho Gerenciada da Microsoft adiciona o produto à lista [aprovada,](device-list.md)liberando efetivamente o produto para as inscrições do cliente. Independentemente da data em que  um dispositivo é certificado, sua data aprovada é aplicada novamente à data de disponibilidade geral do próprio produto. 


## <a name="product-primary-availability-period"></a>Período de disponibilidade principal do produto

Esse período é o núcleo da disponibilidade do produto:

![linha do tempo do ciclo de vida mostrando a disponibilidade principal](../../media/non-dark4-edits.PNG)

Qualquer dispositivo inscrito durante esse período recebe os três anos completos de suporte da Área de Trabalho Gerenciada da Microsoft (conforme mostrado pela linha do tempo azul). Esse período dura até uma data de término definida como 24 meses a partir da data de disponibilidade geral.

Você pode pensar nesse período como efetivamente "registro aberto", portanto, para maximizar o valor da Área de Trabalho Gerenciada da Microsoft, você deve direcionar seus modelos de compra e produtos selecionados para dentro desse período. Como um pequeno exemplo, você deve evitar ficar em um período de distribuição de dois anos usando um produto que está em seu último [](#product-grace-period) mês de disponibilidade principal – a maioria desses dispositivos não receberá os três anos completos de gerenciamento da Área de Trabalho Gerenciada da Microsoft (veja o período de carência para obter mais informações).  

## <a name="product-grace-period"></a>Período de carência do produto

O período de carência do produto é um período de três anos após a disponibilidade principal. Esta fase permite que você inscreva dispositivos que são de uma família de produtos com suporte, mas ainda mantém a segurança das promessas da Área de Trabalho Gerenciada da Microsoft em relação ao hardware moderno e ao desempenho do dispositivo. Esta fase é ideal para clientes que tomaram decisões de compra antes de conhecer a Área de Trabalho Gerenciada da Microsoft. 

Se você comprou recentemente dispositivos aprovados antes de se inscrever na Área de Trabalho Gerenciada da Microsoft, ainda poderá inscreveu-os, mas não receberá um gerenciamento completo de três anos. Em vez disso, eles sairão da conformidade na data da baixa, independentemente de quando foram inscritos. Nos bastidores, a Área de Trabalho Gerenciada da Microsoft tratará esses dispositivos como se fossem inscritos no último dia de disponibilidade principal. Nesta ilustração, você pode ver esse cenário, notando que os dispositivos azul e verde terminam no mesmo dia, apesar da diferença de um ano no registro:


![linha do tempo do ciclo de vida mostrando o período de carência](../../media/non-dark2-edits.PNG)

O exemplo do Fabrikam Laptop da tabela anterior ilustra essa situação: 

|Produto  |Data aprovada  |Fim da disponibilidade principal  |Fim da qualificação  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Como cliente, você pode registrar laptops da Fabrikam até 01/06/2022– no entanto, todos eles serão tratados como se você os registrava em 01/06/2019. Se você registrar um laptop Fabrikam em 1/6/2021, só terá um ano de gerenciamento. Essa política permite extrair ciclos de vida parciais de produtos com suporte anteriormente, em vez de precisar adquirir novos dispositivos prematuramente. 

Por fim, durante essa fase, o dispositivo é removido da lista [de](device-list.md) dispositivos e movido para a lista [de dispositivos arquivados.](archived-device-list.md)


## <a name="product-retirement"></a>Baixa do produto

A baixa do produto é a fase final do ciclo de vida. Nesta fase, nenhum dispositivo novo desse tipo de produto pode ser inscrito na Área de Trabalho Gerenciada da Microsoft e, por definição, todos os dispositivos existentes agora estão fora do período de três anos permitido. Durante esse tempo, a Área de Trabalho Gerenciada da Microsoft removerá totalmente o dispositivo da lista pública. Também durante essa fase, se você ainda não tiver adquirido substituições, começará a ver serviços reduzidos à medida que a Área de Trabalho Gerenciada da Microsoft começar a aumentar os dispositivos que estão fora de conformidade. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivos que estão fora de conformidade

Um dispositivo está fora de conformidade quando a janela permitida para o gerenciamento da Área de Trabalho Gerenciada da Microsoft decorrido. Essa situação ocorre quando o dispositivo atinge três anos de gerenciamento ou quando esse tipo de produto é removido do catálogo de dispositivos, o que ocorrer primeiro. Você deve sempre direcionar seus ciclos de compras de forma que novos dispositivos sejam implantados antes dos dispositivos atuais sairem de conformidade.

A equipe da Área de Trabalho Gerenciada da Microsoft sabe que os ciclos de compra são longos e planejados em torno de orçamentos de execução longa. Para garantir que você esteja sempre ciente do estado da população de dispositivos, fornecemos um [site](https://aka.ms/mmdportal) que lista todos os dispositivos sob gerenciamento, sua idade e um status indicando sua conformidade. O site ajuda você a sempre ter as informações mais recentes sobre a idade do dispositivo e pode usar o relatório em qualquer ciclo de planejamento de compras. 







