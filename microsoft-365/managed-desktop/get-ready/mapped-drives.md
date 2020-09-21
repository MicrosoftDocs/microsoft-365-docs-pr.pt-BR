---
title: Prepare as unidades mapeadas da Área de trabalho gerenciada da Microsoft
description: Etapas importantes para garantir
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104589"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Prepare as unidades mapeadas da Área de trabalho gerenciada da Microsoft

Muitos ambientes corporativos têm requisitos herdados para unidades mapeadas para permitir que seus usuários ou equipes compartilhem e armazenem arquivos ou para aplicativos locais. A Microsoft não recomenda o uso de unidades mapeadas com a área de trabalho gerenciada da Microsoft. Em vez disso, recomendamos que você Modernize suas soluções de acesso a arquivos da seguinte maneira:
  
- Migrar unidades mapeadas usadas por usuários individuais para o OneDrive for Business. 
- Migrar unidades mapeadas usadas pelo Teams para compartilhar arquivos com o SharePoint Online. 
- Modernizar ou substituir qualquer aplicativo que use compartilhamentos de arquivos locais para remover esse requisito.
  
A modernização desses serviços permitirá a melhor experiência do usuário com a área de trabalho gerenciada da Microsoft. Os serviços do Microsoft FastTrack podem ajudá-lo a modernizar seu ambiente usando os serviços em nuvem da Microsoft. Você pode verificar se está qualificado para serviços do FastTrack em [serviços e planos qualificados](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) e, em seguida, contatá-los diretamente para se preparar para a área de trabalho gerenciada da Microsoft. Para obter informações sobre a migração do FastTrack OneDrive for Business ou do SharePoint Online, consulte [migração de dados](https://docs.microsoft.com/fasttrack/o365-data-migration).

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

1. Navegue até [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e selecione "solução de problemas + suporte" e procure por "solicitações de serviço" na seção Microsoft Managed deskop.  
2. Envie uma solicitação de suporte intitulado "implantação de unidades mapeadas" e forneça todos os detalhes de compartilhamento de arquivos necessários.  
3. As operações de ti de área de trabalho gerenciada da Microsoft avisarão usando as atualizações de solicitação de suporte, quando a solicitação tiver sido concluída. Inicialmente, essa configuração só será implantada em dispositivos no grupo de implantação de teste.  
4. Você deve testar e confirmar se a configuração implantada pelas operações de ti de área de trabalho gerenciada da Microsoft funciona conforme o esperado. Responda usando a guia discussão nos detalhes da mesma solicitação de suporte para notificar as operações de ti de área de trabalho gerenciada pela Microsoft após a conclusão do teste.  
5. A equipe de operações de ti de área de trabalho gerenciada da Microsoft implantará a configuração em outros grupos de implantação. 
