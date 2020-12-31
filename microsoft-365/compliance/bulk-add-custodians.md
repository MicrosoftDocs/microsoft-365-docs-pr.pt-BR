---
title: Importar os responsáveis para uma ocorrência de descoberta eletrônica avançada
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
description: Use o dto Tool de importação para adicionar rapidamente vários responsáveis e suas fontes de dados associadas a um caso na descoberta eletrônica avançada.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740298"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importar os responsáveis para uma ocorrência de descoberta eletrônica avançada

Para casos de descoberta eletrônica avançada que envolvem muitos responsáveis, você pode importar vários responsáveis de uma só vez usando um arquivo CSV que contenha as informações necessárias para adicioná-los a um caso.

## <a name="import-custodians"></a>Importar os responsáveis

1. Abra o caso de descoberta eletrônica avançada e selecione a guia **fontes de dados** .

2. Clique em **adicionar os**  >  **responsáveis de importação** de fonte de dados.

3. Na página **importar** o submenu responsáveis, clique em **baixar um modelo em branco** para baixar um arquivo CSV de modelo de responsáveis.

   ![Baixar um modelo CSV da página de submenu importar responsáveis](../media/ImportCustodians1.png)

4. Adicione as informações do custodial ao arquivo CSV e salve-o em seu computador local. Consulte a seção [arquivo CSV de responsáveis](#custodian-csv-file) para obter informações sobre as propriedades necessárias no arquivo CSV.

5. Depois de preparar o arquivo CSV com as informações dos responsáveis, volte para a guia **fontes de dados** e clique em **Adicionar fonte de dados**  >  **importar os responsáveis** novamente.

6. Na página do submenu **importar responsáveis** , clique em **procurar** e carregue o arquivo CSV que contém as informações dos responsáveis.

   Após o carregamento do arquivo CSV, um trabalho chamado **BulkAddCustodian** é criado e exibido na guia **trabalhos** . O trabalho valida os responsáveis e suas fontes de dados associadas e os adiciona à página de **fontes de dados** do caso.

## <a name="custodian-csv-file"></a>Arquivo CSV de responsáveis

Depois de baixar o modelo de responsáveis por CSV, você pode adicionar os responsáveis e a fonte de dados em cada linha. Certifique-se de não alterar os nomes de coluna na linha de cabeçalho. Use as colunas tipo de carga de trabalho e local de carga de trabalho para associar outras fontes de dados a um funcionário.

| Nome da coluna|Descrição|
|:------- |:------------------------------------------------------------|
|**ContactEmail**     |O endereço de email UPN do responsáveis. Por exemplo, sarad@contoso.onmicrosoft.com.           |
|**Exchange habilitado** | Valor verdadeiro/falso para incluir ou não a caixa de correio do responsáveis.      |
|**OneDrive habilitado** | Valor verdadeiro/falso para incluir ou não a conta do OneDrive for Business do responsáveis. |
|**É onHold**        | Valor verdadeiro/falso para indicar se deve colocar as fontes de dados dos responsáveis em espera.       |
|**Tipo Workload1**         |Valor da cadeia de caracteres que indica o tipo de fonte de dados a ser associado ao funcionário. Os valores possíveis incluem: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Local Workload1**     | Dependendo do seu tipo de carga de trabalho, esse seria o local da fonte de dados. Por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint. |
|||

Veja um exemplo de um arquivo CSV com informações sobre os responsáveis:<br/><br/>

|ContactEmail      | Exchange habilitado | OneDrive habilitado | É onHold | Tipo Workload1 | Local Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validação de responsáveis e fonte de dados

Depois que você carregar o arquivo CSV de responsáveis, a descoberta eletrônica avançada fará o seguinte:

1. Valida os responsáveis e suas fontes de dados.

2. Indexa todas as fontes de dados de cada responsáveis e as coloca em espera (se a propriedade **is onHold** no arquivo CSV estiver definida como true).

### <a name="custodian-validation"></a>Validação de responsáveis

No momento, só há suporte para importar os responsáveis que estão incluídos no Azure Active Directory (Azure AD) da sua organização.

A ferramenta de importação de responsáveis localiza e valida os responsáveis usando o valor UPN na coluna **contactEmail** do arquivo CSV. Os responsáveis que são validados são automaticamente adicionados ao caso e listados na guia **fontes de dados** do caso. Se não for possível validar os responsáveis, eles serão listados no log de erros para o trabalho do BulkAddCustodian listado na guia **trabalhos** no caso. Os responsáveis não validados não são adicionados ao caso ou listados na guia **fontes de dados** .

### <a name="data-source-validation"></a>Validação da fonte de dados

Após os responsáveis serem validados e adicionados ao caso, cada caixa de correio principal e conta do OneDrive associada a um objectserá adicionado.

No entanto, se qualquer uma das outras fontes de dados (como sites do SharePoint, Microsoft Teams, Microsoft 365 groups ou Yammer groups) associada a um solicitante não puder ser encontrada, nenhuma delas será atribuída aos responsáveis e o valor **não validado** será exibido na coluna **status** ao lado dos responsáveis na guia **fontes de dados** .

Para adicionar fontes de dados validadas para um responsáveis:

1. Na guia **fontes de dados** , selecione um responsáveis que contenha fontes de dados que não são validadas.

2. Na página do submenu de responsáveis, role até a seção **locais do custodial** para ver as fontes de dados validadas e não validadas que estão associadas aos responsáveis.

3. Clique em **Editar** na parte superior da página de menu suspenso para remover fontes de dados inválidas ou adicionar novas.

4. Após a remoção de fontes de dados não validadas ou a adição de uma nova, o valor **ativo** será exibido na coluna **status** para os responsáveis na guia **fontes de dados** . Para adicionar fontes que anteriormente apareciam como inválidas, siga as etapas de correção abaixo para adicioná-las manualmente a um solicitante.

### <a name="remediating-invalid-data-sources"></a>Correção de fontes de dados inválidas

Para adicionar e associar manualmente uma fonte de dados que era previamente inválida:

1. Na guia **fontes de dados** , selecione um funcionário para adicionar e associar manualmente uma fonte de dados que antes era inválida.

2. Clique em **Editar** na parte superior da página de menu para associar caixas de correio, sites, equipes ou grupos do Yammer aos responsáveis. Para isso, clique em **Editar** ao lado do tipo de local de dados apropriado.

3. Clique em **Avançar** para exibir a página **configurações de retenção** e definir a configuração de retenção para as fontes de dados que você adicionou.

4. Clique em **Avançar** para exibir a página **revisar responsáveis** e, em seguida, clique em **Enviar** para salvar as alterações.
