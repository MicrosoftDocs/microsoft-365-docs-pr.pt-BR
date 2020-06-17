---
title: Adicionar os responsáveis em massa a um caso de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Use a ferramenta de adição em massa para adicionar rapidamente vários responsáveis e suas fontes de dados associadas a um caso na descoberta eletrônica avançada.
ms.openlocfilehash: 921d4a1616d97f2adde7e40baa5c73f607c849b6
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741636"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a>Adicionar os responsáveis em massa a um caso de descoberta eletrônica avançada

Para casos de descoberta eletrônica avançada que envolvem muitos responsáveis, você pode importar vários responsáveis de uma só vez por um arquivo CSV que contém todas as informações necessárias para adicioná-los a um caso.

## <a name="bulk-add-custodians"></a>Adicionar responsáveis em massa

1. Insira o caso e navegue até a guia **fontes** .

2. Clique em **importar responsáveis**

3. Na página do menu suspenso, clique em **baixar um modelo em branco** para baixar um arquivo de modelo CSV.

4. Adicione as informações do custodial ao arquivo CSV e salve-o no computador local. Consulte a próxima seção para obter informações sobre as propriedades no arquivo CSV.

5. Na guia **fontes** , clique em **importar os responsáveis** novamente. 
6. Na página de submenu, clique em **procurar** e carregar o arquivo CSV.

   Após o carregamento do arquivo CSV, um trabalho do BulkAddCustodian é criado e exibido na guia **trabalhos** . O trabalho valida os responsáveis e suas fontes de dados correspondentes e os adiciona à guia **responsáveis** na página de **fontes** do caso.

## <a name="custodian-csv-file"></a>Arquivo CSV de responsáveis

Depois de baixar o modelo CSV, você poderá adicionar os responsáveis e sua fonte de dados em cada linha. Certifique-se de não alterar os nomes de coluna na linha de cabeçalho.

| Nome da coluna|Descrição|
|:------- |:------------------------------------------------------------|
|**ContactEmail**     | Email UPN dos responsáveis. Exemplo: sarad@onmicrosoft.contoso.com           |
|**Exchange habilitado** | Valor TRUE/FALSE no qual adicionar a caixa de correio do responsáveis.      |
|**OneDrive habilitado** | Valor verdadeiro/falso no caso de adicionar a conta do OneDrive for Business dos responsáveis. |
|**É onHold**        | Valor verdadeiro/falso se deseja colocar os responsáveis em espera.       |
|**Tipo Workload1**         | Valor da cadeia de caracteres que indica o tipo de fonte de dados a ser associado ao funcionário. <br />Os valores possíveis incluem: <br />ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Local Workload1**     | Dependendo do seu tipo de carga de trabalho, esse seria o local de dados da carga de trabalho (por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint). |
|||

Veja um exemplo de um arquivo CSV com informações sobre os responsáveis:  

| ContactEmail      | Exchange habilitado | OneDrive habilitado | É onHold | Tipo Workload1 | Local Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validação de responsáveis e fonte de dados

Quando você carrega o arquivo CSV do Object, a descoberta eletrônica avançada realiza as seguintes ações:

1. Valida os responsáveis e suas fontes de dados. 

2. Indexa todas as fontes de dados de cada responsáveis e as coloca em espera (se a propriedade is onHold estiver definida como TRUE).

### <a name="custodian-validation"></a>Validação de responsáveis

No momento, só damos suporte à importação de responsáveis que estão no Azure Active Directory (AAD).

Validamos e localizaram os responsáveis usando o valor UPN na coluna **email de contato** no arquivo CSV. Os responsáveis que são validados são automaticamente adicionados ao caso e listados na guia **responsáveis** na página de **fontes** do caso. Se não for possível validar os responsáveis, eles serão listados no log de erros para o trabalho do BulkAddCustodian listado na guia **trabalhos** no caso. Os responsáveis não validados não são adicionados ao caso.

### <a name="data-source-validation"></a>Validação da fonte de dados

Após os responsáveis serem validados e adicionados ao caso, cada fonte de dados associada a um responsáveis será validada. Se qualquer fonte de dados para um Objectnão puder ser encontrada, o valor **não validado** será exibido na coluna **validada** na guia **responsáveis** por esses responsáveis.

### <a name="remediating-unvalidated-data-sources"></a>Solucionando fontes de dados não validadas

Para corrigir os responsáveis por fontes de dados não validadas: 

1. Na guia **responsáveis** , selecione um funcionário que não é validado.

2. Na página do submenu de responsáveis, role até a seção **fontes de dados** para exibir as fontes de dados associadas aos responsáveis. As fontes de dados validadas e não validadas são listadas.

3. Na seção **fontes de dados** , clique em **Editar**.

4. Na página **escolher locais de custodial** , remova uma fonte de dados não validada.

5. Na página **selecionar locais adicionais** , clique em **Atualizar** para adicionar outras fontes de dados para um responsáveis.
