---
title: Criar e publicar rótulos de confidencialidade
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
description: 'Um requisito para todas as soluções de proteção de informações da Microsoft: criar, configurar e publicar rótulos de confidencialidade para classificar e proteger os documentos e emails da sua organização.'
ms.openlocfilehash: 50411e04ac04dc0bf00e7b743f3f30d25b9fa12e
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352208"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>Criar e configurar rótulos de confidencialidade e suas políticas

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Todas as soluções de proteção de informações da Microsoft (às vezes abreviadas para MIP) são implementadas usando [rótulos de sensibilidade](sensitivity-labels.md). Para criar e publicar seus rótulos de confidencialidade, vá para o centro de administração de rótulo, como o [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/). Você também pode usar o centro de segurança do Microsoft 365 ou o Centro de Conformidade e Segurança.

Primeiro, crie e configure os rótulos de confidencialidade que você deseja disponibilizar nos aplicativos e outros serviços. Por exemplo, os rótulos que você deseja que os usuários vejam e se apliquem a partir dos aplicativos do Office. 

Em seguida, crie uma mais políticas de rótulos que contenham os rótulos e as configurações de política que você configurar. É a política de rótulos que publica os rótulos e as configurações dos seus usuários e locais selecionados.

## <a name="before-you-begin"></a>Antes de começar

O administrador global da sua organização tem permissões completas para criar e gerenciar todos os aspectos de rótulos de sensibilidade. Se você não estiver entrando como um administrador global do, confira [permissões necessárias para criar e gerenciar os rótulos de confidencialidade](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).

## <a name="create-and-configure-sensitivity-labels"></a>Criar e configurar rótulos de confidencialidade

1. No centro de administração de rótulos, navegue até os rótulos de confidencialidade:
    
    - Centro de conformidade do Microsoft 365: 
        - **Proteção de Informações** > ** de soluções **
        
        Se você não vir essa opção imediatamente, selecione primeiro **Mostrar tudo**. 
    
    - Centro de segurança do Microsoft 365: 
        - **Rótulos de confidencialidade** > ** de Classificação**
    
    - Centro de Conformidade e Segurança:
        - **Rótulos de confidencialidade** > ** de Classificação**

2. Na guia **Rótulos**, selecione **+ Criar um rótulo** para iniciar o assistente **Novo rótulo de confidencialidade**.

