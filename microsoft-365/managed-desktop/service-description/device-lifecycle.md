---
title: Área de Trabalho Gerenciada da Microsoft ciclo de vida do produto
description: Este artigo lista as especificações de dispositivo usadas Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245307"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a>Área de Trabalho Gerenciada da Microsoft ciclo de vida do produto

Área de Trabalho Gerenciada da Microsoft os usuários garantem que sempre usem dispositivos que ofereçam os melhores recursos de desempenho, confiabilidade, design e segurança (como suporte para recursos como o Windows Hello). Para fazer isso, Área de Trabalho Gerenciada da Microsoft mantém um breve catálogo de dispositivos aprovados continuamente atualizados. Você pode exibir dispositivos aprovados filtrando para Área de Trabalho Gerenciada da Microsoft no site de Windows 10 Pro [de negócios](https://www.microsoft.com/windowsforbusiness/view-all-devices) da Loja.
 
Este artigo detalha o ciclo de vida dos dispositivos à medida que eles são adicionados e removidos do catálogo aprovado. 

> [!NOTE]
> Neste tópico, faremos uma distinção entre um "dispositivo" e um "produto". Por "dispositivo", queremos dizer um computador específico e individual. Por exemplo, "Número de série 1234", "Laptop de Bill", "VM XYZ compartilhada" referem-se a dispositivos específicos. Um "produto", no entanto, refere-se a uma coleção ou família de dispositivos. Por exemplo, "Laptop Fabrikam", "Laptop Adatum ZX450", etc. Isso é importante porque os produtos são adicionados à nossa lista aprovada ou catálogo, e os dispositivos são o que são inscritos no Área de Trabalho Gerenciada da Microsoft.

## <a name="product-lifecycle"></a>Ciclo de vida do produto

 Geralmente, os produtos se movem por essas fases de ciclo de vida:

- [Versão e avaliação do produto](#product-release-and-evaluation)
- [Período de disponibilidade principal do produto](#product-primary-availability-period)
- [Período de carência do produto](#product-grace-period)
- [Ressução do produto](#product-retirement)


Esta ilustração mostra toda a sequência:

![linha do tempo do ciclo de vida: a partir da disponibilidade geral do produto, a "disponibilidade primária" dura dois anos. Durante esse tempo, a janela de certificação termina e, em algum momento, o dispositivo está onboarded. No final da disponibilidade primária, o produto é arquivado e o "período de carência" de três anos é iniciado. A partir da integração do dispositivo, ele tem um período de 3 anos de uso até ser removido do gerenciamento. No final do período de carência, removemos o produto do catálogo.](../../media/non-dark1-edits.PNG)

Os produtos permanecem no catálogo por até <em></em> 24 meses, mas os dispositivos permanecem sob gerenciamento por três anos com base em suas datas de registro individuais. Efetivamente, cada produto tem três datas importantes, mas cada dispositivo tem apenas uma. Para produtos, todas essas três datas são calculadas com base na data de aprovação <em>e,</em>portanto, publicamos essas datas após aprovação para que você possa sempre olhar para frente e planejar adequadamente todo o ciclo de vida do produto.

Esta tabela mostra datas de exemplo para um produto teórico:


|Produto  |Data aprovada  |Fim da disponibilidade primária  |Fim da qualificação  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 1/1/2017 | 6/1/2019 | 6/1/2022 |
|Adatum Laptop   | 1/1/2018 | 6/1/2020 | 6/1/2023  |

Esta tabela mostra datas de exemplo para dispositivos *teóricos*:


|ID do dispositivo  |Data de inscrição  |Data de aposentadoria  |
|---------|---------|---------|
|Laptop #123412     |  2/3/2018       |  2/3/2021       |
|Área de trabalho #321513     | 6/2/2018        |  6/2/2021       |


## <a name="product-release-and-evaluation"></a>Versão e avaliação do produto

O ciclo de vida do produto começa quando um fabricante publicamente libera o produto:

![linha do tempo de ciclo de vida mostrando o período de versão e avaliação](../../media/non-dark3-edits.PNG)

Durante esse estágio, a equipe Área de Trabalho Gerenciada da Microsoft engenharia faz sua avaliação e certificação de um produto. A equipe avalia coisas como confiabilidade e desempenho com Windows, conformidade com uma linha de base de hardware, sentimento de mercado e preparação de inventário e canal, entre outras coisas. Esse processo normalmente leva aproximadamente seis semanas.
  
Área de Trabalho Gerenciada da Microsoft avaliará apenas dispositivos para certificação nos primeiros seis meses de disponibilidade. Essa política garante que estamos sempre concentrando nossos esforços na última geração de hardware.
 
No final dessa fase, Área de Trabalho Gerenciada da Microsoft o produto à lista aprovada [,](device-list.md)liberando efetivamente o produto para registro de clientes. Independentemente da data em que  um dispositivo é certificado, sua data aprovada é data de disponibilidade geral do produto. 


## <a name="product-primary-availability-period"></a>Período de disponibilidade principal do produto

Esse período é o núcleo da disponibilidade do produto:

![linha do tempo do ciclo de vida mostrando a disponibilidade principal](../../media/non-dark4-edits.PNG)

Qualquer dispositivo inscrito durante esse período recebe os três anos completos de suporte do Área de Trabalho Gerenciada da Microsoft (conforme mostrado pela linha do tempo azul). Esse período dura até que uma data final seja definida como 24 meses a partir da data de disponibilidade geral.

Você pode pensar nesse período como efetivamente "abrir registro", portanto, para maximizar o valor de Área de Trabalho Gerenciada da Microsoft, você deve direcionar seus modelos de aquisição e produtos selecionados para se enquadrar nesse período. Como um pequeno exemplo, você deve evitar se fixar em um período de distribuição de dois anos usando um produto que está em seu último [](#product-grace-period) mês de disponibilidade primária – a maioria desses dispositivos não receberá os três anos completos de gerenciamento de Área de Trabalho Gerenciada da Microsoft (consulte período de carência para obter mais informações).  

## <a name="product-grace-period"></a>Período de carência do produto

O período de carência do produto é um período de três anos após a disponibilidade primária. Essa fase permite que você inscreva dispositivos que são de uma família de produtos com suporte, mas ainda mantém firmes as promessas de Área de Trabalho Gerenciada da Microsoft em relação ao desempenho moderno de hardware e dispositivo. Essa fase é ideal para os clientes que tomaram decisões de compra antes de saber sobre Área de Trabalho Gerenciada da Microsoft. 

Se você comprou recentemente dispositivos aprovados antes de se inscrever no Área de Trabalho Gerenciada da Microsoft, ainda pode inscreve-los, mas não receberá um gerenciamento completo de três anos. Em vez disso, eles não cumprirão a data de aposentadoria, independentemente de quando foram inscritos. Nos bastidores, Área de Trabalho Gerenciada da Microsoft tratará esses dispositivos como se eles estavam inscritos no último dia de disponibilidade primária. Nesta ilustração, você pode ver esse cenário, notando que o dispositivo azul e verde termina no mesmo dia, apesar da diferença de um ano no registro:


![linha do tempo de ciclo de vida mostrando o período de carência](../../media/non-dark2-edits.PNG)

O exemplo do Laptop Fabrikam da tabela anterior ilustra essa situação: 

|Produto  |Data aprovada  |Fim da disponibilidade primária  |Fim da qualificação  |
|---------|---------|---------|---------|
|Fabrikam Laptop    | 6/1/2017 | 6/1/2019 | 6/1/2022 |

Como cliente, você pode registrar laptops Fabrikam até 1/6/2022 – no entanto, todos eles serão tratados como se você os registrava em 01/06/2019. Se você registrar um Laptop Fabrikam em 1/6/2021, você só terá um ano de gerenciamento. Essa política permite extrair ciclos de vida parciais de produtos que anteriormente eram suportados, em vez de ter que adquirir novos dispositivos prematuramente. 

Por fim, durante essa fase, o dispositivo é removido da lista [de](device-list.md) dispositivos e movido para a lista [de dispositivos arquivados.](archived-device-list.md)


## <a name="product-retirement"></a>Ressução do produto

A aposentadoria do produto é a fase final do ciclo de vida. Nesta fase, nenhum novo dispositivo desse tipo de produto pode ser inscrito no Área de Trabalho Gerenciada da Microsoft e, por definição, todos os dispositivos existentes agora estão fora do período permitido de três anos. Durante esse tempo, Área de Trabalho Gerenciada da Microsoft removerá totalmente o dispositivo da lista pública. Também é durante essa fase que, se você ainda não tiver adquirido substituições, você começará a ver serviços reduzidos à medida que o Área de Trabalho Gerenciada da Microsoft começa a se rebaixar nos dispositivos que estão fora de conformidade. 

## <a name="devices-that-are-out-of-compliance"></a>Dispositivos que estão fora de conformidade

Um dispositivo está fora de conformidade quando a janela permitida para o Área de Trabalho Gerenciada da Microsoft decorrido. Essa situação ocorre quando o dispositivo atingiu três anos de gerenciamento ou quando esse tipo de produto é removido do catálogo de dispositivos, o que ocorrer primeiro. Você sempre deve direcionar seus ciclos de compra para que novos dispositivos sejam implantados antes que os dispositivos atuais não sejam compatíveis.

A Área de Trabalho Gerenciada da Microsoft sabe que os ciclos de compras são longos e planejados em torno de orçamentos de longa duração. Para garantir que você esteja sempre ciente do estado da sua população de dispositivos, fornecemos um [site](https://aka.ms/mmdportal) que lista todos os dispositivos sob gerenciamento, sua idade e um status que indica sua conformidade. O site ajuda você a ter sempre as informações mais recentes sobre a idade do dispositivo e pode usar o relatório em qualquer ciclo de planejamento de compras. 







