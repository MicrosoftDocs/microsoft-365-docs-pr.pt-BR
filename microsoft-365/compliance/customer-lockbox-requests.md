---
title: Solicitações de Lockbox do Cliente
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba mais sobre solicitações de Customer Lockbox que permitem controlar como um engenheiro de suporte da Microsoft pode acessar seus dados quando você corre para um problema.
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922705"
---
# <a name="customer-lockbox-in-office-365"></a>Customer Lockbox in Office 365

Este artigo fornece diretrizes de implantação e configuração para o Customer Lockbox. O Sistema de Proteção de Dados do Cliente dá suporte a solicitações de dados de acesso nos aplicativos Exchange Online, SharePoint Online e OneDrive for Business.  Para recomendar suporte para outros serviços, envie uma solicitação em Office 365 [UserVoice](https://office365.uservoice.com/).

Para ver as opções de licenciamento de seus usuários para se beneficiarem de ofertas de conformidade Microsoft 365, incluindo esta, a partir de 1º de abril de 2020, consulte as diretrizes de licenciamento Microsoft 365 para conformidade & [segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

O Customer Lockbox garante que a Microsoft não possa acessar seu conteúdo para executar uma operação de serviço sem sua aprovação explícita. O Sistema de Proteção de Dados do Cliente leva você para o fluxo de trabalho de aprovação para solicitações de acesso ao seu conteúdo.

Ocasionalmente, os engenheiros da Microsoft ajudam a solucionar e corrigir problemas relatados por clientes no processo de suporte. Normalmente, os problemas são corrigidos por meio de ferramentas de depuração e telemetria abrangentes que a Microsoft possui para seus serviços. No entanto, alguns casos exigem que um engenheiro da Microsoft acesse o conteúdo do cliente para determinar a causa raiz e corrigir o problema. O Sistema de Proteção de Dados do Cliente exige que o engenheiro solicite acesso do cliente como uma etapa final no fluxo de trabalho de aprovação. Isso oferece às organizações a opção de aprovar ou negar essas solicitações e fornecer controle de acesso direto ao cliente.

### <a name="customer-lockbox-overview-video"></a>Vídeo de visão geral do Customer Lockbox

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>Fluxo de trabalho do Sistema de Proteção de Dados do Cliente

As seguintes etapas descrevem o fluxo de trabalho típico quando um engenheiro da Microsoft inicia uma solicitação do Sistema de Proteção de Dados do Cliente:

1. Uma pessoa de uma organização tem um problema com a caixa de correio do Microsoft 365.

2. Depois de tentar solucionar o problema, mas não conseguir, será aberta uma solicitação de suporte junto à Microsoft.

3. Um engenheiro de Suporte da Microsoft analisa a solicitação de serviço e determina a necessidade de acessar o locatário da organização para reparar o problema no Exchange Online.

4. O engenheiro de Suporte da Microsoft entra na ferramenta de solicitação do Sistema de Proteção de Dados do Cliente e faz uma solicitação de acesso aos dados que inclui o nome do locatário da organização, o número da solicitação de serviço e o tempo estimado que o engenheiro precisará para acessar os dados.

5. Depois que um gerente de Suporte da Microsoft aprovar a solicitação, o Sistema de Proteção de Dados do Cliente enviará ao aprovador designado na organização uma notificação por email sobre a solicitação de acesso pendente da Microsoft.

    ![Exemplo de uma notificação de email do Customer Lockbox](../media/CustomerLockbox1.png)

   Qualquer pessoa que tenha a função de administrador [aprovador](/office365/admin/add-users/about-admin-roles) de acesso ao Cofre de Cliente no centro de administração Microsoft 365 pode aprovar solicitações de Caixa de Bloqueio do Cliente.

6. O aprovador entrará no centro de administração Microsoft 365 e aprovará a solicitação. Esta etapa aciona a criação de um registro de auditoria disponível pesquisando o log de auditoria. Para obter mais informações, consulte [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).

   Se o cliente rejeitar a solicitação ou não aprovar a solicitação dentro de 12 horas, a solicitação expirará e nenhum acesso será concedido ao engenheiro da Microsoft.

   > [!IMPORTANT]
   > A Microsoft não inclui links em notificações de email do Customer Lockbox exigindo que você entre Office 365.

7. Depois que o aprovador da organização aprovar a solicitação, o engenheiro da Microsoft receberá a mensagem de aprovação, fará o logon do locatário no Exchange Online e corrigirá o problema do cliente. Os engenheiros da Microsoft têm o tempo solicitado para corrigir o problema, após o qual o acesso será revogado automaticamente.

> [!NOTE]
> Todas as ações realizadas por um engenheiro da Microsoft são registradas no log de auditoria. Você pode pesquisar e analisar esses registros de auditoria.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Ativar ou desativar solicitações de Caixa de Bloqueio do Cliente

Você pode ativar os controles do Sistema de Proteção de Dados do Cliente no Centro de administração do Microsoft 365. Ao ativar o Customer Lockbox, a Microsoft deve obter a aprovação da sua organização antes de acessar qualquer conteúdo do locatário.

1. Usando uma conta de trabalho ou de estudante que tenha o administrador global ou a função de aprovador de acesso ao **Customer Lockbox** atribuída, acesse [https://admin.microsoft.com](https://admin.microsoft.com) e entre.

2. Escolha **Configurações > Org Configurações**.

3. Selecione **Segurança & Edição** do Cofre de Privacidade do Cliente e, em seguida, mova a alternância para Ativar ou Desativar para ativar ou desativar o  >    >  recurso.  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Aprovar ou negar uma solicitação de Proteção de Dados do Cliente

1. Usando uma conta de trabalho ou de estudante que tenha o administrador global ou a função de aprovador de acesso ao **Customer Lockbox** atribuída, acesse [https://admin.microsoft.com](https://admin.microsoft.com) e entre.

2. Escolha **Suporte > Solicitações de Caixa de Bloqueio do Cliente.**

    ![Clique em Suporte e em Solicitações de Caixa de Bloqueio do Cliente](../media/CustomerLockbox5.png)

    Uma lista de solicitações de Caixa de Bloqueio do Cliente é exibida.

    ![Lista de solicitações do Customer Lockbox](../media/CustomerLockbox6.png)

3. Selecione uma solicitação de Caixa de Bloqueio do Cliente e escolha **Aprovar ou** **Negar**.

    ![Aprovar ou negar solicitações de Cofre do Cliente](../media/CustomerLockbox7.png)

    Uma mensagem de confirmação sobre a aprovação da solicitação de Caixa de Bloqueio do Cliente é exibida.

    ![Aprovar ou negar solicitações de Cofre do Cliente](../media/CustomerLockbox8.png)

> [!NOTE]
> Use o cmdlet Set-AccessToCustomerDataRequest para aprovar, negar ou cancelar solicitações de sistema de proteção de dados do cliente do Microsoft 365 que controlam o acesso aos seus dados por engenheiros de suporte da Microsoft. Para obter mais informações, [consulte Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).


## <a name="auditing-customer-lockbox-requests"></a>Auditoria de solicitações de Proteção de Dados do Cliente

Os registros de auditoria que correspondem às solicitações do Customer Lockbox são registrados no log de auditoria. Você pode acessar esses logs usando a ferramenta de pesquisa [de log](search-the-audit-log-in-security-and-compliance.md) de auditoria no Centro de Conformidade & Segurança. Ações relacionadas a aceitar ou negar uma solicitação de Caixa de Bloqueio de Clientes e ações executadas pelos engenheiros da Microsoft (quando as solicitações de acesso são aprovadas) também são registradas no log de auditoria. Você pode pesquisar e analisar esses registros de auditoria.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>Pesquisar no log de auditoria atividades relacionadas a solicitações do Customer Lockbox

Antes de poder usar o log de auditoria para controlar as solicitações do Sistema de Proteção de Dados do Cliente, há algumas etapas que você precisa tomar para configurar o log de auditoria. Para obter mais informações, [consulte Pesquisar o log de auditoria no Centro de Conformidade & Segurança.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) Depois de concluir a instalação, use estas etapas para criar uma consulta de pesquisa de log de auditoria para retornar registros de auditoria relacionados ao Customer Lockbox:

1. Acesse [https://protection.office.com](https://protection.office.com).
  
2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo do Centro de Conformidade & segurança, escolha **Pesquisar**&  >  **pesquisa de log de auditoria de investigação.**

    A **página de pesquisa de log** de auditoria é exibida.

    ![Página de pesquisa de log de auditoria](../media/auditlogsearch1.png)
  
4. Configure os seguintes critérios de pesquisa: 

    1. **Atividades** - Deixe esse campo em branco para que a pesquisa retorne registros de auditoria para todas as atividades. Isso é necessário para retornar quaisquer registros de auditoria relacionados a solicitações de Customer Lockbox e atividades correspondentes executadas pelos engenheiros da Microsoft.

    1. **Data de** início **e data de** término - Selecione uma data e intervalo de tempo para exibir os eventos que ocorreram nesse período.

    1. **Usuários** - Deixe esse campo em branco.

    1. **Arquivo, pasta ou site** - Deixe este campo em branco.

5. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. 

    Os resultados da pesquisa são carregados e, após alguns instantes, eles são exibidos em **Resultados** na página de pesquisa **de log de** auditoria.

6. Clique **em Filtrar** resultados na página de resultados da pesquisa e faça uma das seguintes coisas:

   - Para exibir registros de auditoria relacionados a um aprovador em sua organização aprovando  ou negando uma solicitação de Caixa de Bloqueio do Cliente: Na caixa na coluna Atividade, digite **Set-AccessToCustomerDataRequest**.

   - Para exibir registros de auditoria relacionados a um engenheiro da Microsoft executando ações  em resposta a uma solicitação de Caixa de Bloqueio do Cliente aprovada: na caixa na coluna Usuário, digite **Operador microsoft**. A **coluna Atividade** exibe a ação executada pelo engenheiro.

      ![Filtrar em "Microsoft Operator" para exibir registros de auditoria](../media/CustomerLockbox10.png)

7. Na lista de resultados, clique em um registro de auditoria para exibi-lo.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Registro de auditoria de uma solicitação de acesso do Sistema de Proteção de Dados do Cliente

Quando uma pessoa em sua organização aprova ou nega uma solicitação de Caixa de Bloqueio do Cliente, um registro de auditoria é registrado no log de auditoria. Esse registro contém as seguintes informações.

| Propriedade de registro de auditoria| Descrição|
|:---------- |:----------|
| Date       | A data e a hora em que a solicitação de Proteção de Dados do Cliente foi aprovada ou negada.
| Endereço IP | O endereço IP do computador usado pelo aprovador para aprovar ou recusar uma solicitação. |
| Usuário       | A conta de serviço BOXServiceAccount@ \[ customerforest \] .prod.outlook.com.            |
| Atividade   | Set-AccessToCustomerDataRequest: esta é a atividade de auditoria registrada quando você aprova ou nega uma solicitação de Proteção de Dados do Cliente.                                |
| Item       | O Guid da solicitação de Caixa de Bloqueio do Cliente                             |

A captura de tela a seguir mostra um exemplo de um registro de log de auditoria que corresponde a uma solicitação de Caixa de Bloqueio de Cliente aprovada. Se uma solicitação de Caixa de Bloqueio de Cliente foi negada, o valor do parâmetro **ApprovalDecision** seria **Deny**.

![Registro de auditoria de uma solicitação de Caixa de Bloqueio do Cliente aprovada](../media/CustomerLockbox9.png)

> [!TIP]
> Para exibir informações mais detalhadas em um registro de auditoria, clique **em Mais informações.**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Registro de auditoria para uma ação executada por um engenheiro da Microsoft

As ações executadas por um engenheiro da Microsoft após uma solicitação de Proteção de Dados do Cliente ser aprovada (e que podem resultar em acessar o conteúdo do cliente) são registradas no log de auditoria. Esses registros contêm as seguintes informações.

| Propriedade de registro de auditoria| Descrição|
|:---------- |:----------|
| Date       | Data em que a ação foi executada. Observe que o tempo em que essa ação foi realizada será de até quatro horas após a solicitação de Proteção de Dados do Cliente ter sido aprovada.              |
| Endereço IP | O Endereço IP da máquina da Microsoft usada pelo engenheiro. |
| Usuário       | Microsoft Operator: esse valor indica que esse registro está relacionado a uma solicitação de Proteção de Dados do Cliente.                                  |
| Atividade   | Nome da atividade realizada pelo engenheiro da Microsoft.|
| Item       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>A quais Microsoft 365 serviços se aplicam ao Customer Lockbox?

O Customer Lockbox atualmente tem suporte no Exchange Online, SharePoint Online e OneDrive for Business.

#### <a name="is-customer-lockbox-available-to-all-customers"></a>O Customer Lockbox está disponível para todos os clientes?

O Customer Lockbox está incluído nas assinaturas Microsoft 365 ou Office 365 E5 e pode ser adicionado a outros planos com uma Proteção de Informações e Conformidade ou uma assinatura de complemento de Conformidade Avançada. Confira [Planos e preços para](https://products.office.com/business/office-365-enterprise-e5-business-software) obter mais informações.

#### <a name="what-is-customer-content"></a>O que é conteúdo do cliente?

O conteúdo do cliente são os dados criados pelos usuários de serviços Microsoft 365 aplicativos. Exemplos de conteúdo do cliente incluem:

- Corpo do e-mail ou anexos de e-mail

- Conteúdo do site do Microsoft Office SharePoint Online

- Informações no corpo de um arquivo do Microsoft Office SharePoint Online

- Skype for Business corpo do arquivo de apresentação

- Mensagens instantâneas (IM) ou conversas de voz

- Dados de blob gerados pelo cliente ou armazenamento estruturado (por exemplo, Contêiners SQL)

- Informações de segurança de propriedade do cliente (por exemplo, certificados, chaves de criptografia e senhas)

- Inferências e todas as inferências subsequentes, se o conteúdo do cliente permanecer

Para obter informações adicionais sobre o conteúdo do cliente Office 365, consulte o [Office 365 Central de Confiações](https://products.office.com/business/office-365-trust-center-privacy/).

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>Who é notificado quando há uma solicitação para acessar meu conteúdo?

Os administradores globais e qualquer pessoa atribuída à função de administrador aprovador de acesso ao Customer Lockbox são notificados. Esses também são os mesmos usuários que podem aprovar as solicitações do Customer Lockbox.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>Who pode aprovar ou rejeitar essas solicitações na minha organização?

Os administradores globais e qualquer pessoa atribuída à função de administrador aprovador de acesso ao Cofre de Cliente pode aprovar solicitações de Caixa de Bloqueio do Cliente. Os clientes controlam essas atribuições de função em suas organizações.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>Como faço para entrar no Cofre do Cliente?

Um administrador global pode habilitar e configurar o Customer Lockbox no Microsoft 365 ou Microsoft 365 de administração.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Se eu aprovar uma solicitação de Caixa de Bloqueio do Cliente, o que o engenheiro pode fazer e como saberei o que o engenheiro da Microsoft fez?

Depois de aprovar uma solicitação de Cofre do Cliente, o engenheiro da Microsoft concedeu esses privilégios necessários para acessar o conteúdo do cliente usando cmdlets pré-aprovados. As ações realizadas pelos engenheiros da Microsoft em resposta às solicitações do Customer Lockbox são registradas e acessíveis no log de auditoria no Centro de Conformidade & Segurança.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Como saber se a Microsoft segue o processo de aprovação?

Você pode fazer referência cruzada às notificações de aprovação de email enviadas aos administradores e aprovadores em sua organização com o histórico de solicitações de Caixa de Bloqueio do Cliente no centro de administração Microsoft 365 cliente.

O Customer Lockbox está incluído no relatório de auditoria [mais recente do SOC 1 SSAE 16.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports) Para obter mais detalhes, você pode encontrar os relatórios mais recentes no [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>A Microsoft pode modificar a lista de aprovadores do meu locatário? Caso não seja, como isso é impedido?

Somente um administrador global em sua organização pode especificar quem pode aprovar solicitações de Caixa de Bloqueio do Cliente. Isso significa que apenas os membros do grupo administrador global no Azure Active Directory podem especificar quem pode aprovar a solicitação. A associação ao grupo de administradores global no Azure Active Directory é gerenciada somente pela sua organização.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>E se eu precisar de mais informações sobre uma solicitação de acesso ao conteúdo para aprove-la?

Cada solicitação do Customer Lockbox contém um Microsoft 365 de solicitação de serviço. Você pode entrar em contato com o Suporte da Microsoft e fazer referência a esse número de serviço para obter mais informações sobre a solicitação.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>Quando uma solicitação de Cofre de Cliente é aprovada, por quanto tempo as permissões são válidas?

Atualmente, o período máximo para as permissões de acesso concedidas ao engenheiro da Microsoft é de 4 horas. O engenheiro da Microsoft também pode solicitar um período mais curto.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>Como posso obter um histórico de todas as solicitações do Customer Lockbox?

Todas as solicitações do Customer Lockbox são exibidas no Microsoft 365 de administração.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>Como correlacionar as solicitações de acesso ao conteúdo com os logs de auditoria relacionados?

O Feed de Atividades do Centro de Conformidade contém atividades de log do Customer Lockbox. Os clientes podem fazer referência cruzada às atividades de log de Caixa de Bloqueio do Cliente a partir do feed de atividade em relação à solicitação de email que recebem.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>O que acontece quando um cliente não responde a uma solicitação de Caixa de Bloqueio do Cliente?

As solicitações de Sistema de Proteção de Dados do Cliente têm uma duração padrão de 12 horas. Se você não responder a uma solicitação dentro de 12 horas, a solicitação expirará.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>O que a Microsoft faz quando um cliente rejeita uma solicitação de Caixa de Bloqueio do Cliente?

Se um cliente rejeitar uma solicitação do Customer Lockbox, não ocorrerá acesso ao conteúdo do cliente. Se um usuário em sua organização continuar a experimentar um problema de serviço exigindo que a Microsoft acesse o conteúdo do cliente para resolver o problema, o problema de serviço poderá persistir e a Microsoft informará o usuário sobre isso.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>O Customer Lockbox protege contra solicitações de dados de agências de aplicação da lei ou de terceiros?

Não. A Microsoft leva a sério as solicitações de terceiros para dados do cliente. Como provedor de serviços de nuvem, a Microsoft sempre defende a privacidade dos dados do cliente. Caso obtenhamos uma intimação, a Microsoft sempre tenta redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [Protegendo os dados do cliente contra o snooping do governo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos periodicamente [informações detalhadas sobre](https://www.microsoft.com/corporate-responsibility/lerr) as solicitações de aplicação da lei que a Microsoft recebe.

Consulte o [Centro de Confiança da Microsoft em](https://www.microsoft.com/trustcenter/default.aspx) relação a solicitações de dados de terceiros e a seção "Divulgação de Dados do Cliente" nos Termos de Serviços [Online](https://www.microsoft.com/Licensing/product-licensing/products.aspx) para obter mais informações.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Como a Microsoft garante que um membro de sua equipe não tenha acesso permanente ao conteúdo do cliente em Office 365 aplicativos?

A Microsoft implementa medidas preventivas abrangentes por meio de sistemas de controle de acesso e medidas de detetive para identificar e resolver tentativas de contornar esses sistemas de controle de acesso. Microsoft 365 opera com os princípios de menor privilégio e acesso just-in-time. Portanto, nenhuma equipe da Microsoft tem permissão para acessar o conteúdo do cliente de forma contínua. Se a permissão for concedida, será por uma duração limitada. 

Microsoft 365 usa um sistema de controle de acesso chamado *Lockbox* para processar solicitações de permissões que concedam a capacidade de executar funções operacionais e administrativas dentro do serviço. Um operador deve solicitar acesso ao conteúdo do cliente usando o Lockbox, o que exige que uma segunda pessoa tome medidas sobre a solicitação (por exemplo, aprove-a) antes que o acesso seja concedido. Essa segunda pessoa não pode ser o solicitante e deve ser designada para aprovar o acesso ao conteúdo do cliente. Somente se a solicitação for aprovada o operador adquirirá acesso temporário ao conteúdo do cliente. Após o período de elevação expirar, o Lockbox revoga o acesso.

Consulte os Termos de [Serviços Online para](https://www.microsoft.com/licensing/product-licensing/products) obter mais detalhes sobre as práticas gerais de segurança da Microsoft.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>Em que circunstâncias os engenheiros da Microsoft precisam de acesso ao meu conteúdo?

O cenário mais comum em que os engenheiros da Microsoft precisam acessar o conteúdo do cliente é quando o cliente faz uma solicitação de suporte que exige acesso para solução de problemas. Um princípio básico da Microsoft 365 é que o serviço opera sem o acesso da Microsoft ao conteúdo do cliente. Quase todas as operações de serviço executadas pela Microsoft são totalmente automatizadas e o envolvimento humano é altamente controlado e abstraído do conteúdo do cliente. O objetivo Microsoft 365 acesso ao conteúdo do cliente para dar suporte ao serviço não é necessário até que o cliente aprove uma solicitação específica para o acesso da Microsoft.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Eu já achei que meus dados estavam seguros com a nuvem da Microsoft, então por que preciso de Caixa de Bloqueio do Cliente?

O Customer Lockbox fornece uma camada extra de controle, oferecendo aos clientes a capacidade de dar autorização de acesso explícito para operações de serviço. Ao demonstrar que existem procedimentos para autorização explícita de acesso a dados, o Customer Lockbox também ajuda os clientes a cumprir determinadas obrigações de conformidade, como HIPAA e FEDRAMP.