---
title: Aplicar proteção a dados pessoais no Office 365
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Saiba como usar políticas DLP para proteger dados pessoais no Office 365.
ms.openlocfilehash: 12d6de9b8012062e26daec922d5c55fa0f52381a
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38708019"
---
# <a name="apply-protection-to-personal-data-in-office-365"></a>Aplicar proteção a dados pessoais no Office 365

A proteção de informações pessoais no Office 365 inclui o uso de recursos de prevenção contra perda de dados. Com as políticas de prevenção de perda de dados (DLP) no centro de conformidade, você pode identificar, monitorar e proteger automaticamente informações confidenciais no Office 365.

Este tópico descreve como usar a DLP para proteger dados pessoais. Este tópico também lista outros recursos de proteção que podem ser usados para garantir a conformidade com o GDPR, incluindo como definir as permissões das bibliotecas do SharePoint e usar as políticas de acesso de dispositivos.

## <a name="apply-protection-using-data-loss-prevention-in-office-365"></a>Aplicar proteção usando prevenção contra perda de dados no Office 365

Com a DLP, você pode:

-   Identificar informações confidenciais em muitos locais.

-   Impedir o compartilhamento acidental de informações confidenciais.

-   Ajudar os usuários a aprender a manter a conformidade sem interromper o fluxo de trabalho.

-   Ver relatórios de DLP que mostram conteúdo que corresponde às políticas de DLP da sua organização.

Para mais informações, confira [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).

![Opções para criar uma política de Prevenção Contra Perda de Dados](Media/Apply-protection-to-personal-data-in-Office-365-image1.png)

Esta ilustração mostra as opções para criar uma política DLP:

-   Escolha a proteção a aplicar. A proteção pode incluir:

    -   Dicas de política para usuários

    -   Relatório de email para administradores

    -   Impedir o compartilhamento externamente, internamente ou ambos

-   Escolha os critérios para aplicar a proteção. Aplique a proteção a documentos com esse tipo de conteúdo: é possível configurar a política para usar tipos de informações confidenciais e/ou rótulos.

### <a name="using-dlp-for-gdpr-compliance"></a>Usar DLP para conformidade com o GDPR

Um dos principais usos da DPL do Office 365 é identificar dados pessoais relacionados a assuntos de dados da UE no ambiente do Office 365. A DPL do Office 365 pode notificar as equipes de conformidade sobre onde as informações pessoais estão armazenadas no SharePoint Online e no OneDrive for Business, ou quando os usuários enviam email contendo informações pessoais. A DLP pode ainda fornecer dicas de políticas aos seus funcionários ao trabalhar com informações pessoais relacionadas a residentes da UE.

Instruir e aumentar a conscientização em relação a onde os dados de residentes da UE estão armazenados no seu ambiente e como os seus funcionários têm permissão para gerenciá-los representam um nível de proteção de informações usando a DLP do Office 365. Muitas vezes, os funcionários que já têm acesso a esse tipo de informação precisam desse acesso para executar as suas tarefas do dia a dia. A aplicação das políticas de DLP para ajudar a manter a conformidade com o GDPR pode não exigir a restrição do acesso.

No entanto, a conformidade com o GDPR geralmente envolve uma avaliação baseada em risco da organização da perspectiva de segurança das informações e legal, identificação do tipo e onde as informações pessoais foram armazenadas, bem como se há uma justificativa legal para armazenar e processar essas informações. Com base nessa avaliação, a implementação de políticas para proteger a organização e estar em conformidade com o GDPR pode exigir a remoção do acesso dos funcionários a documentos que contenham informações de assuntos de dados da UE. Nos casos em que for preciso maior proteção, é possível configurar uma proteção adicional de DLP.

