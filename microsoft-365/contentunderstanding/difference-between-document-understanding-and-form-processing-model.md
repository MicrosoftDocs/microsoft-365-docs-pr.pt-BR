---
title: Diferença entre modelo de compreensão de documentos e modelo de processamento de formulário
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Descreve as principais diferenças entre o modelo de compreensão de documentos e o modelo de processamento de formulário
ms.openlocfilehash: 555dfa7d76335a3b943e860e5f41ed64c9d3e874
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596975"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Diferença entre modelo de compreensão de documentos e modelo de processamento de formulário 


A compreensão do conteúdo no Microsoft SharePoint Syntex permite que você identifique e classifique os documentos carregados nas bibliotecas de documentos do SharePoint e extraia informações relevantes de cada arquivo.  Por exemplo, conforme os arquivos são carregados em uma biblioteca de documentos do SharePoint, todos os arquivos identificados como *Pedidos de Compra* são classificados como tal e, em seguida, exibidos em um modo de exibição de biblioteca de documentos personalizado. Além disso, você pode inserir informações específicas de cada arquivo (por exemplo, *Número do PC* e *Total*) e exibi-las como uma coluna no modo de exibição da biblioteca de documentos. 

A compreensão de conteúdo permite que você crie *modelos* para identificar e extrair as informações necessárias. Os modelos têm valor para ajudar a resolver problemas de negócios para pesquisa, processos de negócios, conformidade e muitos outros.

Há dois tipos de modelo que você pode usar:

- [Modelos de compreensão de documentos](document-understanding-overview.md)
- [Modelos de processamento de formulário](form-processing-overview.md)

Embora os dois modelos sejam usados para a mesma finalidade, as principais diferenças listadas abaixo afetam quais podem ser usadas.

> [!NOTE]
> Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para saber mais sobre os exemplos de cenários de processamento de formulário e compreensão de documentos.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Conteúdo estruturado versus conteúdo não estruturado e semiestruturado

Utilize modelos de compreensão de documento para identificar e extrair dados de documentos não estruturados, como cartas ou contratos, onde as entidades de texto que você deseja extrair estão em frases ou regiões específicas do documento. Por exemplo, um documento não estruturado pode ser uma carta de renovação de contrato que pode ser escrita de maneiras diferentes. No entanto, as informações existem de forma consistente no corpo de cada documento de renovação de contrato, como a cadeia de texto *Data de início do serviço de* seguida de uma data real.

Use modelos de processamento de formulário para identificar arquivos e extrair dados de documentos estruturados e semiestruturados, como formulários ou faturas. Os modelos de processamento de formulário são treinados para entender o layout do seu formulário a partir de documentos de exemplo e aprender a procurar os dados que você precisa extrair de locais semelhantes. Os formulários geralmente têm um layout mais estruturado, onde as entidades estão no mesmo local (por exemplo, um número de previdência social em um formulário de imposto).

> [!NOTE]
> Você deve ter acesso a um site do centro de conteúdo para criar um modelo de compreensão de documentos ou aplicar um a uma biblioteca de documentos do SharePoint. 


## <a name="where-models-are-created"></a>Onde os modelos são criados

Os modelos de compreensão de documentos são criados e gerenciados em um site do centro de conteúdo do SharePoint. 

