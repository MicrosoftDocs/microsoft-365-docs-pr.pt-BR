---
title: Usar OneDrive interoperabilidade de ferramentas de aprendizagem
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
description: Crie e grade atribuições, crie e crie e crie conteúdo do curso e colabore em arquivos em tempo real com o novo aplicativo de interoperabilidade de ferramentas de aprendizagem OneDrive de aprendizagem.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327677"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>Use Microsoft OneDrive com seu Sistema de Gerenciamento de Aprendizagem

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Saiba os benefícios de usar Microsoft OneDrive com seu Sistema de Gerenciamento de Aprendizagem (LMS).

**Traz Microsoft Office 365 diretamente para seus fluxos de trabalho**

O Microsoft OneDrive aplicativo de Interoperabilidade de Ferramentas de Aprendizagem (LTI) integra-se ao seu LMS para trazer Microsoft OneDrive e Microsoft Office 365 diretamente para seus fluxos de trabalho mais importantes que incluem:

- Anexando recursos e organizando conteúdo.
- Iniciando documentos colaborativos.
- Criação e classificação de atribuições.

**Seguro e totalmente em conformidade com os padrões LTI mais recentes**

O Microsoft OneDrive LTI App é compatível com LTI 1.3 e LTI Advantage. Essa vantagem permite uma experiência de usuário altamente segura e integrada.

**Experiência do usuário moderna e rica**

O Microsoft OneDrive LTI app traz o melhor da Microsoft para sua experiência lms. Estamos melhorando a integração de Office 365 existente em seu LMS, fornecendo uma experiência de usuário mais moderna, completa com um selador de arquivos Microsoft OneDrive novo e expandido e experiências de edição mais ricas para arquivos Office. A Microsoft também será totalmente a Microsoft OneDrive aplicativo LTI daqui para frente, o que significa que você sempre receberá o mais recente e o melhor da Microsoft automaticamente.

O Microsoft OneDrive LTI App permite que você:

- Anexe Office 365 arquivos, incluindo documentos do Word, PowerPoint apresentações e Excel do Editor de Conteúdo Rico.

- Distribua Office 365 de nuvem.

- Exibir e organizar seus arquivos pessoais e Microsoft OneDrive curso.

- Crie colaborações nas quais os membros do curso possam trabalhar juntos em documentos compartilhados em tempo real.

- Acesse várias Microsoft OneDrive, incluindo contas pessoais e de estudante.

- Integre Office 365 arquivos com seus módulos de curso.

- Use sua conta da Microsoft para fazer o login único com seu LMS.

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
