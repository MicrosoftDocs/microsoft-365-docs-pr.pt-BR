---
title: Preparar unidades mapeadas para a área de trabalho gerenciada da Microsoft
description: Etapas importantes para garantir
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e4c2dbe8f1cae12aa1b10c6cd43f295a9a6062d0
ms.sourcegitcommit: 8102751ae20c93439e19afded396c4e6ee5ea5a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2019
ms.locfileid: "34100707"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparar unidades mapeadas para a área de trabalho gerenciada da Microsoft

Muitos ambientes corporativos têm requisitos herdados para unidades mapeadas para permitir que seus usuários ou equipes compartilhem e armazenem arquivos ou para aplicativos locais. A Microsoft não recomenda o uso de unidades mapeadas com a área de trabalho gerenciada da Microsoft. Em vez disso, recomendamos modernizar as soluções de acesso de arquivos do yor da seguinte maneira:
  
- Migrar unidades mapeadas usadas por usuários individuais para o OneDrive for Business. 
- Migrar unidades mapeadas usadas pelo Teams para compartilhar arquivos com o SharePoint Online. 
- Modernizar ou substituir qualquer aplicativo que use compartilhamentos de arquivos locais para remover esse requisito.
  
A modernização desses serviços permitirá a melhor experiência do usuário final com a área de trabalho gerenciada da Microsoft. Os serviços do Microsoft FastTrack podem ajudá-lo a modernizar seu ambiente usando os serviços em nuvem da Microsoft. Você pode verificar se está qualificado para serviços do FastTrack em [serviços e planos qualificados](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) e, em seguida, contatá-los diretamente para se preparar para a área de trabalho gerenciada da Microsoft. Para obter informações sobre a migração do FastTrack OneDrive for Business ou do SharePoint Online, consulte [migração de dados](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades mapeadas na área de trabalho gerenciada da Microsoft
 
Se você não puder remover ou substituir unidades mapeadas para alguns casos de uso, envie uma solicitação de suporte no portal de administração de área de trabalho gerenciada da Microsoft para que eles sejam implantados em usuários de área de trabalho gerenciada da Microsoft.
    
Para tal solicitação, você precisará fornecer os seguintes detalhes na solicitação de suporte: 

- Todos os caminhos UNC para locais de compartilhamento de arquivos que precisarão ser mapeados para os dispositivos de área de trabalho gerenciada da Microsoft 
- Grupos de usuários que exigem acesso a esses locais de compartilhamento de arquivos 
- Qualquer letra de unidade específica que precisa ser atribuída (se necessário)

Por exemplo:

| Letra da unidade | Caminho UNC | Grupo de usuários |
|--------------|----------|------------|
| X  | \\\server\share\Marketing | ContosoMarketing |

É inteiramente sua responsabilidade garantir que os usuários e grupos tenham e mantenha as permissões corretas para acessar locais de compartilhamento de arquivos e que os serviços de arquivos locais permaneçam acessíveis. Além disso, você deve remover os requisitos desses compartilhamentos de arquivos o mais rápido possível.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para ter unidades mapeadas implantadas na área de trabalho gerenciada da Microsoft
 
Verifique se as unidades mapeadas não podem ser evitadas e se você analisou cuidadosamente os requisitos antes de enviar qualquer solicitação de serviço. Siga estas etapas:

1. Navegue até o [portal de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).  
2. Envie uma solicitação de suporte intitulada "implantação de unidades mapeadas" por meio da seção de suporte de **solicitações de suporte >** e forneça todos os detalhes necessários do compartilhamento de arquivos.  
3. As operações de ti de área de trabalho gerenciada da Microsoft avisarão usando as atualizações de solicitação de suporte, quando a solicitação tiver sido concluída. Inicialmente, essa configuração só será implantada em dispositivos no grupo de implantação de teste.  
4. Você deve testar e confirmar se a configuração implantada pelas operações de ti de área de trabalho gerenciada da Microsoft funciona conforme o esperado. Responda usando a guia discussão na solicitação de suporte para notificar as operações de ti de área de trabalho gerenciada da Microsoft depois de concluir o teste.  
5. A equipe de operações de ti de área de trabalho gerenciada da Microsoft implantará a configuração em outros grupos de implantação. 
