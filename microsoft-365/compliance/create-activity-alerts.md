---
title: Criar alertas de atividade
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
ROBOTS: NOINDEX, NOFOLLOW
description: Adicionar e gerenciar alertas de atividade no Centro de & Conformidade e Segurança para que o Microsoft 365 envie notificações por email quando os usuários executarem atividades específicas
ms.openlocfilehash: ac78c57d368e27c43cc5f25733d49fad5fe4374a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818020"
---
# <a name="create-activity-alerts"></a>Criar alertas de atividade

Você pode criar um alerta de atividade que enviará uma notificação por email quando os usuários executarem atividades específicas no Office 365. Os alertas de atividade são semelhantes à pesquisa de eventos no log de auditoria, exceto pelo fato de você receber uma mensagem de email quando um evento de uma atividade em que você criou um alerta ocorrer. 
  
 **Por que usar alertas de atividade em vez de pesquisar o log de auditoria?** Pode haver certos tipos de atividade ou atividades realizadas por usuários específicos que você realmente deseja saber. Em vez de precisar se lembrar de pesquisar o log de auditoria dessas atividades, você pode usar alertas de atividade para que o Microsoft 365 envie uma mensagem de email quando os usuários realizarem essas atividades. Por exemplo, você pode criar um alerta de atividade para notificá-lo quando um usuário excluir arquivos no SharePoint ou você pode criar um alerta para notificá-lo quando um usuário excluir permanentemente mensagens de sua caixa de correio. A notificação por email enviada a você inclui informações sobre qual atividade foi realizada e o usuário que a realizou.

> [!NOTE]
> Os alertas de atividade estão sendo preterido. Recomendamos que você comece a usar políticas de alerta no centro de conformidade e segurança em vez de criar novos alertas de atividade. As políticas de alerta fornecem funcionalidade de adição, como a capacidade de criar uma política de alerta que dispara um alerta quando qualquer usuário executa uma atividade especificada e exibir alertas na página Exibir **alertas** no centro de conformidade e segurança. Para obter mais informações, consulte [Políticas de alerta.](alert-policies.md)
  
## <a name="confirm-roles-and-configure-audit-logging"></a>Confirmar funções e configurar o log de auditoria

