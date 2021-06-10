---
title: Criar uma política de DLP para proteger documentos com FCI ou outras propriedades
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar uma política de prevenção contra perda de dados (DLP) para proteger documentos que tenham propriedades de um sistema de terceiros.
ms.openlocfilehash: d3e635080ce05314adc8dd9599012e5f76bc0815
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113477"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Criar uma política de DLP para proteger documentos com FCI ou outras propriedades

Microsoft 365 políticas de prevenção contra perda de dados (DLP) podem usar propriedades de classificação ou propriedades de item para identificar itens confidenciais. Por exemplo, você pode usar:

- Windows Propriedades FCI (Infraestrutura de Classificação de Arquivo de Servidor)
- SharePoint do documento
- propriedades de documento do sistema de terceiros

![Diagrama mostrando o Office 365 e o sistema de classificação externa](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Por exemplo, sua organização pode usar o FCI do Windows Server para identificar itens com dados pessoais, como números de segurança social, e classificar o documento definindo a propriedade **Personally Identifiable Information** como **Alta,** **Moderada,** **Baixa**, **Pública** ou Não **PII** com base no tipo e no número de ocorrências de dados pessoais encontrados no documento.

No Microsoft 365, você pode criar uma política DLP que identifique documentos que tenham essa propriedade definida como valores específicos, como **Alto** e **Médio,** e, em seguida, toma uma ação como bloquear o acesso a esses arquivos. A mesma política pode ter outra regra que executa uma ação diferente se a propriedade for definida como **Baixa**, como o envio de uma notificação por email. Dessa forma, a DLP se integra ao Windows Server FCI e pode ajudar a proteger Office documentos carregados ou compartilhados no Microsoft 365 de servidores de arquivos baseados no Windows Server.

Uma política de DLP simplesmente procura por um par de nome/valor de propriedade específico. Qualquer propriedade de documento pode ser usada, contanto que a propriedade tenha uma propriedade gerenciada correspondente para a pesquisa do SharePoint. Por exemplo, um conjunto de sites do SharePoint pode usar um tipo de conteúdo chamado **Relatório de viagem** com um campo obrigatório chamado **Cliente**. Sempre que uma pessoa criar um relatório de viagem, ela deve digitar o nome do cliente. Esse par de nome/valor de propriedade também pode ser usado em uma política DLP, por  exemplo, se você quiser uma regra que bloqueia o acesso ao documento para convidados quando o campo Cliente contiver **Contoso**.

Se você deseja aplicar sua política de DLP ao conteúdo com rótulos Microsoft 365 específicos, não siga as etapas aqui. Em vez disso, saiba como [usar um rótulo de retenção como condição em uma política DLP.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

## <a name="before-you-create-the-dlp-policy"></a>Antes de criar a política de DLP

Antes de usar uma propriedade de FCI do Windows Server ou outra propriedade em uma política de DLP, você precisa criar uma propriedade gerenciada no centro de administração do SharePoint. Veja o motivo.

Exemplos

> [!NOTE]
> Certifique-se de usar um nome de propriedade gerenciada e não um nome de propriedade rastreado ao criar regras DLP usando a `ContentPropertyContainsWords` condição.

Isso é importante porque a DLP usa o rastreador de pesquisa para identificar e classificar informações confidenciais em seus sites e, em seguida, armazenar essas informações confidenciais em uma parte segura do índice de pesquisa. Quando você carregar um documento no Office 365, o SharePoint cria automaticamente propriedades rastreadas com base nas propriedades do documento. Mas, para usar uma FCI ou outra propriedade em uma política de DLP, essa propriedade rastreada precisa ser mapeada para uma propriedade gerenciada para que o conteúdo com essa propriedade seja mantido no índice.

Para obter mais informações sobre propriedades gerenciadas e de pesquisa, consulte [Gerenciar o esquema de pesquisa em SharePoint Online](/sharepoint/manage-search-schema).

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Etapa 1: Carregar um documento com a propriedade necessária para o Office 365

Primeiro você precisa carregar um documento com a propriedade à qual você deseja fazer referência em sua política de DLP. Microsoft 365 detectará a propriedade e criará automaticamente uma propriedade rastreada a partir dela. Na próxima etapa, você criará uma propriedade gerenciada e mapeará a propriedade gerenciada para essa propriedade rastreada.

### <a name="step-2-create-a-managed-property"></a>Etapa 2: Criar uma propriedade gerenciada

1. Entre no Centro de administração do Microsoft 365.

2. Na navegação à esquerda, escolha **Centros de administração** \> **SharePoint**. Agora você está no centro de administração do SharePoint.

3. Na navegação à esquerda, escolha **pesquisar** \> na página administração da **pesquisa** Gerenciar Esquema \> **de Pesquisa**.

   ![página de administração de pesquisa no centro de administração do SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. Na página **Propriedades Gerenciadas** \> **Nova Propriedade Gerenciada**.

   ![Página de propriedades gerenciadas com o botão Nova Propriedade Gerenciada realçado](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Insira um nome e uma descrição para a propriedade. Esse nome é o que aparecerá em suas políticas de DLP.

6. Para **Tipo**, escolha **Texto**.

7. Em **Características principais**, selecione **Consultável** e **Recuperável**.

8. Em **Mapeamentos para propriedades rastreadas** \> **Adicione um mapeamento**.

9. Na caixa **de diálogo seleção** de propriedade rastreada, localmente e selecione a propriedade rastreada que corresponde à propriedade FCI do servidor Windows ou outra propriedade que você usará em sua política de \> DLP \> **OK**.

   ![caixa de diálogo de seleção da propriedade rastreada](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. Na parte inferior da página \> **OK**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Criar uma política de DLP que usa uma propriedade FCI ou outra propriedade

Neste exemplo, uma organização está usando o FCI em seus Windows de arquivos baseados em servidor; especificamente, eles estão usando a propriedade de classificação FCI chamada **Informações de** Identificação Pessoal com valores possíveis de **High**, **Moderate**, **Low**, **Public** e **Not PII**. Agora eles querem usar a classificação de FCI existente em suas políticas de DLP em Office 365.

Primeiro, ela segue as etapas acima para criar uma propriedade gerenciada no SharePoint Online, a qual mapeia para a propriedade rastreada criada automaticamente da propriedade FCI.

Em seguida, eles criam uma política DLP com duas regras que usam a condição **Propriedades do documento contêm qualquer um desses valores:**

- **Conteúdo de PII de FCI - Alto, Moderado** A primeira regra restringe o acesso ao documento se a propriedade de classificação  FCI **Informações** de identificação pessoal for igual a **Alta** ou Moderada e o documento for compartilhado com pessoas de fora da organização.

- **Conteúdo de PII de FCI - Baixo** A segunda regra envia uma notificação ao proprietário do documento se a propriedade de classificação FCI **Informações de** identificação pessoal for igual a **Baixo** e o documento for compartilhado com pessoas de fora da organização.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Criar a política DLP usando o PowerShell

A condição As propriedades **do** documento contêm qualquer um desses valores temporariamente não está disponível na interface do usuário do Centro de Conformidade de Segurança, mas você ainda pode usar essa condição usando &amp; o PowerShell. Você pode usar os cmdlets para trabalhar com uma política DLP e usar os  `New\Set\Get-DlpCompliancePolicy`  `New\Set\Get-DlpComplianceRule` cmdlets com o parâmetro para adicionar a condição Propriedades do documento contêm qualquer  `ContentPropertyContainsWords` **um desses valores**.

Para obter mais informações sobre esses cmdlets, consulte [ &amp; Cmdlets](/powershell/exchange/exchange-online-powershell)do Centro de Conformidade de Segurança.

1. [Conexão para o Centro de &amp; Conformidade de Segurança usando o PowerShell remoto](/powershell/exchange/connect-to-scc-powershell)

2. Crie a política usando  `New-DlpCompliancePolicy` .

Este PowerShell cria uma política DLP que se aplica a todos os locais.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Crie as duas regras descritas acima usando , onde uma regra é para o valor Baixo e outra é para `New-DlpComplianceRule` os valores **Alto** **e** Moderado. 

   Aqui está um exemplo do PowerShell que cria essas duas regras. Os pares de nome/valor da propriedade estão entre aspas e um nome de propriedade pode especificar vários valores separados por vírgulas sem espaços, como  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows O FCI do servidor inclui muitas propriedades in-locar, incluindo **Informações de Identificação** Pessoal usadas neste exemplo. Os valores possíveis para cada propriedade podem ser diferentes para cada organização. Os **valores Alto,** **Moderado** e **Baixo** usados aqui são apenas um exemplo. Para sua organização, você pode exibir as propriedades de classificação do Windows Server FCI com seus valores possíveis no Gerenciador de Recursos do Servidor de arquivos no servidor de arquivos Windows servidor baseado em servidor. Para obter mais informações, consulte [Create a classification property](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11)).

Quando terminar, sua política deverá ter duas novas regras que usam as propriedades **Document contendo qualquer uma dessas condições de** valores. Essa condição não aparecerá na interface do usuário, embora as outras condições, ações e configurações apareçam.

Uma regra bloqueia o acesso ao conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Alta** ou **Moderada**. Uma segunda regra envia uma notificação sobre o conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Baixa**.

![Caixa de diálogo de nova política de DLP mostrando duas regras recém-criadas](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Depois de criar a política de DLP

Fazer as etapas nas seções anteriores criará uma política de DLP que detectará rapidamente o conteúdo com essa propriedade, mas somente se esse conteúdo for carregado recentemente (para que o conteúdo seja indexado) ou se esse conteúdo for antigo, mas apenas editado (para que o conteúdo seja re indexado).

Para detectar o conteúdo com essa propriedade em todos os lugares, convém solicitar manualmente que sua biblioteca, site ou conjunto de sites seja reindexado, para que a política de DLP esteja ciente de todo o conteúdo com essa propriedade. No SharePoint Online, o conteúdo é rastreado automaticamente com base em um agendamento de rastreamento definido. O rastreador seleciona o conteúdo que foi alterado desde o último rastreamento e atualiza o índice. Se você precisar de sua política de DLP para proteger o conteúdo antes do próximo rastreamento agendado, você pode executar estas etapas.

> [!CAUTION]
> A reindexação de um site pode gerar uma grande carga no sistema de pesquisa. Não re indexe seu site, a menos que seu cenário o exija.

Para saber mais, confira [Solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](/sharepoint/crawl-site-content).

### <a name="reindex-a-site-optional"></a>Reindexar um site (opcional)

1. No site, **escolha** Configurações (ícone de engrenagem no canto superior direito) \> **Site Configurações**.

2. Em **Pesquisa**, escolha **Pesquisar e disponibilidade offline** \> **Reindexar site**.

## <a name="more-information"></a>Mais informações

- [Saiba mais sobre a prevenção contra perda de dados](dlp-learn-about-dlp.md)

- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)

- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)

- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)