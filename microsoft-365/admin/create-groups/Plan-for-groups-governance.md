---
title: Planejar a governança de grupos
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Saiba como planejar a governança de grupos do Microsoft 365.
ms.openlocfilehash: e5e3b640edd15cb46fa3da8b65141fe9f63d6399
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322094"
---
# <a name="plan-for-governance-in-groups"></a>Planejar a governança em grupos

O Microsoft 365 grupos tem um conjunto avançado de ferramentas para implementar qualquer recurso de governança que sua organização possa exigir. Este artigo orienta os profissionais de ti a fazer as perguntas certas para determinar seus requisitos de governança e como atendê-los com base em seu perfil organizacional.

## <a name="why-microsoft-365-groups"></a>Por que os grupos Microsoft 365?
![DESC de imagem](../../media/01.png)

Sabemos que as organizações atuais estão usando um conjunto de ferramentas diversificado. Há a equipe de desenvolvedores usando o chat de equipe, os executivos que enviam emails e toda a organização que se conecta através da empresa social. Várias ferramentas de colaboração estão em uso porque cada grupo é exclusivo e tem suas próprias necessidades funcionais e trabalho. Algumas usarão apenas emails, enquanto outros moram principalmente no chat. 

Se os usuários acharem que as ferramentas fornecidas não atendem às suas necessidades, elas provavelmente baixarão seus aplicativos de consumidor favorito que dão suporte aos seus cenários. Embora esse processo permita que os usuários sejam iniciados rapidamente, ele leva a uma experiência de usuário frustrante em toda a organização com vários logins, compartilhamento de dificuldade e sem um local para exibir conteúdo. Esse conceito é conhecido como "Shadow IT" e representa um risco significativo para as organizações. Ele reduz a capacidade de gerenciar de forma uniforme o acesso do usuário, garantir a segurança e as necessidades de conformidade do serviço.

O Microsoft 365 grupos capacita os usuários e reduz o risco de sombreamento de ti, fornecendo em uma única etapa várias das ferramentas necessárias para colaborar. Os grupos do Microsoft 365 permitem que você escolha um conjunto de pessoas com as quais você deseja colaborar e configure facilmente uma coleção de recursos para que as pessoas compartilhem. A atribuição manual de permissões a recursos é uma coisa do passado de que a adição de membros ao grupo concede automaticamente as permissões necessárias a todos os ativos fornecidos pelo grupo.

## <a name="technical-architecture"></a>Arquitetura técnica

Há três métodos de comunicação principais suportados pelos grupos do Microsoft 365. Os grupos podem ser criados dentro dessas experiências e usados no Microsoft 365:
- Outlook: colaboração por email com um grupo compartilhado caixa de entrada e calendário
- Microsoft Teams: um espaço de trabalho com base em chat persistente onde você pode ter conversas informais, em tempo real, em torno de vários tópicos, organizados por subgrupos específicos
- Yammer: experiência social corporativa para colaboração

> [!NOTE]
> Criar um novo grupo por meio de outros aplicativos de trabalho em equipe-como o SharePoint, o Planner ou o Stream-criará um grupo com uma caixa de entrada do Outlook e a capacidade de se conectar ao Microsoft Teams.

