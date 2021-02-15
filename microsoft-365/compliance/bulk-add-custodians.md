---
title: Importar custodiantes para uma ocorrência de Descoberta Avançada
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
description: Use a ferramenta de importação para adicionar rapidamente vários custodiantes e suas fontes de dados associadas a um caso na Descoberta Avançada.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740298"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importar custodiantes para uma ocorrência de Descoberta Avançada

Para casos de Descoberta Avançada que envolvem muitos custodiantes, você pode importar vários custodiantes de uma só vez usando um arquivo CSV que contém as informações necessárias para adicioná-los a uma ocorrência.

## <a name="import-custodians"></a>Importar custodiantes

1. Abra a ocorrência de Descoberta Avançada e selecione a **guia Fontes de** dados.

2. Clique **em Adicionar custodiantes de**  >  **importação de fonte de dados.**

3. Na página **importar custodiantes,** clique em **Baixar** um modelo em branco para baixar um arquivo CSV de modelo custodiante.

   ![Baixar um modelo CSV da página importar custodiantes](../media/ImportCustodians1.png)

4. Adicione as informações de custodiante ao arquivo CSV e salve-as no computador local. Consulte a [seção arquivo CSV Custodian](#custodian-csv-file) para obter informações sobre as propriedades necessárias no arquivo CSV.

5. Depois de preparar o arquivo CSV com as informações  de custodiante, volte para a guia Fontes de dados e clique em Adicionar custodiantes de importação de fonte  >  **de** dados novamente.

6. Na página **importar custodiantes,** clique em **Procurar** e carregue o arquivo CSV que contém as informações custodiantes.

   Depois que o arquivo CSV é carregado, um trabalho chamado **BulkAddCustodian** é criado e exibido na **guia** Trabalhos. O trabalho valida os custodiantes e suas fontes de  dados associadas e os adiciona à página Fontes de dados do caso.

## <a name="custodian-csv-file"></a>Arquivo CSV custodiado

Depois de baixar o modelo custodiante CSV, você pode adicionar custodiantes e sua fonte de dados em cada linha. Certifique-se de não alterar os nomes das colunas na linha de header. Use o tipo de carga de trabalho e as colunas de local de carga de trabalho para associar outras fontes de dados a um custodiante.

| Nome da coluna|Descrição|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |O endereço de email UPN do custodiatário. Por exemplo, sarad@contoso.onmicrosoft.com.           |
|**Exchange Habilitado** | Valor VERDADEIRO/FALSO para incluir ou não incluir a caixa de correio do custodiante.      |
|**OneDrive habilitado** | Valor VERDADEIRO/FALSO para incluir ou não incluir a conta do OneDrive for Business do custodiante. |
|**Está OnHold**        | Valor VERDADEIRO/FALSO para indicar se as fontes de dados custodiante serão colocadas em espera.       |
|**Tipo workload1**         |Valor da cadeia de caracteres indicando o tipo de fonte de dados a ser associada ao custodiante. Os valores possíveis incluem: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Local workload1**     | Dependendo do tipo de carga de trabalho, esse seria o local da fonte de dados. Por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint. |
|||

Veja um exemplo de um arquivo CSV com informações de custodiação:<br/><br/>

|Custodian contactEmail      | Exchange Habilitado | OneDrive habilitado | Está OnHold | Tipo workload1 | Local workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validação de custodiante e fonte de dados

Depois de carregar o arquivo CSV custodiante, a Descoberta Avançada faz o seguinte:

1. Valida os custodiantes e suas fontes de dados.

2. Indexa todas as fontes de dados para cada custodiante e coloca-as em espera (se a propriedade **Is OnHold** no arquivo CSV estiver definida como VERDADEIRO).

### <a name="custodian-validation"></a>Validação custodian

Atualmente, só damos suporte à importação de custodiantes incluídos no Azure Active Directory (Azure AD) da sua organização.

A ferramenta de importação custodiada localiza e valida custodiantes usando o valor UPN na coluna **Custodian contactEmail** no arquivo CSV. Custodiantes validados são adicionados automaticamente à ocorrência e listados na guia **Fontes de** dados do caso. Se um custodiante não puder ser validado, eles serão listados no log de erros  do trabalho BulkAddCustodian listado na guia Trabalhos no caso. Os custodiantes nãovalidados não são adicionados à ocorrência ou listados na **guia Fontes de** dados.

### <a name="data-source-validation"></a>Validação da fonte de dados

Depois que os responsáveis são validados e adicionados à ocorrência, cada caixa de correio principal e a conta do OneDrive associada a um custodiante são adicionadas.

No entanto, se qualquer uma das outras fontes de dados (como sites do SharePoint, Microsoft Teams, Grupos do Microsoft 365 ou grupos do Yammer) associadas a um custodiante não puder  ser encontrada, nenhuma delas será atribuída ao custodiante e o valor Não validado será exibido na coluna **Status** ao lado do custodiante na guia Fontes de dados. 

Para adicionar fontes de dados validadas para um custodiante:

1. Na guia **Fontes de dados,** selecione um custodiante que contenha fontes de dados não validadas.

2. Na página do flyout custodiante, role até a seção Locais custodiais para exibir fontes de dados validadas e nãovalidadas associadas ao custodiante. 

3. Clique **em Editar** na parte superior da página do flyout para remover fontes de dados inválidas ou adicionar novas.

4. Depois de remover fontes de dados nãovalidadas ou adicionar uma nova, o valor **Ativo** será exibido na coluna **Status** do custodiante na guia Fontes **de** dados. Para adicionar fontes que anteriormente aparentam ser inválidas, siga as etapas de correção abaixo para adicioná-las manualmente a um custodiante.

### <a name="remediating-invalid-data-sources"></a>Correção de fontes de dados inválidas

Para adicionar e associar manualmente uma fonte de dados que anteriormente era inválida:

1. Na guia **Fontes de dados,** selecione um custodiante para adicionar e associar manualmente uma fonte de dados anteriormente inválida.

2. Clique **em Editar** na parte superior da página do flyout para associar caixas de correio, sites, equipes ou grupos do Yammer ao custodiante. Faça isso clicando em **Editar** ao lado do tipo de local de dados apropriado.

3. Clique **em Próximo** para exibir a página de **configurações de** Espera e definir a configuração de espera para as fontes de dados que você adicionou.

4. Clique **em Próximo** para exibir a página Revisar **custodiantes** e clique **em Enviar** para salvar suas alterações.
