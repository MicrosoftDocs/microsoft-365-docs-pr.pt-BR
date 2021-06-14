---
title: Saiba mais sobre retenção para o SharePoint e o OneDrive
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
description: Saiba mais sobre funciona a retenção para o SharePoint e o OneDrive.
ms.openlocfilehash: 14b3bebab8b73b7b45c79a34903fed5d0f6ec9ca
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861582"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>Saiba mais sobre retenção para o SharePoint e o OneDrive

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

As informações contidas neste artigo complementam [Saiba mais sobre retenção](retention.md) porque são informações específicas para o SharePoint e o OneDrive.

Para outras cargas de trabalho, confira:

- [Saiba mais sobre retenção para o Microsoft Teams](retention-policies-teams.md)
- [Saiba mais sobre retenção no Yammer](retention-policies-yammer.md)
- [Saiba mais sobre a retenção para o Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>O que está incluído para retenção e exclusão

Todos os arquivos armazenados em sites do Microsoft Office SharePoint Online ou Microsoft OneDrive podem ser retidos aplicando uma política de retenção ou rótulo de retenção. 

Os seguintes arquivos podem ser excluídos:

- Quando você usa uma política de retenção: Todos os arquivos em bibliotecas de documentos, que incluem quaisquer bibliotecas de documentos do Microsoft Office SharePoint Online criadas automaticamente, como **Ativos de Sites**.
    
- Quando você usa rótulos de retenção: todos os arquivos em todas as bibliotecas de documentos e todos os arquivos no nível raiz que não estão em uma pasta.
    
> [!TIP]
> Ao usar uma [consulta com uma política de aplicação automática para um rótulo de retenção](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties), você pode excluir bibliotecas de documentos usando a seguinte entrada: `NOT(DocumentLink:"<URL to document library>")`

Os itens da lista não são compatíveis com as políticas de retenção, mas são compatíveis com os rótulos de retenção, com exceção dos itens nas listas do sistema. Essas são listas ocultas usadas pelo Microsoft Office SharePoint Online para gerenciar o sistema e incluem o catálogo da página mestra, o catálogo de soluções e as fontes de dados. Quando você aplica um rótulo de retenção a um item de lista compatível que tem um anexo de documento:
- Para uma etiqueta de retenção padrão (não declara o item como um registro):
    - O anexo do documento não herda automaticamente as configurações de retenção do rótulo, mas pode ser rotulado de forma independente.
- Para uma etiqueta de retenção que declara o item um registro: 
    - O anexo do documento herda automaticamente as configurações de retenção da etiqueta se o documento ainda não estiver etiquetado.

As configurações de retenção de políticas de retenção e rótulos de retenção não se aplicam a estruturas de organização que incluem bibliotecas, listas e pastas.

Para políticas de retenção e políticas de aplicação automática: sites do SharePoint devem ser indexados para que as configurações de retenção sejam aplicadas. No entanto, se os itens nas bibliotecas de documentos do Microsoft Office SharePoint Online forem configurados para não aparecer nos resultados da pesquisa, essa configuração não excluirá os itens das configurações de retenção.

## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>Como funciona a retenção para o SharePoint e o OneDrive

Para armazenar o conteúdo que precisa ser retido, o SharePoint e o OneDrive criam uma biblioteca de retenção para preservação, se não houver uma. Você pode ver essa biblioteca na página **Conteúdo do site** no site de nível superior do conjunto de sites. A maioria dos usuários não poderá ver a biblioteca de Retenção para Preservação porque ela só fica visível para os administradores do conjunto de sites.

Os itens no SharePoint que têm um rótulo de retenção padrão (não declara o item como um registro) não precisam da biblioteca de Retenção de Preservação porque esses itens permanecem em seu local original. O SharePoint impede que os usuários excluam itens quando o rótulo de retenção aplicado é configurado para reter o conteúdo, e o controle de versão do SharePoint preserva as versões mais antigas quando os itens são editados. Mas para outros cenários, a biblioteca de retenção de preservação é usada quando os itens devem ser retidos:
- Itens no OneDrive que possuem rótulos de retenção padrão
- Itens no SharePoint ou OneDrive que têm rótulos de retenção que os declaram um registro, e o item está desbloqueado para edição
- Itens que estão sujeitos a políticas de retenção

Para reter este conteúdo quando um usuário tenta alterá-lo ou excluí-lo, é feita uma verificação se o conteúdo foi alterado desde que as configurações de retenção foram aplicadas. Se essa for a primeira alteração desde que as configurações de retenção foram aplicadas, o conteúdo é copiado para a Biblioteca de Retenção para Preservação, permitindo que a pessoa altere ou exclua o conteúdo original. Todo o conteúdo em um conjunto de sites pode ser copiado para a Biblioteca de Retenção para Preservação, independentemente das configurações de retenção.
  
Um trabalho do temporizador limpa periodicamente a Biblioteca de Retenção para Preservação. Para o conteúdo que estiver na biblioteca de Retenção para Preservação por mais de 30 dias, esse trabalho compara o conteúdo a todas as consultas usadas pelas configurações de retenção para aquele conteúdo. O conteúdo anterior ao período de retenção configurado é excluído da biblioteca de Retenção para Preservação e do local original, se ainda estiver lá. Esse trabalho de temporizador é executado a cada sete dias, o que significa que, juntamente com o mínimo de 30 dias, pode levar até 37 dias para que o conteúdo seja excluído da biblioteca de Retenção para Preservação.

Esse comportamento de copiar arquivos para a biblioteca de Retenção para preservação aplica-se ao conteúdo existente quando as configurações de retenção forem aplicadas. Além disso, para políticas de retenção, qualquer novo conteúdo criado ou adicionado ao site depois que ele foi incluído na política será mantido na biblioteca de Retenção para Preservação. Entretanto, o novo conteúdo não será copiado para a Biblioteca de Retenção para Preservação na primeira vez em que for editado, somente quando for excluído. Para manter todas as versões de um arquivo, você deve ativar o [controle de versão](#how-retention-works-with-document-versions).
  
Os usuários verão uma mensagem de erro se tentarem excluir uma biblioteca, lista, pasta ou site sujeito à retenção. Eles podem excluir uma pasta se primeiro moverem ou excluirem quaisquer arquivos da pasta que estejam sujeitos à retenção.

> [!NOTE]
> Como a biblioteca de Retenção para Preservação é criada apenas quando é necessária, e não quando você aplica uma política de retenção ou rótulo de retenção, para ver isso funcionando, você deve primeiro editar ou excluir um item que está sujeito à retenção. Em seguida, navegue até a biblioteca de Retenção para Preservação para exibir a cópia retida.
  
Depois de atribuir as configurações de retenção ao conteúdo em uma conta do OneDrive ou em um site do SharePoint, os caminhos que o conteúdo assume dependem se as configurações de retenção forem para reter e excluir, reter somente, ou excluir somente.

Quando as configurações de retenção são reter e excluir:

![Diagrama do ciclo de vida de conteúdo no SharePoint e no OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Se o conteúdo for modificado ou excluído** durante o período de retenção, uma cópia do conteúdo original existente na ocasião em que as configurações de retenção foram atribuídas será criada na Biblioteca de Retenção para Preservação. Lá, o trabalho do temporizador identifica itens cujo período de retenção expirou. Esses são movidos para a lixeira de segundo estágio, onde serão excluídos permanentemente após 93 dias. A lixeira de segundo estágio não está visível para os usuários finais (somente a lixeira de primeiro estágio está), mas os administradores de conjunto de sites podem exibir e restaurar o conteúdo de lá.

    > [!NOTE]
    > Para ajudar a evitar a perda de dados acidental, não excluímos mais permanentemente o conteúdo da biblioteca de Retenção para Preservação. Em vez disso, excluímos permanentemente somente o conteúdo da lixeira, portanto, todo o conteúdo da Biblioteca de Retenção para Preservação agora passará pela lixeira de segundo estágio.
    
2. **Se o conteúdo não for modificado ou excluído** durante o período de retenção, o trabalho do temporizador move o conteúdo para a lixeira de primeiro estágio no final do período de retenção. Se um usuário excluir o conteúdo da lixeira ou esvaziá-la (processo também conhecido como limpeza), o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras do primeiro e do segundo estágio. No final de 93 dias, o documento é excluído permanentemente de onde estiver, na Lixeira de primeiro ou de segundo estágio. Como a lixeira não está indexada, ela não está disponível para pesquisa. Como resultado, uma pesquisa de descoberta eletrônica não encontra conteúdos da lixeira para colocar uma retenção.

> [!NOTE]
> Devido ao [primeiro princípio de retenção](retention.md#the-principles-of-retention-or-what-takes-precedence), a eliminação permanente será sempre suspensa se o mesmo item tiver que ser retido por causa de outra política de retenção ou etiqueta de retenção, ou se estiver sob Descoberta Eletrônica por motivos legais ou de investigação.

Quando as configurações forem reter somente ou excluir somente, os caminhos de conteúdo serão variações de reter e excluir:

### <a name="content-paths-for-retain-only-retention-settings"></a>Caminhos de conteúdo para as configurações de reter somente

1. **Se o conteúdo for modificado ou excluído** durante o período de retenção: uma cópia do documento original é criada na Biblioteca de Retenção para Preservação e retida até o fim do período de retenção, quando a cópia na Biblioteca de Retenção para Preservação é movida para a lixeira de segundo estágio e é excluída permanentemente após 93 dias.

2. **Se o conteúdo não for modificado ou excluído** durante o período de retenção: nada acontece antes e depois do período de retenção; o documento permanecerá no local original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Caminhos de conteúdo para as configurações de excluir somente

1. **Se o conteúdo for excluído** durante o período configurado: o documento será movido para a lixeira de primeiro estágio. Se um usuário excluir o documento da lixeira ou esvaziá-la, o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras de primeiro e de segundo estágio. Após os 93 dias, o documento será excluído permanentemente de onde estiver, seja na lixeira de primeiro ou de segundo estágio. Se o conteúdo for modificado durante o período configurado, ele seguirá o mesmo caminho de exclusão depois do período configurado.

2. **Se o conteúdo não for excluído** durante o período configurado: no final do período configurado na política de retenção, o documento é movido para a lixeira de primeiro estágio. Se um usuário excluir o documento da lixeira ou esvaziá-la (processo também conhecido como limpeza), o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras de primeiro e de segundo estágio. Após os 93 dias, o documento será excluído permanentemente de onde estiver, seja na lixeira de primeiro ou de segundo estágio. Como a lixeira não está indexada, ela não está disponível para pesquisa. Como resultado, uma pesquisa de descoberta eletrônica não encontra conteúdos da lixeira para colocar uma retenção.

## <a name="how-retention-works-for-onenote-content"></a>Como funciona a retenção para o conteúdo do Microsoft OneNote

Ao aplicar uma política de retenção a um local que inclui o conteúdo do Microsoft OneNote, nos bastidores, as diferentes seções do Microsoft OneNote são arquivos individuais. Isso significa que cada seção será retida e excluída individualmente, de acordo com as configurações de retenção que você especificar.

## <a name="how-retention-works-with-document-versions"></a>Como funciona a retenção com versões de documentos

O controle de versão é um recurso de todas as listas de documentos e bibliotecas no Microsoft Office SharePoint Online e Microsoft OneDrive. Por padrão, o controle de versão mantém um mínimo de 500 versões principais, embora esse limite possa ser aumentado. Para saber mais, confira [Habilitar e configurar o controle de versão para uma lista ou biblioteca](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37) e [Como funciona o controle de versão em listas e bibliotecas](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247).
  
Quando um documento com versões está sujeito a configurações de retenção para reter esse conteúdo, as versões que são copiadas para a Biblioteca de Retenção de Preservação existem como um item separado. Se as configurações de retenção forem definidas para exclusão no final do período de retenção:

- Se o período de retenção for baseado na data de criação do conteúdo, cada versão terá a mesma data de expiração do documento original. O documento original e suas versões expiram ao mesmo tempo.

- Se o período de retenção for baseado em quando o conteúdo foi modificado pela última vez, cada versão terá sua própria data de expiração com base em quando o documento original foi modificado para criar essa versão. O documento original e suas versões expiram independentemente um do outro.

> [!NOTE]
> As versões retidas desses documentos do Microsoft Office SharePoint Online e do Microsoft OneDrive não podem ser pesquisadas por ferramentas de descoberta eletrônica.

Quando a ação de retenção é excluir o documento, todas as versões que não estão na Biblioteca de Retenção para Preservação serão excluídas ao mesmo tempo, de acordo com a versão atual.

Para itens que estão sujeitos a uma política de retenção (ou uma suspensão da Descoberta eletrônica), os limites de versão da biblioteca de documentos são ignorados até que o período de retenção do documento seja atingido (ou a suspensão da Descoberta eletrônica seja liberada). Nesse cenário, as versões antigas não são eliminadas automaticamente e os usuários são impedidos de excluir versões.

Esse não é o caso dos rótulos de retenção quando o conteúdo não está sujeito a uma política de retenção (ou uma retenção de descoberta eletrônica). Em vez disso, os limites de controle de versão são cumpridos, de modo que as versões mais antigas sejam automaticamente excluídas para acomodar novas versões, mas os usuários ainda poderão excluir versões.

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização

**SharePoint**:

Quando um usuário sai organização, qualquer conteúdo criado por ele não será afetado porque o SharePoint é considerado um ambiente colaborativo, ao contrário da caixa de correio ou da conta OneDrive de um usuário.

**OneDrive**:

Se um usuário sair da organização, quaisquer arquivos sujeitos a uma política de retenção ou que tenham rótulos de retenção permanecerão pela duração da política ou do rótulo.  Durante esse período, todo o acesso à compartilhamentos continua a funcionar. Quando o período de retenção expira, o conteúdo é movido para a Lixeira de Conjuntos de Sites e não pode ser acessado por ninguém, exceto pelo administrador. Se um documento for marcado por um rótulo de retenção como um registro, o documento não será excluído até que o período de retenção termine, após o qual o conteúdo será permanentemente excluído.

## <a name="configuration-guidance"></a>Instruções de configuração

Se você é novo na configuração de retenção no Microsoft 365, consulte [Começar com políticas e rótulos de retenção](get-started-with-retention.md).

Se você estiver pronto para configurar uma política de retenção ou rótulo de retenção do Exchange, consulte as instruções a seguir:
- [Criar e configurar políticas de retenção](create-retention-policies.md)
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)