Dependendo de onde um grupo é criado, determinados recursos são provisionados automaticamente, como:
- [Caixa de entrada](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -para conversas por email entre membros do grupo. Esta caixa de entrada tem um endereço de email e pode ser definida para aceitar mensagens de pessoas de fora do grupo e até mesmo fora da organização, muito parecida com uma lista de distribuição tradicional.
 - [Calendário](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – para eventos de agendamento relacionados ao grupo
- [Site de equipe do SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – um repositório central para informações, links e conteúdo relacionados ao seu grupo
- [Biblioteca de documentos do SharePoint](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403) – um local central para o grupo armazenar e compartilhar arquivos
- [Bloco de anotações do OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – para coletar ideias, pesquisa e informações
- [Planejador](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – para atribuir e gerenciar tarefas de projeto entre seus membros do grupo
- [Grupo do Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – um local comum para ter conversas e compartilhar informações
- Microsoft Teams – um espaço de trabalho baseado em chat no Microsoft 365

Para saber mais sobre quais recursos foram criados para cada grupo, consulte [saiba mais sobre o Microsoft 365 groups](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> Quando um novo grupo Microsoft 365 é criado via Yammer ou Teams, o grupo não fica visível no Outlook ou no catálogo de endereços porque a comunicação principal entre esses usuários ocorre em seus respectivos clientes. Os grupos do Yammer não podem ser conectados ao Microsoft Teams.

## <a name="where-to-start-a-conversation"></a>Onde iniciar uma conversa
Há vários lugares para ter uma conversa no Microsoft 365. A compreensão de onde iniciar uma conversa pode ajudar as organizações a definir uma estratégia de comunicação.

![DESC de imagem](../../media/03.png)

- Teams: espaço de trabalho baseado em chat (colaboração de alta velocidade) – loop interno
   - Projetado para colaboração com as pessoas com as quais você trabalha todos os dias
  - Coloca informações ao alcance dos usuários em uma única experiência
  - Adicionar guias, conectores e bots
  - Chat ao vivo, conferência de áudio/vídeo, reuniões gravadas

- Yammer: conectar-se ao org (Enterprise social) – loop externo
  - Comunidades de grupos de pessoas de prática, que compartilham um interesse ou conhecimento comum, mas não estão necessariamente trabalhando juntas em uma base diária
  - Conexão de liderança, comunidades de aprendizagem, comunidades baseadas em função

- Grupos do Outlook: DL moderna (colaboração baseada em email)
  - Onipresente para comunicação direcionada
  - Atualizar as DLs para grupos do Microsoft 365 – [por que você deve atualizar?](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – experiência de colaboração de conteúdo principal para todos os grupos da Microsoft 365
  - Cada grupo Obtém um site de equipe do SharePoint conectado
  - Compartilhar conteúdo, criar páginas personalizadas e notícias do autor
  - [Conectar](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) sites de equipe do SharePoint existentes a novos grupos do Microsoft 365

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Gerenciando e controlando o Microsoft 365 em escala

O Microsoft 365 grupos tem um conjunto avançado de ferramentas para implementar qualquer recurso de governança que sua organização possa exigir. A seção a seguir descreve os recursos, recomenda as práticas recomendadas e fornece orientações para fazer as perguntas certas para determinar os requisitos de governança e como atendê-las.

**Nesta seção**:
- [Controlar quem pode criar grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Exclusão e restauração reversível de grupo](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Política de nomeação de grupo](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Política de expiração de grupo](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Acesso de convidado de grupo](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Políticas de grupo & proteção de informações](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Atualizar ferramentas de colaboração tradicionais](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Relatórios de grupos](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Controlar quem pode criar grupos do Microsoft 365
Os grupos podem ser criados por usuários finais de vários pontos de extremidade, incluindo Outlook, SharePoint, equipes e outros ambientes.

![DESC de imagem](../../media/04.png)
> [!Tip]
>- Considere o autoatendimento para os proprietários do grupo.
>- Documente e informe como solicitar um grupo.
>- Reveja quem pode criar grupos durante sua jornada na nuvem.
>- Considere usar associação dinâmica para configurar membros do grupo de segurança para controlar a criação do grupo.
>- Avaliar quais cenários de grupos podem ser gerenciados por meio de uma associação dinâmica e permitir autoatendimento para o resto.

Há três modelos principais de provisionamento em grupos: abrir, orientado por ti e controlado. A tabela a seguir descreve as vantagens de cada modelo.

| Modelo          | Vantagens                                                   |
| -------------- | ------------------------------------------------------------ |
| Abrir (padrão) | Os usuários podem criar seus próprios grupos, conforme necessário, sem precisar aguardar ou se aborrecer. |
| LED de ti         | Os usuários solicitam um grupo dele. Ele pode orientá-los na seleção das melhores ferramentas de colaboração para suas necessidades. |
| Incontrolável     | Criação de grupo restrita a pessoas, equipes ou serviços específicos. Para saber mais, confira [gerenciar quem pode criar grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups). |

Sua organização pode ter requisitos específicos para implementar controles estritos em quem pode criar grupos. Use a tabela a seguir para ajudar a tomar a decisão sobre qual modelo de provisionamento se ajusta à sua organização.

|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Qual modelo de provisionamento atende aos requisitos da sua organização?</li><li>Sua organização precisa limitar a criação de grupos aos administradores?</li><li>Sua organização requer limitar a criação de grupos aos membros do grupo de segurança?</li><li>Sua organização exige que alguns grupos sejam criados dinamicamente com base em atributos de usuário, como departamento?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documentar os requisitos de sua organização para a criação de grupos e equipes.</li><li>Planeje a implementação desses requisitos como parte da distribuição de seus grupos.</li><li>Comunicar e publicar suas políticas para informar os usuários sobre o comportamento que podem esperar</li><li>Planejar a implementação da associação dinâmica, quando aplicável.</li></ul>|

> [!Important]
> Limitar o grupo e a criação de equipe pode reduzir a produtividade dos usuários, pois muitos serviços do Microsoft 365 exigem que os grupos sejam criados para que o serviço funcione. Para saber mais, confira [por que controlar quem cria os grupos do Microsoft 365?](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*Recursos*
- [Gerenciar quem pode criar grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Preencher grupos dinamicamente com base em atributos de objeto](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Como alterar a configuração padrão de grupos do Microsoft 365 para Outlook, público ou privado](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Sincronizando grupos de segurança com associação à equipe](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>Exclusão e restauração reversível de grupo
Se você tiver excluído um grupo do Microsoft 365, por padrão, ele será mantido por 30 dias. Esse período de 30 dias é denominado "exclusão temporária" porque ainda é possível restaurar o grupo. Após 30 dias, o grupo e o conteúdo associado são excluídos permanentemente e não podem mais ser restaurados.

> [!Tip]
>- Comunique o processo de restauração aos seus usuários.
>- Treine sua equipe de assistência técnica.
>- Rastrear grupos futuros que serão excluídos usando o script do PowerShell.

|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Você precisa que determinados ativos sejam arquivados para armazenamento de longo prazo?</li><li>Você tem determinados requisitos de retenção para sua organização?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Comunicar e publicar as políticas de exclusão e restauração para informar os usuários sobre o comportamento que podem esperar </li><li> Documente seus requisitos de organização para o monitoramento de grupos excluídos.</li><li>Planeje a implementação desses requisitos como parte da distribuição de seus grupos.</li></ul>|

> [!Important]
>Durante o período de "exclusão temporária", se um usuário tentar acessar, verá uma mensagem 403 Proibido. Após esse período, se o usuário tentar acessar o site, verá uma mensagem 404 Não Encontrado.

#### <a name="resources"></a>*Recursos*
- [Restaurar um grupo do Microsoft 365 excluído](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Restaurar um grupo do Microsoft 365 excluído no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Excluir grupos usando o cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>Política de nomeação de grupo
Uma política de nomenclatura pode ajudar você e seus usuários a identificar a função do grupo, da associação, da região geográfica ou quem criou o grupo. A política de nomenclatura também pode ajudar a categorizar grupos no catálogo de endereços. Você pode usar a política para bloquear a utilização de palavras específicas em nomes de grupo e aliases.

> [!Tip]
> - Usar cadeias de caracteres curtas como sufixo.
> - Use atributos com valores.
> - Não seja muito criativo, o comprimento total do nome tem um máximo de 264 caracteres.
> - Carregue suas palavras bloqueadas específicas da organização para restringir o uso.


|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Sua organização requer uma Convenção de nomenclatura específica para grupos?</li><li>Sua organização requer a Convenção de nomenclatura em todas as cargas de trabalho?</li><li>Sua organização tem palavras específicas que você deseja impedir que os usuários usem?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documente os requisitos de sua organização para grupos de nomeação. </li><li> Planeje a implementação desses requisitos como parte da distribuição de seus grupos.</li><li> Comunicar e publicar as políticas de nomeação e padrões para informar os usuários.</li></ul>|

> [!Important]
>A política de nomenclatura é aplicada a grupos criados em todas as cargas de trabalho de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Ela é aplicada ao nome do grupo e ao alias do grupo. Ela é aplicada quando um usuário cria um grupo e quando o nome ou o alias do grupo é editado para um grupo existente.

#### <a name="resources"></a>*Recursos*
- [Política de nomenclatura de grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Aplicar uma política de nomenclatura para grupos do Microsoft 365 no Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Cmdlets do Azure Active Directory para definição de configurações de grupo](https://go.microsoft.com/fwlink/?linkid=868341)
- [Recursos de visualização para nomeação de grupo](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>Política de expiração de grupo
Os administradores podem especificar um período de expiração e qualquer grupo que atinja o final desse período, e não será renovado, será excluído. O período de expiração começa quando o grupo é criado ou na data da última renovar. Os proprietários de grupo receberão automaticamente um email antes da expiração, permitindo que eles renovem o grupo para outro intervalo de expiração. Os grupos ativos são renovados automaticamente.

Depois de definir um grupo para expirar:
- Os proprietários do grupo são notificados a renovar o grupo como a expiração
- Qualquer grupo não renovado é excluído
- Qualquer grupo excluído pode ser restaurado dentro de 30 dias pelos proprietários do grupo ou pelo administrador

> [!Tip]
> - Piloto com grupos específicos inicialmente.
> - Escolha grupos inativos com base no relatório de atividades no centro de administração do Microsoft 365.
> - Comunique o processo de renovação a proprietários de grupo.
> - Integração da equipe de assistência técnica.
> - Verifique se os grupos têm vários proprietários e configure o email para grupos órfãos.


|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Sua organização exige a especificação de uma data de validade para as equipes?</li><li>Determinar a estratégia para lidar com grupos órfãos.</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documentar os requisitos de sua organização para a expiração de grupo, a retenção de dados e o arquivamento.</li><li>Planeje a implementação desses requisitos como parte da distribuição de seus grupos.</li><li>Planejar a implementação de um trabalho personalizado para relatar grupos com proprietários únicos ou não proprietários. </li></ul>|

> [!Important]
>Quando você altera a política de expiração, o serviço recalcula a data de expiração de cada grupo. Ele sempre inicia a contagem a partir da data em que o grupo foi criado e, em seguida, aplica a nova política de expiração.

#### <a name="resources"></a>*Recursos*
- [Política de expiração de grupo do Microsoft 365](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Configurar a política de expiração para grupos do Microsoft 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>Acesso de convidado de grupo
Os administradores podem controlar se permitirá o acesso de convidados a grupos do Microsoft 365 para toda a sua organização ou para grupos individuais da Microsoft 365. Eles também podem controlar quem permite que os convidados sejam adicionados aos grupos.
>[!Tip]
>- Habilitar o acesso de convidados no nível do locatário. Se necessário, bloqueie os grupos específicos.
>- Controle usando permissões/bloqueio de domínios convidados, função de convidador de convidados, revisões de acesso, termos de uso.
>- Rastrear a atividade do usuário convidado por meio de logs de auditoria.

|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Você precisa restringir a capacidade de adicionar convidados ao Teams por grupo?</li><li> Sua organização precisa apresentar avisos de isenção de responsabilidade relevantes para requisitos legais ou de conformidade?</li><li>Sua organização tem a necessidade de reduzir o cabeçalho administrativo de adicionar e remover usuários?</li><li>Sua organização espera controles de auditoria para acesso de convidados/externos?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documentar requisitos de acesso de convidados/externos para determinados grupos classificados, incluindo o período de retenção e a ocorrência.</li><li>Documente os requisitos da organização para quais grupos exigirão termos de uso e análise de acesso. </li><li>Execute revisões para gerenciar de forma eficiente as associações de grupo para usuários internos e convidados.</li></ul>|


#### <a name="resources"></a>*Recursos*
- [Colaborar com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Gerenciar o acesso de convidados nos grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Acesso de convidados nos grupos do Microsoft 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Revisões de acesso ao Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Recurso de termos de uso do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Federação do Google](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>Políticas de grupo & proteção de informações
O Microsoft 365 groups baseia-se nos recursos avançados de segurança e conformidade do Microsoft 365 e oferece suporte a classificações, auditorias e relatórios, pesquisa de conteúdo de conformidade, pesquisa de e-Discovery, retenção legal e políticas de retenção.
>[!Tip]
>- Configurar a classificação, as diretrizes de uso e os rótulos alinhados às necessidades da sua organização.
>- As políticas de retenção podem ser definidas independentemente dos rótulos.
>- Atividades de grupos de auditoria: criação, exclusão, etc.
>- Gerenciar privacidade de grupo e acesso de convidado com base na classificação.

|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Sua organização tem requisitos de uso específicos que precisam ser comunicados a todos os usuários?</li><li>Sua organização requer as classificações de todo o conteúdo?</li><li>Sua organização exige que o conteúdo seja retido por um período específico de tempo?</li><li>Sua organização exige que políticas de retenção de dados específicas sejam aplicadas a grupos?</li><li>Sua organização espera exigir a capacidade de arquivar grupos inativos para preservar o conteúdo?</li><li>Os criadores de grupo precisam da capacidade de atribuir classificações específicas da organização ao Teams?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documentar as diretrizes de uso de sua organização para grupos</li><li>Documentar os requisitos de classificação da sua organização.</li><li>Determine as políticas a serem aplicadas com base na classificação, por exemplo, confidencialidade, retenção, acesso de convidado.</li><li>Defina os rótulos de sensibilidade para sua organização e quais configurações de proteção você deseja associar.</li><li>Defina uma política de rótulo para controlar quais usuários e grupos serão exibidos nesses rótulos.</li><li>Configure a [visualização do rótulo de confidencialização de grupos](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) e comece a classificar os grupos em sua organização.</li><li>Planeje a implementação desses requisitos como parte da distribuição de seus grupos.</li></ul>|


#### <a name="resources"></a>*Recursos*
- [Link para suas diretrizes de uso de grupos do Microsoft 365](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Definir configurações de grupo](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Visão geral de políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Visão geral de rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [Visão geral de rótulos](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [Pesquisas o log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [Criar ou remover um bloqueio legal no local](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Criar uma política de preservação](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Executar uma pesquisa de conteúdo no centro de conformidade & segurança](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Criação e publicação em massa de rótulos de retenção usando o PowerShell](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>Atualizar ferramentas de colaboração tradicionais
Há anos que as organizações confiaram nos grupos de distribuição para se comunicar e colaborar com grupos de pessoas dentro e fora da empresa. Agora, no entanto, os grupos do Microsoft 365 no Outlook oferecem uma solução mais poderosa para colaboração. Além disso, ser capaz de conectar um grupo do Microsoft 365 a um site existente do SharePoint é importante se você quiser modernizar esse site.

>[!Tip]
>- Atualize facilmente todas as listas de distribuição qualificadas em segundos por meio do centro de administração do Exchange ou usando cmdlets do PowerShell.
>- Conectar sites de equipe do SharePoint existentes a novos grupos do Microsoft 365.

|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Sua organização tem listas de distribuição que [não estão qualificadas](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) para atualização?<li>Determine de qual tipo de grupo é a melhor migração da lista de distribuição.</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Identificar quais listas de distribuição seriam candidatos para atualização para os grupos do Microsoft 365.</li><li>Analise seus sites de equipe existentes do SharePoint para ver quais sites estão prontos para serem conectados ao grupo.</li><li>Deixe outras equipes em sua empresa saber que você atualizou seu grupo de distribuição e quais etapas você levou para fazê-lo com êxito!</li></ul>|


#### <a name="resources"></a>*Recursos*
- [Atualizar listas de distribuição (DL) para grupos no Outlook](https://aka.ms/whyupgradedls)
- Atualização com um clique por meio do centro de administração do Exchange ou por [scripts do PowerShell](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)
- [Migrar listas de distribuição para o Microsoft 365 groups-ajuda para administradores](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Conectar sites existentes do SharePoint a grupos do Microsoft 365:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [Analisar e usar os dados do verificador](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [Verificador de modernização do SharePoint](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (uma ferramenta localizada no GitHub)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>Relatórios de grupos
O painel de relatórios do Microsoft 365 mostra a visão geral das atividades em todos os produtos da Microsoft em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto.
> [!TIP]
>- Você pode usar os relatórios de grupos para obter informações sobre a atividade dos grupos do Microsoft 365 em sua organização e ver quantos grupos estão sendo criados e usados.
>-O relatório de grupos do Microsoft 365 pode ser exibido para as tendências dos últimos sete dias, 30 dias, 90 dias ou 180 dias.
>- Monitorar a atividade de grupo em conversas de caixa de correio de grupo, atividade de arquivo/site de grupo, detalhes sobre a associação de grupo, incluindo contagens de membros externos
>- Monitore regularmente para acessar os proprietários de grupo de grupos ativos para aprender a usar os casos e amplificar-os internamente.
>- Aproveite os pacotes de conteúdo do Power BI para obter informações adicionais.


|         |         |         |
|---------|---------|---------|
|![DESC de imagem](../../media/decision_point.png)|Pontos de decisão|<ul><li>Sua organização precisa de relatórios regulares para entender o uso de grupos do Microsoft 365?<li>Sua organização requer o relatório de todos os grupos que possuem membros externos?</li></ul>|
|![DESC de imagem](../../media/next_steps.png)|Próximas etapas|<ul><li>Documentar os requisitos de sua organização para a análise regular de relatórios de atividade de grupos.</li></ul>|


#### <a name="resources"></a>*Recursos*
- [Relatórios do Microsoft 365 no centro de administração](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Pacote de conteúdo de adoção do Office 365](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Pacote de conteúdo do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [API de atividade de grupos do Microsoft Graph](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Relatório de grupos do Microsoft 365 (grupos unificados)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Relatórios de atividades de auditoria no portal do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph-usar a consulta Delta para controlar alterações](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Introdução com base em sua jornada de adoção na nuvem

O Microsoft 365 grupos fornece um rico conjunto de recursos de governança que sua organização pode exigir. Considere os perfis de organização a seguir como orientação para entender as práticas recomendadas, faça as perguntas certas para determinar os requisitos de governança e como atendê-los.

**Considere os seguintes perfis de organização:**
- Pequena empresa
- Empresas de médio porte
- Regulamentado ou empresarial

### <a name="small-business"></a>Pequena empresa
Considere uma organização que implantou o Microsoft 365 com pelo menos licenças do Exchange Online e do SharePoint Online que inclui os planos Business Essentials e Business Premium, e os planos Enterprise E1, E3 e E5 sem o Licenciamento Premium do Azure active director.

| Etapa | Descrição |
| --------------- | ------------------------------------------------------------ |
| Orientação |<ul><li>Considere um modelo de provisionamento de autoatendimento.</li><li> Os grupos no Outlook & sites do SharePoint são [privados por padrão](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Os grupos podem ser criados por meio da atualização de listas de distribuição existentes (DLs) uma ou em massa por meio do PowerShell. Consulte [upgrade Distribution Lists to Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</li><li> Habilite o acesso de convidados, mas administre usando permitir/bloquear domínios convidados.</li><li> Use o Group Reporting para obter informações sobre como os usuários estão usando grupos.</li><li> Considere a criação de uma equipe do Microsoft Teams para toda a organização como uma maneira de todos fazer parte de uma única equipe para colaboração. </li></ul>|
| Próximas Etapas      |<ul><li>Considere usar [designs de site e scripts de site](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) para definir o design padrão para controles usando as ações definidas dentro da [referência de esquema JSON](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Revisar [grupos de relatórios](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups).</li><li>Rastreie grupos totais e grupos inativos/ativos.</li><li>Acompanhar o armazenamento do Exchange e do SharePoint usado.</li><li>Exibir atividade de grupo entre conversas de caixa de correio de grupo, atividade de arquivos/sites de grupo, etc.</li></ul> |

### <a name="medium-sized-business"></a>Empresas de médio porte
Além das recomendações acima, considere o seguinte para empresas de médio porte que implantou o Microsoft 365 com pelo menos um Enterprise E3/E5 com licenças do Azure Active Directory Premium P1.

| Etapa | Descrição |
| --------------- | ------------------------------------------------------------ |
| Orientação |<ul><li>Decida sobre um modelo de provisionamento aberto ou orientado a ti.</li><li> Considere a criação de determinados grupos vinculados às [regras de associações dinâmicas](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) com base nos atributos do Azure ad como departamento</li><li> Defina classificações dentro da sua organização por exemplo, altamente confidencial, confidencial (padrão), geral.</li><li>  Definir as políticas com base na classificação, como retenção e sensibilidade.</li><li> O SharePoint é o serviço de conteúdo para cada grupo do Microsoft 365. Considere projetar e [implantar sites do SharePoint Online para três camadas de proteção](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) (linha de base, confidencial e altamente confidencial). Para obter mais informações sobre essas três camadas de proteção, consulte [Proteção de arquivos e sites do SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</li><li> Os grupos públicos e privados são listados na GAL por padrão. Determine quais grupos você deseja que apareçam na GAL especificamente grupos criados fora do Microsoft Teams.  Use o cmdlet [set-Unified](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) Group "HiddenFromAddressListsEnabled" ou "HidefromExchangeClients" para ocultar grupos específicos.</li></ul> |
| Próximas Etapas      |<ul><li>Definir [diretrizes de uso](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) para instruir seus usuários sobre as práticas recomendadas que ajudam a manter seus grupos em vigor e informá-los sobre políticas de conteúdo interno. Por exemplo, noções básicas sobre classificações, políticas e procedimentos. </li><li>Defina o período do ciclo de vida do grupo que os grupos devem ser renovados ou serão excluídos-política de expiração.</li><li>Considere a criação dos seguintes trabalhos personalizados para implementar políticas com base em classificações.</li><li>Defina a privacidade como privada.</li><li>Desabilitar Associação/compartilhamento externo. </li><li>Emails para notificar os membros do grupo sobre grupos sem [proprietário](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</li><li>Impor política de propriedade (proprietários min. 2).</li><li> Definir políticas de retenção para grupos com base na classificação. </li><li>Visão geral das políticas de retenção.</li><li>Usando o PowerShell para identificar grupos com uma classificação e [set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Considere usar designs de site e scripts de site para definir os controles usando as ações definidas dentro da [referência do esquema JSON](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Considere [a criação de um diretório de sites simples usando um design de site](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) e o Microsoft Flow. Sempre que um site é criado usando o design do site, os detalhes do site são capturados e escritos em uma lista. </li></ul>|

### <a name="regulated-or-enterprise"></a>Regulamentado ou empresarial
Além das recomendações acima, considere o seguinte para o tipo de entrada altamente regulamentada ou grande-prises, como governo, serviços financeiros ou assistência médica, que implantou o Office 365 com pelo menos um Enterprise E3/E5 com licenças do Azure Active Directory Premium P1/P2.

| Etapa | Descrição |
| --------------- | ------------------------------------------------------------ |
| Orientação |<ul><li> Definir políticas para a governança de dados do site do SharePoint associado ao grupo com base na classificação.</li><li>[Proteger arquivos do SharePoint Online com rótulos e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Proteger arquivos do SharePoint Online com a proteção de informações do Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Site de grupo provisionado na região vinculada ao local de dados preferencial do usuário ([várias GEOS](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)).</li><li> Revisões de associação para grupos com membros externos ([revisões de acesso](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)).</li><li>Certifique-se de que os funcionários ou usuários convidados vejam avisos de isenção de responsabilidade relevantes para requisitos legais ou de conformidade antes de obter acesso. ([termos de uso](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)).</li><li>Identificar e relatar os grupos do Microsoft 365 com uma determinada [classificação que também tenha usuários externos](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561).</li><li>Grupos secretos em que as associações necessárias para serem ocultas devem ser criadas usando o cmdlet [New-unificado](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (usando a opção MembershipEnabled oculto) na criação de grupo.</li><li>Definir os [Rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) da organização para [restringir o acesso ao conteúdo usando a criptografia](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) e publicar em grupos específicos do Microsoft 365.</li><li>Impedir que o conteúdo confidencial saia da sua organização em dispositivos que executam o Windows usando [Rótulos de confidencialidade com a proteção de informações do Windows](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). |
| Próximas Etapas      | <ul><li> Use o design de site e scripts de site para definir as [ações](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) padrão que ocorrem quando um novo site é criado. Por exemplo, [Configure o compartilhamento externo](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) ou [acione um fluxo da Microsoft para chamar uma função do Azure](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) para aplicar configurações que não têm suporte nativo. </li><li> Requisitos de documento para [proteger arquivos do SharePoint Online com rótulos e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para sites associados a grupos do Microsoft 365.</li><li>Documentar requisitos de organização para [proteger sites e arquivos do SharePoint Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) que estão conectados a grupos do Microsoft 365. </li><li>Documentar requisitos de organização para publicar [Rótulos de sensibilidade](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) para usuários ou grupos específicos para proteger o conteúdo.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Lista de verificação de planejamento de recursos de gerenciamento de grupos

Vários controles relacionados a grupos podem ser administrados por meio do Azure Active Directory. Para saber mais sobre como definir as configurações de grupo, confira [cmdlets do Azure Active Directory para definir as configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

Use a tabela a seguir para determinar quais recursos você precisará para implantar seus requisitos de organização. Ele o ajudará a determinar quais licenças você precisa para que você possa planejar o futuro.

| **Funcionalidade**      | **Detalhes**                                    | **Licença do Azure AD Premium necessária** | **Decisão** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Política de nomeação de grupo | Use palavras bloqueadas personalizadas com base no sufixo de prefixo. | P1                                    |      A definir     |
| Classificação de grupo | Atribuir classificações ao Teams. | P1                                    |   A definir        |
| Acesso de convidado de grupo | Permitir ou impedir que convidados sejam adicionados aos grupos. | Não                                    |  A definir        |
| Criação de grupo | Limitar a criação de equipe aos administradores. | Não                                    |   A definir        |
| Criação de grupo | Limitar a criação de equipe aos membros do grupo de segurança. | P1                                    |     A definir      |
| Diretrizes de uso de grupo | Definir um link as diretrizes de uso de grupo que serão visíveis em todos os pontos de extremidade de criação de grupo. | P1                                    |   A definir        |
| Associação oculta | Ocultar os membros do grupo Microsoft 365 dos usuários que não são membros do grupo | Não                                    |   A definir        |
| Política de expiração | Gerenciar o ciclo de vida de grupos do Microsoft 365 Configurando uma política de expiração. | P1                                    |  A definir        |
| Relatórios de atividades de grupo | Obtenha informações sobre a atividade de grupos do Microsoft 365 em sua organização e veja quantos grupos da Microsoft 365 estão sendo criados e usados. | Não                                    |    A definir       |
| Diretiva de retenção | Reter ou excluir dados de um período de tempo específico definindo políticas de retenção para os grupos do Microsoft 365 no centro de conformidade do & de segurança. **Observação:** O uso deste recurso requer o licenciamento do Office 365 Enterprise E3 ou superior. | Não                                    |    A definir       |
| Política de prevenção contra perda de dados | Identificar informações confidenciais em sites conectados ao grupo do Microsoft 365 e impedir o compartilhamento acidental. **Observação:** O uso deste recurso requer o licenciamento do Office 365 Enterprise E3 ou superior. | Não                                    |     A definir      |
| Arquivar e restaurar | Arquive uma equipe quando ela não estiver mais ativa, mas você quiser mantê-la em torno da referência ou reativar no futuro. | Não                                    |   A definir        |
| Revisões de acesso | Executar revisões para gerenciar de forma eficiente as associações de grupo para usuários internos e convidados | P2                                    |   A definir       |
| Termos de Uso | Um método simples que as organizações podem usar para apresentar informações aos usuários finais. Esta apresentação garante que os usuários vejam avisos de isenção de responsabilidade relevantes para requisitos legais ou de conformidade. | P1                                    |         A definir  |

