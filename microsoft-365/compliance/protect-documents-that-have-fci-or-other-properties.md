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
description: Saiba como usar uma política de prevenção contra perda de dados (DLP) para proteger documentos que têm propriedades de um sistema de terceiros.
ms.openlocfilehash: cf026e447ad1f0da3486a36dd5e36c52c09998cb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288224"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Criar uma política de DLP para proteger documentos com FCI ou outras propriedades

As políticas de prevenção contra perda de dados (DLP) do Microsoft 365 podem usar propriedades de classificação ou propriedades de item para identificar itens confidenciais. Por exemplo, você pode usar:

- Propriedades da FCI (Infraestrutura de Classificação de Arquivos) do Windows Server
- Propriedades do documento do SharePoint
- propriedades do documento do sistema de terceiros

![Diagrama mostrando o Office 365 e o sistema de classificação externa](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Por exemplo, sua organização pode usar a FCI do Windows Server para identificar itens com  dados pessoais, como números de previdência social, e classificar o documento definindo a propriedade de Informações de Identificação Pessoal como **Alta** **,** Moderada **,** Baixa **,** Pública ou Não **PII** com base no tipo e no número de ocorrências de dados pessoais encontrados no documento.

No Microsoft 365, você pode criar uma política de DLP que identifica  documentos que têm essa propriedade definida como valores específicos, como Alto e Médio, e, em seguida, toma uma ação como bloquear o acesso a esses arquivos. A mesma política pode ter outra regra que executa uma ação diferente se a propriedade for definida como **Baixa**, como o envio de uma notificação por email. Dessa forma, a DLP se integra à FCI do Windows Server e pode ajudar a proteger documentos do Office carregados ou compartilhados no Microsoft 365 a partir de servidores de arquivos baseados no Windows Server.

Uma política de DLP simplesmente procura por um par de nome/valor de propriedade específico. Qualquer propriedade de documento pode ser usada, contanto que a propriedade tenha uma propriedade gerenciada correspondente para a pesquisa do SharePoint. Por exemplo, um conjunto de sites do SharePoint pode usar um tipo de conteúdo chamado **Relatório de viagem** com um campo obrigatório chamado **Cliente**. Sempre que uma pessoa criar um relatório de viagem, ela deve digitar o nome do cliente. Esse par nome/valor de propriedade também pode ser usado em uma política de DLP — por  exemplo, se você quiser uma regra que bloqueia o acesso ao documento para convidados quando o campo Cliente contiver **Contoso**.

Se você quiser aplicar sua política de DLP ao conteúdo com rótulos específicos do Microsoft 365, não siga as etapas aqui. Em vez disso, saiba como [usar um rótulo de retenção como uma condição em uma política de DLP.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

## <a name="before-you-create-the-dlp-policy"></a>Antes de criar a política de DLP

Antes de usar uma propriedade de FCI do Windows Server ou outra propriedade em uma política de DLP, você precisa criar uma propriedade gerenciada no centro de administração do SharePoint. Veja por quê.

Exemplos

> [!NOTE]
> Certifique-se de usar um nome de propriedade gerenciada e não um nome de propriedade rastreada ao criar regras de DLP usando a `ContentPropertyContainsWords` condição.

Isso é importante porque a DLP usa o rastreador de pesquisa para identificar e classificar informações confidenciais em seus sites e, em seguida, armazenar essas informações confidenciais em uma parte segura do índice de pesquisa. Quando você carregar um documento no Office 365, o SharePoint cria automaticamente propriedades rastreadas com base nas propriedades do documento. Mas, para usar uma FCI ou outra propriedade em uma política de DLP, essa propriedade rastreada precisa ser mapeada para uma propriedade gerenciada para que o conteúdo com essa propriedade seja mantido no índice.

Para saber mais sobre propriedades gerenciadas e de pesquisa, confira [Gerenciar o esquema de pesquisa no SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=627454)

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Etapa 1: Carregar um documento com a propriedade necessária para o Office 365

Primeiro você precisa carregar um documento com a propriedade à qual você deseja fazer referência em sua política de DLP. O Microsoft 365 detectará a propriedade e criará automaticamente uma propriedade rastreada a partir dela. Na próxima etapa, você criará uma propriedade gerenciada e mapeará a propriedade gerenciada para essa propriedade rastreada.

### <a name="step-2-create-a-managed-property"></a>Etapa 2: Criar uma propriedade gerenciada

1. Acesse o centro de administração do Microsoft 365.

2. Na navegação à esquerda, escolha **Centros de administração do** \> **SharePoint.** Agora você está no centro de administração do SharePoint.

3. Na navegação à esquerda, escolha **pesquisar na** página de \> administração **de** pesquisa Gerenciar Esquema \> **de Pesquisa.**

   ![página de administração de pesquisa no centro de administração do SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. Na página **Propriedades Gerenciadas** \> **Nova Propriedade Gerenciada.**

   ![Página de propriedades gerenciadas com o botão Nova Propriedade Gerenciada realçado](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Insira um nome e uma descrição para a propriedade. Esse nome é o que aparecerá em suas políticas de DLP.

6. Para **Tipo**, escolha **Texto**.

7. Em **Características principais**, selecione **Consultável** e **Recuperável**.

8. Em **Mapeamentos para propriedades rastreadas,** \> **adicione um mapeamento.**

9. In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.

   ![caixa de diálogo de seleção da propriedade rastreada](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. Na parte inferior da página \> **OK**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Criar uma política de DLP que usa uma propriedade FCI ou outra propriedade

Neste exemplo, uma organização está usando FCI em seus servidores de arquivos baseados no Windows Server; especificamente, eles estão usando a propriedade  de classificação de FCI chamada Informações de Identificação Pessoal com valores possíveis **de High**, **Moderate**, **Low**, **Public** e **Not PII**. Agora eles querem usar sua classificação de FCI existente em suas políticas de DLP no Office 365.

Primeiro, ela segue as etapas acima para criar uma propriedade gerenciada no SharePoint Online, a qual mapeia para a propriedade rastreada criada automaticamente da propriedade FCI.

Em seguida, eles criam uma política de DLP com duas regras que usam a condição Propriedades do documento **contêm qualquer um destes valores:**

- **Conteúdo de PII de FCI - Alto, Moderado** A primeira regra restringe o acesso ao documento  se a propriedade de classificação  de FCI Informações de Identificação Pessoal for igual a **Alta** ou Moderada e o documento for compartilhado com pessoas de fora da organização.

- **Conteúdo de PII de FCI - Baixo** A segunda regra envia uma notificação ao proprietário  do documento se a propriedade de classificação de FCI Informações De identificação pessoal for igual a **Baixa** e o documento for compartilhado com pessoas de fora da organização.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Criar a política DLP usando o PowerShell

A condição **Propriedades** do documento contêm qualquer um desses valores temporariamente não está disponível na interface do usuário do Centro de Conformidade de Segurança, mas você ainda pode usar essa condição usando &amp; o PowerShell. Você pode usar os cmdlets para trabalhar com uma política de DLP e usar os cmdlets com o parâmetro para adicionar a condição Propriedades do documento contêm qualquer `New\Set\Get-DlpCompliancePolicy` `New\Set\Get-DlpComplianceRule` um desses `ContentPropertyContainsWords` **valores.**

Para obter mais informações sobre esses cmdlets, consulte [ &amp; cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)do Centro de Conformidade de Segurança.

1. [Conectar-se ao Centro &amp; de Conformidade de Segurança usando o PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. Crie a política usando  `New-DlpCompliancePolicy` .

Esse PowerShell cria uma política de DLP que se aplica a todos os locais.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Crie as duas regras descritas acima usando , onde uma regra é para o valor Baixo e outra regra é para os valores `New-DlpComplianceRule` **Alto** **e** Moderado. 

   Aqui está um exemplo do PowerShell que cria essas duas regras. Os pares nome/valor da propriedade estão entre aspas, e um nome de propriedade pode especificar vários valores separados por vírgulas sem espaços, como  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   A FCI do Windows Server inclui muitas propriedades criadas, incluindo Informações de Identificação **Pessoal** usadas neste exemplo. Os valores possíveis para cada propriedade podem ser diferentes para cada organização. Os **valores Alto**, **Moderado** e **Baixo** usados aqui são apenas um exemplo. Para sua organização, você pode exibir as propriedades de classificação de FCI do Windows Server com seus valores possíveis no gerenciador de recursos do servidor de arquivos no servidor de arquivos baseado no Windows Server. Para obter mais informações, consulte [Criar uma propriedade de classificação.](https://go.microsoft.com/fwlink/p/?LinkID=627456)

Quando você terminar, sua política deverá ter duas novas regras que usam as propriedades **Document que contenham qualquer uma dessas condições de** valores. Essa condição não aparecerá na interface do usuário, embora as outras condições, ações e configurações apareçam.

Uma regra bloqueia o acesso ao conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Alta** ou **Moderada**. Uma segunda regra envia uma notificação sobre o conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Baixa**.

![Caixa de diálogo de nova política de DLP mostrando duas regras recém-criadas](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Depois de criar a política de DLP

As etapas nas seções anteriores criarão uma política de DLP que detectará rapidamente o conteúdo com essa propriedade, mas somente se esse conteúdo for carregado recentemente (para que o conteúdo seja indexado) ou se esse conteúdo for antigo, mas apenas editado (para que o conteúdo seja indexado novamente).

Para detectar o conteúdo com essa propriedade em todos os lugares, convém solicitar manualmente que sua biblioteca, site ou conjunto de sites seja reindexado, para que a política de DLP esteja ciente de todo o conteúdo com essa propriedade. No SharePoint Online, o conteúdo é rastreado automaticamente com base em um agendamento de rastreamento definido. O rastreador seleciona o conteúdo que foi alterado desde o último rastreamento e atualiza o índice. Se você precisar de sua política de DLP para proteger o conteúdo antes do próximo rastreamento agendado, você pode executar estas etapas.

> [!CAUTION]
> A reindexação de um site pode gerar uma grande carga no sistema de pesquisa. Não indexe seu site de novo, a menos que seu cenário realmente exija isso.

Para saber mais, confira [Solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://go.microsoft.com/fwlink/p/?LinkID=627457).

### <a name="reindex-a-site-optional"></a>Reindexar um site (opcional)

1. No site, escolha **Configurações** (ícone de engrenagem no canto superior direito) \> **Configurações do Site.**

2. Em **Pesquisa,** escolha **Pesquisar e disponibilidade offline** \> **Reindexar site.**

## <a name="more-information"></a>Mais informações

- [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md)

- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)

- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)

- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
