---
title: Criar, publicar ou aplicar automaticamente rótulos de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Instruções para criar, publicar e aplicar automaticamente rótulos de retenção para reter o que você precisa, excluir o que não é necessário e declarar um item como um registro no seu ambiente do Office 365.
ms.openlocfilehash: a3ba321c9eae91bf701646a45271d3edcbc8dccc
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545953"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a>Criar, publicar ou aplicar automaticamente rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Use as informações a seguir para ajudá-lo a criar [rótulos de retenção](labels.md) e, em seguida, aplicá-los automaticamente a documentos e emails, ou publicá-los para que os usuários possam aplicá-los manualmente.

Os rótulos de retenção ajudam a reter o que você precisa e excluir o que não é necessário. Eles também são usados para declarar um item como um registro como parte de uma solução de [gerenciamento de registros](records-management.md) para seus dados do Microsoft 365.

Onde você cria e configura seus rótulos de retenção depende se você está usando o gerenciamento de registros ou não. São fornecidas instruções para ambos os cenários.

## <a name="before-you-begin"></a>Antes de começar

Os membros da sua equipe de conformidade que criarão rótulos de retenção precisam de permissões para o Centro de Conformidade e Segurança do &amp;. Por padrão, o administrador do locatário tem acesso a esse local e pode conceder, aos agentes de conformidade e a outras pessoas, acesso ao Centro de Conformidade e Segurança do &amp;, sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você acesse a página **Permissões** do Centro de Conformidade e Segurança do &amp;, edite o grupo de função **Administrador de Conformidade** e adicione membros a esse grupo de função. 
  
Para saber mais, consulte [Dar aos usuários acesso ao &amp;Centro de Conformidade](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) e Segurança do Office 365.
  
Essas permissões só serão necessárias para criar e aplicar rótulos de retenção. A imposição da política não exige acesso ao conteúdo.

## <a name="create-and-configure-retention-labels"></a>Criar e configurar rótulos de retenção

1. No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros:
        - **Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**
        
    - Se você não estiver usando o gerenciamento de registros:
       - **Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente. Se você estiver usando o gerenciamento de registros:
    
    - Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)
    
    - Para usar o rótulo de retenção para declarar conteúdo como um registro, ative a caixa de seleção **Usar rótulo para classificar o conteúdo como um "Registro"**.

3. Repita essas etapas para criar mais rótulos.

Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para começar o mesmo assistente que permite alterar as descrições de rótulo e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2. Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a>Publicar rótulos de retenção criando uma política de rótulo de retenção

Publique seus rótulos de retenção, para que possam ser aplicados manualmente pelos usuários.

