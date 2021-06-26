---
title: Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Saiba como usar o Microsoft Teams para criar seu canal de gerenciamento de contratos usando uma solução Microsoft 365 contrato.
ms.openlocfilehash: 7c7d3ef30d376e14e033243413637cdb51ba548a
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148969"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Etapa 2. Use Microsoft Teams para criar seu canal de gerenciamento de contratos

Quando sua organização configura uma solução de gerenciamento de contratos, você precisa de um local central no qual os participantes possam revisar e gerenciar contratos. Para isso, você pode [usar](/microsoftteams/) Microsoft Teams para configurar um canal Teams e usar os recursos em Teams para:

- **Crie um local para que as partes interessadas vejam facilmente todos os contratos que exigem ação.** Por exemplo, Teams você pode criar uma guia **Contratos** no canal Gerenciamento de Contratos no qual os membros podem ver uma exibição de azulejo útil de todos os contratos que precisam de aprovação. Você também pode configurar o modo de exibição para que cada "cartão" lista os dados importantes com os quais você se importa (como *Cliente,* Prestador de Serviços *e* *Valor da Taxa).*

     ![Guia Contratos.](../media/content-understanding/tile-view.png)

- **Ter um local para os membros interagirem uns com os outros e ver eventos importantes.** Por exemplo, Teams, a guia **Postagens** pode ser usada para ter conversas, obter atualizações e ver ações (como um membro rejeitando um contrato). Quando algo aconteceu (como um novo contrato enviado para aprovação), a guia **Postagens** pode ser usada não apenas para anuiá-lo, mas também para manter um registro dele. E se os membros assinarem as notificações, eles serão notificados sempre que houver uma atualização.

     ![Guia Postagens.](../media/content-understanding/posts.png)

- **Tenha um local para os membros ver contratos aprovados para saber quando eles podem ser enviados para pagamento.** No SharePoint, você precisará criar uma  lista Para Pagamento e incluir colunas para **Client,**  **Contractor** e **Fee amount,** selecionando Uma única linha de texto como o tipo de coluna. Você precisará adicionar a lista **Para Pagamento** como uma guia Teams no canal Gerenciamento de Contratos, semelhante ao que você fará para a guia [ **Contratos.**](solution-manage-contracts-step2.md#attach-your-sharepoint-document-library-to-the-contracts-tab) A **guia Para Pagamento lista** todos os contratos que precisarão ser enviados para pagamento. Você pode estender facilmente essa solução para gravar essas informações diretamente em um aplicativo financeiro de terceiros (por exemplo, Dynamics CRM). 


## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Anexar sua SharePoint de documentos à guia Contratos

Depois de criar uma guia **Contratos** em seu canal de Gerenciamento de Contratos, você precisará anexar sua SharePoint [de documentos a ela.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) A SharePoint de documentos que você deseja anexar é a que você aplicou seu SharePoint Syntex de conhecimento de documentos na seção anterior.

Depois de anexar a SharePoint de documentos, você poderá exibir quaisquer contratos confidenciais por meio de um modo de exibição de lista padrão.

   ![List view of SharePoint library.](../media/content-understanding/list-view.png)

## <a name="customize-your-contracts-tab-tile-view"></a>Personalizar o seu exibição de tile de tabulação Contratos

> [!NOTE]
> Esta seção faz referência a exemplos de código contidos no arquivo [ContractTileFormatting.json](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) incluído no repositório de Ativos da Solução de Gerenciamento de [Contratos.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)

Enquanto Teams permite que você veja seus contratos em uma exibição de azulejo, talvez você queira personalizá-los para exibir os dados de contrato que você deseja tornar visíveis no cartão de contrato. Por exemplo, para a guia **Contratos,** é importante que os membros vejam o cliente, o contratado e o valor da taxa no cartão de contrato. Todos esses campos foram extraídos de cada contrato por meio do seu modelo SharePoint Syntex que foi aplicado à biblioteca de documentos. Você também deseja poder alterar a barra de header de azulejo para cores diferentes para cada status para que os membros possam ver facilmente onde o contrato está no processo de aprovação. Por exemplo, todos os contratos aprovados terão uma barra de header azul.

   ![Exibição de SharePoint de azulejos.](../media/content-understanding/tile.png)

A exibição de azulejo personalizada que você usa exige que você faça alterações no arquivo JSON usado para formatar o exibição de azulejo atual. Você pode fazer referência ao arquivo JSON usado para criar o exibição de cartão olhando para o arquivo [ContractTileFormatting.json.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) Nas seções a seguir, você verá seções específicas do código para recursos que estão nos cartões de contrato.

Se você quiser ver ou fazer alterações no código JSON para seu exibição no canal Teams, no canal Teams, selecione o menu suspenso exibir e selecione **Formatar** o exibição atual .

   ![Captura de tela do formato json no Teams canal.](../media/content-understanding/jason-format.png)

## <a name="card-size-and-shape"></a>Tamanho e forma do cartão

No arquivo [ContractTileFormatting.json,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) consulte a seção a seguir para ver o código de como o tamanho e a forma do cartão são formatados.

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```

## <a name="contract-status"></a>Status do contrato

O código a seguir permite definir o status de cada cartão de título. Observe que cada valor de status (*Novo*, *Em revisão,* Aprovado e *Rejeitado*) exibirá um código de cor diferente para cada um. No arquivo [ContractTileFormatting.json,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) veja a seção que define o status.

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```

## <a name="extracted-fields"></a>Campos extraídos

Cada cartão de contrato exibirá três campos que foram extraídos para cada contrato (*Client,* *Contractor* e *Fee Amount*). Além disso, você também deseja exibir a hora/data em que o arquivo foi classificado pelo modelo SharePoint Syntex usado para identificá-lo.

No arquivo [ContractTileFormatting.json,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) as seções a seguir definem cada uma delas.

### <a name="client"></a>Cliente

Esta seção define como "Cliente" será exibido no cartão e usa o valor do contrato específico.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a>Prestador de serviços

Esta seção define como o "Contratado" será exibido no cartão e usa o valor do contrato específico.

```JSON
                        {
                            "elmType": "div",
                            "txtContent": "Contractor",
                            "style": {
                              "color": "#767676",
                              "font-size": "12px",
                              "margin-bottom": "2px"
                            }
                          },
                          {
                            "elmType": "div",
                            "style": {
                              "margin-bottom": "12px",
                              "font-size": "14px"
                            },
                            "txtContent": "[$Contractor]"
                          },
```

### <a name="fee-amount"></a>Valor da taxa

Esta seção define como o "Valor da Taxa" será exibido no cartão e usa o valor do contrato específico.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```

### <a name="classification-date"></a>Data da classificação

Esta seção define como "Classificação" será exibida no cartão e usa o valor do contrato específico.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a>Próxima etapa

[Etapa 3. Use Power Automate para criar seu fluxo para processar seus contratos](solution-manage-contracts-step3.md)