3. Siga as notificações para as configurações de rótulo.
    
    Para saber mais sobre as configurações de rótulo, confira [O que rótulos de confidencialidade podem fazer](sensitivity-labels.md#what-sensitivity-labels-can-do) nas informações gerais.

4. Repita essas etapas para criar mais rótulos. Entretanto, se você deseja criar um subrótulo, selecione primeiro o rótulo pai e selecione **...** para **Mais ações** e selecione **Adicionar subrótulo**.

5. Quando você tiver criado todos os rótulos necessários, examine a ordem deles e, se necessário, mova-os para cima ou para baixo. Para alterar a ordem de um rótulo, selecione **...** para **Mais ações** e depois selecione **Mover para cima** ou **Mover para baixo**. Para saber mais, confira [Prioridade de rótulo (a ordem importa)](sensitivity-labels.md#label-priority-order-matters) nas informações gerais.

Para editar um rótulo existente, selecione-o e depois selecione **Editar rótulo**. Isso inicia o assistente **Editar rótulo de confidencialidade**, que permite que você altere todas as configurações de rótulo na etapa 3. 

> [!NOTE]
> Se você editar um rótulo que já foi publicado usando uma política de rótulo, etapas adicionais não serão necessárias quando você concluir o assistente. Por exemplo, não é necessário adicioná-lo a uma nova política de rótulos para que as alterações fiquem disponíveis para os mesmos usuários. No entanto, aguarde 24 horas para que as alterações sejam replicadas para usuários e serviços.

Até que você publique seus rótulos, eles não estarão disponíveis para seleção em aplicativos ou em serviços. Para publicar os rótulos, eles dever ser [adicionados a uma política de rótulos](#publish-sensitivity-labels-by-creating-a-label-policy).

> [!IMPORTANT]
> Na guia **Rótulos**, não selecione a guia **Publicar rótulos** (ou o botão **Publicar rótulo** ao editar um rótulo), a menos que você precise criar uma nova política de rótulo. Você precisará de várias políticas de rótulo somente se os usuários precisarem de rótulos diferentes ou configuracoes de política diferentes. Tenha como objetivo ter o menor número de rótulos possível; não é incomum ter apenas uma politica de rótulo para a organização.

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a>Configurações adicionais de rótulo com o PowerShell do Centro de Conformidade e Segurança

As configurações adicionais de rótulo estão disponíveis com o cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) do [PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Use o parâmetro *LocaleSettings* para implantações multinacionais, assim os usuários podem ver o nome do rótulo e a dica de ferramenta no idioma local. Confira a seção a seguir para conferir um exemplo de configuração. 

Usando esse cmdlet, você também pode especificar [configurações avançadas](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para o cliente de rotulagem unificada da Proteção de Informações do Azure. Essas configurações avançadas incluem a definição de uma cor de rótulo e a aplicação de uma propriedade personalizada quando um rótulo é aplicado. Para obter a lista completa, confira [Configurações avançadas disponíveis para as políticas de rótulo](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies). 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>Configuração de exemplo para configurar um rótulo de configurar em idiomas diferentes

O exemplo a seguir mostra a configuração do PowerShell para um rótulo chamado "Público" com o texto de espaço reservado para a dica de ferramenta. Neste exemplo, o nome do rótulo e o texto da dica de ferramenta estão configurados em francês, italiano e alemão.

Como resultado dessa configuração, os usuários com aplicativos do Office que usam tais idiomas de exibição verão seus nomes de etiqueta e as dicas de ferramentas no mesmo idioma. Da mesma forma, se você tiver o cliente de rotulagem unificado da Proteção de Informações do Azure instalado para rotular arquivos do Explorador de Arquivos, os usuários que tiverem essas versões de idioma do Windows verão os nomes de etiqueta e as dicas de ferramenta no idioma local deles quando usarem o clique com o botão direito do mouse para rotular.

Para os idiomas para os quais você precisa oferecer suporte, use os [identificadores de idiomas](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) do Office (também conhecidos como marcas de idioma) e especifique a sua própria tradução para o rótulo e para a dica de ferramenta.

Antes de executar os comandos no PowerShell, você dever primeiro [conectar-se com o Centro de Segurança e Conformidade do PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>Publicar rótulos de confidencialidade criando uma política de rótulo

1. No centro de administração de rótulos, navegue até os rótulos de confidencialidade:
    
    - Centro de conformidade do Microsoft 365: 
        - **Proteção de Informações** > ** de soluções **
        
        Se você não vir essa opção imediatamente, selecione primeiro **Mostrar tudo**. 
    
    - Centro de segurança do Microsoft 365: 
        - **Rótulos de confidencialidade** > ** de Classificação**
    
    - Centro de Conformidade e Segurança:
        - **Rótulos de confidencialidade** > ** de Classificação**

2. Selecione a guia **Políticas de rótulo**.

3. Selecione **Publicar rótulos** para iniciar o **Assistente de criação de política**.

4. Selecione **Escolher rótulos de confidencialidade para publicar**. Selecione os rótulos que você deseja disponibilizar nos aplicativos e serviços, e selecione **Adicionar**.
    
    Se você selecionar um subrótulo, certifique-se de também selecionar seu rótulo pai.
    
5. Examine os rótulos selecionados, e para fazer alterações, selecione **Editar**. Caso contrário, selecione **Próximo**.

6. Siga as notificações para definir as configurações de política.
    
    Para obter mais informações sobre essas configurações, confira [O que as políticas de rótulo podem fazer](sensitivity-labels.md#what-label-policies-can-do) nas informações gerais.

7. Repita essas etapas se você precisar de configurações de política para usuários ou locais diferentes. Por exemplo, você deseja rótulos adicionais para um grupo de usuários ou um rótulo padrão diferente para um subconjunto de usuários.

8. Se você criar mais de uma política de rótulo que pode resultar em um conflito para um usuário ou local, examine a ordem das políticas e, se necessário, mova-as para cima ou para baixo. Para alterar a ordem de uma política de rótulo, selecione **...** para **Mais ações** e depois selecione **Mover para cima** ou **Mover para baixo**. Para saber mais, confira [Prioridade das políticas de rótulo (a ordem é importante)](sensitivity-labels.md#label-policy-priority-order-matters) nas informações gerais.

Concluir o assistente publica automaticamente a política de rótulo. Para fazer alterações em uma política publicada, basta editá-la. Não há uma ação específica de publicação ou republicação para selecionar.

Para editar uma política de rótulo existente, selecione-a e, em seguida, selecione **Editar Política**. Isso inicia o assistente **Criar política**, que permite editar quais rótulos estão incluídos e as configurações de rótulo. Quando você concluir o assistente, todas as alterações serão replicadas automaticamente para os usuários e serviços selecionados.

Normalmente, os usuários veem os rótulos em seus aplicativos do Office dentro de algumas horas. No entanto, aguarde 24 para que as políticas de rótulo e as alterações feitas nelas sejam replicadas para todos os usuários e serviços.

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a>Configurações adicionais de políticas de rótulo com o PowerShell do Centro de Conformidade e Segurança

As configurações adicionais de políticas de rótulo estão disponíveis com o cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/set-label?view=exchange-ps) do [PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Usando esse cmdlet, você pode especificar [configurações avançadas](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para o cliente de rotulagem unificada da Proteção de Informações do Azure. Essas configurações avançadas incluem a configuração de um rótulo padrão diferente para o Outlook e implementam mensagens pop-up no Outlook que avisam, justificam ou bloqueiam os emails enviados. Para obter a lista completa, confira [Configurações avançadas disponíveis para rótulos](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels). 

Você também pode usar esse cmdlet para adicionar e remover rótulos de e para uma política de rótulo.

## <a name="removing-and-deleting-labels"></a>Remover e excluir rótulos

Em um ambiente de produção, é improvável que você precise remover ou excluir rótulos de confidencialidade de uma política de rótulo. É mais provável que você precise fazer uma dessas ações durante uma fase de testes inicial. Certifique-se de entender o que acontece ao fazer qualquer uma dessas ações.

É menos arriscado remover um rótulo de uma política de rótulo do que eliminá-lo, e sempre será possível adicioná-lo novamente, se necessário:

- Ao remover um rótulo de uma política de rótulo para que ele não seja mais publicado para os usuários especificados originalmente, da próxima vez que a política for atualizada, os usuários não o verão mais no aplicativo do Office. No entanto, se o rótulo foi aplicado a documentos ou emails, ele não é removido desse conteúdo. Qualquer criptografia aplicada pelo rótulo permanecerá e o modelo de proteção subjacente permanecerá publicado. 

- Para rótulos removidos mas que foram previamente aplicados ao conteúdo, os usuários que usam rótulos internos para Word, Excel e PowerPoint, ainda verão o nome do rótulo aplicado na barra de status. Da mesma forma, os rótulos removidos que foram aplicados aos sites do SharePoint ainda exibem o nome do rótulo na coluna **Confidencialidade**.

Em comparação, ao excluir um rótulo:

- Se uma criptografia foi aplicada pelo rótulo, o modelo de proteção subjacente é arquivado para que o conteúdo previamente protegido ainda possa ser aberto. Devido a esse modelo de proteção arquivado, não será possível criar uma novo rótulo com o mesmo nome. Embora seja possível excluir um modelo de proteção usando o [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), não faça isso, a menos que tenha certeza de que não precisará abrir conteúdos criptografados com o modelo arquivado.

- Para aplicativos da área de trabalho: as informações do rótulo nos metadados permanecem, mas como não será mais possível usar uma ID de rótulo para mapeamento de nomes, os usuários não verão o nome do rótulo aplicado (por exemplo, na barra de status), então os usuários assumirão que o conteúdo não foi rotulado. Se uma criptografia foi aplicada pelo rótulo, a criptografia permanecerá e quando o conteúdo for aberto, os usuários ainda verão o nome e a descrição do modelo de proteção agora arquivado.

- Para o Office na Web: os usuários não verão o nome do rótulo na barra de status ou na coluna **Confidencialidade**. As informações do rótulo nos metadados permanecem somente se o ele não tiver aplicado criptografia. Se uma criptografia foi aplicada pelo rótulo e você habilitou [rótulos de confidencialidade para o SharePoint e o Onedrive](sensitivity-labels-sharepoint-onedrive-files.md), as informações do rótulo nos metadados serão removidos e a criptografia será removida. 

## <a name="next-steps"></a>Próximas etapas

Para configurar e usar seus rótulos de confidencialidade em cenários específicos, use os seguintes artigos:

- [Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade](encryption-sensitivity-labels.md)

- [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)

- [Usar rótulos de confidencialidade para equipes, grupos e sites](sensitivity-labels-teams-groups-sites.md)

- [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)

Para monitorar como os rótulos estão sendo usados, confira [Exibir uso do rótulo com análise de rótulo](label-analytics.md).
