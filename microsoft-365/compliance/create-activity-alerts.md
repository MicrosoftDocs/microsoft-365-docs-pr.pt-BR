---
title: Criar alertas de atividade no Office 365
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
description: Adicione e gerencie alertas de atividade no centro de conformidade e segurança para que o Office 365 envie notificações por email quando os usuários executarem atividades específicas no Office 365.
ms.openlocfilehash: b83dec740b8b37d3c8a4132f114ee76178b2dd86
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077659"
---
# <a name="create-activity-alerts-in-the-office-365"></a>Criar alertas de atividade no Office 365

Você pode criar um alerta de atividade que lhe enviará uma notificação por email quando os usuários executarem atividades específicas no Office 365. Os alertas de atividade são semelhantes à pesquisa de eventos no log de auditoria do Office 365, exceto pelo fato de você receber uma mensagem de email quando um evento de uma atividade que você criou um alerta para acontecer. 
  
 **Por que usar alertas de atividade em vez de Pesquisar o log de auditoria?** Pode haver certos tipos de atividade ou atividade executados por usuários específicos que você realmente deseja saber. Em vez de ter que se lembrar de Pesquisar o log de auditoria dessas atividades, você pode usar os alertas de atividade para que o Office 365 envie uma mensagem de email quando os usuários realizarem essas atividades. Por exemplo, você pode criar um alerta de atividade para notificá-lo quando um usuário exclui arquivos no SharePoint ou você pode criar um alerta para notificá-lo quando um usuário exclui permanentemente mensagens de suas caixas de correio. A notificação de email enviada para você inclui informações sobre qual atividade foi realizada e o usuário que a realizou. 

> [!NOTE]
> Recomendamos que você comece a usar políticas de alerta no centro de segurança e conformidade, em vez de criar novos alertas de atividade. As políticas de alerta fornecem funcionalidade adicional, como a capacidade de criar uma política de alerta que dispara um alerta quando qualquer usuário executa uma atividade específica e exibe alertas na página **exibir alertas** no centro de segurança e conformidade. Para obter mais informações, consulte [políticas de alerta](alert-policies.md).
  
## <a name="before-you-begin"></a>Antes de começar

