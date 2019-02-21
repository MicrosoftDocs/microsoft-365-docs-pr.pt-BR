---
title: Configurações configuráveis para a área de trabalho gerenciada da Microsoft
description: Informações sobre configurações configuráveis com a área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, configurações, configurações configuráveis
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 64560a1eb597072dd99c1538b0131e3cd807899c
ms.sourcegitcommit: 1942a860d1b65e1f8062564ec4703b953e0c2fd7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30122241"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Configurações configuráveis-Microsoft Managed desktop

O Microsoft Managed desktop implanta configurações e políticas que são aplicadas a todos os dispositivos gerenciados pela área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [Device Configuration](../service-description/device-policies.md).

As configurações que podem ser conFiguradas no Microsoft Managed desktop concedem aos administradores de ti uma maneira de personalizar e implantar as configurações exclusivas de sua organização e necessidades de negócios. Essas configurações são adicionais às configurações e políticas de configuração de dispositivo gerenciadas pela área de trabalho gerenciada da Microsoft.  

Alterações de configuração configuráveis são feitas na nuvem e aplicadas a seus dispositivos de área de trabalho gerenciada da Microsoft nos toques de implantação definidos. Esse processo é semelhante à forma como o Microsoft Managed desktop gerencia alterações nas configurações e políticas do configuruation de dispositivos definidas e gerenciadas pelo serviço. Usando o mesmo processo que o Microsoft Managed desktop usa para implantar alterações, você continua a mover sua organização para frente, usando práticas modernas de gerenciamento de ti.

## <a name="when-to-use-configurable-settings"></a>Quando usar as configurações configuráveis?

Há algumas vezes para usar as configurações que podem ser definidas. 

**Processo de integração** : o Microsoft Managed desktop recomenda que você personalize as configurações configuráveis ao fazer a integração com o serviço de área de trabalho gerenciada da Microsoft ou quando você integrar um grande número de dispositivos (20 ou mais). A configuração de categorias é configurada no portal de administração do Microsoft Managed desktop. Depois de ter integrado e ter acesso ao portal de administração, você pode decidir quais categorias de configuração você deseja personalizar para sua organização, fazer as alterações, preparar uma implantação e implantar suas alterações.

**Manter configurações** – revise suas configurações regularmente e faça as atualizações necessárias. Talvez seja necessário fazer alterações para dar suporte a uma alteração em sua empresa.   

## <a name="setting-categories"></a>Configurações de categorias

Estas são as categorias de configurações configuráveis que você pode personalizar:
- [Imagem de plano de fundo da área de trabalho](config-setting-ref.md#desktop-background-picture) – personalizar a imagem de plano de fundo da área de trabalho para os dispositivos 
- [Páginas iniciais do navegador](config-setting-ref.md#browser-start-pages) – adicione as páginas iniciais a serem usadas com o Microsoft Edge. Consulte a página inicial do navegador
- [Lista de sites do modo empresarial](config-setting-ref.md#enterprise-mode-site-list-location) – adicione sites e o modo de compatibilidade. Os sites na lista serão iniciados no Internet Explorer. 
- [Sites confiáveis](config-setting-ref.md#trusted-sites) – adicione sites confiáveis e defina zonas de segurança para cada site. 
- [Exceções de site de proxy](config-setting-ref.md#proxy) – configure o número de endereço e o número de porta do servidor proxy e adicione exceções de site de proxy.

Cada categoria de configuração pode ser personalizada e implantada por conta própria. Você pode implantar alterações em várias categorias de configurações ao mesmo tempo, no entanto, você só pode implantar uma alteração por vez em uma categoria de configuração.

Por exemplo:
- Você pode implantar alterações na imagem de plano de fundo da área de trabalho e sites confiáveis, cada como sua própria implantação, ao mesmo tempo. 
- Você não pode implantar duas implantações em páginas iniciais do navegador ao mesmo tempo. A implantação mais recente interromperá implantações anteriores que ainda estão em andamento.

## <a name="configurable-setting-process"></a>Processo de configuração configurável

O processo geral tem a seguinte aparência. 

**Etapa 1-plano** : Saiba mais sobre as configurações configuráveis e decida quais categorias de configuração você deseja configurar para sua organização. Planejar a comunicação com seus usuários que atendam aos processos internos de gerenciamento de alterações. Por exemplo, se você estiver adicionando páginas iniciais do navegador, informe seus usuários de que eles terão um novo conjunto de páginas iniciais em seus navegadores após a implantação.  

**Etapa 2-configurar e testar a implantação** -faça alterações nas configurações configuráveis no portal de administração de área de trabalho gerenciada da Microsoft. Preparar as alterações para que estejam prontas para implantação. Lembre-se de permitir que os usuários saibam sobre as alterações e como as alterações mudarão sua experiência de dispositivo.   

Você configura e testa alterações no portal de administração de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [personalizar definições configuráveis](config-setting-ref.md). 

**Etapa 3: comunicar as alterações** Comunicar informações sobre as futuras alterações para seus usuários. Para cada implantação, conclua a comunicação que faz parte dos seus processos de gerenciamento de alterações. Você deve comunicar claramente qualquer alteração que afete o funcionamento de um usuário ou o que eles verão em seus dispositivos.

**Etapa 4: implantar alterações** – implante suas alterações, começando com o anel de teste. O anel de teste permite validar e solucionar problemas em um toque com menos dispositivos, antes de implantar alterações em grupos maiores de dispositivos. Se você tiver problemas, poderá reverter a alteração, atualizar a configuração e testar uma nova implantação. O Microsoft Managed desktop recomenda que você siga a abordagem estruturada e implante para toques nesta ordem: Test, First, Fast e, em seguida, ampla.   

Todas as configurações configuráveis são gerenciadas usando o portal de administração do Microsoft Managed desktop. Para obter mais informações, consulte [implantar alterações](config-setting-deploy.md). 

**Etapa 5 – controlar alterações** – acompanhar o progresso de suas alterações no status de implantação. Para cada configuração, você pode:
- **Acompanhar progresso** – rastreie o status após implantar a alteração. O status será alterado para **em andamento**e, em seguida, **concluído**ou **falha**. Se uma implantação falhar, uma solicitação de suporte será aberta automaticamente para operações de área de trabalho gerenciada da Microsoft para investigar o problema.  
- **Confira a versão** implantada: cada alteração implantada tem um número de versão.
- **Reverter alterações** – reverter uma alteração interrompe a implantação atual e reverte todos os toques para as últimas alterações implantadas em todos os toques. Você está retornando para o último valor de configuração em boas condições.
- **Validar alterações** – após a conclusão da implantação, valide as alterações aplicadas conforme o esperado.  

Se uma implantação tiver falhado ou se você não puder reverter uma alteração, [abra uma solicitação de suporte](admin-support.md) com as operações de área de trabalho gerenciada da Microsoft. 

Para obter mais informações, consulte [implantar e acompanhar definições configuráveis](config-setting-deploy.md).

## <a name="additional-resources"></a>Recursos adicionais
- [Referência de configurações configuráveis](config-setting-ref.md) 
- [Implantar configurações configuráveis](config-setting-deploy.md) 
