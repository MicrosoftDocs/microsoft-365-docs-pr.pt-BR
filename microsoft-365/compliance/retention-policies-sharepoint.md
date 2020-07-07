---
title: Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre as políticas de retenção que se aplicam ao SharePoint e ao OneDrive.
ms.openlocfilehash: db0dfdbddc620bfc7449397bad02463b02c270bd
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049879"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

As informações contidas neste artigo complementam [Saiba mais sobre as políticas de retenção](retention-policies.md) porque são informações específicas para o SharePoint e o OneDrive.

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>Como funciona uma política de retenção com o SharePoint e o OneDrive

Uma política de retenção é aplicada no nível de um conjunto de site. Quando um conjunto de sites do SharePoint ou uma conta do OneDrive é incluído em uma política de retenção, uma Biblioteca de Retenção para Preservação será criada, caso ainda não exista. Você pode ver essa biblioteca na página **Conteúdo do site** no site de nível superior do conjunto de sites. A maioria dos usuários não poderá ver a biblioteca de Retenção para Preservação porque ela só fica visível para os administradores do conjunto de sites.
  
Caso uma pessoa tente alterar ou excluir o conteúdo de um site que esteja sujeito à política de retenção, primeiro a política verificará se o conteúdo foi alterado desde a aplicação da política. Se essa for a primeira alteração desde que a política foi aplicada, a política de retenção copiará o conteúdo na Biblioteca de Retenção para Preservação e, então, permitirá que a pessoa altere ou exclua o conteúdo original. Qualquer conteúdo do conjunto de sites poderá ser copiado para a Biblioteca de Retenção para Preservação, mesmo se o conteúdo não corresponder à consulta usada pela política de retenção.
  
Um trabalho do temporizador limpa periodicamente a Biblioteca de Retenção para Preservação. Esta tarefa compara todo o conteúdo da Biblioteca de Retenção para Preservação para todas as consultas usadas pelas políticas de retenção no site. O conteúdo anterior ao período de retenção configurado é excluído da Biblioteca de Retenção para Preservação e do local original, se ainda estiver lá. Este trabalho temporizado é executado a cada sete dias, o que significa que pode levar até sete dias para que o conteúdo seja apagado.
  
