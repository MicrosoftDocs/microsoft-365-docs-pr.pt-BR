---
title: Visão geral da prevenção contra perda de dados
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Com uma política de prevenção contra perda de dados (DLP) no Centro de Conformidade &amp; Segurança, você pode identificar, monitorar e proteger automaticamente as informações confidenciais no Office 365.
ms.openlocfilehash: e2fab1df550382f44e09629e5b82a079d6f6555f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806614"
---
# <a name="overview-of-data-loss-prevention"></a>Visão geral da prevenção contra perda de dados
<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
> [!NOTE]
> Os recursos de prevenção contra perda de dados foram recentemente adicionados às mensagens de chat e de canal do Microsoft Teams para usuários licenciados para a Conformidade Avançada do Office 365, disponível como uma opção independente e está incluso na Conformidade do Office 365 E5 e no Microsoft 365 E5. Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

Para estar em conformidade com padrões de negócios e regulamentações do setor, as organizações precisam proteger as informações confidenciais e evitar sua divulgação acidental. Informação confidencial inclui dados financeiros ou informações de identificação pessoal (PII), como números de cartão de crédito, números de CPF ou registros de saúde. Com uma política DLP no Centro de Conformidade &amp; Segurança do Office 365, você pode identificar, monitorar e proteger automaticamente as informações confidenciais no Office 365.
  
Com uma política de DLP, você pode:
  
- **Identificar informações confidenciais em vários locais, como no Exchange Online, SharePoint Online, OneDrive for Business e Microsoft Teams.**
    
    Por exemplo, você pode identificar qualquer documento com um número de cartão de crédito armazenado em qualquer site do OneDrive for Business ou você pode pesquisar apenas os sites do OneDrive de pessoas específicas.
    
- **Impedir o compartilhamento acidental de informações confidenciais**. 
    
    Por exemplo, você pode identificar qualquer documento ou email com um registro de saúde compartilhado com pessoas de fora da sua organização e, em seguida, bloquear automaticamente o acesso a esse documento ou bloquear o envio do email.
    
- **Monitorar e proteger informações confidenciais nas versões da área de trabalho do Excel, PowerPoint e Word.**
    
    Assim como no Exchange Online, no SharePoint Online e no OneDrive for Business, esses programas da área de trabalho do Office incluem os mesmos recursos para identificar informações confidenciais e aplicar políticas de DLP. A DLP oferece monitoramento contínuo, quando as pessoas compartilham conteúdo nestes programas do Office.
    
- **Ajude os usuários a manter a conformidade sem interromper o fluxo de trabalho.**
    
    Você pode instruir os usuários sobre políticas de DLP e ajudá-los a permanecer em conformidade sem bloquear seu trabalho. Por exemplo, se um usuário tentar compartilhar um documento que contém informações confidenciais, uma política de DLP pode enviar uma notificação por email e mostrar uma dica de política no contexto da biblioteca de documentos que permite substituir a política se ele tivere uma justificativa de negócios. As mesmas dicas de política também aparecem no Outlook na Web, no Outlook, no Excel, no PowerPoint e no Word.
    
- **Visualizar relatórios de DLP que mostrem conteúdo que corresponda às políticas de DLP da sua organização.**
    
    Para avaliar como a sua organização está em conformidade com uma política DLP, você pode ver o número de correspondências de cada política e regra ao longo do tempo. Se uma política DLP permitir aos usuários substituir uma dica de política e comunicar um falso positivo, você também poderá ver o que os usuários informaram.
    
Você cria e gerencia políticas DLP na página de Prevenção contra Perda de Dados no Centro de Conformidade &amp; Segurança do Office 365.
  
