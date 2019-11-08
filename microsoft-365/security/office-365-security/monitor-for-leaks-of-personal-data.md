---
title: Monitorar o vazamento de dados pessoais
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Conheça três ferramentas disponíveis para monitorar o vazamento de dados pessoais.
ms.openlocfilehash: b4ca34f3446a0067c6497d844e5b79a78d0eb35e
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032236"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Monitorar o vazamento de dados pessoais

Existem várias ferramentas disponíveis destinadas a monitorar o uso e o transporte de dados pessoais. Este tópico descreve três ferramentas muito úteis.

![Ferramentas para monitorar o uso e o transporte de dados pessoais](../media/Monitor-for-leaks-of-personal-data-image1.png)

Na ilustração:

-   Comece a usar os relatórios de prevenção contra perda de dados do Office 365 para monitorar dados pessoais no SharePoint Online, no OneDrive for Business e nos emails em trânsito. Eles fornecem um monitoramento mais detalhado de dados pessoais. No entanto, esses relatórios não incluem todos os serviços do Office 365.

-   Em seguida, use as políticas de alerta e os logs de auditoria para monitorar as atividades em todos os serviços do Office 365. Configure um monitoramento permanente ou pesquise os logs de auditoria para investigar incidentes. Os logs de auditoria do Office 365 atuam em todos os serviços desta plataforma: Sway, PowerBI, Descoberta Eletrônica, Dynamics 365, Microsoft Flow, Microsoft Teams, Atividade do administrador, OneDrive for Business, SharePoint Online, emails em trânsito e caixas de correio em repouso. As caixas de correio em repouso incluem as conversas do Skype.

-   Por fim, use o Microsoft Cloud App Security para monitorar os arquivos com dados confidenciais em outros provedores de SaaS. Em breve, adicionaremos a capacidade de usar tipos de informações confidenciais e rótulos unificados do Office 365 com o Cloud App Security, na Proteção de Informações do Azure e no Office. Você pode configurar políticas que se apliquem a todos os aplicativos SaaS ou a aplicativos específicos, como o Box. O Cloud App Security não descobre arquivos no Exchange Online, nem os arquivos anexados em emails.

## <a name="office-365-data-loss-prevention-reports"></a>Relatórios de prevenção contra perda de dados do Office 365

Após criar as políticas DLP (prevenção contra perda de dados), convém verificar se elas estão funcionando conforme esperado e se estão ajudando a manter a conformidade. Com os relatórios DLP do Office 365, você pode exibir rapidamente o número de falsos positivos, substituições ou correspondências de regra e política DLP; verificar se elas estão mais ou menos populares ao longo do tempo; filtrar o relatório de várias maneiras e exibir mais detalhes selecionando um ponto em uma linha no gráfico.

Você pode usar os relatórios DLP para:

-   Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.

-   Descobrir processos empresariais que violam as políticas DLP da organização.

-   Compreender qualquer impacto nos negócios das políticas de DLP.

-   Exiba as justificativas enviadas pelos usuários quando eles resolverem uma dica de política substituindo a política ou relatando um falso positivo.

-   Verificar a conformidade com uma determinada política DLP mostrando as correspondências dessa política.

-   Exibir uma lista de arquivos com dados confidenciais que correspondem às políticas DLP no painel de detalhes.

Além disso, você pode usar os relatórios de DLP para ajustar suas políticas DLP conforme as executa no modo de teste.

Os relatórios DLP estão no centro de segurança e o no centro de conformidade. Navegue até Relatórios \> Exibir relatórios. Em prevenção de perda de dados (DLP), vá para correspondências de políticas e regras DLP ou substituições e falsos positivos DLP.

