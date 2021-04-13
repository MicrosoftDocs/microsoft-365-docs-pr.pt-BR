---
title: Configurar notificações de alerta no Microsoft Defender para Ponto de Extremidade
description: Você pode usar o Microsoft Defender para o Ponto de Extremidade para configurar as configurações de notificação de email para alertas de segurança, com base na gravidade e em outros critérios.
keywords: notificações por email, configurar notificações de alerta, notificações do microsoft defender atp, alertas do microsoft defender atp, windows 10 enterprise, windows 10 education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5a19464b9d5d1b9659d7bfae2d853f7a640a00b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687884"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Configurar notificações de alerta no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Você pode configurar o Defender para o Ponto de Extremidade para enviar notificações de email para destinatários especificados para novos alertas. Esse recurso permite identificar um grupo de indivíduos que serão imediatamente informados e poderão agir em alertas com base em sua gravidade.

> [!NOTE]
> Somente usuários com permissões "Gerenciar configurações de segurança" podem configurar notificações por email. Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações por email.

Você pode definir os níveis de gravidade do alerta que disparam notificações. Você também pode adicionar ou remover destinatários da notificação de email. Novos destinatários são notificados sobre alertas disparados depois que são adicionados. Para obter mais informações sobre alertas, consulte [Exibir e organizar a fila de alertas.](alerts-queue.md)

Se você estiver usando o controle de acesso baseado em função (RBAC), os destinatários receberão notificações apenas com base nos grupos de dispositivos que foram configurados na regra de notificação.
Os usuários com a permissão adequada só podem criar, editar ou excluir notificações limitadas ao escopo de gerenciamento do grupo de dispositivos.
Somente os usuários atribuídos à função de administrador global podem gerenciar regras de notificação configuradas para todos os grupos de dispositivos.

A notificação por email inclui informações básicas sobre o alerta e um link para o portal onde você pode fazer uma investigação adicional.


## <a name="create-rules-for-alert-notifications"></a>Criar regras para notificações de alerta
Você pode criar regras que determinam os dispositivos e as gravidades de alerta para enviar notificações por email e para os destinatários de notificação.


1. No painel de navegação, selecione **Configurações**  >  **Notificações de email.**

2. Clique **em Adicionar item**.

3. Especifique as informações gerais:
    - **Nome da** regra - Especifique um nome para a regra de notificação.
    - **Incluir nome da** organização - Especifique o nome do cliente que aparece na notificação de email.
    - **Incluir link de portal específico do locatário** - Adiciona um link com a ID do locatário para permitir o acesso a um locatário específico.
    - **Incluir informações do dispositivo** - Inclui o nome do dispositivo no corpo do alerta de email.
    
        >[!NOTE]
        > Essas informações podem ser processadas por servidores de email de destinatário que não estão na localização geográfica selecionada para os dados do Defender para o Ponto de Extremidade.

    - **Dispositivos** - Escolha se deve notificar os destinatários para alertas em todos os dispositivos (função de administrador global somente) ou em grupos de dispositivos selecionados. Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).
    - **Gravidade do alerta** - Escolha o nível de gravidade do alerta.

4. Clique em **Avançar**.
    
5. Insira o endereço de email do destinatário e clique em **Adicionar destinatário**. Você pode adicionar vários endereços de email.

6. Verifique se os destinatários de email podem receber as notificações de email selecionando **Enviar email de teste.**

7. Clique **em Salvar regra de notificação**.

## <a name="edit-a-notification-rule"></a>Editar uma regra de notificação
1. Selecione a regra de notificação que você gostaria de editar.

2. Atualize as informações da guia Geral e destinatário.

3. Clique **em Salvar regra de notificação**.


## <a name="delete-notification-rule"></a>Excluir regra de notificação

1. Selecione a regra de notificação que você gostaria de excluir.

2. Clique em **Excluir**.


## <a name="troubleshoot-email-notifications-for-alerts"></a>Solucionar problemas de notificações por email para alertas
Esta seção lista vários problemas que você pode encontrar ao usar notificações de email para alertas.

**Problema:** Os destinatários pretendido relatam que não estão recebendo as notificações.

**Solução:** Certifique-se de que as notificações não sejam bloqueadas por filtros de email:

1. Verifique se as notificações de email do Defender para Ponto de Extremidade não são enviadas para a pasta Lixo Eletrônico. Marcá-los como Não lixo eletrônico.
2. Verifique se seu produto de segurança de email não está bloqueando as notificações de email do Defender para o Ponto de Extremidade.
3. Verifique as regras do aplicativo de email que podem estar capturando e movendo o Defender para notificações de email do Ponto de Extremidade.

## <a name="related-topics"></a>Tópicos relacionados
- [Atualizar configurações de retenção de dados](data-retention-settings.md)
- [Configurar recursos avançados](advanced-features.md)