Esse comportamento se aplica ao conteúdo que existe quando a política de retenção é aplicada. Além disso, qualquer conteúdo novo criado ou adicionado ao conjunto de sites depois que ele tiver sido incluído na política será retido após a exclusão. Entretanto, o novo conteúdo não será copiado para a Biblioteca de Retenção para Preservação na primeira vez em que for editado, somente quando for excluído. Para manter todas as versões de um arquivo, você deve ativar o [controle de versão](#how-a-retention-policy-works-with-document-versions-in-a-site-collection).
  
O usuário recebe um erro se tentar excluir uma biblioteca, lista, pasta ou um site sujeitos a uma política de retenção. Para excluir uma pasta, o usuário deve mover ou excluir todos os arquivos da pasta que estejam sujeitos à política. Além disso, a Biblioteca de Retenção para Preservação é criada nesse estágio, e não quando você cria a política de retenção. Isso significa que, para testar a política, você deve primeiro editar ou excluir um documento em um site sujeito à política de retenção e, em seguida, navegar até a Biblioteca de Retenção para Preservação para exibir a cópia retida.
  
Depois que uma política de retenção é atribuída a uma conta do OneDrive ou a um site do SharePoint, os caminhos que o conteúdo assume dependem se a política de retenção for para reter e excluir, somente reter ou somente excluir.

Quando a política de retenção for reter e excluir:

![Diagrama do ciclo de vida de conteúdo no SharePoint e no OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Se o conteúdo for modificado ou excluído** durante o período de retenção, uma cópia do conteúdo original existente na ocasião em que a política de retenção foi atribuída será criada na Biblioteca de Retenção para Preservação. Lá, o trabalho do temporizador identifica itens cujo período de retenção expirou. Esses são movidos para a lixeira de segundo estágio, onde serão excluídos permanentemente após 93 dias. A lixeira de segundo estágio não está visível para os usuários finais (somente a lixeira de primeiro estágio está), mas os administradores de conjunto de sites podem exibir e restaurar o conteúdo de lá.

    > [!NOTE]
    > Para ajudar a evitar a perda de dados acidental, não excluímos mais permanentemente o conteúdo da biblioteca de Retenção para Preservação. Em vez disso, excluímos permanentemente somente o conteúdo da lixeira, portanto, todo o conteúdo da Biblioteca de Retenção para Preservação agora passará pela lixeira de segundo estágio.
    
2. **Se o conteúdo não for modificado ou excluído** durante o período de retenção, o trabalho do temporizador move o conteúdo para a lixeira de primeiro estágio no final do período de retenção. Se um usuário excluir o conteúdo da lixeira ou esvaziá-la (processo também conhecido como limpeza), o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras do primeiro e do segundo estágio. No final de 93 dias, o documento é excluído permanentemente de onde estiver, na Lixeira de primeiro ou de segundo estágio. Como a lixeira não está indexada, ela não está disponível para pesquisa. Como resultado, uma pesquisa de descoberta eletrônica não encontra conteúdos da lixeira para colocar uma retenção.

Quando a política de retenção for reter somente ou excluir somente, os caminhos de conteúdo serão variações de reter e excluir:

### <a name="content-paths-for-retain-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção reter somente

1. **Se o conteúdo for modificado ou excluído** durante o período de retenção: uma cópia do documento original é criada na Biblioteca de Retenção para Preservação e retida até o fim do período de retenção, quando a cópia na Biblioteca de Retenção para Preservação é movida para a lixeira de segundo estágio e é excluída permanentemente após 93 dias.

2. **Se o conteúdo não for modificado ou excluído** durante o período de retenção: nada acontece antes e depois do período de retenção; o documento permanecerá no local original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção excluir somente

1. **Se o conteúdo for excluído** durante o período configurado: o documento será movido para a lixeira de primeiro estágio. Se um usuário excluir o documento da lixeira ou esvaziá-la, o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras de primeiro e de segundo estágio. Após os 93 dias, o documento será excluído permanentemente de onde estiver, seja na lixeira de primeiro ou de segundo estágio. Se o conteúdo for modificado durante o período configurado, ele seguirá o mesmo caminho de exclusão depois do período configurado.

2. **Se o conteúdo não for excluído** durante o período configurado: no final do período configurado na política de retenção, o documento é movido para a lixeira de primeiro estágio. Se um usuário excluir o documento da lixeira ou esvaziá-la (processo também conhecido como limpeza), o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras de primeiro e de segundo estágio. Após os 93 dias, o documento será excluído permanentemente de onde estiver, seja na lixeira de primeiro ou de segundo estágio. Como a lixeira não está indexada, ela não está disponível para pesquisa. Como resultado, uma pesquisa de descoberta eletrônica não encontra conteúdos da lixeira para colocar uma retenção.

## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Como funciona uma política de retenção com versões de documento em um conjunto de sites

O controle de versão é um recurso de todas as bibliotecas de documentos no SharePoint e no OneDrive. Por padrão, o controle de versão retém no mínimo 500 versões principais, embora você possa aumentar esse limite. Confira mais informações em [Habilitar e configurar o controle de versão para uma lista ou biblioteca](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Uma política de retenção mantém todas as versões de um documento em um conjunto de sites do SharePoint ou em uma conta do OneDrive. Quando um documento sujeito a uma política de retenção ou bloqueio for editado pela primeira vez, uma versão do documento original será copiada na Biblioteca de Retenção para Preservação. Quando um documento sujeito a uma política de retenção ou de bloqueio for excluído, todas as versões serão copiadas para a Biblioteca de Retenção para Preservação se o controle de versão estiver habilitado. Cada versão de um documento na Biblioteca de Retenção para Preservação existe como um item separado com seu próprio período de retenção:
  
- If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.

- If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.

> [!NOTE]
> As versões preservadas dos documentos do SharePoint e do OneDrive não são pesquisáveis por ferramentas de Descoberta Eletrônica.

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização

**SharePoint**:

Quando um usuário sai organização, qualquer conteúdo criado por ele não será afetado porque o SharePoint é considerado um ambiente colaborativo, ao contrário da caixa de correio ou da conta OneDrive de um usuário.

**OneDrive**:

Se um usuário sair da organização, quaisquer arquivos sujeitos a uma política de retenção ou que tenham rótulos de retenção permanecerão pela duração da política ou do rótulo.  Durante esse período, todo o acesso à compartilhamentos continua a funcionar. Quando o período de retenção expira, o conteúdo é movido para a Lixeira de Conjuntos de Sites e não pode ser acessado por ninguém, exceto pelo administrador. Se um documento for marcado por uma política de retenção como um registro, ele não será excluído até que o período de retenção termine, após o qual o conteúdo será permanentemente excluído.

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>Como configurar uma política de retenção para o SharePoint e o OneDrive

Siga as instruções para [Criar e configurar políticas de retenção](create-retention-policies.md) e, na página **Escolher locais** do assistente, escolha uma das seguintes opções:

- **Aplicar política apenas ao conteúdo em emails do Exchange, pastas públicas, Grupos do Office 365, documentos do OneDrive e do SharePoint**

- **Deixe-me escolher locais específicos** > **sites do SharePoint**, **contas do OneDrive**e **grupos do Office 365**.

Quando você escolhe o local **Sites do SharePoint**, a política de retenção pode reter o conteúdo nos sites de comunicação do SharePoint, sites de equipes que não estão conectados por grupos do Office 365 e sites clássicos. Os sites de equipes conectados por grupos do Office 365 não possuem suporte com essa opção e, em vez disso, use a **Grupos do Office 365** local que se aplicam ao conteúdo na caixa de correio do grupo, sites e arquivos.

Ao especificar os locais para os sites do SharePoint, não será preciso ter permissões para acessar o site e nenhuma validação será feita ao especificar a URL na página **Editar locais**. No entanto, os sites devem ser indexados e os especificados por você, serão verificados no final do assistente.

Se essa verificação falhar, uma mensagem será exibida informando que a validação falhou para a URL inserida, e o assistente não criará a política de retenção até que a verificação de validação seja aprovada. Se você vir esta mensagem, volte ao assistente para alterar a URL ou remover o site.
