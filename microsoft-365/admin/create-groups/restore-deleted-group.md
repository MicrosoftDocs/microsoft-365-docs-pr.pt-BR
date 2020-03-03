---
title: Restaurar um Grupo do Office 365 excluído
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Saiba como restaurar um grupo excluído do Office 365 usando o centro de administração do Exchange. '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352432"
---
# <a name="restore-a-deleted-office-365-group"></a>Restaurar um Grupo do Office 365 excluído

Se você for o proprietário de um grupo do Office 365, poderá restaurar o grupo seguindo estas etapas.

1. Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.
2. Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.

Se o grupo excluído não aparecer aqui, entre em contato com um administrador.
  
Se você for um usuário que deseja restaurar um grupo do Office 365, peça ao administrador para executar estas etapas ou entrar em contato com o suporte técnico.  
   
Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão. Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.
  
Durante o período de "exclusão reversível", se um usuário tentar acessar o site, ele receberá uma mensagem de _proibido_ 404. Após esse período, se um usuário tentar acessar o site, ele receberá uma mensagem 404 _não encontrada_ .
  
Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:
  
- Azure Active Directory (AD) grupos do Office 365, propriedades e membros.
    
- Endereços de email do grupo.
    
- Calendário e caixa de entrada compartilhada do Exchange Online.
    
- Arquivos e site de equipe do SharePoint Online.
    
- Bloco de anotações do OneNote
    
- Planner
    
- Teams

- Grupo e conteúdo de grupo do Yammer (se o grupo do Office 365 foi criado a partir do Yammer)
    
Você também pode [Excluir permanentemente um grupo do Office 365](#permanently-delete-an-office-365-group) caso não possa esperar os 30 dias do período de retenção para que o conteúdo seja excluído permanentemente. 

> [!NOTE]
> O proprietário do grupo do Office 365 excluído também é capaz de restaurar o grupo. Para restaurar um grupo do Office 365 usando permissão de proprietário sem permissão de administrador, confira [restaurar um grupo do office 365 usando o PowerShell](#restore-an-office-365-group-using-powershell).

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>Restaurar um grupo do Office 365 usando o Centro de administração do Exchange

Você deve ter permissões de administrador global do Office 365.

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
    
2. No Centro de administração do Exchange, selecione **destinatários** e escolha **grupos**. Você pode ver se o grupo está ativo ou excluído de forma reversível. Se o grupo tiver sido excluído permanentemente, ele não aparecerá na lista.
  
3. Para exibir o horário exato em que o grupo foi excluído por software, selecione o grupo e exiba as informações no painel direito.
      
4. Selecione o grupo que você deseja restaurar e, em seguida, selecione o ícone restaurar.
    
    ![Escolha o grupo que você deseja restaurar e, em seguida, selecione o ícone restaurar.](../../media/restore-group.png)
  
5. Selecionar atualizar ![Ícone Atualizar](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) para atualizar as informações na página. Seu grupo será exibido como Ativo. Todos os formulários e dados de formulário associados ao grupo também serão restaurados.
    
## <a name="restore-an-office-365-group-using-powershell"></a>Restaurar um grupo do Office 365 usando o PowerShell

Você deve ter permissões de administrador global do Office 365 ou ser um antigo proprietário do grupo do Office 365 excluído.

> [!IMPORTANT]
> Se você usar remove-MsolGroup no PowerShell para excluir um grupo, isso excluirá o grupo permanentemente. Ao usar o PowerShell para excluir grupos, é recomendável usar **Remove-AzureADMSGroup** para excluir o grupo do Office365 temporariamente. Assim você poderá recuperá-lo caso necessário. 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Instalar a versão de visualização do PowerShell do Azure Active Directory para Graph

> [!IMPORTANT]
> Não é possível instalar as versões de visualização e GA no mesmo computador ao mesmo tempo.
  
Como prática recomendada, recomendamos *sempre* permanecer atualizado, ou seja, desinstalar o antigo AzureADPreview ou a versão antiga do AzureAD e obter o mais recente. 
  
 
1. Na barra de pesquisa, digite Windows PowerShell.
    
2. Clique com o botão direito do mouse em **Windows PowerShell** e selecione **Executar como administrador**.
  
2. Revise seus módulos instalados:
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. Para desinstalar a versão anterior do AzureADPreview ou do AzureAD, execute o seguinte comando:
  
```
   Uninstall-Module AzureADPreview
```

ou
  
```
   Uninstall-Module AzureAD
```

4. To install the latest version of AzureADPreview, run this command:
  
```
   Install-Module AzureADPreview
```



At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 
  
### <a name="restore-the-deleted-group"></a>Restaure o grupo excluído
  
1. Você instalou o módulo **AzureADPreview** , conforme instruído na seção previoius "instalar a versão de visualização do módulo do Azure Active Directory para Windows PowerShell"?  Não ter a versão de **visualização** mais recente é o principal motivo pelo qual esses procedimentos não funcionam. 
    
2. Se ainda não o fez, abra uma janela do Windows PowerShell no seu computador (não importa se for uma janela normal do Windows PowerShell ou uma que você abriu selecionando **Executar como administrador**).
    
3. Execute os seguintes comandos pressionando **Enter** depois de cada um: 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  Na tela **entrar na sua conta** que é aberta, insira seu nome de usuário e senha da conta administrativa para conectá-lo ao seu serviço do Azure AD e selecione **entrar**.
  
4. Execute este comando para exibir todos os grupos do Office 365 excluídos por software em sua organização que ainda estejam dentro do período de exclusão reversível de 30 dias:
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. Anote a ID de objeto do grupo, ou grupos, que você deseja restaurar. Se você não vir o grupo que está procurando nessa lista, provavelmente ele já foi descartado permanentemente.
    
    > [!CAUTION]
    > Se um novo grupo tiver sido criado com o mesmo alias ou endereço SMTP do grupo excluído, será necessário excluir esse novo grupo antes que você possa restaurar o grupo excluído. 
  
6. Para restaurar esse grupo, execute este comando:
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. Esse processo geralmente leva apenas alguns minutos, mas em alguns casos raros, pode levar até 24 horas para ser totalmente restaurado. Para verificar se o grupo foi restaurado, execute este comando no PowerShell:
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

Após a restauração ser concluída, o grupo deverá reaparecer no painel de navegação no Outlook e no Outlook na Web. Todo o conteúdo restaurado, inclusive o SharePoint e o Planner, deverá estar disponível para os membros do grupo novamente.
  
## <a name="permanently-delete-an-office-365-group"></a>Excluir permanentemente um grupo do Office 365

Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire. Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:
  
```
Get-AzureADMSDeletedGroup
```

Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.
  
> [!CAUTION]
> Ao limpar o grupo, você removerá o grupo e os dados nele para sempre. 
  
Para limpar o grupo, execute o seguinte comando no PowerShell:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente. 
  
## <a name="got-questions-about-office-365-groups"></a>Você tem dúvidas sobre os Grupos do Office 365?

Visite a [comunidade de tecnologia da Microsoft](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre grupos do Office 365. 
  
## <a name="related-articles"></a>Artigos relacionados

[Gerenciar Grupos do Office 365 com o PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Excluir grupos usando o cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Gerenciar as configurações do site de equipe conectado ao grupo](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Excluir um grupo no Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