- Você deve ter a função Configuração da Organização atribuída no Centro de Conformidade e Segurança & gerenciar alertas de atividade. Por padrão, essa função é atribuída aos grupos de funções Administrador de Conformidade e Gerenciamento da Organização. Para obter mais informações sobre como adicionar membros a grupos de função, consulte [Give users access to the Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Você (ou outro administrador) deve ativar primeiro o log de auditoria para sua organização antes de começar a usar alertas de atividade. Para fazer isso, basta clicar em **Iniciar a gravação** da atividade de usuários e administradores na página **Alertas de** atividade. (Se você não vir esse link, a auditoria já foi responsabilidade da sua organização.) Você também pode ativar a auditoria na página de pesquisa de & **log** de auditoria no Centro de Conformidade e Segurança (vá para pesquisa de log de  \> **auditoria de pesquisa).** Você só precisa fazer isso uma vez para sua organização.
  
- Você pode criar alertas para as mesmas atividades que pode pesquisar no log de auditoria. Consulte a [seção Mais informações](#more-information) para obter uma lista de cenários comuns (e a atividade específica a ser monitorada) para a onde você pode criar alertas. 
    
- Você pode usar a página **Alertas** de atividade no Centro de Conformidade e Segurança para criar alertas somente para atividades executadas por usuários listados no livro de endereço & s da sua organização. Você não pode usar essa página para criar alertas para atividades realizadas por usuários externos que não estão listados no livro de endereços. 
    
## <a name="create-an-activity-alert"></a>Criar um alerta de atividade

1. Acesse [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. Na página **Alertas de atividade,** clique no ![ ícone Adicionar ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Novo.**

   A página do flyout para criar um alerta de atividade é exibida.

    
    ![Criar um alerta de atividade](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Preencha os seguintes campos para criar um alerta de atividade:
    
    a. **Nome** - Digite um nome para o alerta. Os nomes de alerta devem ser exclusivos em sua organização.
    
    b. **Descrição** (opcional) - Descrever o alerta, como as atividades e os usuários que estão sendo rastreados, e os usuários para os que as notificações por email são enviadas. As descrições fornecem uma maneira rápida e fácil de descrever a finalidade do alerta para outros administradores.
    
    c. **Tipo de** alerta - Certifique-se **de que a opção** Personalizado está selecionada. 

    d. **Envie esse alerta quando** - Clique em **Enviar este alerta quando** e, em seguida, configure estes dois campos:
    
    - **Atividades** - Clique na lista drop-down para exibir as atividades para as que você pode criar um alerta. Essa é a mesma lista de atividades exibida quando você pesquisa o log de auditoria. Você pode selecionar uma ou mais atividades específicas ou pode clicar no nome do grupo de atividades para selecionar todas as atividades no grupo. Para uma descrição dessas atividades, consulte a seção "Atividades auditadas" em [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md#audited-activities) Quando um usuário executa qualquer uma das atividades que você adicionou ao alerta, uma notificação por email é enviada. 
    
     - **Usuários** - Clique nesta caixa e selecione um ou mais usuários. Se os usuários nesta caixa executarem as atividades que você adicionou à caixa **Atividades,** um alerta será enviado. Deixe a **caixa Usuários** em branco para enviar um alerta quando qualquer usuário em sua organização executar as atividades especificadas pelo alerta. 

    e. Send **this alert to** - Click Send this **alert**, and then click in the **Recipients** box and type a name to add a users who will receive an email notification when a user (specified in the **Users** box) performs an activity (specified in the **Activities** box). Observe que você é adicionado à lista de destinatários por padrão. Você pode remover seu nome dessa lista.
    
5. Clique **em** Salvar para criar o alerta. 
    
    O novo alerta é exibido na lista na página **Alertas de** atividade. 
    
    ![Uma lista de alertas é exibida na página Alertas de atividade](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    O status do alerta é definido como **Ligado.** Observe que os destinatários que receberão uma notificação por email quando um alerta for enviado também estão listados. 
  
## <a name="turn-off-an-activity-alert"></a>Desativar um alerta de atividade

Você pode desativar um alerta de atividade para que uma notificação por email não seja enviada. Depois de desativar o alerta de atividade, ele ainda será exibido na lista de alertas de atividade da sua organização e você ainda poderá exibir suas propriedades.
  
1. Vá para [https://protection.office.com/managealerts](https://protection.office.com/managealerts) .
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. Na lista de alertas de atividade da sua organização, clique no alerta que você deseja desativar.
    
4. Na página **Editar alerta,** clique no botão **de** alternância Ao alterar o status para **Desligado** e clique em **Salvar.**
    
    O status do alerta nas páginas **de alertas de** atividade é definido como **Desligado.** 
    
Para ativar novamente um alerta de atividade,  basta repetir essas etapas e clicar no botão de alternância Para alterar o status para **Ligado.**
  
## <a name="more-information"></a>Mais informações

- Aqui está um exemplo da notificação por email que é enviada aos usuários especificados no campo Enviar este alerta para (e listado em **Destinatários** na página **alertas** de atividade ) no Centro de Conformidade e & Segurança. 
    
    ![Exemplo de notação de email enviada para um alerta de atividade](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Aqui estão algumas atividades comuns de documento e email para as que você pode criar alertas de atividade. As tabelas descrevem a atividade, o nome da atividade para a criação de um alerta e  o nome do grupo de atividades em que a atividade está listada na lista de Atividades. Para ver uma lista completa das atividades para as que você pode criar alertas de atividade, consulte a seção "Atividades auditadas" em [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md#audited-activities)
    
    > [!TIP]
    > Talvez você queira criar um alerta de atividade para apenas uma atividade executada por qualquer usuário. Ou talvez você queira criar um alerta de atividade que rastreia várias atividades executadas por um ou mais usuários. 
  
    A tabela a seguir lista algumas atividades comuns relacionadas a documentos no SharePoint ou no OneDrive for Business.
    
    |**Quando um usuário faz isso...**|**Criar um alerta para essa atividade**|**Grupo de atividades**|
    |:-----|:-----|:-----|
    |Visualiza um documento em um site.  <br/> |Arquivo acessado  <br/> |Atividades de arquivos e pastas  <br/> |
    |Edita ou altera um documento.  <br/> |Arquivo modificado  <br/> |Atividades de arquivos e pastas  <br/> |
    |Compartilha um documento com um usuário fora da sua organização.  <br/> |Compartilhar arquivo, pasta ou site  <br/> And  <br/> Convite de compartilhamento criado  <br/> Para saber mais, veja [Usar a auditoria de compartilhamento no log de auditoria](use-sharing-auditing.md).  <br/> |Atividades de compartilhamento e solicitação de acesso  <br/> |
    |Carrega ou baixa um documento.  <br/> |Arquivo carregado  <br/> E/ou  <br/> Arquivo baixado  <br/> |Atividades de arquivos e pastas  <br/> |
    |Altera as permissões de acesso para um site.  <br/> |Permissões de site modificadas  <br/> |Atividades de administração do site  <br/> |

    A tabela a seguir lista algumas atividades comuns relacionadas a email no Exchange Online.

    |**Quando um usuário faz isso...**|**Criar um alerta para essa atividade**|**Grupo de atividades**|
    |:-----|:-----|:-----|
    |Exclui permanentemente (limpa) uma mensagem de email de sua caixa de correio.  <br/> |Mensagens limpas da caixa de correio  <br/> | Atividades de caixa de correio do Exchange  <br/> |
    |Envia uma mensagem de email de uma caixa de correio compartilhada.  <br/> |Mensagem enviada com permissões Enviar Como  <br/> And  <br/> Mensagem enviada com permissões Enviar em Nome de  <br/> | Atividades de caixa de correio do Exchange  <br/> |
   
- Você também pode usar os cmdlet & s **New-ActivityAlert** e **Set-ActivityAlert** no PowerShell do Centro de Conformidade e Segurança para criar e editar alertas de atividade. Lembre-se do seguinte se usar esses cmdlets para criar ou editar alertas de atividade: 
    
  - Se você usar um cmdlet para adicionar uma atividade ao  alerta que não está listado na lista de Atividades, uma mensagem será exibida na página de propriedades do alerta que diz, "Este alerta tem operações personalizadas não listadas no seletor". 
    
  - Um bom motivo para usar os cmdlets para criar ou editar um alerta de atividade é enviar notificações por email para alguém de fora da sua organização. Esse usuário externo será listado na lista de destinatários do alerta. Mas se você remover esse usuário externo do alerta, esse usuário não poderá ser adicionado ao alerta usando a página **Editar alerta.** Você terá que adicionar o usuário externo usando o cmdlet **Set-ActivityAlert** ou usar o cmdlet **New-ActivityAlert** para adicionar o mesmo usuário externo (ou diferente) a um novo alerta. 