1. No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros:
        - **Soluções** > **Gerenciamento de Registros** > > guia **Políticas de Rótulo** > **Publicar Rótulos**
    
    - Se você não estiver usando o gerenciamento de registros:
        - **Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Publicar Rótulos**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente.
    
    Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](labels.md#retention-label-policies-and-locations). 

Para editar uma política de rótulo de retenção existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2. Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.

## <a name="auto-apply-a-retention-label"></a>Aplicação automática de um rótulo de retenção

Aplique automaticamente um rótulo de retenção, com base nas condições que você especificar.

1. No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros: **Governança de Informações**:
        - **Soluções** > **Gerenciamento de Registros** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**
    
    - Se você não estiver usando o gerenciamento de registros:
        - **Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente.
    
    Para saber mais sobre como configurar condições que aplicam automaticamente o rótulo de retenção, confira o [Configurar condições para a aplicação automática de rótulos de retenção](#configuring-conditions-for-auto-apply-retention-labels) nesta página.
    
    Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](labels.md#retention-label-policies-and-locations).

Para editar uma política de rótulo de aplicação automática existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2. Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Configurar condições para a aplicação automática de rótulos de retenção

Você pode aplicar os rótulos de retenção automaticamente ao conteúdo quando esse conteúdo apresentar:
  
- [Tipos específicos de informações confidenciais](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [Palavras-chave específicas que correspondem a uma consulta criada por você](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Uma correspondência de classificadores treináveis](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Escolha a página de condição para aplicação automática de rótulo](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

Pode levar até sete dias para que os rótulos de retenção sejam aplicados automaticamente a todo o conteúdo que corresponde às condições que você configurou.

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Aplicar automaticamente rótulos a conteúdo com tipos específicos de informações confidenciais

Ao criar rótulos de retenção de aplicação automática para informações confidenciais, você vê a mesma lista de modelos de política que quando cria uma política de prevenção contra perda de dados (DLP). Cada modelo de política é pré-configurado para procurar tipos específicos de informações confidenciais. Por exemplo, o modelo mostrado aqui procura os números do ITIN (Número de Identificação de Contribuinte Individual) dos EUA, SSN (CPF) e passaporte. Para saber mais sobre DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).
  
![Modelos de política com tipos de informações confidenciais](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
Depois de selecionar um modelo de política, você pode adicionar ou remover quaisquer tipos de informações confidenciais, e pode alterar a contagem de instâncias e a precisão de correspondência. No exemplo mostrado aqui, um rótulo de retenção será aplicado automaticamente apenas quando:
  
- O conteúdo tiver entre uma e nove instâncias de qualquer um destes três tipos de informações confidenciais. Você pode excluir o valor **max** para que mude para **any**.
    
- O tipo de informação confidencial detectado tiver uma precisão de correspondência (ou nível de confiança) de pelo menos 75. Muitos tipos de informações confidenciais são definidos com vários padrões, em que um padrão de precisão de correspondência superior exige mais evidências para ser encontrado (como palavras-chave, datas ou endereços), enquanto um padrão de precisão de correspondência inferior exige menos evidências. Resumindo, quanto menor a precisão de correspondência **min**, mais fácil será para o conteúdo atender à condição. 
    
Para saber mais sobre essas opções, confira [Como ajustar as regras para facilitar ou dificultar a correspondência](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).
    
![Opções para identificar tipos de informações confidenciais](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Aplicar rótulos automaticamente a conteúdos com palavras-chave ou propriedades pesquisáveis

Você pode aplicar automaticamente os rótulos ao conteúdo que atenda a certas condições. As condições disponíveis agora dão suporte à aplicação de um rótulo a conteúdos que incluem palavras ou frases específicas, ou valores de propriedades pesquisáveis. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT.

Para saber mais sobre sintaxe de consulta, confira:

- [Referência de sintaxe da Linguagem de Consulta de Palavra-chave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

Rótulos baseados em consultas usam o índice de pesquisa para identificar conteúdos. Para saber mais sobre propriedades pesquisáveis válidas, confira:

- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
- [Visão geral de propriedades rastreadas e gerenciadas no SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

Consultas de exemplos:

- Exchange
    - assunto:"Finanças trimestrais"
    - destinatários:garthf<!--nolink-->@contoso.com
- SharePoint e OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement E contenttype:contract

![Editor de consultas](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Aplicar rótulos automaticamente ao conteúdo usando classificadores treináveis

Ao escolher a opção de um classificador treinado, você pode selecionar um dos classificadores internos ou um classificador personalizado. Os classificadores internos incluem **Currículos**, **SourceCode**, **Assédio Direcionado**, **Profanação** e **Ameaças**:

![Escolha classificador treinável](../media/retention-label-classifers.png)

Para aplicar um rótulo automaticamente usando essa opção, as caixas de correio e sites do SharePoint Online devem ter pelo menos 10 MB de dados.

Para obter mais informações sobre os classificadores treináveis, confira [Introdução aos classificadores treináveis (visualização)](classifier-getting-started-with.md).

Para um exemplo de configuração, consulte [Como preparar e usar um classificador interno](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Quanto tempo demora para os rótulos de retenção entrarem em vigor

Quando você publica ou aplica rótulos de retenção automaticamente, eles não entram em vigor imediatamente:
  
1. Primeiro, a política de rótulos precisa ser sincronizada desde o centro de administração até os locais na política.
    
2. Em seguida, o local pode precisar de tempo para disponibilizar rótulos de retenção publicados para os usuários finais ou para aplicar rótulos automaticamente ao conteúdo. Quanto tempo isso leva depende do local e do tipo de rótulo de retenção.
    
### <a name="published-retention-labels"></a>Rótulos de retenção publicados

Se você publicar rótulos de retenção no SharePoint ou no OneDrive, talvez demore um dia para que esses rótulos de retenção apareçam para os usuários finais. Além disso, se você publicar os rótulos de retenção no Exchange, talvez demore 7 dias para que eles apareçam para os usuários finais, e a caixa de correio deles deve conter pelo menos 10 MB de dados.
  
![Diagrama de quando os rótulos manuais entram em vigor](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>Aplicação automática de rótulos de retenção

Se você aplicar automaticamente rótulos de retenção a conteúdos que se encaixem em condições específicas, poderá levar sete dias para que os rótulos de retenção sejam aplicados a todo o conteúdo existente que se encaixe nas condições.
  
![Diagrama de quando a aplicação automática de rótulos entra em vigor](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Como verificar o status dos rótulos de retenção publicados no Exchange

No Exchange Online, os rótulos são disponibilizados para os usuários finais por um processo que é executado a cada sete dias. Usando o Powershell, você pode ver quando esse processo foi executado pela última vez e, assim, determinar quando ele será executado novamente.
  
1. [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. Execute estes comandos.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

Nos resultados, a propriedade `ELCLastSuccessTimeStamp` (UTC) mostra quando o sistema processou sua caixa de correio pela última vez. Se isso não tiver acontecido desde a hora em que você criou a política, os rótulos não serão exibidos. Para forçar o processamento, execute o  `Start-ManagedFolderAssistant -Identity <user>`.
    
Se os rótulos não estiverem aparecendo no Outlook na Web, e você achar que deveriam aparecer, limpe o cache do navegador (CTRL + F5).
    

## <a name="updating-retention-labels-and-their-policies"></a>Atualizar rótulos de retenção e suas políticas

Se você editar um rótulo de retenção, política de rótulo de retenção ou política de aplicação automática e o rótulo de retenção já estiver aplicado ao conteúdo, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo recentemente rotulado.

Algumas configurações não podem ser alteradas depois que o rótulo ou política é criado e salvo, que incluem:
- As configurações de retenção, exceto o período de retenção, a menos que você tenha configurado o rótulo para reter ou excluir o conteúdo com base em quando ele foi criado.
- A opção para classificar como um registro.

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a>Localizar os cmdlets do Windows PowerShell para rótulos de retenção

Para usar os cmdlets de rótulos de retenção:
  
1. [Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. Use esses cmdlets do Centro de Conformidade e Segurança do Office 365
    
    - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
