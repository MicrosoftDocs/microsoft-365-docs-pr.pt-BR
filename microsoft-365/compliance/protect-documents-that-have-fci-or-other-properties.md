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
description: Muitas organizações já têm um processo para identificar e classificar informações confidenciais usando as propriedades de classificação no arquivo de classificação de infraestrutura (FCI) do Windows Server, as propriedades do documento no SharePoint ou as propriedades do documento aplicadas por um sistema de terceiros. Se essa for a sua organização, você pode criar uma política de DLP no Office 365 que reconhece as propriedades que foram aplicadas a documentos pelo FCI do Windows Server ou outro sistema, para que a política de DLP possa ser imposta em documentos do Office com FCI específico ou outros valores de propriedade.
ms.openlocfilehash: 32d40c110ca67e15c1be3443999c75c0e36d323e
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193489"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Criar uma política de DLP para proteger documentos com FCI ou outras propriedades

No Office 365, você pode usar uma política de prevenção (DLP) contra perda de dados para identificar, monitorar e proteger informações confidenciais. Muitas organizações já têm um processo para identificar e classificar informações confidenciais usando as propriedades de classificação no arquivo de classificação de infraestrutura (FCI) do Windows Server, as propriedades do documento no SharePoint ou as propriedades do documento aplicadas por um sistema de terceiros. Se essa for a sua organização, você pode criar uma política de DLP no Office 365 que reconhece as propriedades que foram aplicadas a documentos pelo FCI do Windows Server ou outro sistema, para que a política de DLP possa ser imposta em documentos do Office com FCI específico ou outros valores de propriedade.
  
