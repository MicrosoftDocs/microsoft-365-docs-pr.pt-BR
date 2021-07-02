---
title: Usar Microsoft Teams reuniões com o Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams reuniões com o Canvas
ms.openlocfilehash: 946abaec52cb1c5060d5490b409758cf230a4e5a
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256874"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Usar Microsoft Teams reuniões com o Canvas

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Microsoft Teams reuniões é um aplicativo de interoperabilidade de ferramentas (LTI) Learning que ajuda educadores e alunos a navegar facilmente entre seu Learning Management System (LMS) e Teams. Os usuários podem acessar suas equipes de classe associadas ao curso diretamente de dentro do LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Admin

Antes de gerenciar a integração do Microsoft Teams no Instructure Canvas, é importante que o aplicativo **microsoft-Teams-Sync-for-Canvas** do Canvas do Canvas seja aprovado pelo administrador do Microsoft Office 365 da sua instituição em seu locatário do Microsoft Azure antes de concluir a configuração do administrador do Canvas.

1. Entre no Canvas.

2. Selecione o link **Administrador** na navegação global e selecione sua conta.

3. Na navegação do administrador, selecione o link **Configurações** e, em seguida, a **guia** Integrações.

4. Insira seu atributo de logon e nome de locatário da Microsoft.

   O atributo login será usado para associar o usuário do Canvas a um Azure Active Directory usuário.

5. Selecione **Atualizar Configurações** uma vez feito.

6. Para aprovar o acesso ao **aplicativo Microsoft-Teams-Sync-for-Canvas** do Canvas do Canvas, selecione o link Conceder acesso **ao** locatário. Você será redirecionado para o Ponto de Extremidade de Consentimento de Administrador da Plataforma de Identidade da Microsoft.

   ![permissões](media/permissions.png)

7. Selecione **Aceitar**.

8. Habilita Microsoft Teams sincronização ativando a alternância.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Administrador do Canvas

Configurar a integração Microsoft Teams LTI 1.3.

Como administrador do Canvas, você precisará adicionar o aplicativo LTI de reuniões Microsoft Teams reuniões em seu ambiente. Anote a ID do Cliente LTI para o aplicativo.

 - Microsoft Teams reuniões - 17000000000703

1. Configurações **do Administrador do** Access  >  **Aplicativos**.

2. Selecione **+ Aplicativo** para adicionar os aplicativos Teams LTI.

   ![external-apps](media/external-apps.png)

3. Selecione **Por ID do Cliente para** o tipo de configuração.

   ![adicionar aplicativo](media/add-app.png)

4. Insira a ID do Cliente fornecida e selecione **Enviar**.

   Você notará o nome do aplicativo LTI Microsoft Teams reuniões para a ID do Cliente para confirmação.

5. Selecione **Instalar**.

   O Microsoft Teams lti de reuniões de reuniões será adicionado à lista de aplicativos externos.
