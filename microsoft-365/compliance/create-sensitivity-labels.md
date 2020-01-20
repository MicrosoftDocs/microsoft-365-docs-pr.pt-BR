---
title: Criar e publicar rótulos de confidencialidade
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
description: Instruções para criar, configurar e publicar rótulos de confidencialidade para classificar e proteger os documentos e emails da sua organização.
ms.openlocfilehash: edcfcf5a4f4891e4e1159c4c42327e59ceb35449
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238398"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>Criar e configurar rótulos de confidencialidade e suas políticas

Para criar e publicar seus [rótulos de confidencialidade](sensitivity-labels.md), vá para o centro de administração de rótulos, como o [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/). Você também pode usar o centro de segurança do Microsoft 365 ou o Centro de Conformidade e Segurança do Office 365.

Primeiro, crie e configure os rótulos de confidencialidade que você deseja disponibilizar nos aplicativos do Office e para serviços. Em seguida, crie uma mais políticas de rótulos que contenham os rótulos e as configurações de política que você configurar. É a política de rótulos que publica os rótulos e as configurações dos seus usuários e locais selecionados.

## <a name="create-and-configure-sensitivity-labels"></a>Criar e configurar rótulos de confidencialidade

1. No centro de administração de rótulos, navegue até os rótulos de confidencialidade:
    
    - Centro de conformidade do Microsoft 365: 
        - **Proteção de Informações** > ** de soluções (versão prévia)**
        
        Se você não vir essa opção imediatamente, selecione primeiro **Mostrar tudo**. 
    
    - Centro de segurança do Microsoft 365: 
        - **Rótulos de confidencialidade** > ** de Classificação**
    
    - Centro de Conformidade e Segurança do Office 365:
        - **Rótulos de confidencialidade** > ** de Classificação**

2. Na guia **Rótulos**, selecione **+ Criar um rótulo** para iniciar o assistente **Novo rótulo de confidencialidade**.

3. Siga as notificações para as configurações de rótulo.
    
    Para saber mais sobre as configurações de rótulo, confira [O que rótulos de confidencialidade podem fazer](sensitivity-labels.md#what-sensitivity-labels-can-do) nas informações gerais.

4. Repita essas etapas para criar mais rótulos. Entretanto, se você deseja criar um sub-rótulo, selecione primeiro o rótulo pai e selecione **...** para **Mais ações** e selecione **Adicionar sub-rótulo**.

5. Quando você tiver criado todos os rótulos necessários, examine a ordem deles e, se necessário, mova-os para cima ou para baixo. Para alterar a ordem de um rótulo, selecione **...** para **Mais ações** e depois selecione **Mover para cima** ou **Mover para baixo**. Para saber mais, confira [Prioridade de rótulo (a ordem importa)](sensitivity-labels.md#label-priority-order-matters) nas informações gerais.

Para editar um rótulo existente, selecione-o e depois selecione **Editar rótulo**. Isso inicia o assistente **Editar rótulo de confidencialidade**, que permite que você altere todas as configurações de rótulo na etapa 3. Se o rótulo já tiver sido publicado usando uma política de rótulo, não serão necessárias etapas adicionais, mas aguarde 24 horas para que as alterações serem replicadas para usuários e locais.

Até que você publique seus rótulos, eles não estarão disponíveis para seleção em aplicativos ou para serviços. Para publicar os rótulos, eles devem ser adicionados a uma política de rótulo.

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Configurações adicionais de rótulo com o PowerShell do Centro de Conformidade e Segurança do Office 365.

As configurações adicionais de rótulo estão disponíveis com o cmdlet de [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) do [PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Por exemplo, use o parâmetro *LocaleSettings* para especificar idiomas diferentes para seus nomes de rótulo e dicas de ferramenta. 

Usando esse cmdlet, você também pode especificar [configurações avançadas](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para o cliente de rotulagem unificada da Proteção de Informações do Azure. Essas configurações avançadas incluem a definição de uma cor de rótulo e a aplicação de uma propriedade personalizada ao aplicar um rótulo. Para obter a lista completa, confira [Configurações avançadas disponíveis para as políticas de rótulo](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies). 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>Publicar rótulos de confidencialidade criando uma política de rótulo

1. No centro de administração de rótulos, navegue até **Rótulos de confidencialidade** > **de Classificação**.

2. Selecione a guia **Políticas de rótulo**.

3. Selecione **Publicar rótulos** para iniciar o **Assistente criar política**.

4. Selecione **Escolher rótulos de confidencialidade para publicar**. Selecione os rótulos que você deseja disponibilizar nos aplicativos e para serviços e selecione **Adicionar**.

5. Examine os rótulos selecionados e para fazer alterações, selecione **Editar**. Caso contrário, selecione **Próximo**.

6. Siga as notificações para configurar as configurações de política.
    
    Para obter mais informações sobre as configurações, confira [O que as políticas de rótulo podem fazer](sensitivity-labels.md#what-label-policies-can-do) nas informações gerais.

7. Repita essas etapas se você precisar de configurações de política para usuários ou locais diferentes. Por exemplo, você deseja rótulos adicionais para um grupo de usuários ou um rótulo padrão diferente para um subconjunto de usuários.

8. Se você criar mais de uma política de rótulo que pode resultar em um conflito para um usuário ou local, examine a ordem das políticas e, se necessário, mova-as para cima ou para baixo. Para alterar a ordem de uma política de rótulo, selecione **...** para **Mais ações** e depois selecione **Mover para cima** ou **Mover para baixo**. Para saber mais, confira [Prioridade das políticas de rótulo (a ordem é importante)](sensitivity-labels.md#label-policy-priority-order-matters) nas informações gerais.

Concluir o assistente publica automaticamente a política de rótulo. Para fazer alterações em uma política publicada, basta editá-la. Não há uma ação específica de publicação ou republicação para selecionar.

Para editar uma política de rótulo existente, selecione-a e depois selecione **Editar Política**. Isso inicia o assistente **Criar política**, que permite editar quais rótulos estão incluídos e as configurações de rótulo. Quando você concluir o assistente, todas as alterações serão replicadas automaticamente para os usuários e locais selecionados. Aguarde 24 para que a replicação seja concluída.

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Configurações adicionais de política de rótulo com o PowerShell do Centro de Conformidade e Segurança do Office 365

As configurações adicionais de política de rótulo estão disponíveis no cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) do [PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Usando esse cmdlet, você pode especificar [configurações avançadas](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para o cliente de rotulagem unificada da Proteção de Informações do Azure. Essas configurações avançadas incluem a definição de um rótulo padrão para o Outlook e a implementação de mensagens pop-up no Outlook que alertam, justificam ou bloqueio emails enviados. Para obter a lista completa, confira [Configurações avançadas disponíveis para rótulos](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels). 

Você também pode usar esse cmdlet para adicionar e remover rótulos de e para uma política de rótulo.


## <a name="next-steps"></a>Próximas etapas

Para configurar e usar seus rótulos de confidencialidade em cenários específicos, confira os seguintes artigos:

- [Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade](encryption-sensitivity-labels.md)

- [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](apply-sensitivity-label-automatically.md)

- [Usar rótulos de confidencialidade para equipes, grupos e sites](sensitivity-labels-teams-groups-sites.md)

- [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)

Para monitorar como os rótulos estão sendo usados, confira [Exibir uso do rótulo com análise de rótulo](label-analytics.md).