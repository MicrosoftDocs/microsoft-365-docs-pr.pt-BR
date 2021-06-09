---
title: Configurações configuráveis para Área de Trabalho Gerenciada da Microsoft
description: Informações sobre configurações configuráveis com Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, configurações, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371485"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Configurações que podem ser alteradas – Área de Trabalho Gerenciada da Microsoft

Área de Trabalho Gerenciada da Microsoft implanta configurações e políticas que são aplicadas a todos os dispositivos gerenciados por Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Configuração do dispositivo](../service-description/device-policies.md).

As configurações configuráveis no Área de Trabalho Gerenciada da Microsoft dão aos administradores de IT uma maneira de personalizar e implantar configurações exclusivas para suas necessidades de organização e negócios. Essas configurações são além das configurações do dispositivo e das políticas gerenciadas por Área de Trabalho Gerenciada da Microsoft.  

As alterações de configuração configuráveis são feitas na nuvem e aplicadas aos dispositivos Área de Trabalho Gerenciada da Microsoft em grupos de implantação definidos. Esse processo é semelhante à forma como o Área de Trabalho Gerenciada da Microsoft gerencia as alterações nas configurações do dispositivo e nas políticas definidas e gerenciadas pelo serviço. Usando o mesmo processo que Área de Trabalho Gerenciada da Microsoft para implantar alterações, você continua a mover sua organização para frente, usando práticas modernas de gerenciamento de TI.

## <a name="when-to-use-configurable-settings"></a>Quando usar configurações configuráveis?

Há algumas vezes para usar configurações configuráveis. 

**Processo de** integração – Área de Trabalho Gerenciada da Microsoft recomenda que você personalize as configurações configuráveis quando você integra o serviço Área de Trabalho Gerenciada da Microsoft ou quando você integra um grande número de dispositivos (20 ou mais). As categorias de configuração são configuradas Área de Trabalho Gerenciada da Microsoft portal de administração. Depois de entrar e ter acesso ao portal de administração, você pode decidir quais categorias de configuração deseja personalizar para sua organização, fazer as alterações, preparar uma implantação e implantar suas alterações.

**Manter configurações** - Revise suas configurações regularmente e faça as atualizações necessárias. Talvez seja necessário fazer alterações para dar suporte a uma mudança em sua empresa.   

## <a name="setting-categories"></a>Definindo categorias

Estas são as categorias de configurações configuráveis que você pode personalizar:
- [Imagem em segundo plano da](config-setting-ref.md#desktop-background-picture) área de trabalho – Personalize a imagem de plano de fundo da área de trabalho para Área de Trabalho Gerenciada da Microsoft dispositivos. 
- [Páginas de início do navegador](config-setting-ref.md#browser-start-pages) – Adicione páginas in-locar para usar com Microsoft Edge. Consulte Página inicial do navegador
- [Enterprise de site de modo](config-setting-ref.md#enterprise-mode-site-list-location) – Adicionar sites e seu modo de compatibilidade. Os sites na lista começarão no Internet Explorer. 
- [Sites confiáveis](config-setting-ref.md#trusted-sites) – Adicione sites confiáveis e desmarcar zonas de segurança para cada site. 
- [Exceções de site de](config-setting-ref.md#proxy) proxy – Configurar o número de endereço do servidor proxy e o número da porta e adicionar exceções de site de proxy.

Cada categoria de configuração pode ser personalizada e implantada por conta própria. Você pode implantar alterações em várias categorias de configuração ao mesmo tempo, no entanto, você só pode implantar uma alteração de cada vez em uma categoria de configuração.

Por exemplo:
- Você pode implantar alterações na imagem em segundo plano da área de trabalho e em sites confiáveis, cada um como sua própria implantação, ao mesmo tempo. 
- Não é possível implantar duas implantações nas páginas in- locar do navegador ao mesmo tempo. A implantação mais recente interromperá implantações anteriores que ainda estão em andamento.

## <a name="configurable-setting-process"></a>Processo de configuração configurável

Área de Trabalho Gerenciada da Microsoft recomenda seguir um processo semelhante ao seguinte ao utilizar configurações configuráveis para sua organização:

**Etapa 1 - Planejar** - Saiba mais sobre configurações configuráveis e decida quais categorias de configuração você deseja configurar para sua organização. Crie uma linha do tempo para quando você espera implantar alterações em cada grupo. Planeje a comunicação com seus usuários que atendam aos processos internos de gerenciamento de alterações. Por exemplo, se você estiver adicionando páginas de início do navegador, avise aos usuários que eles terão um novo conjunto de páginas in-locar no navegador após a implantação.  

**Etapa 2 - Configurar e implantação de estágio** - Fazer alterações nas configurações configuráveis no Área de Trabalho Gerenciada da Microsoft de administração. Stage the changes so they're ready to deploy. Lembre-se de deixar seus usuários saberem sobre as alterações e como as alterações alterarão a experiência do dispositivo.   

Você configura e em estágios as alterações no portal Área de Trabalho Gerenciada da Microsoft administrador. Para obter mais informações, consulte [Personalizar configurações configuráveis](config-setting-ref.md). 

**Etapa 3 - Comunicar alterações** Comunicar informações sobre as próximas alterações aos seus usuários. Para cada implantação, conclua a comunicação que faz parte de seus processos de gerenciamento de alterações. Você deve comunicar claramente qualquer alteração que impacte na forma como um usuário funciona ou o que ele verá em seus dispositivos.

**Etapa 4 - Implantar alterações** – Implantar suas alterações, começando com o grupo Teste. O grupo Test permite validar e solucionar problemas em um grupo com menos dispositivos, antes de implantar alterações em grupos maiores de dispositivos. Se você tiver problemas, poderá reverter a alteração, atualizar a configuração e fazer uma nova implantação. Área de Trabalho Gerenciada da Microsoft recomenda que você siga a abordagem estruturada e implante em grupos nesta ordem: Test, First, Fast e then Broad.   

Todas as configurações configuráveis são gerenciadas usando o portal Área de Trabalho Gerenciada da Microsoft administrador. Para obter mais informações, consulte [Deploy changes](config-setting-deploy.md). 

**Etapa 5 - Controlar alterações** – Acompanhar o progresso das alterações no status da implantação. Para cada configuração, você pode:
- **Acompanhar o progresso** – controlar o status depois de implantar a alteração. O status mudará para **Em andamento** e, em seguida, **concluirá** ou **falhará.** Se uma implantação falhar, uma solicitação de suporte será aberta automaticamente Área de Trabalho Gerenciada da Microsoft operações para investigar o problema.  
- **Confira versão implantada** – Cada alteração implantada tem um número de versão.
- **Reverter alterações** – Reverter uma alteração interrompe a implantação atual e reverte todos os grupos para as últimas alterações que foram implantadas em todos os grupos. Você está voltando para o último valor de configuração conhecido como bom.
- **Validar** alterações - Após a conclusão da implantação, valide as alterações que foram aplicadas conforme o esperado.  

Se uma implantação tiver falhado ou você não puder reverter uma alteração, [abra](admin-support.md) uma solicitação de suporte com Área de Trabalho Gerenciada da Microsoft Operations. 

Para obter mais informações, [consulte Deploy and track configurble settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Recursos adicionais
- [Referência de configurações que podem ser alteradas](config-setting-ref.md) 
- [Implantar configurações que podem ser alteradas](config-setting-deploy.md) 
