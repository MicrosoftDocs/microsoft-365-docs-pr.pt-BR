---
title: Exclusão de dados do Skype for Business do Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, você pode encontrar uma explicação da exclusão de dados no Skype for Business, incluindo os tipos de conteúdo que não são mantidos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a47df4dd0dfdf5551668f8cafc9baa023bd6db1
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332707"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Exclusão de dados do Skype for Business no Office 365

O Skype for Business oferece arquivamento de mensagens instantâneas ponto a ponto, mensagens instantâneas entre várias pessoas e atividades de carregamento de conteúdo em reuniões. O recurso de arquivamento requer o Exchange e é controlado pelo atributo de Bloqueio In-loco da caixa de correio do Exchange do usuário, que arquiva tanto o email quanto o conteúdo do Skype for Business.

Todo o arquivamento no Skype for Business é considerado "arquivamento de nível do usuário" porque é possível habilitá-lo ou desabilitá-lo para um ou mais usuários ou grupos de usuários específicos criando, configurando e aplicando uma política de arquivamento de nível do usuário para esses usuários. Não há controle direto das configurações de arquivamento de dentro do Centro de administração do Skype for Business.

Os seguintes tipos de conteúdo não são arquivados no Skype for Business:

- Transferências de arquivo ponto a ponto
- Áudio/vídeo para mensagens instantâneas ponto a ponto e conferências
- Compartilhamento de aplicativo para mensagens instantâneas ponto a ponto e conferências
- Anotações de conferência 

## <a name="meeting-content-retention"></a>Retenção de conteúdo de reunião

Os clientes que usam o Skype for Business podem carregar conteúdo para uma reunião do Skype for Business como anexos, como apresentações do PowerPoint, arquivos do OneNote e outros arquivos. O período de retenção para o conteúdo que foi carregado para uma reunião é o seguinte:

- **Reunião de uso único** -o conteúdo é mantido por 15 dias a partir de quando a última pessoa deixa a reunião.
- **Reunião recorrente** -o conteúdo é mantido por 15 dias após a última pessoa sair da última sessão da reunião. O temporizador de retenção reinicia se alguém ingressar na mesma sessão de reunião em 15 dias. Por exemplo, suponha que uma reunião do Skype for Business está agendada para ocorrer semanal por um ano, e um arquivo é carregado para a reunião durante a primeira instância. Se pelo menos uma pessoa ingressar na sessão de reunião toda semana, o arquivo será mantido nos servidores do Skype for Business online por todo o ano mais 15 dias após a última pessoa sair da última reunião da série.
- **Reunião agora** -o conteúdo é retido por 8 horas após a hora de término da reunião.

> [!NOTE]
> Se um usuário não estiver licenciado ou estiver desabilitado (por exemplo, se **msRTCSIP-userhabilitado** for definido como *false*) e, em seguida, for novamente licenciado ou reabilitado, o conteúdo da reunião não será mantido.

## <a name="meeting-expiration"></a>Expiração de reunião

Os usuários podem acessar uma reunião específica, após a reunião ter terminado, sujeitos aos seguinte períodos de expiração:

- **Reunião de uso único** – a reunião expira 14 dias após a hora de término da reunião agendada.
- **Reunião recorrente com data de término** – a reunião expira 14 dias após a hora de término agendada da última ocorrência da reunião.
- **Reunião agora** – a reunião expira após 8 horas.

## <a name="whiteboard-collaboration"></a>Colaboração de quadro de comunicações

As anotações feitas em quadros de comunicação serão vistas por todos os participantes. Ao salvar um quadro de comunicações, o quadro de comunicações e todas as anotações serão armazenados em um Skype for Business Server e serão retidos no servidor de acordo com as políticas de expiração de conteúdo da reunião definidas pelo administrador.

## <a name="audio-test-service"></a>Serviço de teste de áudio

Um curto (aproximadamente 5 segundos) amostra de sua voz é registrado durante a chamada do serviço de teste de áudio. O exemplo de voz é usado para verificar e/ou verificar a qualidade de som da chamada do Skype for Business com base na qualidade da gravação. Quando a chamada de serviço de teste de áudio termina, a amostra de voz é excluída.

## <a name="persistent-group-chat"></a>Chat de grupo persistente

O chat de grupo persistente armazena o conteúdo de conversas de chat de grupo. Se for habilitada, o administrador poderá controlar o período de retenção, o servidor em que essas informações estão armazenadas, se o histórico de chat de grupo for arquivado para fins de conformidade ou outras finalidades, e gerenciar/modificar quaisquer propriedades em uma sala. Os usuários com funções diferentes têm acesso diferente aos dados persistentes da seguinte maneira:

- Os administradores podem excluir conteúdo mais antigo (por exemplo, o conteúdo postado antes de uma determinada data) de qualquer sala de chat para manter o tamanho do banco de dados crescendo muito. Ou podem remover ou substituir mensagens consideradas inadequadas para uma determinada sala de chat (ou consideradas inadequadas).
- Os usuários finais, incluindo autores de mensagens, não podem excluir conteúdo de qualquer sala de chat.
- Os gerentes de salas de chat podem desabilitar salas, mas não podem excluir salas. Somente os administradores podem excluir uma sala de chat após sua criação.