> [!NOTE]
> Para obter mais informações sobre documentos de entrada, confira [Requisitos e limitações do modelo de processamento de formulário](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Os modelos de processamento de formulário são criados no PowerApps [Construtor AI](https://docs.microsoft.com/ai-builder/overview), mas a criação começa diretamente a partir de uma biblioteca de documentos do Microsoft Office SharePoint Online. Uma biblioteca de documentos deve ter a criação do modelo de processamento de formulário habilitada antes que um usuário possa criar um modelo de processamento de formulário para ela. Os administradores podem ativar a criação do modelo de processamento de formulário nas configurações de administração de compreensão de conteúdo. Os modelos de processamento de formulário usam fluxos do PowerAutomate para processar arquivos quando eles são carregados na biblioteca de documentos.

Ao criar um modelo de compreensão de documentos, você cria um novo [tipo de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que é salvo na galeria Tipos de Conteúdo do SharePoint. Ou você pode usar modelos de conteúdo existentes para definir seu modelo, se necessário.

Os modelos de processamento de formulário também criam novos [tipos de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) e também são armazenados na galeria Tipos de Conteúdo do SharePoint.

## <a name="where-they-can-be-applied"></a>Onde eles podem ser aplicados

Você pode aplicar os modelos de compreensão de documentos nas bibliotecas de documentos do SharePoint as quais você tem acesso. Use o centro de conteúdo para criar um modelo de compreensão de documentos e aplique-o em diferentes bibliotecas de documentos. O centro de conteúdo oferece um controle mais central de como os modelos de compreensão de documentos são utilizados e onde são aplicados. Observe que esta informações também devem ser acumuladas em um centro de conteúdo.

No momento, os modelos de processamento de formulário só podem ser aplicados à biblioteca de documentos do SharePoint a partir da qual eles foram criados. Isso permite que usuários licenciados com acesso ao site criem um modelo de processamento de formulário. Observe que um administrador precisa habilitar o processamento de formulários em uma biblioteca de documentos do Microsoft Office SharePoint Online para que esteja disponível para usuários licenciados.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Comparação de processamento de formulários e compreensão de documentos

Use a tabela a seguir para entender quando usar o processamento de formulários e quando usar a compreensão de documentos:

| Recurso | Processamento de formulários | Compreensão de documentos |
| ------- | ------- | ------- |
| Tipo de modelo - quando usar cada um | Usado para formatos de arquivo semiestruturados - por exemplo, documentos do Office onde há diferenças no layout, mas ainda assim informações semelhantes a serem extraídas. | Usado para formatos de arquivo não estruturados, por exemplo PDFs para conteúdo de formulários, como faturas ou pedidos de compra, onde o layout e a formatação são semelhantes. |
| Criação de modelo | Modelo criado no construtor de AI com acesso direto da biblioteca de documentos do Microsoft Office SharePoint Online.| Modelo criado em interface nativa embutida no Centro de Conteúdo do Microsoft Office SharePoint Online.|
| Tipo de classificação| Classificador configurável onde o ensino por máquina é usado para dar pistas ao sistema sobre quais dados extrair.| Classificador treinável com extratores opcionais usando ensino de máquina para atribuir a localização do documento em quais dados extrair.|
| Localizações | Restrito a uma única Biblioteca de Documentos, a menos que você use o Power Platform para recuperar do CDS.| Pode ser aplicado a várias bibliotecas.|
| Tipos de arquivo compatíveis| Treine em PDF, JPG, formato PNG, total de 50 MB e 500 páginas.| Treine em 5-10 arquivos PDF, Office ou e-mail, incluindo exemplos negativos.<br>Os arquivos do Office são truncados em 64k caracteres. Os arquivos digitalizados por OCR são limitados a 20 páginas.|
| Integrar com metadados gerenciados | Não | Sim, por meio da configuração nas colunas da Biblioteca de Documentos antes do modelo de treinamento.|
| Integração de recursos de conformidade quando a Proteção de Informações da Microsoft está habilitada | Defina rótulos de retenção.<br>Definir rótulos de sensibilidade está chegando. | Defina rótulos de retenção.<br>Definir rótulos de sensibilidade está chegando. |
| Regiões com suporte| O processamento de formulários depende do Power Platform. Para obter informações sobre a disponibilidade global para Power Platform e AI Builder, consulte [Disponibilidade da Power Platform ](https://dynamics.microsoft.com/geographic-availability/). | Disponível em todas as regiões.|
| Custo de transação | Usa créditos do AI Builder.<br>Os créditos podem ser adquiridos em lotes de 1M.<br>1M de créditos são incluídos quando 300+ licenças do Microsoft Office SharePoint Online Syntex são adquiridas.<br>1M de créditos permitirá o processamento de 2.000 páginas de arquivo.| N/A |
| Capacidade | Provisionado no ambiente de serviço de dados comum padrão.| Sem restrições de capacidade.|
| Idiomas compatíveis| English <br>Chegando no final de 2021: Espanhol, Alemão, Francês, Italiano| Os modelos funcionam em todas as línguas do alfabeto latino. Além do Inglês: Alemão, Sueco, Francês, Espanhol, Italiano e Português.|

## <a name="see-also"></a>Confira também
[Treinamento: melhore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Visão geral da compreensão de documentos](document-understanding-overview.md)

[Visão geral do processamento de formulário](form-processing-overview.md)

[Introdução ao SharePoint Syntex](index.md)
