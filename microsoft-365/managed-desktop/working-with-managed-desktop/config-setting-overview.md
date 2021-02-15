---
title: Configurações configuráveis para a Área de Trabalho Gerenciada da Microsoft
description: Informações sobre configurações configuráveis com a Área de Trabalho Gerenciada da Microsoft
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

A Área de Trabalho Gerenciada da Microsoft implanta configurações e políticas aplicadas a todos os dispositivos gerenciados pela Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Configuração do dispositivo.](../service-description/device-policies.md)

As configurações configuráveis na Área de Trabalho Gerenciada da Microsoft dão aos administradores de IT uma maneira de personalizar e implantar configurações exclusivas para suas necessidades de organização e negócios. Essas configurações são além das configurações de dispositivos e políticas gerenciadas pela Área de Trabalho Gerenciada da Microsoft.  

As alterações de configuração configuráveis são feitas na nuvem e aplicadas aos dispositivos da Área de Trabalho Gerenciada da Microsoft em grupos de implantação definidos. Esse processo é semelhante ao modo como a Área de Trabalho Gerenciada da Microsoft gerencia as alterações nas configurações de dispositivos e políticas definidas e gerenciadas pelo serviço. Usando o mesmo processo que a Área de Trabalho Gerenciada da Microsoft usa para implantar alterações, você continua a mover sua organização para frente, usando as práticas modernas de gerenciamento de TI.

## <a name="when-to-use-configurable-settings"></a>Quando usar configurações configuráveis?

Há algumas vezes para usar configurações configuráveis. 

**Processo de** integração – a Área de Trabalho Gerenciada da Microsoft recomenda que você personalize as configurações configuráveis ao fazer a integração ao serviço de Área de Trabalho Gerenciada da Microsoft ou quando você integra um grande número de dispositivos (20 ou mais). As categorias de configuração são configuradas no portal de administração da Área de Trabalho Gerenciada da Microsoft. Depois de ter feito a integração e ter acesso ao portal de administração, você pode decidir quais categorias de configuração você deseja personalizar para sua organização, fazer as alterações, preparar uma implantação e implantar suas alterações.

**Manter configurações** - Revise suas configurações regularmente e faça as atualizações necessárias. Talvez seja necessário fazer alterações para dar suporte a uma alteração em sua empresa.   

## <a name="setting-categories"></a>Definindo categorias

Estas são as categorias de configurações configuráveis que você pode personalizar:
- [Imagem de plano de fundo da](config-setting-ref.md#desktop-background-picture) área de trabalho – Personalize a imagem de plano de fundo da área de trabalho para dispositivos da Área de Trabalho Gerenciada da Microsoft. 
- [Páginas inciais do](config-setting-ref.md#browser-start-pages) navegador – Adicione páginas inciais para usar com o Microsoft Edge. Consulte a página inicial do navegador
- [Lista de sites do modo Empresarial](config-setting-ref.md#enterprise-mode-site-list-location) – Adicionar sites e seu modo de compatibilidade. Os sites na lista serão iniciar no Internet Explorer. 
- [Sites confiáveis](config-setting-ref.md#trusted-sites) – Adicionar sites confiáveis e definir zonas de segurança para cada site. 
- [Exceções de site de](config-setting-ref.md#proxy) proxy – Configurar o número de endereço do servidor proxy e o número da porta e adicionar exceções de site de proxy.

Cada categoria de configuração pode ser personalizada e implantada por conta própria. Você pode implantar alterações em várias categorias de configuração ao mesmo tempo, no entanto, só é possível implantar uma alteração de cada vez em uma categoria de configuração.

Por exemplo:
- Você pode implantar alterações na imagem de plano de fundo da área de trabalho e em sites confiáveis, cada um como sua própria implantação, ao mesmo tempo. 
- Não é possível implantar duas implantações em páginas inciais do navegador ao mesmo tempo. A implantação mais recente interromperá implantações anteriores que ainda estão em andamento.

## <a name="configurable-setting-process"></a>Processo de configuração configurável

A Área de Trabalho Gerenciada da Microsoft recomenda seguir um processo semelhante ao seguinte ao utilizar configurações configuráveis para sua organização:

**Etapa 1 - Planejar** - Saiba mais sobre configurações configuráveis e decida quais categorias de configuração você deseja configurar para sua organização. Crie uma linha do tempo para quando você espera implantar alterações em cada grupo. Planeje a comunicação com seus usuários que atenda aos seus processos internos de gerenciamento de alterações. Por exemplo, se você estiver adicionando páginas inciais do navegador, avise aos usuários que eles terão um novo conjunto de páginas in iniciar no navegador após a implantação.  

**Etapa 2 : Configurar e configurar a implantação em estágios** - Faça alterações nas configurações configuráveis no portal de administração da Área de Trabalho Gerenciada da Microsoft. Prepare as alterações para que elas estão prontas para implantação. Lembre-se de permitir que os usuários saibam sobre as alterações e como as alterações alterarão a experiência do dispositivo.   

Configure e configure as alterações no portal de administração da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Personalizar configurações configuráveis.](config-setting-ref.md) 

**Etapa 3- Comunicar alterações** Comunique informações sobre alterações futuras para seus usuários. Para cada implantação, conclua a comunicação que faz parte dos seus processos de gerenciamento de alterações. Você deve comunicar claramente qualquer alteração que a impacte na forma como um usuário trabalha ou o que ele verá em seus dispositivos.

**Etapa 4 - Implantar alterações** – Implante suas alterações, começando com o grupo Teste. O grupo teste permite validar e solucionar problemas em um grupo com menos dispositivos, antes de implantar alterações em grupos maiores de dispositivos. Se você tiver algum problema, poderá reverter a alteração, atualizar a configuração e configurar uma nova implantação. A Área de Trabalho Gerenciada da Microsoft recomenda que você siga a abordagem estruturada e implante em grupos nesta ordem: Test, First, Fast e then Broad.   

Todas as configurações configuráveis são gerenciadas usando o portal de administração da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Implantar alterações.](config-setting-deploy.md) 

**Etapa 5 - Controlar alterações** – Controlar o progresso das alterações no status da implantação. Para cada configuração, você pode:
- **Acompanhar o progresso** – Acompanhar o status depois de implantar a alteração. O status mudará para **Em andamento** e, em **seguida, concluirá** ou **falhou.** Se uma implantação falhar, uma solicitação de suporte será aberta automaticamente para que as Operações da Área de Trabalho Gerenciada da Microsoft investiguem o problema.  
- **Veja a versão implantada** – cada alteração implantada tem um número de versão.
- **Reverter alterações** – a reversão de uma alteração interrompe a implantação atual e reverte todos os grupos para as últimas alterações que foram implantadas em todos os grupos. Você está voltando para o último valor de configuração bem-conhecido.
- **Validar** alterações - Após a conclusão da implantação, valide se as alterações foram aplicadas conforme o esperado.  

Se uma implantação falhou ou não é possível reverter uma [alteração,](admin-support.md) abra uma solicitação de suporte com as Operações de Área de Trabalho Gerenciada da Microsoft. 

Para obter mais informações, [consulte Implantar e acompanhar configurações configuráveis.](config-setting-deploy.md)

## <a name="additional-resources"></a>Recursos adicionais
- [Referência de configurações que podem ser alteradas](config-setting-ref.md) 
- [Implantar configurações que podem ser alteradas](config-setting-deploy.md) 