A tabela a seguir lista três configurações de aumento de proteção usando DLP. A primeira configuração, reconhecimento, pode ser usada como ponto de partida e nível mínimo de proteção do GDPR.

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a>Exemplo de níveis de proteção que podem ser configurados com políticas DLP e usados para conformidade com o GDPR

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nível de Proteção</strong></th>
<th align="left"><strong>Configuração de DLP para documentos com informações pessoais relacionadas a assuntos de dados da UE</strong></th>
<th align="left"><strong>Benefícios e riscos</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Reconhecimento</td>
<td align="left"><p>Envie notificações por email para as equipes de conformidade quando esses dados forem encontrados em documentos no SharePoint Online e OneDrive for Business.</p>
<p>Personalize e exiba Dicas de Política para funcionários no SharePoint e no OneDrive for Business ao acessar documentos contendo esses dados.</p>
<p>Detectar e relatar quando esses dados estiverem sendo compartilhados.</p></td>
<td align="left"><p>Aumente a conscientização das equipes de conformidade, bem como dos funcionários sobre onde esses dados são armazenados.</p>
<p>Instrua os funcionários sobre a política corporativa para lidar com documentos que contêm esses dados.</p>
<p>Não impede que os funcionários compartilhem esses dados internamente ou externamente.</p>
<p>Revise os relatórios de DLP de dados compartilhados e decida se precisa aumentar a proteção.</p></td>
</tr>
<tr class="even">
<td align="left">Impedir o compartilhamento externo</td>
<td align="left"><p>Restrinja o acesso a documentos que contenham esses dados no SharePoint Online e no OneDrive for Business quando esse conteúdo for compartilhado com usuários externos.</p>
<p>Impedir o envio de emails com documentos contendo esses dados para destinatários externos.</p>
<p>Detectar e relatar quando esses dados estiverem sendo compartilhados.</p></td>
<td align="left"><p>Impede o compartilhamento externo desses dados enquanto permite que os funcionários trabalhem com esses dados internamente.</p>
<p>Revise os relatórios de DLP de dados compartilhados internamente e decida se precisa aumentar essa proteção.</p></td>
</tr>
<tr class="odd">
<td align="left">Impedir o compartilhamento interno e externo</td>
<td align="left"><p>Restrinja o acesso a documentos que contenham esses dados no SharePoint Online e no OneDrive for Business quando esse conteúdo for compartilhado internamente ou externamente.</p>
<p>Impedir o envio de email contendo esses dados para destinatários internos e externos.</p></td>
<td align="left"><p>Impede o compartilhamento interno e externo desses dados.</p>
<p>Os funcionários podem não conseguir concluir tarefas que exijam trabalhar com esses dados.</p>
<p>Você pode revisar os relatórios de DLP para dados compartilhados internamente e externamente e decidir se é necessário um treinamento para usuário final.</p></td>
</tr>
</tbody>
</table>

Observação: conforme os níveis de proteção aumentam, a capacidade dos usuários de acessar informações diminuirá em alguns casos e pode afetará a produtividade ou capacidade para concluir as tarefas diárias. O aumento dos níveis de proteção com a implementação de políticas que afetam os funcionários geralmente é acompanhado por um treinamento de usuários finais, instruindo os usuários sobre novas políticas de segurança e procedimentos para continuar a ser mais produtivo em um ambiente mais seguro.

### <a name="example-dlp-policy-for-gdpr--awareness"></a>Exemplo de política DLP para GDPR — Reconhecimento 

Nome: o reconhecimento de dados pessoais sujeitos ao GDPR.

Descrição: exibir dicas de política para os funcionários, notificar equipes de conformidade quando esses dados forem encontrados no SharePoint Online e OneDrive for Business, detectar e relatar quando esses dados estiverem sendo compartilhados fora da sua organização.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controle</strong></th>
<th align="left"><strong>Configurações</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Escolha as informações para proteger</td>
<td align="left">Selecione um modelo de política personalizada.</td>
</tr>
<tr class="even">
<td align="left">Locais</td>
<td align="left">Todos os locais no Office 365</td>
</tr>
<tr class="odd">
<td align="left">Localizar conteúdo que contém</td>
<td align="left">Clique em "Editar" e adicione todos os tipos de informações confidenciais coletadas para seu ambiente.</td>
</tr>
<tr class="even">
<td align="left">Detectar quando este conteúdo é compartilhado</td>
<td align="left">Marque esta caixa e selecione "com pessoas fora da minha organização".</td>
</tr>
<tr class="odd">
<td align="left">Notificar os usuários quando o conteúdo corresponder às configurações de política</td>
<td align="left"><p>Marque esta caixa ("Mostrar dicas de política a usuários e enviar uma notificação de email para eles.")</p>
<p>Clique em "Personalizar a dica e o email" e atualize eles para o seu ambiente. Veja as notificações padrão neste artigo: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Enviar notificações por email e mostrar dicas de política para políticas DLP</a>.</p></td>
</tr>
<tr class="even">
<td align="left">Detectar quando uma quantidade específica de informações confidenciais estiver sendo compartilhada de uma só vez</td>
<td align="left"><p>"Detectar quando o conteúdo que está sendo compartilhado contém: pelo menos ____ instâncias do mesmo tipo de informação confidencial" — Configure esse valor como 1.</p>
<p>"Enviar relatórios de incidentes por email" — marque esta caixa. Clique em "Escolha o que incluir no relatório e quem receberá". Certifique-se de adicionar a sua equipe de conformidade.</p>
<p>"Restringir quem pode acessar o conteúdo e substituir a política" — desmarque esta caixa de seleção para receber notificações sobre informações confidenciais sem impedir os usuários de acessarem as informações.</p></td>
</tr>
</tbody>
</table>

