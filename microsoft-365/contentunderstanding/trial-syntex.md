---
title: Executar uma avaliação do Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Saiba como planejar e executar um programa piloto de avaliação para SharePoint Syntex em sua organização.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327071"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Executar uma avaliação do Microsoft SharePoint Syntex

Este artigo descreve como configurar e executar um programa piloto de avaliação para implantar SharePoint Syntex em sua organização. Ele também recomenda práticas recomendadas para a avaliação.

## <a name="sign-up-for-a-trial"></a>Inscrever-se para uma avaliação

A avaliação de SharePoint Syntex dá acesso a 300 usuários por 30 dias.

> [!NOTE]
> Até 300 usuários são incluídos na avaliação para garantir a adição automática de 1 milhão de créditos do Construtor de AI. Você não precisa incluir 300 usuários para que uma avaliação seja bem-sucedida.

Você pode obter a versão de avaliação de uma das seguintes fontes:

- A [SharePoint Syntex do produto](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- O [Centro de administração do Microsoft 365](https://admin.microsoft.com)
    1.  Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com).
    2.  Vá para **Serviços de Compra de**  >  **Cobrança.**
    3.  Role para baixo até a seção **Complementos**.
    4.  No SharePoint Syntex, selecione **Detalhes**.
    5.  Selecione **Obter avaliação gratuita**.
    6.  Para confirmar a avaliação, siga as etapas restantes do assistente.

Você deve ser um administrador Microsoft 365 global ou administrador de cobrança para ativar uma avaliação.

### <a name="who-should-be-involved-in-a-trial"></a>Who deve estar envolvido em uma avaliação

|Função  |Atividade  |
|---------|---------|
|Microsoft 365 administrador global ou administrador de cobrança    |     Ativar a avaliação e atribuir licenças    |
|Microsoft 365 administrador global ou SharePoint administrador     |   Configurar SharePoint Syntex e criar centros de conteúdo      |
|Usuários de negócios     |    Model building and testing     |

### <a name="before-you-activate-a-trial"></a>Antes de ativar uma avaliação

Para planejar com êxito uma SharePoint Syntex, considere os seguintes fatores:

- O teste mais significativo é concluído em cenários e dados do "mundo real".
- Você só pode ativar uma avaliação SharePoint Syntex uma vez por locatário.

Um locatário de teste ou demonstração pode ser usado como uma "corrida a seco" para passar pelas etapas de ativação e controles administrativos. Mas provavelmente é melhor avaliar a criação de modelos em um locatário de produção.

Para maximizar o valor de uma avaliação em um locatário de produção, o planejamento e o envolvimento comercial são essenciais. Você deve envolver uma ou mais áreas de negócios para identificar de três a seis casos de uso que podem ser abordados por SharePoint Syntex. Esses casos de uso devem:

- Inclua cenários que podem ser resolvidos pelo processamento de formulários ou pelo modelo de compreensão de documentos.
- Tenha uma compreensão clara da finalidade de todos os metadados extraídos; por exemplo, exibir formatação ou automação usando Power Automate. Embora SharePoint Syntex se concentre em classificar documentos e extrair metadados, o valor a ser quantificado é o que esses metadados habilitam.
- Basear-se em um conjunto definido de dados; por exemplo, sites SharePoint ou bibliotecas específicas. Um equívoco comum da SharePoint Syntex é que os modelos de finalidade geral podem ser aplicados em todo o conteúdo da organização. Uma visão mais precisa é que os modelos são construídos para ajudar a resolver problemas comerciais específicos em locais direcionados.

Todos esses casos de uso podem não ser um bom ajuste para SharePoint Syntex. O objetivo de uma avaliação de qualidade não é provar que SharePoint Syntex se ajustará a todos os cenários. Em vez disso, a avaliação deve ajudá-lo a entender melhor o valor do produto.

Para cada um dos casos de uso planejados, identifique os usuários que são especialistas em assunto no conteúdo ou processo relacionado. A criação de SharePoint Syntex é voltada para especialistas de domínio no conteúdo, em vez de profissionais de TI ou recursos de desenvolvedor.

## <a name="activate-a-trial"></a>Ativar uma avaliação

Ao iniciar uma avaliação, você precisa:

- Atribua licenças aos usuários relevantes.
- Execute [a instalação adicional de SharePoint Syntex](set-up-content-understanding.md).
    - Talvez você queira criar [centros de conteúdo adicionais.](create-a-content-center.md)

Depois que a avaliação for ativada, você poderá criar modelos e processar arquivos. Consulte [diretrizes para criação de modelo](create-a-content-center.md).

## <a name="during-a-trial"></a>Durante uma avaliação

Os períodos de avaliação são limitados, portanto, é melhor se concentrar inicialmente em se os SharePoint Syntex podem classificar documentos e extrair metadados para os casos de uso definidos. Após o período de avaliação, você pode avaliar como os metadados podem ser explorados.

## <a name="after-a-trial"></a>Após uma avaliação

Com base no resultado da avaliação, você pode decidir se deve prosseguir para o uso de produção de SharePoint Syntex.

### <a name="proceed-to-production-use"></a>Prossiga para o uso de produção

Para garantir a continuidade do serviço, você precisa comprar o número necessário de licenças e atribuir essas licenças aos usuários. Os usuários de avaliação que não têm uma licença completa no final do período de avaliação não poderão utilizar totalmente SharePoint Syntex.

Talvez seja preciso estimar o uso projetado do processamento de formulários e planejar a quantidade esperada de créditos do Construtor de AI. Para saber mais, confira Estimar a capacidade do Construtor de [AI que é o correto para você.](https://powerapps.microsoft.com/ai-builder-calculator/)

### <a name="dont-proceed-to-production-use"></a>Não prossiga para uso de produção

Se você não comprar licenças após a avaliação:

- Você não poderá criar novos modelos.
- Bibliotecas que estavam executando modelos não classificarão automaticamente arquivos ou modelos de extração.
- Quaisquer arquivos classificados anteriormente ou metadados extraídos não serão afetados. 
- Os centros de conteúdo e os modelos de compreensão de documentos não serão excluídos automaticamente. Elas permanecerão disponíveis para uso se você decidir comprar licenças no futuro.
- Os modelos de processamento de formulários serão armazenados na instância CDS (Common Data Services) do ambiente padrão da Plataforma Power. Eles podem ser usados com licenciamento futuro para SharePoint Syntex ou com recursos de Construtor de AI na Plataforma Power.

## <a name="see-also"></a>Confira também

[Adoção SharePoint Syntex Microsoft: Começar](adoption-getstarted.md)