![Diagrama mostrando o Office 365 e o sistema de classificação externa](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Por exemplo, sua organização pode usar o FCI do Windows Server para identificar documentos com informações de identificação pessoal (PII), como cadastros de pessoas físicas e, em seguida, classificar o documento, definindo a propriedade **Informações de Identificação Pessoal** como **Alta**, **Moderada**, **Baixa**, **Pública** ou **Não PII** com base no tipo e número de ocorrências de PII localizadas no documento. No Office 365, você pode criar uma política de DLP que identifica documentos que têm essa propriedade definida como valores específicos, como **Alta** e **Média** e depois executa uma ação como o bloqueio do acesso a esses arquivos. A mesma política pode ter outra regra que executa uma ação diferente se a propriedade for definida como **Baixa**, como o envio de uma notificação por email. Dessa forma, a DLP no Office 365 integra-se com o Windows Server FCI e pode ajudar a proteger os documentos do Office carregados ou compartilhados para o Office 365 a partir de servidores de arquivos baseados no Windows Server.
  
Uma política de DLP simplesmente procura por um par de nome/valor de propriedade específico. Qualquer propriedade de documento pode ser usada, contanto que a propriedade tenha uma propriedade gerenciada correspondente para a pesquisa do SharePoint. Por exemplo, um conjunto de sites do SharePoint pode usar um tipo de conteúdo chamado **Relatório de viagem** com um campo obrigatório chamado **Cliente**. Sempre que uma pessoa criar um relatório de viagem, ela deve digitar o nome do cliente. Esse par de nome/valor de propriedade também pode ser usado em uma política de DLP — por exemplo, se você desejar que uma regra que bloqueia o acesso ao documento para usuários externos quando o campo **Cliente** contiver **Contoso**.
  
Observe que, se você quiser aplicar sua política de DLP ao conteúdo com rótulos específicos do Office 365, não siga as etapas aqui. Em vez disso, saiba como [usar um rótulo de retenção como uma condição em uma política de DLP](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Antes de criar a política de DLP

Antes de usar uma propriedade de FCI do Windows Server ou outra propriedade em uma política de DLP, você precisa criar uma propriedade gerenciada no centro de administração do SharePoint. Veja por quê.
  
Exemplos
  
Isso é importante porque a DLP no Office 365 usa o rastreador de pesquisa para identificar e classificar informações confidenciais em seus sites e, em seguida, armazenar informações confidenciais em uma parte segura do índice de pesquisa. Quando você carregar um documento no Office 365, o SharePoint cria automaticamente propriedades rastreadas com base nas propriedades do documento. Mas, para usar uma FCI ou outra propriedade em uma política de DLP, essa propriedade rastreada precisa ser mapeada para uma propriedade gerenciada para que o conteúdo com essa propriedade seja mantido no índice.
  
Para obter mais informações sobre propriedades gerenciadas e pesquisa, consulte [gerenciar o esquema de pesquisa no SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Etapa 1: Carregar um documento com a propriedade necessária para o Office 365

Primeiro você precisa carregar um documento com a propriedade à qual você deseja fazer referência em sua política de DLP. O Office 365 detecta a propriedade e cria automaticamente uma propriedade rastreada a partir dela. Na próxima etapa, você criará uma propriedade gerenciada e, em seguida, mapeará a propriedade gerenciada para essa propriedade rastreada.
  
### <a name="step-2-create-a-managed-property"></a>Etapa 2: Criar uma propriedade gerenciada

1. Acesse o centro de administração do Microsoft 365.
    
2. No painel de navegação à esquerda, escolha **central** \> de administração **do SharePoint**. Agora você está no centro de administração do SharePoint.
    
3. No painel de navegação à esquerda, escolha **Pesquisar** \> na página \> **Administração da pesquisa** **gerenciar esquema de pesquisa**.
    
    ![página de administração de pesquisa no centro de administração do SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. Na \> página **propriedades gerenciadas** **nova propriedade gerenciada**.
    
    ![Página de propriedades gerenciadas com o botão Nova Propriedade Gerenciada realçado](../media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Insira um nome e uma descrição para a propriedade. Esse nome é o que aparecerá em suas políticas de DLP.
    
6. Para **Tipo**, escolha **Texto**. 
    
7. Em **Características principais**, selecione **Consultável** e **Recuperável**.
    
8. \> Em **mapeamentos para propriedades rastreadas** , **adicione um mapeamento**.
    
9. Na caixa \> de diálogo **seleção de propriedade rastreada** , localize e selecione a propriedade rastreada que corresponde à propriedade FCI do Windows Server, ou outra propriedade que você usará em \> sua política de DLP **OK**.
    
    ![caixa de diálogo de seleção da propriedade rastreada](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. Na parte inferior da página \> , **OK**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Criar uma política de DLP que usa uma propriedade FCI ou outra propriedade

Neste exemplo, uma organização está usando o FCI em seus servidores de arquivos baseados em Windows Server; especificamente, eles estão usando a propriedade de classificação FCI chamada **informações de identificação pessoal** com possíveis valores de **alta**, **moderado**, **baixo**, **público**e **não PII**. Agora eles querem aproveitar a classificação existente do FCI em suas políticas de DLP no Office 365.
  
Primeiro, ela segue as etapas acima para criar uma propriedade gerenciada no SharePoint Online, a qual mapeia para a propriedade rastreada criada automaticamente da propriedade FCI.
  
Em seguida, ele cria uma política de DLP com duas regras que usam as **Propriedades de documento de condição conter qualquer um destes valores**:
  
- **Conteúdo PII FCI-alto, moderado** A primeira regra restringe o acesso ao documento se as **informações de identificação pessoal** da propriedade de classificação FCI são iguais a **alta** ou **moderada** e o documento é compartilhado com pessoas de fora da organização. 
    
- **Conteúdo de PII FCI-baixo** A segunda regra envia uma notificação ao proprietário do documento, se as informações de **identificação pessoal** da propriedade de classificação FCI forem **baixas** e o documento for compartilhado com pessoas de fora da organização. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Criar a política de DLP usando o PowerShell

Observe que as **Propriedades de documento de condição contêm qualquer um desses valores** temporariamente indisponíveis na interface do usuário do &amp; centro de conformidade de segurança, mas você ainda pode usar essa condição usando o PowerShell. Você pode usar os `New\Set\Get-DlpCompliancePolicy` cmdlets para trabalhar com uma política de DLP e usar os `New\Set\Get-DlpComplianceRule` cmdlets com o `ContentPropertyContainsWords` parâmetro para adicionar as propriedades de documento de condição que **contenham qualquer**um desses valores.
  
Para obter mais informações sobre esses cmdlets, consulte [cmdlets &amp; do centro de conformidade de segurança do Office 365](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Conectar-se ao Centro de Conformidade &amp; Segurança do Office 365 usando o PowerShell Remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Crie a política usando `New-DlpCompliancePolicy`o.

Veja a seguir um exemplo do PowerShell que cria uma política de DLP que se aplica a todos os locais.

```powershell
New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
```

3. Crie as duas regras descritas acima usando `New-DlpComplianceRule`, onde uma regra é para o valor **baixo** e outra regra é para os valores **altos** e **moderados** . 
    
    Veja a seguir um exemplo do PowerShell que cria essas duas regras. Observe que os pares nome/valor da propriedade são colocados entre aspas, e um nome de propriedade pode especificar vários valores separados por vírgulas sem espaços, como`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

```powershell
New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
```

    Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Quando você terminar, a política deverá ter duas novas regras que usem as **Propriedades do documento contendo qualquer uma dessas** condições. Observe que essa condição não aparecerá na interface do usuário, embora as outras condições, ações e configurações apareçam.
  
Uma regra bloqueia o acesso ao conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Alta** ou **Moderada**. Uma segunda regra envia uma notificação sobre o conteúdo em que a propriedade **Informações de identificação pessoal** é igual a **Baixa**.
  
![Caixa de diálogo de nova política de DLP mostrando duas regras recém-criadas](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Depois de criar a política de DLP

Executar as etapas nas seções anteriores criará uma política de DLP que detectará rapidamente o conteúdo com essa propriedade, mas somente se o conteúdo for carregado recentemente (para que o conteúdo seja indexado) ou se esse conteúdo for antigo, mas apenas editado (para que o conteúdo seja indexado novamente).
  
Para detectar o conteúdo com essa propriedade em todos os lugares, convém solicitar manualmente que sua biblioteca, site ou conjunto de sites seja reindexado, para que a política de DLP esteja ciente de todo o conteúdo com essa propriedade. No SharePoint Online, o conteúdo é rastreado automaticamente com base em um agendamento de rastreamento definido. O rastreador seleciona o conteúdo que foi alterado desde o último rastreamento e atualiza o índice. Se você precisar de sua política de DLP para proteger o conteúdo antes do próximo rastreamento agendado, você pode executar estas etapas.
  
> [!CAUTION]
> A reindexação de um site pode gerar uma grande carga no sistema de pesquisa. Não reindexe o site, a menos que o cenário o exija absolutamente. 
  
Para saber mais, confira [Solicitar manualmente o rastreamento e a reindexação de um site, uma biblioteca ou uma lista](https://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Reindexar um site (opcional)

1. No site, escolha **configurações** (ícone de engrenagem no canto superior direito \> ) **configurações do site**.
    
2. Em **Pesquisar**, escolha o site de \> **reindexação** **de pesquisa e disponibilidade offline** .
    
## <a name="more-information"></a>Mais informações

- [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md)
    
- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)
    
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
    
- [Inventário de tipos de informações confidenciais](what-the-sensitive-information-types-look-for.md)