Todos os locais incluem:

-   SharePoint Online

-   Contas do OneDrive for Business

-   Caixas de correio do Exchange

Como a Pesquisa de Conteúdo, no momento, não permite testar tipos de informações confidenciais com email, considere criar políticas separadas para o Exchange com um subconjunto de tipos de informações confidenciais em cada política e monitore a distribuição dessas políticas.

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-office-365"></a>Proteção adicional que pode ser aplicada para proteger dados pessoais no Office 365

Os tipos de informações confidenciais, os rótulos e as políticas de proteção contra perda de dados ajudam a identificar os documentos que contêm dados específicos e a aplicar proteção. No entanto, essas proteções dependem da configuração de permissões apropriadas de acesso a dados, usuários com contas que não sejam comprometidas e dispositivos saudáveis.

A ilustração a seguir detalha uma proteção adicional que pode ser aplicada para proteger o acesso a dados pessoais.

![Proteção adicional para dar segurança ao acesso a dados pessoais](Media/Apply-protection-to-personal-data-in-Office-365-image2.png)

Para maior acessibilidade, a tabela a seguir fornece as mesmas informações da ilustração.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Escopo de proteção</strong></th>
<th align="left"><strong>Funcionalidades</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Proteção no nível do email e documento (inclui emails em trânsito, mas, no momento, não inclui caixas de correio em repouso)</td>
<td align="left"><p>Tipos de informações confidenciais</p>
<p>Rótulos do Office.</p>
<p>Políticas de prevenção contra perda de dados</p>
<p>Criptografia de Mensagem do Office 365 para email</p></td>
</tr>
<tr class="even">
<td align="left">Proteção no nível da biblioteca e site (inclui sites do SharePoint Online e OneDrive for Business)</td>
<td align="left"><p>Permissões para bibliotecas e sites do SharePoint Online e do OneDrive for Business</p>
<p>Políticas de compartilhamento externo do SharePoint Online e OneDrive for Business (no nível do site)</p>
<p>Políticas de acesso de dispositivo no nível do site</p></td>
</tr>
<tr class="odd">
<td align="left">Proteção de acesso a serviços (inclui acesso a todos os serviços do Office 365)</td>
<td align="left"><p>Proteção à identidade e ao acesso a dispositivos no pacote Enterprise Mobility + Security (EMS)</p>
<p>Gerenciamento de acesso privilegiado</p>
<p>Recursos de segurança do Windows 10</p></td>
</tr>
</tbody>
</table>

O restante deste artigo fornecerá mais informações sobre cada uma dessas categorias de proteção.

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a>Funcionalidades que podem ser usadas com o GDPR

Você pode usar as seguintes funcionalidades em um ambiente configurado para conformidade com o GDPR. Esses recursos não são necessários para a conformidade com o GDPR, mas podem ser usados sem afetar sua capacidade de descobrir, proteger, monitorar e informar sobre dados relacionados à conformidade do GDPR.

Chave de Cliente — Permite que os clientes forneçam e mantenham o controle sobre as chaves de criptografia que são usadas para criptografar dados em repouso no Office 365. Recomendado somente para clientes que tenham a necessidade regulatória de gerenciar suas próprias chaves de criptografia.

Sistema de Proteção de Dados do Cliente — O sistema de proteção de dados do cliente permite controlar como um engenheiro de suporte da Microsoft acessa os seus dados, se necessário, para corrigir um problema técnico com base em cada caso. Controle se deseja dar ao engenheiro de suporte acesso aos seus dados ou não. Um tempo de expiração é fornecido com cada solicitação.

## <a name="site-and-library-level-protection"></a>Proteção no nível da biblioteca e site

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a>Permissões para bibliotecas e documentos do SharePoint e do OneDrive for Business

Use permissões do SharePoint para fornecer ou restringir o acesso de usuário ao site ou conteúdo. Adicione usuários individuais ou grupos do Azure Active Directory aos grupos padrão do SharePoint. Ou crie um grupo personalizado para um controle mais refinado.