Para saber mais, confira o artigo [Exibir o relatório de prevenção contra perda de dados](https://support.office.com/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).

![Relatório mostrando correspondências de política DLP](../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a>Log de auditoria e políticas de alerta do Office 365

O log de auditoria inclui eventos das plataformas Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway e de outros serviços do Office 365.

O centro de conformidade e o centro de segurança oferecem duas maneiras de monitorar e gerar relatórios no log de auditoria do Office 365:

-   Configurar políticas de alerta, exibir alertas e monitorar tendências – Use as ferramentas painel de alerta e política de alerta no centro de conformidade ou no centro segurança.

-   Pesquisar diretamente no log de auditoria – você pode pesquisar todos os eventos em um intervalo de datas especificado ou filtrar os resultados com base em determinados critérios; por exemplo, o usuário que executou a ação, a ação ou o objeto de destino.

As equipes de conformidade e segurança de informações podem usar essas ferramentas de forma proativa para revisar as atividades executadas por usuários finais e administradores em todos os serviços do Office 365. É possível configurar alertas automáticos a fim de enviar notificações por email, quando ocorrem determinadas atividades em conjuntos de sites específicos; por exemplo, quando o conteúdo é compartilhado de sites conhecidos por incluir informações relacionadas ao GDPR. Dessa forma, as equipes podem acompanhar os usuários para garantir que as políticas de segurança corporativa sejam cumpridas ou para fornecer treinamento adicional.

As equipes de segurança de informações podem também pesquisar o log de auditoria para investigar suspeitas de violação de dados, bem como determinar a causa raiz e a abrangência da violação. Esta funcionalidade interna facilita o cumprimento dos artigos 33 e 34 do GDPR, que exige o envio de notificações sobre violação de dados à autoridade supervisora do GDPR e aos detentores dos dados, em um período específico. As entradas do log de auditoria são mantidas apenas por 90 dias no serviço. Recomendamos e a maioria das organizações exige que esses logs sejam mantidos por mais tempo.

Existem soluções disponíveis, com quais é possível inscrever-se nos logs de auditoria unificados por meio da API da Atividade de Gestão da Microsoft, que podem armazenar as entradas do log conforme necessário, além de fornecer alertas e painéis avançados. Por exemplo, o [OMS (Microsoft Operations Management Suite)](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-office-365).

Clique nos links abaixo para saber mais sobre as políticas de alerta e como pesquisar no log de auditoria.

-   [Políticas de alerta nos centros de conformidade e segurança do Microsoft Office 365](https://support.office.com/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

-   [Pesquisar as atividades do administrador e dos usuários no log de auditoria do Office 365](https://support.office.com/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introdução)

-   [Ativar e desativar a Pesquisa de log de auditoria do Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

-   [Pesquisas o log de auditoria](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)

-   [Search-UnifiedAuditLog](https://technet.microsoft.com/library/mt238501(v=exchg.160).aspx) (cmdlet) 

-   [Propriedades detalhadas no log de auditoria do Office 365](https://support.office.com/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

O Microsoft Cloud App Security ajuda a descobrir outros aplicativos SaaS em uso nas redes e os dados confidenciais enviados desses aplicativos ou para eles.

O Microsoft Cloud App Security é um serviço abrangente que fornece visibilidade ampliada, controles granulares e proteção aprimorada contra ameaças para os aplicativos de nuvem. Ele identifica mais de 15 mil aplicativos de nuvem na rede, em todos os dispositivos, além de fornecer análise, avaliação e pontuação de risco contínuas. Não são necessários agentes: os dados são coletados nos firewalls e proxies para que você tenha contexto e visibilidade completa do uso da nuvem e da TI sombra.

Para entender melhor o ambiente de nuvem, o recurso de investigação do Cloud App Security fornece uma ampla visibilidade de atividades, arquivos e contas para aplicativos gerenciados e sancionados. Você pode obter informações detalhadas em nível de arquivo e descobrir o deslocamento dos dados nos aplicativos de nuvem.

Por exemplo, a ilustração a seguir mostra duas políticas do Cloud App Security que podem ajudar com o GDPR.

![Exemplos de políticas do Cloud App Security](../media/Monitor-for-leaks-of-personal-data-image3.png)

A primeira política alerta quando os arquivos escolhidos, que incluem expressões personalizadas ou atributos de PII predefinidos, são compartilhados fora da organização nos aplicativos SaaS.

A segunda política bloqueia os downloads de arquivos em dispositivos não gerenciados. Você escolhe os atributos que deseja procurar nos arquivos, bem como os aplicativos SaaS aos quais deseja aplicar a política.

Em breve, os seguintes tipos de atributos estarão disponíveis para o Cloud App Security:

-   Tipos de informações confidenciais do Office 365

-   Rótulos unificados no Office 365 e na Proteção de Informações do Azure

### <a name="cloud-app-security-dashboard"></a>Painel do Cloud App Security

Se ainda não começou a usar o Cloud App Security, o primeiro passo é iniciá-lo. Acesse o Cloud App Security em <https://portal.cloudappsecurity.com>.

Observação: não deixe de habilitar a opção "Examinar automaticamente os arquivos com rótulos de classificação da Proteção de Informações do Azure" (nas Configurações Gerais) quando começar a usar o Cloud App Security ou antes de atribuir rótulos. Depois de configurar o Cloud App Security, ele não examinará os arquivos existentes novamente até eles serem modificados.

![Painel mostrando informações sobre alertas](../media/Monitor-for-leaks-of-personal-data-image4.png)

Mais informações:

-   [Implantar o Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

-   [Mais informações sobre o Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

-   [Bloqueando downloads de informações confidenciais usando o proxy do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>Políticas de atividade e arquivo de exemplo para detectar o compartilhamento de dados pessoais

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: número de cartão de crédito

Alerta quando um arquivo que contém um número de cartão de crédito é compartilhado em um aplicativo de nuvem aprovado.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controle</strong></th>
<th align="left"><strong>Configurações</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de política</td>
<td align="left">Política de arquivo</td>
</tr>
<tr class="even">
<td align="left">Modelo de política</td>
<td align="left">Sem modelo</td>
</tr>
<tr class="odd">
<td align="left">Severidade da política</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoria</td>
<td align="left">DLP</td>
</tr>
<tr class="odd">
<td align="left">Configurações de Filtro</td>
<td align="left"><p>Nível de acesso = Público (Internet), público, externo</p>
<p>Aplicativo = &lt;selecionar aplicativos&gt; (use essa configuração caso pretenda limitar o monitoramento a aplicativos SaaS específicos)</p></td>
</tr>
<tr class="even">
<td align="left">Aplicar a</td>
<td align="left">Todos os arquivos, todos os proprietários</td>
</tr>
<tr class="odd">
<td align="left">Inspeção de conteúdo</td>
<td align="left"><p>Inclui os arquivos que correspondam a uma expressão presente: "Todos os países: finanças: número do cartão de crédito"</p>
<p>Não exige contexto relevante: não selecionado (isso corresponde a palavras-chave e expressões regulares)</p>
<p>Inclui arquivos com pelo menos uma correspondência</p>
<p>Remover a máscara dos quatro últimos caracteres da violação: selecionado</p></td>
</tr>
<tr class="even">
<td align="left">Alertas</td>
<td align="left"><p>Criar um alerta para cada arquivo correspondente: selecionado</p>
<p>Limite diário de alerta: 1.000</p>
<p>Selecionar um alerta como email: selecionado</p>
<p>Para: infosec@contoso.com</p></td>
</tr>
<tr class="odd">
<td align="left">Gestão</td>
<td align="left"><p>Microsoft OneDrive for Business</p>
<p>Tornar particular: selecionar "Remover usuários externos"</p>
<p>Todas as outras configurações: não selecionadas</p>
<p>Microsoft SharePoint Online</p>
<p>Tornar particular: selecionar "Remover usuários externos"</p>
<p>Todas as outras configurações: não selecionadas</p></td>
</tr>
</tbody>
</table>

Políticas semelhantes:

-   Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: endereço de email

-   Detectar compartilhamento de arquivos que contêm informações de identificação pessoal: número do passaporte

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Detectar clientes ou dados de RH no Box ou no OneDrive for Business

Alerta quando um arquivo rotulado como "Dados do cliente" ou "Dados de RH" é carregado no Box ou no OneDrive for Business.

Observações:

-   o monitoramento do Box exige configurar um conector com o SDK do conector de API.

-   Essa política exige funcionalidades que estão atualmente em visualização privada.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controle</strong></th>
<th align="left"><strong>Configurações</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de política</td>
<td align="left">Política de atividade</td>
</tr>
<tr class="even">
<td align="left">Modelo de política</td>
<td align="left">Sem modelo</td>
</tr>
<tr class="odd">
<td align="left">Severidade da política</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoria</td>
<td align="left">Controle de Compartilhamento</td>
</tr>
<tr class="odd">
<td align="left">Atuar em</td>
<td align="left">Atividade única</td>
</tr>
<tr class="even">
<td align="left">Configurações de Filtro</td>
<td align="left"><p>Tipo de atividade = carregar arquivo</p>
<p>Aplicativo = Microsoft OneDrive for Business e Box</p>
<p>Rótulo de classificação (atualmente em visualização privada): Proteção de Informações do Azure = Dados do cliente, Recursos humanos: dados de salário; Recursos humanos: dados do funcionário</p></td>
</tr>
<tr class="odd">
<td align="left">Alertas</td>
<td align="left"><p>Criar um alerta: selecionado</p>
<p>Limite diário de alerta: 1.000</p>
<p>Selecionar um alerta como email: selecionado</p>
<p>Para: infosec@contoso.com</p></td>
</tr>
<tr class="even">
<td align="left">Gestão</td>
<td align="left"><p>Todos os aplicativos</p>
<p>Colocar o usuário em quarentena: selecionar</p>
<p>Todas as outras configurações: não selecionadas</p>
<p>Office 365</p>
<p>Colocar o usuário em quarentena: selecionar</p>
<p>Todas as outras configurações: não selecionadas</p></td>
</tr>
</tbody>
</table>

Políticas semelhantes:

-   Detectar grandes downloads de dados do cliente ou de RH – alerta quando for detectada uma grande quantidade de arquivos que contêm dados de clientes ou de RH sendo baixada por um único usuário, dentro de um curto período.

-   Detectar o compartilhamento de dados de clientes e de RH – alerta quando os arquivos com dados de clientes ou de RH são compartilhados.
