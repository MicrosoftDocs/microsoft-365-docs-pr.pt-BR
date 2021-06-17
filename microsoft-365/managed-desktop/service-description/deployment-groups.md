---
title: Grupos de implantação de dispositivo
description: Os grupos de implantação usados para gerenciar atualizações e outras alterações
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985513"
---
# <a name="device-deployment-groups"></a>Grupos de implantação de dispositivo

Área de Trabalho Gerenciada da Microsoft usa grupos de implantação para gerenciar a versão de atualizações e alterações de configuração em dispositivos. Os dispositivos são adicionados a grupos de implantação ("anéis" ou "grupos de atualização") automaticamente quando estão inscritos Área de Trabalho Gerenciada da Microsoft. Os grupos de implantação permitem que os dispositivos recebam alterações em uma linha do tempo em fases.

Talvez você queira atribuir determinados dispositivos apenas para fins de teste ou designar os primeiros adotantes específicos para receber as alterações primeiro. Se você tiver dispositivos críticos, como aqueles usados por executivos ou que fazem funções críticas para os negócios, talvez você queira mantê-los no grupo que recebe atualizações na cadência mais lenta. Área de Trabalho Gerenciada da Microsoft permite especificar que um dispositivo deve permanecer em qualquer um dos grupos a seguir.

- **Teste**: melhor para dispositivos usados para testes ou usuários que podem tolerar alterações frequentes e exposição a novos recursos e também fornecer comentários antecipados. Esse grupo recebe alterações com frequência e as experiências nesse grupo têm um efeito forte. O grupo Test está isento de quaisquer contratos de nível de serviço estabelecidos e suporte ao usuário. É melhor mover apenas alguns dispositivos no início e verificar a experiência do usuário. Área de Trabalho Gerenciada da Microsoft não atribuirá automaticamente dispositivos a esse grupo; ele só terá dispositivos que você especificar.
- **Primeiro:** ideal para os usuários in-loco, validadores voluntários ou designados, profissionais de TI ou representantes de funções comerciais, ou seja, pessoas que podem validar alterações e fornecer comentários sobre a experiência.
- **Broad** recebe as alterações por último. A maioria da sua organização normalmente estará nesse grupo. Você também pode especificar dispositivos que devem estar nesse grupo e devem receber apenas as alterações por último porque eles estão fazendo funções críticas dos negócios ou pertencem aos usuários em funções críticas. 
- **Automático**: selecione essa opção quando quiser Área de Trabalho Gerenciada da Microsoft atribuir automaticamente dispositivos a um dos outros grupos. (Não atribuiremos automaticamente dispositivos a Test.) Se você quiser liberar um dispositivo especificado anteriormente para que ele possa ser atribuído automaticamente novamente, selecione essa opção. 

Área de Trabalho Gerenciada da Microsoft usa alguns grupos adicionais para controlar implantações, mas você não poderá atribuir dispositivos a eles. No entanto, você pode mover dispositivos desses grupos para um dos grupos neste artigo. Para obter mais informações sobre como Windows as atualizações são gerenciadas em grupos, consulte [How updates are handled in Área de Trabalho Gerenciada da Microsoft](updates.md).

Se um dispositivo estiver em um grupo que você especificou, **Group atribuído por** dirá **Admin**. Se Área de Trabalho Gerenciada da Microsoft tiver atribuído o grupo, ele dirá **Auto**. Enquanto um dispositivo está em processo de mudança para um grupo, ele dirá **Pendente**. O **campo Grupo** sempre mostra o grupo em que o dispositivo está no momento e apenas é atualizado quando uma movimentação é concluída.

> [!IMPORTANT]
> Não tente modificar diretamente a associação desses grupos. Siga sempre as etapas descritas em [Atribuir dispositivos a um grupo de implantação](../working-with-managed-desktop/assign-deployment-group.md).