![Página de Prevenção contra Perda de Dados no Centro de Conformidade &amp; Segurança do Office 365](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>O que uma política de DLP contém

Uma política de DLP contém algumas informações básicas:
  
- Onde proteger o conteúdo: **Locais** como os sites do Exchange Online, SharePoint Online e OneDrive for Business, bem como mensagens no chat e de canais do Microsoft Teams. 
    
- Quando e como proteger o conteúdo aplicando **regras** compostas por: 
    
  - **Condições** com as quais o conteúdo deve corresponder antes que a regra seja aplicada. Por exemplo, a regra deve ser configurada para procurar apenas conteúdo com números de previdência social compartilhados com pessoas de fora da sua organização. 
    
  - **Ações** que a regra deve executar automaticamente quando o conteúdo correspondente às condições for encontrado. Por exemplo, uma regra pode ser configurada para bloquear o acesso a um documento e enviar uma notificação por email ao usuário e ao responsável pela conformidade. 
    
Você pode usar uma regra para atender a um requisito específico de proteção e depois usar uma política DLP para agrupar requisitos de proteção comuns, como todas as regras necessárias para manter a conformidade com uma regulamentação específica.
  
Por exemplo, você pode ter uma política DLP que ajuda a detectar a presença de informações sujeitas à lei americana HIPAA (Health Insurance Portability Accountability Act). Essa política DLP pode ajudar a proteger dados HIPAA (objeto) em todos os sites do SharePoint Online e OneDrive for Business (local) ao encontrar qualquer documento com essas informações confidenciais que são compartilhadas com pessoas de fora da sua organização (condições) e, em seguida, bloquear o acesso ao documento e enviar uma notificação (ações). Esses requisitos são armazenados como regras individuais e agrupadas como uma política DLP para simplificar o gerenciamento e a geração de relatório.
  
![O diagrama mostra que a política de DLP contém locais e regras](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>Locais

Uma política DLP pode encontrar e proteger informações confidenciais no Office 365, não importa se essas informações estão armazenadas no Exchange Online, SharePoint Online, OneDrive for Business, ou Microsoft Teams. Você pode optar por proteger o conteúdo de emails do Exchange, mensagens do chat e de canal do Microsoft Teams e todas as bibliotecas do SharePoint ou do OneDrive, ou selecionar locais específicos para uma política.
  
![Opções para locais onde uma política DLP pode ser aplicada](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)

 Se você optar por incluir grupos de distribuição específicos no Exchange, a política DLP será delimitada somente aos membros desse grupo. Da mesma maneira, a exclusão de um grupo de distribuição excluirá todos os membros desse grupo de distribuição da avaliação de políticas. Você pode optar por criar uma política para os membros das listas de distribuição, grupos de distribuição dinâmicas e grupos de segurança. Uma política DLP pode conter, no máximo, 50 inclusões e exclusões.

Se optar por incluir ou excluir sites específicos do SharePoint ou contas do OneDrive, uma política de DLP pode conter até 100 inclusões e exclusões. Embora esses limites existam, você pode excede-los ao ignorar uma política no âmbito da organização ou uma política que se aplica a locais inteiros.
  
### <a name="rules"></a>Regras

As regras aplicam os requisitos de negócios para o conteúdo da sua organização. Uma política contém uma ou mais regras, e cada regra consiste em condições e ações. Para cada regra, quando as condições forem atendidas, as ações são executadas automaticamente. As regras são executadas sequencialmente, começando pela prioridade mais alta em cada política.
  
Uma regra também fornece opções para notificar os usuários (com dicas de política e notificações por email) e os administradores (com relatórios de incidentes por email) cujo conteúdo correspondeu à regra.
  
Veja a seguir os componentes de uma regra, cada um explicado abaixo.
  
![Seções do editor regras DLP](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condições

As condições são importantes porque elas determinam que tipos de informações confidenciais está procurando e quando uma ação deve ser executada. Por exemplo, você pode optar por ignorar o conteúdo com números de passaporte, a menos que o conteúdo contenha mais de 10 números e seja compartilhado com pessoas de fora da sua organização.
  
As condições se concentram no **conteúdo**, como quais tipos de informações confidenciais está procurando e também no **contexto**, como com quem o documento é compartilhado. Você pode usar condições para atribuir ações diferentes a diferentes níveis de risco. Por exemplo, o conteúdo confidencial compartilhado internamente pode diminuir o risco e exigir menos ações do que o conteúdo confidencial compartilhado com pessoas de fora da organização. 
  
![Lista que mostra as condições DLP disponíveis](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
As condições disponíveis agora podem determinar se:
  
- O conteúdo contém um tipo de informação confidencial.
    
- O conteúdo contém um rótulo. Para saber mais, confira a seção abaixo [Usar um rótulo como uma condição em uma política de DLP](#using-a-label-as-a-condition-in-a-dlp-policy).
    
- O conteúdo é compartilhado com pessoas de fora ou de dentro da sua organização.

> [!NOTE]
> Os usuários que têm contas não convidadas no Active Directory ou no locatário do Azure Active Directory de uma organização são considerados como pessoas dentro da organização.
    
#### <a name="types-of-sensitive-information"></a>Tipos de informações confidenciais

Uma política DLP ajuda a proteger informações confidenciais, que são definidas como um **tipo de informações confidenciais**. O Office 365 inclui 51 definições para vários tipos comuns de informações confidenciais em diferentes regiões que estão prontos para uso, como um número de cartão de crédito, números de contas bancárias, números de carteiras de identidade e números de passaporte. 
  
![Lista de tipos de informações confidenciais disponíveis](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Quando uma política DLP procura por um tipo de informação confidencial, como um número de cartão de crédito, ela não procura simplesmente por um número de 16 dígitos. Cada tipo de informação confidencial é definido e detectado usando uma combinação de:
  
- Palavras-chave
    
- Funções internas para validar as somas de verificação ou a composição
    
- Avaliação de expressões regulares para localizar correspondências padrão
    
- Análise de outros conteúdos
    
Isso ajuda a detecção de DLP a alcançar um alto grau de precisão, reduzindo o número de falsos positivos que pode interromper o trabalho das pessoas.
  
#### <a name="actions"></a>Ações

Quando o conteúdo corresponde a uma condição em uma regra, você pode aplicar ações para proteger automaticamente o conteúdo.
  
![Lista de ações DLP disponíveis](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Com as ações agora disponíveis, você pode:
  
- **Restringir o acesso ao conteúdo** Para o conteúdo do site, isso significa que as permissões para o documento são restritas a todos exceto o administrador principal do conjunto de sites, o proprietário do documento e a pessoa que modificou o documento pela última vez. Essas pessoas podem remover as informações confidenciais do documento ou executar outras ações corretivas. Quando o documento estiver em conformidade, as permissões originais serão restauradas automaticamente. Quando o acesso a um documento é bloqueado, o documento é exibido com um ícone de dica de política especial na biblioteca do site. 
    
    ![A dica de política mostrando acesso ao documento está bloqueada](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    Para conteúdo de email, essa ação bloqueia o envio da mensagem. Dependendo de como a regra DLP estiver configurada, o remetente verá uma notificação de falha na entrega (se a regra usar uma notificação) ou uma dica de política e/ou notificação por email.
    
    ![Aviso de que destinatários não autorizados devem ser removidos da mensagem](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notificações e substituições do usuário

Você pode usar notificações e substituições para instruir usuários sobre políticas de DLP e ajudá-los a permanecer em conformidade sem bloquear seu trabalho. Por exemplo, se um usuário tentar compartilhar um documento que contém informações confidenciais, uma política de DLP pode enviar uma notificação por email e mostrar uma dica de política no contexto da biblioteca de documentos que permite substituir a política se ele tivere uma justificativa de negócios.
  
![Seções de notificações e substituições do usuário do editor de regras DLP](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
O email pode notificar a pessoa que enviou, compartilhou ou modificou o conteúdo por último e, no caso de conteúdo de sites, o administrador principal do conjunto de sites e o proprietário do documento. Além disso, você pode adicionar ou remover quem quiser na notificação por email.
  
Além de enviar uma notificação por email, uma notificação do usuário exibe uma dica de política:
  
- No Outlook e no Outlook na Web.
    
- Para o documento no SharePoint ou no site do OneDrive for Business.
    
- No Excel, PowerPoint, e Word, quando o documento está armazenado em um site incluído em uma política DLP.
    
A notificação de email e a dica de política explicam a razão do conflito do conteúdo com uma política DLP. Se você escolher, a notificação por email e a dica de política podem permitir que usuários substituam uma regra ao relatar um falso positivo ou fornecer uma justificativa de negócios. Isso pode ajudar você a treinar os usuários sobre as políticas de DLP e aplicá-las sem impedir que as pessoas façam seu trabalho. Informações sobre substituições e falsos positivos também são registradas para relatório (veja abaixo sobre os relatórios de DLP) e incluídas nos relatórios de incidentes (próxima seção), para que o responsável pela conformidade possa analisar regularmente essas informações.
  
Esta é a aparência de uma dica de política em uma conta do OneDrive for Business.
  
![Dica de política para um documento em uma conta do OneDrive](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 Para saber mais sobre as notificações de usuário e as dicas de política em políticas DLP, confira [Usar notificações e dicas de política](use-notifications-and-policy-tips.md).

#### <a name="incident-reports"></a>Relatórios de incidentes

Quando uma regra é correspondida, você pode enviar um relatório de incidentes ao responsável pela conformidade (ou qualquer pessoa que você escolher) com detalhes sobre o evento. Esse relatório inclui informações sobre o item que foi correspondido, o conteúdo real que correspondeu à regra e o nome da pessoa que modificou o conteúdo por último. Para mensagens de email, o relatório também inclui a mensagem original como anexo que corresponde a uma política DLP.
  
![Página para configurar relatórios de incidente](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>Agrupamento e operadores lógicos

Muitas vezes, sua política DLP tem um requisito direto, como identificar todo o conteúdo que contém um número de CPF. No entanto, em outras situações, talvez seja necessário que sua política DLP identifique dados definidos de forma mais flexível.
  
Por exemplo, para identificar conteúdo sujeito à HIPAA (Lei de Seguro de Saúde) dos EUA, você precisa procurar:
  
- Conteúdo que apresente tipos específicos de informações confidenciais, como um Número de Seguro Social dos EUA ou Número da DEA (Agência de Combate às Drogas dos EUA).
    
    E
    
- Conteúdo que é mais difícil de identificar, como comunicações sobre cuidados de um paciente ou descrições de serviços médicos fornecidos. Identificar esse conteúdo requer a combinação de palavras-chave de listas de palavras-chave muito extensas, como a Classificação Internacional de Doenças (ICD-9-CM ou ICD-10-CM).
    
Você pode identificar facilmente esses dados definidos de forma mais flexível usando agrupamentos e operadores lógicos (E, OU). Ao criar uma política DLP, você pode:
  
- Agrupar tipos de informações confidenciais.
    
- Escolher o operador lógico entre os tipos de informações confidenciais dentro de um grupo e entre os próprios grupos.
    
### <a name="choosing-the-operator-within-a-group"></a>Escolher o operador dentro de um grupo

Dentro de um grupo, você pode escolher se uma ou todas as condições desse grupo devem ser atendidas para que o conteúdo corresponda à regra.
  
![Grupo que mostra os operadores dentro do grupo](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Adicionar um grupo

Você pode adicionar rapidamente um grupo, que pode ter suas próprias condições e operador dentro desse grupo.
  
![Botão Adicionar Grupo](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Escolher o operador entre grupos

Entre grupos, você pode escolher se as condições em apenas um grupo ou todos os grupos devem ser atendidas para que o conteúdo corresponda à regra.
  
Por exemplo, a política interna ** HIPAA (Lei de Seguro de Saúde) dos EUA** tem uma regra que usa um operador **E** entre os grupos para que identifique o conteúdo que apresente: 
  
- do grupo **Identificadores PII** (pelo menos um número de CPF **OU** número da Agência de Combate às Drogas) 
    
    **E**
    
- do grupo **Termos Médicos** (pelo menos uma palavra-chave do ICD-9-CM **OU** do ICD-10-CM) 
    
![Grupos que mostram o operador entre grupos](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>A prioridade em que as regras são processadas

Quando você cria regras em uma política, cada regra recebe uma prioridade na ordem em que ela é criada, ou seja, a regra criada primeiro tem a primeira prioridade, a regra criada em segundo lugar tem a segunda prioridade e assim por diante. 
  
![Regras na ordem de prioridade](media/dlp-rules-in-priority-order.png)
  
Após configurar mais de uma política DLP, você pode alterar a prioridade de uma ou mais políticas. Para fazer isso, selecione uma política, clique em **Editar política**e use a lista **Prioridade** para especificar a prioridade.

![Definir a prioridade em uma política](media/dlp-set-policy-priority.png)

Quando o conteúdo é avaliado em relação às regras, estas são processadas na ordem de prioridade. Se o conteúdo corresponde a várias regras, as regras são processadas na ordem de prioridade, e a ação mais restritiva será aplicada. Por exemplo, se o conteúdo corresponder a todas as regras a seguir, a Regra 3 será aplicada porque tem a prioridade mais alta, é a regra mais restritiva:
  
- Regra 1: apenas notifica os usuários
    
- Regra 2: notifica os usuários, restringe o acesso e permite o usuário substituir
    
- Regra 3: notifica os usuários, restringe o acesso e não permite o usuário substituir
    
- Regra 4: apenas notifica os usuários
    
- Regra 5: restringe o acesso
    
- Regra 6: notifica os usuários, restringe o acesso e não permite o usuário substituir
    
Nesse exemplo, observe que as correspondências para todas as regras são registradas nos logs de auditoria e exibidas nos relatórios de DLP, embora apenas a regra mais restritiva seja aplicada.
  
Referente às dicas de política, observe que:
  
- Apenas a dica de política da prioridade mais alta e restritiva será exibida. Por exemplo, uma dica de política de uma regra que bloqueia o acesso ao conteúdo será mostrada em detrimento de uma dica de política de uma regra que simplesmente envia uma notificação. Isso impede que as pessoas vejam uma cascata de dicas de política.
    
- Se as dicas de política na regra mais restritiva permitir que as pessoas substituam a regra, substituir essa regra também substitui quaisquer outras regras que o conteúdo correspondeu.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Ajustar as regras para que a correspondência seja mais fácil ou mais difícil

Após criar e ativar as políticas de DLP, algumas vezes ocorre esses problemas:
  
- Grande parte do conteúdo que **não é** confidencial corresponde com as regras, ou seja, há muitos falsos positivos. 
    
- Pequena parte do conteúdo que **tem** informações confidenciais corresponde com as regras. Em outras palavras, as ações de proteção não estão sendo aplicadas nas informações confidenciais. 
    
Para resolver esses problemas, você pode regular suas regras ajustando a contagem de instância e a precisão da correspondência para dificultar ou facilitar a correspondência do conteúdo às regras. Cada tipo de informação confidencial usado em uma regra tem uma contagem de instância e uma precisão de correspondência.
  
### <a name="instance-count"></a>Contagem de instâncias

A contagem de instâncias se refere à quantidade de ocorrências de um tipo específico de informação confidencial que deve estar presente para que o conteúdo corresponda à regra. Por exemplo, o conteúdo corresponde com a regra mostrada abaixo se entre 1 e 9 passaportes únicos dos EUA ou UE são identificados.
  
Observe que a contagem de instâncias inclui apenas correspondências **únicas** a palavras-chave e tipos de informações confidenciais. Por exemplo, se um email contém 10 ocorrências do mesmo número de cartão de crédito, as 10 ocorrências são contadas como uma única instância de um número de cartão de crédito. 
  
Para usar a contagem de instâncias para ajustar as regras, a orientação é simples:
  
- Para tornar a regra mais fácil para a correspondência, diminua a contagem **mín** e/ou aumente a contagem **máx**. Também é possível definir o **máx** para **qualquer** excluindo o valor numérico. 
    
- Para tornar a regra mais difícil para a correspondência, aumente a contagem **mín**. 
    
Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma contagem de instâncias inferior (por exemplo, 1-9). E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça substituição, em uma regra com uma contagem de instância superior (por exemplo, 10 – qualquer).
  
![Contagens de instância no editor de regra](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisão de correspondência

Conforme descrito acima, o tipo de informação confidencial é definido e detectado usando uma combinação de diferentes tipos de evidências. Em geral, um tipo de informação confidencial é definido por várias dessas combinações, chamadas padrões. Um padrão que requer menos evidências tem uma precisão de correspondência inferior (ou nível de confiança), enquanto um padrão que exige mais evidências tem uma maior precisão de correspondência (ou nível de confiança). Para saber mais sobre os padrões reais e níveis de confiança usados por todos os tipos de informações confidenciais, confira o artigo sobre [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
Por exemplo, o tipo de informação confidencial chamado Número de Cartão de Crédito é definido por dois padrões:
  
- Um padrão com confiança de 65% que exige:
    
  - Um número no formato de um número de cartão de crédito.
    
  - Um número que passa na soma de verificação.
    
- Um padrão com confiança de 85% que exige:
    
  - Um número no formato de um número de cartão de crédito.
    
  - Um número que passa na soma de verificação.
    
  - Uma palavra-chave ou uma data de validade no formato certo.
    
Você pode usar esses níveis de confiança (ou precisão de correspondência) em suas regras. Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma precisão de correspondência inferior. E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça uma substituição, em uma regra com uma precisão de correspondência superior.
  
É importante compreender que quando um tipo específico de informação confidencial, como um número de cartão de crédito, é identificado no conteúdo, somente um único nível de confiança é retornado:
  
- Se todas as correspondências forem para um único padrão, o nível de confiança para aquele padrão será retornado.
    
- Se houver correspondências para mais de um padrão (ou seja, há correspondências com dois níveis de confiança diferentes), o nível de confiança maior do que qualquer um dos padrões únicos sozinhos será retornado. Esta é a parte desafiadora. Por exemplo, para um cartão de crédito, se os padrões de 65% e 85% forem atendidos, o nível de confiança retornado para aquele tipo de informação confidencial será maior que 90%, pois quanto mais evidências, mais confiança.
    
Portanto, se você quiser criar duas regras mutuamente exclusivas para cartões de crédito, uma para a precisão de correspondência de 65% e outro para a precisão de correspondência de 85%, os intervalos para a precisão de correspondência serão parecidos com isto: A primeira regra pega apenas as correspondências ao padrão de 65%. A segunda regra pega as correspondências com **pelo menos uma** correspondência de 85% e **pode ter** outras correspondências de confiança inferiores. 
  
![Duas regras com intervalos diferentes para precisão de correspondência](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Por essas razões, a orientação para a criação de regras com diferentes precisões de correspondência é:
  
- O menor nível de confiança normalmente usa o mesmo valor para **mín** e **máx** (não um intervalo). 
    
- O nível mais alto de confiança é um intervalo entre o valor logo acima do nível de confiança inferior a 100.
    
- Qualquer nível de confiança intermediário normalmente varia de um valor logo acima do nível de confiança inferior para um valor logo abaixo do nível de confiança superior.
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>Usar um rótulo como condição em uma política DLP

Você pode criar um rótulo e, em seguida:
<!-- what kind of label? -->
  
- **Publicá-lo**, para que os usuários finais possam ver e aplicar manualmente o rótulo ao conteúdo. 
    
- **Aplicá-lo automaticamente** ao conteúdo que corresponde às condições escolhidas. 
    
Para mais informações sobre rótulos, consulte [Visão geral de rótulos de retenção](labels.md).
  
Após criar um rótulo, você pode usá-lo como uma condição em suas políticas de DLP. 

![Rótulos como uma condição](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

Por exemplo, talvez você queira fazer isso porque:
  
- Publicou um rótulo denominado **Confidencial**, para que as pessoas da sua organização possam aplicar manualmente o rótulo a documentos e emails confidenciais. Usando esse rótulo como uma condição em sua política de DLP, você pode restringir que o conteúdo rotulado como **Confidencial** seja compartilhado com pessoas de fora da sua organização. 
    
- Você criou um rótulo chamado **Casa Alpina** para um projeto com esse nome e, em seguida, aplicou esse rótulo automaticamente ao conteúdo contendo as palavras-chave “Casa Alpina”. Usando esse rótulo como uma condição em sua política de DLP, você pode mostrar uma dica de política aos usuários finais quando eles estiverem prestes a compartilhar esse conteúdo com alguém de fora da sua organização. 
    
- Você publicou um rótulo chamado **Registro de impostos**, para que seu gerente de registros possa aplicar manualmente o rótulo ao conteúdo que precise ser classificado como um registro. Usando esse rótulo como uma condição em sua política de DLP, você pode procurar conteúdo com esse rótulo em outros tipos de informações confidenciais como CPF; aplicar ações de proteção ao conteúdo rotulado **Registro de impostos**; e obter relatórios de atividade detalhados sobre a política de DLP de relatórios de DLP e os dados do log de auditoria. 
    
- Você publicou um rótulo chamado **Equipe Executiva de Liderança – Confidencial** para as contas de caixa de correio do Exchange e OneDrive de um grupo de executivos. Usando esse rótulo como uma condição em sua política de DLP, você pode aplicar ações de retenção e proteção no mesmo subconjunto de conteúdo e usuários. 
    
Usando rótulos como uma condição em suas regras de DLP, você pode aplicar seletivamente ações de proteção a um conjunto específico de conteúdos, locais ou usuários. 

> [!NOTE]
> Se você especificar um rótulo de retenção como uma condição em uma política DLP e também incluir o Exchange e/ou Teams como um local, receberá a seguinte mensagem de erro: "não há suporte para a proteção de conteúdo rotulado em mensagens de email e equipes. Remova a etiqueta abaixo ou desative o Exchange e ao Teams como um local. " Isso ocorre porque o transporte do Exchange não avalia os metadados do rótulo durante o envio e a entrega da mensagem. 

### <a name="support-for-sensitivity-labels-is-coming"></a>O suporte para rótulos de confidencialidade estará disponível em breve

No momento, você pode usar apenas um rótulo de retenção como uma condição, não um [rótulo de confidencialidade](sensitivity-labels.md). Estamos trabalhando no suporte para usar um rótulo de confidencialidade nesta condição.
  
### <a name="how-this-feature-relates-to-other-features"></a>Como esse recurso se relaciona a outros recursos

Diversos recursos podem ser aplicados ao conteúdo com informações confidenciais:
  
- Um [rótulo de retenção](labels.md#applying-a-retention-label-automatically-based-on-conditions) e uma [política de retenção](retention-policies.md) podem impor ações de **retenção** nesse conteúdo. 
    
- Uma política de DLP pode impor ações de **proteção** nesse conteúdo. E antes de aplicar essas ações, uma política de DLP pode exigir que outras condições sejam atendidas além do conteúdo que contém um rótulo. 
    
![Diagrama de recursos que podem ser aplicados a informações confidenciais](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Observe que uma política de DLP tem um recurso de detecção mais avançado do que um rótulo ou política de retenção aplicada a informações confidenciais. Uma política de DLP pode impor ações de proteção ao conteúdo que contiver informações confidenciais e se as informações confidenciais forem removidas do conteúdo, essas ações de proteção serão desfeitas da próxima vez que o conteúdo for verificado. Mas se uma política ou rótulo de retenção for aplicado ao conteúdo com informações confidenciais, essa será uma ação única que não será desfeita, mesmo se as informações confidenciais forem removidas.
  
Usando um rótulo como uma condição em uma política de DLP, você pode aplicar ações de retenção e proteção no conteúdo com esse rótulo. Pense no conteúdo com um rótulo exatamente como um conteúdo com informações confidenciais – tanto um rótulo quanto um tipo de informação confidencial são propriedades usadas para classificar o conteúdo, para poder impor ações para esse conteúdo.
  
![Diagrama de política de DLP usando rótulo como uma condição](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Configurações simples versus configurações avançadas

Ao criar uma política DLP, decida entre configurações simples ou avançadas:
  
- **Configurações simples** facilitam a criação do tipo mais comum de política DLP sem usar o editor de regras para criar ou modificar regras. 
    
- **Configurações avançadas** usam o editor de regras para oferecer controle completo sobre cada configuração para a sua política DLP. 
    
Não se preocupe, nos bastidores, as configurações simples e avançadas funcionam exatamente da mesma forma, aplicando regras compostas por condições e ações. A única diferença é que, com configurações simples, você não vê o editor de regras. Trata-se de uma maneira rápida de criar uma política DLP.
  
### <a name="simple-settings"></a>Configurações simples

Sem dúvida, o cenário mais comum de DLP é criar uma política para ajudar a evitar que um conteúdo com informações confidenciais seja compartilhado com pessoas fora da sua organização e realizar uma ação corretiva automática, como restringir quem pode acessar o conteúdo, enviar notificações ao usuário final ou ao administrador e auditar o evento para investigação posterior. As pessoas usam a DLP para ajudar a evitar a divulgação acidental de informações confidenciais.
  
Para simplificar essa meta, ao criar uma política DLP, você pode escolher **Usar configurações simples**. Essas configurações fornecem todos os elementos necessários para implementar a política DLP mais comum, sem precisar acessar o editor de regras.
  
![Opções de DLP para configurações simples e avançadas](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Configurações avançadas

Se você precisa criar políticas DLP mais personalizadas, pode escolher **Usar configurações avançadas**.
  
As configurações avançadas apresentam o editor de regras, no qual você tem controle total sobre todas as opções possíveis, incluindo a contagem de instâncias e a precisão de correspondência (nível de confiança) de cada regra.
  
Para acessar rapidamente uma seção, clique em um item na navegação superior do editor de regras para ir até essa seção abaixo.
  
![Menu de navegação superior do editor de regras DLP](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Modelos de política DLP

A primeira etapa na criação de uma política DLP é escolher quais informações serão protegidas. A partir de um modelo DLP, você economiza o trabalho de criar um novo conjunto de regras do zero e descobrir quais tipos de informações devem ser incluídas por padrão. Em seguida, você pode adicionar ou modificar esses requisitos para ajustar a regra para atender aos requisitos específicos da sua organização.
  
Um modelo de política DLP pré-configurado pode ajudar a detectar tipos específicos de informações confidenciais, como dados de HIPAA, dados de PCI-DSS, dados da Lei Gramm-Leach-Bliley ou até informações de identificação pessoal (PII) específicas de localidade. Para facilitar a localização e a proteção de tipos comuns de informações confidenciais, os modelos de política incluídos no Office 365 já contêm os tipos mais comuns de informações confidenciais necessários para você começar.
  
![Lista de modelos para políticas de prevenção contra perda de dados com o foco no modelo para a Lei Patriota dos EUA](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Sua organização também pode ter suas próprias exigências específicas e, nesse caso, você pode criar uma política DLP do zero, escolhendo a opção **Política personalizada**. Uma política personalizada é vazia e não contém regras pré-criadas. 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>Implementar políticas de DLP gradualmente com o modo de teste

Depois de criar as políticas de DLP, você deve considerar a implementação gradual delas para avaliar o impacto e testar a eficácia delas antes de aplicá-las completamente. Por exemplo, você não quer que uma nova política DLP, inadvertidamente, bloqueie o acesso a milhares de documentos que as pessoas precisam acessar para realizar seus trabalhos.
  
Se estiver criando políticas DLP com um grande impacto em potencial, é recomendável seguir esta sequência:
  
1. **Iniciar no modo de teste sem Dicas de Política** e, em seguida, usar os relatórios de DLP e de qualquer incidente para avaliar o impacto. Você pode usar relatórios de DLP para exibir o número, o local, o tipo e a gravidade das correspondências de política. Com base nos resultados, você pode ajustar as regras conforme necessário. No modo de teste, as políticas de DLP não afetarão a produtividade das pessoas que trabalham na sua organização. 
    
2. **Mover para o modo de teste com Dicas de Política e notificações** para que você possa começar a ensinar os usuários sobre suas políticas de conformidade e prepará-los para as regras que serão aplicadas. Nesse estágio, você também pode pedir aos usuários para relatar falsos positivos para que você possa refinar as regras. 
    
3. **Inicie a imposição total das políticas** para que as ações sejam aplicadas nas regras e o conteúdo seja protegido. Continue a monitorar os relatórios de DLP e qualquer relatório de incidente ou notificações para se certificar de que os resultados sejam os desejados. 
    
![Opções para usar o modo de teste e ativar a política](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
Você pode desativar uma política de DLP a qualquer momento, o que afeta todas as regras da política. No entanto, as regras também podem ser desativadas individualmente, alternando o status no editor de regras.
  
![Opções para desativar uma regra em uma política](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

Você também pode alterar a prioridade de várias regras em uma política. Para fazer isso, abra uma política para edição. Em uma linha para uma regra, escolha as reticências (**...**) e, em seguida, escolha uma opção, como **Mover para baixo** ou **Colocar como mais baixa**.

![Definir prioridade da regra](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a>Relatórios DLP

Após criar e ativar as políticas de DLP, verifique se elas estão funcionando conforme esperado e se estão ajudando a manter a conformidade. Com os relatórios de DLP, você pode exibir rapidamente o número de correspondências de regra e política de DLP ao longo do tempo e o número de falsos positivos e substituições. Para cada relatório, você pode filtrar as correspondências por local, intervalo de tempo e até mesmo restringi-lo a uma diretiva, regra ou ação específica.
  
Com os relatórios de DLP, você pode obter ideias de negócios e:
  
- Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.
    
- Descobrir os processos de negócios que violam as políticas de conformidade da sua organização.
    
- Compreender qualquer impacto nos negócios das políticas de DLP.
    
Além disso, você pode usar os relatórios de DLP para ajustar suas políticas de DLP conforme as executar.
  
![Painel de Relatórios no Centro de Conformidade e Segurança](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Como funcionam as políticas de DLP

A DLP detecta informações confidenciais usando análise profunda de conteúdo (não apenas uma simples verificação de texto). Essa análise profunda de conteúdo usa correspondências de palavra-chave, correspondências de dicionário, a avaliação de expressões regulares, funções internas e outros métodos para detectar conteúdos que violam as políticas de DLP. Possivelmente, apenas uma pequena porcentagem dos seus dados é considerada confidencial. Uma política de DLP pode identificar, monitorar e proteger automaticamente apenas esses dados, sem impedir ou afetar as pessoas que trabalham com o restante do seu conteúdo.
  
### <a name="policies-are-synced"></a>As políticas são sincronizadas

Após criar uma política de DLP no Centro de Segurança &amp; Conformidade, ela é armazenada em um repositório central de políticas e sincronizada com várias fontes de conteúdo, incluindo:
  
- Exchange Online, e de lá para o Outlook na Web e o Outlook
    
- Sites do OneDrive for Business
    
- Sites do SharePoint Online
    
- Programas da área de trabalho do Office (Excel, PowerPoint e Word)

- Mensagens de canais e de chats do Microsoft Teams
    
Após a sincronização da política com os locais corretos, ela começa avaliar o conteúdo e aplicar as ações.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Avaliação da política em sites do OneDrive for Business e do SharePoint Online

Em todos os seus sites do SharePoint Online e sites do OneDrive for Business, os documentos estão em constante mudança — eles estão continuamente sendo criados, editados, compartilhados, movidos e assim por diante. Isso significa que os documentos podem conflitar ou ficar em conformidade com uma política de DLP a qualquer momento. Por exemplo, uma pessoa pode carregar um documento que não contém nenhuma informação confidencial para seus sites de equipe, mas, posteriormente, outra pessoa pode editar o mesmo documento e adicionar informações confidenciais a ele.
  
Por esse motivo, as políticas de DLP verificam documentos em busca de correspondências de política com frequência em segundo plano. Você pode considerar isso uma avaliação assíncrona da política.
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Como funciona
 
À medida em que as pessoas adicionam ou alteram documentos em seus sites, o mecanismo de pesquisa examina o conteúdo, para que você possa pesquisá-lo posteriormente. Enquanto isso, o conteúdo também será verificado quanto às informações confidenciais e para verificar se ele é compartilhado. Todas as informações confidenciais encontradas serão armazenadas de forma segura no índice de pesquisa, de modo que somente a equipe de conformidade possa acessá-la, mas não usuários comuns. Cada política de DLP ativada é executada em segundo plano (de forma assíncrona), verificando a pesquisa frequentemente por qualquer conteúdo que corresponda a uma política e aplicando ações para protegê-lo contra perdas acidentais.
  
![Diagrama mostrando como a política DLP avalia o conteúdo de forma assíncrona](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> Por fim, os documentos podem conflitar uma política de DLP, mas eles também podem ficar em conformidade com ela. Por exemplo, se uma pessoa adicionar números de cartão de crédito a um documento, isso poderá fazer com que uma política de DLP bloqueie o acesso ao documento automaticamente. Mas, se a pessoa remover, mais tarde, as informações confidenciais, a ação (neste caso, bloqueio) será desfeita na próxima vez que se avaliar se o documento está de acordo com a política.
  
A DLP avalia qualquer conteúdo que pode ser indexado. Para saber mais sobre os tipos de arquivo que são rastreados por padrão, confira [Extensões de nomes de arquivos rastreados e tipos de arquivos padrão analisados no SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Avaliação de políticas no Exchange Online, Outlook e Outlook na Web

Ao criar uma política DLP que inclui o Exchange Online como um local, a política foi sincronizada no Centro de Conformidade &amp; Segurança do Office 365 para o Exchange Online e, em seguida, do Exchange Online para o Outlook na Web e no Outlook.
  
Quando uma mensagem está sendo redigida no Outlook, o usuário pode ver dicas de política à medida que o conteúdo sendo criado é avaliado em relação às políticas DLP. Após uma mensagem ser enviada, ela é avaliada em relação às políticas DLP como parte normal do fluxo de emails, juntamente com regras de fluxo de emails do Exchange e as políticas DLP criadas no Centro de Administração do Exchange. As políticas DLP examinam tanto a mensagem quanto os anexos.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Avaliação de política nos programas da área de trabalho do Office

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint e Word incluem os mesmos recursos para identificar informações confidenciais e aplicar políticas de DLP como o SharePoint Online e o OneDrive for Business. Esses programas do Office sincronizam suas políticas DLP diretamente do repositório central de políticas e, em seguida, avaliam continuamente o conteúdo em relação às políticas DLP quando as pessoas trabalham com documentos abertos de um site incluso em uma política DLP.
  
A avaliação das políticas DLP no Office foi desenvolvida para não afetar o desempenho dos programas ou a produtividade de pessoas que trabalham no conteúdo. Se estiverem trabalhando em um documento grande ou o computador do usuário estiver ocupado, pode demorar alguns segundos para uma dica de política ser exibida.

### <a name="policy-evaluation-in-microsoft-teams"></a>Avaliação de políticas no Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Ao criar uma política DLP que inclui o Microsoft Teams como um local, a política foi sincronizada no centro de Conformidade &amp; Segurança do Office 365 para contas de usuários e mensagens de chat e de canais do Microsoft Teams. Dependendo da configuração das políticas DLP, quando alguém tentar compartilhar informações confidenciais em uma mensagem de chat ou canal do Microsoft Teams, a mensagem pode ser bloqueada ou revogada. Os documentos com informações confidenciais e que são compartilhados com convidados (usuários externos) não abrirão para esses usuários. Para saber mais, confira [Prevenção contra perda de dados no Microsoft Teams](dlp-microsoft-teams.md).
 
## <a name="permissions"></a>Permissões

Os membros da sua equipe de conformidade que irão criar políticas DLP precisam de permissões ao Centro de Conformidade &amp; Segurança. Por padrão, o administrador de locatário terá acesso a esse local e pode conceder aos responsáveis pela conformidade e outras pessoas acesso ao Centro de Conformidade &amp; Segurança, sem conceder todas as permissões de um administrador de locatário. Para fazer isso, recomendamos:
  
1. Criar um grupo no Office 365 e adicione os responsáveis pela conformidade.
    
2. Criar um grupo de funções na página **Permissões** do Centro de Conformidade &amp; Segurança. 
    
3. Adicionar o grupo do Office 365 ao grupo de funções.
    
Para saber mais, consulte [Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Essas permissões são necessárias somente para criar e aplicar uma política de DLP. A imposição da política não exige acesso ao conteúdo.
  
## <a name="find-the-dlp-cmdlets"></a>Encontre os cmdlets da DLP

Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:
  
1. [Conectar-se ao Centro de Conformidade &amp; Segurança do Office 365 usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. Usar qualquer um destes [cmdlets policy-and-compliance-dlp](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)
    
No entanto, os relatórios DLP precisam extrair dados do Office 365, incluindo o Exchange Online. Por esse motivo, **os cmdlets para os relatórios DLP estão disponíveis no Exchange Online Powershell, e não no Centro de Conformidade &amp; Segurança do Powershell**. Portanto, para usar os cmdlets para os relatórios DLP, você precisa:
  
1. [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. Usar qualquer um destes cmdlets para os relatórios DLP:
    
  - [Get-DlpDetectionsReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [Get-DlpDetailReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a>Mais informações

- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)
    
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
    
- [O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)
    
- [O que as funções DLP procuram](what-the-dlp-functions-look-for.md)
    
- [Criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md)
    