![Níveis de permissão de controle total para somente exibição](Media/Apply-protection-to-personal-data-in-Office-365-image3.png)

A ilustração apresenta os níveis de permissão, desde Controle total a Somente exibição. A tabela a seguir inclui as mesmas informações.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controle total</strong></th>
<th align="left"><strong>Design</strong></th>
<th align="left"><strong>Editar</strong></th>
<th align="left"><strong>Colaboração</strong></th>
<th align="left"><strong>Leitura</strong></th>
<th align="left"><strong>Somente Exibição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left">Contribuir + aprovar e personalizar</td>
<td align="left">Contribuir + adicionar, editar e excluir listas (não apenas itens da lista)</td>
<td align="left">Exibir, adicionar, atualizar e excluir documentos e itens da lista.</td>
<td align="left">Exibir e baixar</td>
<td align="left">Exibir sem baixar</td>
</tr>
</tbody>
</table>

Mais informações:

-   [Compreender os níveis de permissão no SharePoint](https://support.office.com/pt-BR/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [Compreender os grupos do SharePoint](https://support.office.com/pt-BR/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a>Políticas de compartilhamento externo para bibliotecas do SharePoint e OneDrive for Business

Muitas organizações permitem o compartilhamento externo para dar suporte à colaboração. Descubra como suas configurações de locatário estão configuradas. Em seguida, revise as configurações de compartilhamento externo para sites que contêm dados pessoais.

Um usuário externo é alguém de fora da sua organização que é convidado a acessar seus documentos e sites do SharePoint Online, mas não tem uma licença para sua assinatura do Microsoft Office 365 ou SharePoint Online.

As políticas de compartilhamento externo se aplicam ao SharePoint Online e OneDrive for Business

-   É preciso ser um administrador do SharePoint Online para configurar as políticas de compartilhamento.

-   É preciso ser um Proprietário de site ou ter permissões de controle total para compartilhar um site ou documento com usuários externos.

A tabela a seguir resume os controles que você pode configurar.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Categoria de controle</strong></th>
<th align="left"><strong>Opções</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo de compartilhamento</td>
<td align="left"><p>Não permitir o compartilhamento fora da sua organização (pode ser definido para conjuntos de sites individuais)</p>
<p>Permitir o compartilhamento somente com usuários externos autenticados (permitir novos ou limitar aos já existentes, pode ser definido para conjuntos de sites individuais)*</p>
<p>Permitir o compartilhamento com usuários externos com um link de acesso anônimo (pode ser definido para conjuntos de sites individuais)</p>
<p>Limitar o compartilhamento externo usando domínios (lista permitir e negar)</p>
<p>Escolha o tipo de link padrão (anônimo, compartilhável na empresa ou restrito)</p>
</td>
</tr>
<tr class="even">
<td align="left">O que os usuários externos podem fazer</td>
<td align="left"><p>Impedir que os usuários externos compartilhem arquivos, pastas, sites que eles não possuem</p>
<p>Exigir que os usuários externos aceitem convites de compartilhamento com a mesma conta para a qual o convite foi enviado</p></td>
</tr>
<tr class="odd">
<td align="left">Notificações</td>
<td align="left"><p>Disponível atualmente só no OneDrive for Business. Notificar os proprietários quando:</p>
- <p>Os usuários convidarem usuários externos adicionais para os arquivos compartilhados</p>
- <p>Os usuários externos aceitarem convites para acessar os arquivos</p>
- <p>Um link de acesso anônimo for criado ou alterado</p></td>
</tr>
</tbody>
</table>

Mais informações:

-   [Gerenciar compartilhamento externo para o ambiente do SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [Compartilhar sites ou documentos com pessoas de fora da organização](https://support.office.com/pt-BR/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a>Políticas de acesso de dispositivo no nível do site

O SharePoint Online e o OneDrive for Business permitem configurar as políticas de acesso a dispositivos no nível do site. Isso permite configurar maior proteção para sites com dados confidenciais.

Se você configurar políticas de acesso de dispositivo no nível do site, certifique-se de coordená-las com as políticas a nível de locatário e também com as políticas de acesso configuradas no Azure Active Directory, Intune e Gerenciamento de Aplicativos do Intune.

As políticas de acesso de dispositivos do SharePoint e do OneDrive for Business exigem políticas com suporte no Azure Active Directory e no Microsoft Intune, dependendo do cenário que está sendo implementado. A tabela a seguir resume os objetivos que podem ser alcançados com as políticas de acesso e indica quais produtos exigem políticas com suporte.

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Só permitir o acesso de locais de endereço IP específicos</th>
<th align="left">Impedir que os usuários baixem arquivos para dispositivos que não ingressaram no domínio</th>
<th align="left">Bloquear o acesso em dispositivos que não ingressaram no domínio</th>
<th align="left">Impedir que os usuários baixem arquivos para dispositivos que não estão em conformidade</th>
<th align="left">Bloquear o acesso a dispositivos que não estão em conformidade</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Centro de administração do SharePoint</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
<tr class="even">
<td align="left">Azure Active Directory</td>
<td align="left"></td>
<td align="left">Sim</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
<tr class="odd">
<td align="left">Microsoft Intune</td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
</tbody>
</table>

Mais informações: [Centro de administração do SharePoint Online: controlar o acesso de dispositivos não gerenciados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).

## <a name="service-access-protection-for-identities-and-devices"></a>Proteção de acesso a serviços de identidades e dispositivos

A Microsoft recomenda configurar a proteção de identidades e dispositivos que acessam o serviço. Seus esforços para proteger o acesso aos serviços do Office 365 também podem ser usados para proteger outros serviços de SaaS, serviços de PaaS e até aplicativos em outros provedores de nuvem.

A proteção de acesso de identidades e dispositivos oferece um parâmetro de proteção para garantir que as identidades não sejam comprometidas, que os dispositivos estejam em segurança e que os dados da organização que são acessados nos dispositivos estejam isolados e protegidos.

Como ponto de partida para as orientações de configuração e recomendações, confira [Diretrizes de segurança da Microsoft para campanhas políticas, organizações sem fins lucrativos e outras organizações Agile](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).

Para ambientes com identidade híbrida com o AD FS, confira [Recomendações de configurações e políticas de segurança](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).

A ilustração a seguir descreve como os serviços em nuvem (SaaS, PaaS), tipos de conta (contas de domínio de locatário vs. contas B2B) e funcionalidades de recursos de acesso estão relacionadas. É importante observar quais funcionalidades podem ser usadas com contas B2B.

![Serviços em nuvem, tipos de conta e funcionalidades de acesso](Media/Apply-protection-to-personal-data-in-Office-365-image4.png)

Para fins de acessibilidade, o restante desta seção descreverá esta ilustração.

### <a name="cloud-services"></a>Serviços em nuvem

O Azure Active Directory fornece acesso de identidade para qualquer serviço em nuvem, incluindo de outros provedores diferentes da Microsoft, como o Amazon Web Services. A ilustração mostra o Office 365, "Outro aplicativo de SaaS" e "aplicativo de PaaS". Setas apontam do Azure Active Directory para cada um desses serviços, mostrando que o Active Directory do Azure pode ser usado para autenticação em todos esses tipos de aplicativos.

### <a name="types-of-accounts"></a>Tipos de contas

Contas de domínio do locatário são contas que você adiciona ao seu locatário e gerencia diretamente. Contas B2B são para usuários de fora da sua organização que você convida para colaborar. Estas podem ser outras contas do Office 365, contas de outra organização ou contas de cliente (como Gmail). A ilustração mostra ambos os tipos de conta no Azure Active Directory.

### <a name="capabilities"></a>Funcionalidades

As funcionalidades na tabela a seguir protege identidades e dispositivos. A tabela indica quais funcionalidades também podem ser usadas com contas B2B, de modo similar à ilustração.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Funcionalidade</strong></th>
<th align="left"><strong>Funciona com contas de domínio do locatário</strong></th>
<th align="left"><strong>Funciona com contas B2B do Azure (sem licenciamento adicional)</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Autenticação multifatorial e acesso condicional</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
<tr class="even">
<td align="left">Azure AD Identity Protection</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
<tr class="odd">
<td align="left">Azure AD Privileged Identity Management</td>
<td align="left">Sim</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Gerenciamento de Aplicativos Móveis (MAM)</td>
<td align="left">Sim</td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left">Gerenciamento e registro de dispositivos</td>
<td align="left">Sim</td>
<td align="left">Apenas uma organização pode gerenciar um dispositivo</td>
</tr>
<tr class="even">
<td align="left">As funcionalidades de segurança do Windows 10 (acesso condicional com base na conformidade do dispositivo requer o gerenciamento de dispositivos)</td>
<td align="left">Sim</td>
<td align="left">Sim</td>
</tr>
</tbody>
</table>

Adicione licenças a contas B2B para oferecer a esses usuários funcionalidades adicionais, se necessário, para proteger o acesso a dados pessoais no seu ambiente.
