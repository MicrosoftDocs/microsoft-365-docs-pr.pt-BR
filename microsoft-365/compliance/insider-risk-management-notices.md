---
title: Modelos de aviso de gerenciamento de risco interno
description: Saiba mais sobre modelos de avisos de gerenciamento de riscos no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de risco, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416475"
---
# <a name="insider-risk-management-notice-templates"></a>Modelos de aviso de gerenciamento de risco interno

Os modelos de aviso de gerenciamento de riscos insider permitem que você envie mensagens de email para os usuários quando suas atividades geram uma combinação de política e alerta. Na maioria dos casos, as ações do usuário que geram alertas são resultado de erros ou atividades inadvertida sem intenção irreversível. Os avisos servem como lembretes simples para os usuários serem mais cuidadosos, para fornecer links para informações para treinamento de atualização ou para recursos de política corporativa. Os avisos podem ser uma parte importante do programa de treinamento de conformidade interna e podem ajudar a criar uma trilha de auditoria documentada para usuários com atividades de risco recorrentes.

Crie modelos de aviso se quiser enviar aos usuários um aviso de lembrete de email para as combinações de política como parte do processo de resolução de problemas. Os avisos só podem ser enviados para o endereço de email do usuário associado ao alerta específico que está sendo revisado. Ao selecionar um modelo de aviso para aplicar a uma combinação de política, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.

## <a name="notice-templates-dashboard"></a>Painel de modelos de aviso

O **de modelos de avisos** exibe uma lista de modelos de aviso configurados e permite que você crie novos modelos de aviso. Os modelos de aviso são listados na ordem de data inversa com o modelo de aviso mais recente listado primeiro.

![Painel de modelo de aviso de gerenciamento de riscos do Insider](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML para avisos

Se você quiser criar mais do que uma mensagem de email simples baseada em texto para notificações, você pode criar uma mensagem mais detalhada usando HTML no campo corpo da mensagem de um modelo de aviso. O exemplo a seguir fornece o formato do corpo da mensagem para um modelo básico de notificação de email baseado em HTML:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> A implementação do atributo href HTML nos modelos de aviso de gerenciamento de riscos insider atualmente suporta apenas aspas simples, em vez de aspas duplas para referências de URL.

## <a name="create-a-new-notice-template"></a>Criar um novo modelo de aviso

Para criar um novo modelo de aviso de gerenciamento de riscos do **insider,** você usará o assistente de aviso na solução de gerenciamento de riscos do Insider no Microsoft 365 de conformidade.

Conclua as etapas a seguir para criar um novo modelo de aviso de gerenciamento de risco interno:

1. No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.
2. Selecione **Criar modelo de aviso** para abrir o assistente de aviso.
3. Na página **Criar um novo modelo de aviso,** conclua os seguintes campos:
    - **Nome do** modelo : Insira um nome amigável para o aviso. Esse nome aparece na lista de avisos no painel de avisos e na lista de seleção de avisos ao enviar avisos de uma ocorrência.
    - **Enviar de**: Insira o endereço de email do remetente para o aviso. Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.
    - **Campos Cc e Cc:** Usuários opcionais ou grupos a serem notificados da combinação de política, selecionados no Active Directory para sua assinatura.
    - **Assunto**: Informações que aparecem na linha de assunto da mensagem, suporta caracteres de texto.
    - **Corpo da** mensagem : Informações que aparecem no corpo da mensagem, suportam valores de texto ou HTML.
4. Selecione **Criar** para criar e salvar o modelo de aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.

## <a name="update-a-notice-template"></a>Atualizar um modelo de aviso

Para atualizar um modelo de aviso de gerenciamento de riscos insider existente, conclua as seguintes etapas:

1. No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.
2. No painel de avisos, selecione o modelo de aviso que você deseja gerenciar.
3. Na página detalhes do aviso, selecione **Editar**
4. Na página **Editar,** você pode editar os seguintes campos:
    - **Nome do** modelo : Insira um novo nome amigável para o aviso. Esse nome aparece na lista de avisos no painel de avisos e na lista de seleção de avisos ao enviar avisos de uma ocorrência.
    - **Enviar de**: Atualizar o endereço de email do remetente para o aviso. Esse endereço aparecerá no campo **De:** em todos os avisos enviados aos usuários, a menos que seja alterado ao enviar um aviso de uma ocorrência.
    - **Campos Cc e Cc:** Atualize usuários opcionais ou grupos a serem notificados da combinação de política, selecionados no Active Directory para sua assinatura.
    - **Assunto**: Atualize as informações que aparecem na linha de assunto da mensagem, suporta caracteres de texto.
    - **Corpo da** mensagem : Atualize as informações que aparecem no corpo da mensagem, suporta valores de texto ou HTML.
5. Selecione **Salvar** para atualizar e salvar o aviso ou selecione **Cancelar** para fechar sem salvar o modelo de aviso.

## <a name="delete-a-notice-template"></a>Excluir um modelo de aviso

Para excluir um modelo de aviso de gerenciamento de risco interno existente, conclua as seguintes etapas:

1. No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia Modelos de** aviso.
2. No painel de avisos, selecione o modelo de aviso que você deseja excluir.
3. Selecione o **ícone Excluir** na barra de ferramentas.
4. Para excluir o modelo de aviso, selecione **Sim** na caixa de diálogo excluir. Para cancelar a exclusão, selecione **Cancelar**.
