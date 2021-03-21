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
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922903"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Prepare as unidades mapeadas da Área de trabalho gerenciada da Microsoft

Muitos ambientes corporativos têm requisitos herdados para unidades mapeadas para permitir que seus usuários ou equipes compartilhem e armazenem arquivos ou para aplicativos locais. A Microsoft não recomenda o uso de unidades mapeadas com a Área de Trabalho Gerenciada da Microsoft. Em vez disso, recomendamos modernizar suas soluções de acesso a arquivos da seguinte forma:
  
- Migrar unidades mapeadas usadas por usuários individuais para o OneDrive for Business. 
- Migrar unidades mapeadas usadas pelas equipes para compartilhar arquivos no SharePoint Online. 
- Modernize ou substitua todos os aplicativos que usam compartilhamentos de arquivos locais para remover esse requisito.
  
A modernização desses serviços permitirá a melhor experiência do usuário com a Área de Trabalho Gerenciada da Microsoft. O Microsoft FastTrack Services pode ajudá-lo a modernizar seu ambiente usando o Microsoft Cloud Services. Você pode verificar se está qualificado para serviços do FastTrack em [Serviços](/fasttrack/m365-eligible-services-and-plans) e Planos Qualificados e entrar em contato diretamente com eles para se preparar para a Área de Trabalho Gerenciada da Microsoft. Para saber mais sobre o FastTrack OneDrive for Business ou a Migração do SharePoint Online, consulte [Migração de Dados](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unidades mapeadas na Área de Trabalho Gerenciada da Microsoft
 
Se você não puder remover ou substituir unidades mapeadas para alguns casos de uso, envie uma solicitação de suporte no portal de administração da Área de Trabalho Gerenciada da Microsoft para que elas tenham sido implantadas para usuários da Área de Trabalho Gerenciada da Microsoft.
    
Para essa solicitação, você terá que fornecer os seguintes detalhes na solicitação de suporte: 

- Todos os caminhos UNC para locais de compartilhamento de arquivos que precisarão ser mapeados para dispositivos da Área de Trabalho Gerenciada da Microsoft 
- Grupos de usuários que exigem acesso a esses locais de compartilhamento de arquivos 
- Qualquer letra de unidade específica que precise ser atribuída (se necessário)

Por exemplo:

| Letra da unidade | Caminho UNC | Grupo de usuários |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

É inteiramente sua responsabilidade garantir que os usuários e grupos tenham e mantenham as permissões corretas para acessar locais de compartilhamento de arquivos e que os serviços de arquivos locais permaneçam acessíveis. Além disso, você deve remover seus requisitos para compartilhamentos de arquivos assim que possível.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Para ter unidades mapeadas implantadas na Área de Trabalho Gerenciada da Microsoft
 
Certifique-se de que as unidades mapeadas não podem ser evitadas e você reviu cuidadosamente os requisitos antes de enviar qualquer solicitação de serviço. Em seguida, siga estas etapas:

1. Navegue [até o Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e selecione "Solução de problemas + suporte" e procure "Solicitações de serviço" na seção Área de Trabalho Gerenciada da Microsoft.  
2. Envie uma solicitação de suporte intitulada "Implantação de unidades mapeadas" e forneça todos os detalhes de compartilhamento de arquivos necessários.  
3. As Operações de IT da Área de Trabalho Gerenciada da Microsoft aconselharão, usando atualizações de solicitação de suporte, quando a solicitação for concluída. Inicialmente, essa configuração só será implantada em dispositivos no grupo de implantação de teste.  
4. Você deve testar e confirmar se a configuração implantada pelas Operações de TI da Área de Trabalho Gerenciada da Microsoft funciona conforme o esperado. Responder usando a guia Discussão nos detalhes da mesma solicitação de suporte para notificar as Operações de TI da Área de Trabalho Gerenciada da Microsoft depois de concluir o teste.  
5. A equipe de Operações de ÁREA de Trabalho Gerenciada da Microsoft implantará a configuração para os outros grupos de implantação.