- Você deve receber a função de configuração da organização no centro de conformidade de & de segurança para gerenciar os alertas de atividade. Por padrão, essa função é atribuída ao administrador de conformidade e aos grupos de função de gerenciamento da organização. Para obter mais informações sobre como adicionar membros a grupos de função, consulte [conceder aos usuários acesso ao centro de conformidade de & de segurança](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Você (ou outro administrador) deve primeiro ativar o log de auditoria para sua organização antes de começar a usar os alertas de atividade. Para fazer isso, basta clicar em **iniciar a gravação da atividade de administrador e usuário** na página alertas de **atividade** . (Se você não vir este link, a auditoria já foi ativada para sua organização.) Você também pode ativar a auditoria na página **pesquisa de log de auditoria** no centro de conformidade de & de segurança (vá para pesquisa de log de **auditoria**de **pesquisa** \> ). Você só precisa fazer isso uma vez para sua organização.
  
- Você pode criar alertas para as mesmas atividades que você pode pesquisar no log de auditoria do Office 365. Consulte a seção [mais informações](#more-information) para obter uma lista de cenários comuns (e a atividade específica a ser monitorada) para a qual você pode criar alertas. 
    
- Você pode usar a página **alertas de atividade** no centro de conformidade de & de segurança para criar alertas somente para atividades realizadas por usuários que estão listados no catálogo de endereços da sua organização. Você não pode usar esta página para criar alertas para atividades realizadas por usuários externos que não estão listados no catálogo de endereços. 
    
## <a name="create-an-activity-alert"></a>Criar um alerta de atividade

1. Acesse [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. Na página **alertas de atividade** , clique ![em Adicionar](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) ícone **novo**.

   A página de menu para criar um alerta de atividade é exibida.

    
    ![Criar um alerta de atividade](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Preencha os seguintes campos para criar um alerta de atividade:
    
    a. **Name** -digite um nome para o alerta. Os nomes de alerta devem ser exclusivos dentro da sua organização.
    
    b. **Descrição** (opcional)-descrever o alerta, como as atividades e os usuários que estão sendo controlados e os usuários para os quais as notificações de email são enviadas. As descrições fornecem uma maneira rápida e fácil de descrever a finalidade do alerta para outros administradores.
    
    c. **Tipo de alerta** : Certifique-se de que a opção **personalizada** está selecionada. 

    d. **Envie este alerta quando** -clique em **Enviar este alerta quando** e configure estes dois campos:
    
    - **Atividades** -clique na lista suspensa para exibir as atividades para as quais você pode criar um alerta. Esta é a mesma lista de atividades que é exibida quando você pesquisa o log de auditoria do Office 365. Você pode selecionar uma ou mais atividades específicas ou pode clicar no nome do grupo de atividades para selecionar todas as atividades no grupo. Para obter uma descrição dessas atividades, consulte a seção "atividades auditadas" em [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#audited-activities). Quando um usuário executa qualquer uma das atividades que você adicionou ao alerta, uma notificação de email é enviada. 
    
     - **Usuários** – clique nesta caixa e selecione um ou mais usuários. Se os usuários nessa caixa executarem as atividades que você adicionou à caixa **atividades** , um alerta será enviado. Deixe a caixa **usuários** em branco para enviar um alerta quando qualquer usuário em sua organização executar as atividades especificadas pelo alerta. 

    e. **Envie este alerta para** clicar em **Enviar este alerta**e clique na caixa **destinatários** e digite um nome para adicionar um usuário que receberá uma notificação por email quando um usuário (especificado na caixa **usuários** ) executar uma atividade (especificada na caixa **atividades** ). Observe que você é adicionado à lista de destinatários por padrão. Você pode remover seu nome dessa lista.
    
5. Clique em **salvar** para criar o alerta. 
    
    O novo alerta é exibido na lista da página **alertas de atividade** . 
    
    ![Uma lista de alertas é exibida na página alertas de atividade](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    O status do alerta é definido como **ativado**. Observe que os destinatários que receberão uma notificação por email quando um alerta é enviado também são listados. 
  
## <a name="turn-off-an-activity-alert"></a>Desativar um alerta de atividade

Você pode desativar um alerta de atividade para que uma notificação por email não seja enviada. Após desativar o alerta de atividade, ele ainda será exibido na lista de alertas de atividade da sua organização e você ainda poderá exibir suas propriedades.
  
1. Vá para [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. Na lista de alertas de atividade da sua organização, clique no alerta que você deseja desativar.
    
4. Na página **Editar alerta** , clique no botão **Ativar** /desativar para alterar o status para **desativado**e clique em **salvar**.
    
    O status do alerta nas páginas **alertas de atividade** está definido como **desativado**. 
    
Para ativar novamente um alerta de atividade, basta repetir estas etapas e clicar no botão de alternância **desligar** para alterar o status para **ativado**.
  
## <a name="more-information"></a>Mais informações

- Veja um exemplo de notificação de email que é enviada aos usuários que são especificados no campo enviar este alerta para (e listados em **destinatários** da página **alertas de atividade** ) no centro de conformidade de segurança &. 
    
    ![Exemplo de notificação de email enviada para um alerta de atividade](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Veja aqui algumas atividades comuns de documentos e emails para as quais você pode criar alertas de atividade. As tabelas descrevem a atividade, o nome da atividade para criar um alerta e o nome do grupo de atividade em que a atividade está listada na lista suspensa **atividades** . Para ver uma lista completa das atividades para as quais você pode criar alertas de atividade, consulte a seção "atividades auditadas" em [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > Você pode querer criar um alerta de atividade para apenas uma atividade que é executada por qualquer usuário. Ou talvez você queira criar um alerta de atividade que acompanhe várias atividades realizadas por um ou mais usuários. 
  
    A tabela a seguir lista algumas atividades comuns relacionadas a documentos no SharePoint ou no OneDrive for Business.
    
    |**Quando um usuário faz isso...**|**Criar um alerta para esta atividade**|**Grupo de atividade**|
    |:-----|:-----|:-----|
    |Exibe um documento em um site.  <br/> |Arquivo acessado  <br/> |Atividades de arquivo e pasta  <br/> |
    |Edita ou altera um documento.  <br/> |Arquivo modificado  <br/> |Atividades de arquivo e pasta  <br/> |
    |Compartilha um documento com um usuário fora da sua organização.  <br/> |Compartilhar arquivo, pasta ou site  <br/> And  <br/> Convite de compartilhamento criado  <br/> Para saber mais, veja [Usar a auditoria de compartilhamento no log de auditoria do Office 365](use-sharing-auditing.md).  <br/> |Atividades de compartilhamento e solicitação de acesso  <br/> |
    |Carrega ou baixa um documento.  <br/> |Arquivo carregado  <br/> E/ou  <br/> Arquivo baixado  <br/> |Atividades de arquivo e pasta  <br/> |
    |Altera as permissões de acesso para um site.  <br/> |Permissões de site modificadas  <br/> |Atividades de administração do site  <br/> |

    A tabela a seguir lista algumas atividades comuns relacionadas a email no Exchange Online.

    |**Quando um usuário faz isso...**|**Criar um alerta para esta atividade**|**Grupo de atividade**|
    |:-----|:-----|:-----|
    |Exclui permanentemente (limpa) uma mensagem de email da caixa de correio.  <br/> |Mensagens limpas da caixa de correio  <br/> | Atividades de caixa de correio do Exchange  <br/> |
    |Envia uma mensagem de email de uma caixa de correio compartilhada.  <br/> |Mensagem enviada com permissões Enviar Como  <br/> And  <br/> Mensagem enviada com permissões Enviar em Nome de  <br/> | Atividades de caixa de correio do Exchange  <br/> |
   
- Você também pode usar os cmdlets **New-ActivityAlert** e **set-ActivityAlert** em segurança & o PowerShell do centro de conformidade para criar e editar alertas de atividade. Lembre-se dos seguintes pontos se você usar esses cmdlets para criar ou editar alertas de atividades: 
    
  - Se você usar um cmdlet para adicionar uma atividade ao alerta que não está listado na lista suspensa de **atividades** , uma mensagem será exibida na página de propriedades para o alerta que diz, "este alerta tem operações personalizadas não listadas no seletor". 
    
  - Um bom motivo para usar os cmdlets para criar ou editar um alerta de atividade é enviar notificações por email para alguém fora da sua organização. Esse usuário externo será listado na lista de destinatários para o alerta. Mas se você remover esse usuário externo do alerta, esse usuário não poderá ser adicionado novamente ao alerta usando a página **Editar alerta** . Você terá que adicionar novamente o usuário externo usando o cmdlet **set-ActivityAlert** ou usar o cmdlet **New-ActivityAlert** para adicionar o mesmo usuário externo (ou diferente) a um novo alerta. 
