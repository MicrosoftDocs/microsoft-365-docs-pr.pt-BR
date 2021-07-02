---
title: Usar OneDrive Learning interoperabilidade de ferramentas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Crie e grade atribuições, crie e crie e crie conteúdo do curso e colabore em arquivos em tempo real com o novo aplicativo de interoperabilidade de ferramentas OneDrive Learning ferramentas.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256922"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Usar Microsoft OneDrive LTI com Canvas

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

## <a name="integrate-with-canvas"></a>Integrar-se ao Canvas

A pessoa que executa essa integração deve ser um administrador do Canvas e um administrador do Microsoft 365 locatário.

1. Entre no portal Microsoft Azure com a conta de administrador do locatário. O administrador de locatários do Azure também deve ter a função de administrador de grupo.

    ![administrador de grupo realçada](../media/lti-media/lti-group-admin.png)

2. Entre no portal do Microsoft [OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).

3. Aceite as permissões para concluir a assinatura.

    ![aceitar permissões](../media/lti-media/lti-permissions.png)

4. Selecione **Adicionar Locatário LTI**.

     ![adicionar locatário LTI](../media/lti-media/lti-add-tenant.png)

5. Selecione **Plataforma de Consumidor LTI** como **Canvas** no menu suspenso.

6. Selecione **URL da Base de Tela** e selecione **Next**.

    ![selecione Canvas e adicione URL base](../media/lti-media/lti-canvas-base-url.png)

   A próxima tela mostra campos que são confidenciais para você.

7. Selecione **Próximo** em ?? page. OS REVISADORES PODEM PREENCHER O ESPAÇO EM BRANCO AQUI?

8. Selecione **Next** na tela que mostra informações confidenciais para você.

   A tela final do portal do Azure mostra as próximas etapas para adicionar sua instância do Canvas.

9. Copie as Chaves do Desenvolvedor desta tela. Você usará ao criar a instância canvas.

## <a name="add-the-canvas-instance"></a>Adicionar a instância do Canvas

1. Em sua instância do Canvas, desmarque **As Chaves** do Desenvolvedor de  >  **Administrador.**

2. Escolha **LTI Key** no menu suspenso em **Chave do Desenvolvedor.**

   ![Obter as chaves do desenvolvedor LTI](../media/lti-media/lti-developer-keys.png)

3. Colar as chaves do desenvolvedor aqui.

     ![Colar as chaves do desenvolvedor](../media/lti-media/lti-developer-keys.png)

   A chave é criada no **modo** OFF

   ![As chaves de desenvolvedor criadas no modo desligado](../media/lti-media/lti-copy-developer-keys.png)

4. Copie o texto realçado.
    Isso serve como ID do Cliente no Microsoft OneDrive lti portal.

5. Colar o texto no campo **ID do** Cliente Microsoft OneDrive portal LTI e selecione **Next**.

6. Selecione **Salvar**.

7. Exibir as configurações selecionando **Exibir Locatários LTI**.
