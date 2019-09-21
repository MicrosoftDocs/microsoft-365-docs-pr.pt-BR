---
title: Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Quando você cria um rótulo de confidencialidade, pode restringir o acesso ao conteúdo ao qual o rótulo será aplicado. Rótulos de confidencialidade podem usar criptografia para proteger o conteúdo.
ms.openlocfilehash: a30f5d6168ea8118ef6b30ff26a429857affaa4a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072686"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a>Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade

Quando você cria um rótulo de confidencialidade, pode restringir o acesso ao conteúdo ao qual o rótulo será aplicado. Por exemplo, com as configurações de criptografia para um rótulo de confidencialidade, você pode proteger conteúdos de modo que:

- Somente os usuários em sua organização possam abrir um documento ou um email confidenciais.
- Somente os usuários do departamento de marketing possam editar e imprimir o documento ou email de comunicado de promoção, enquanto todos os outros usuários em sua organização possam apenas lê-lo.
- Os usuários não podem encaminhar um email ou copiar informações destas fontes que contêm notícias sobre uma reorganização interna.
- A lista de preços atual que enviada a parceiros de negócios não pode ser aberta após uma data especificada.

Quando um documento ou email é criptografado, o acesso ao conteúdo é restrito, para que ele:

- Possa ser descriptografado apenas por usuários autorizados pelas configurações de criptografia do rótulo.
- Permaneça criptografado independentemente de onde esteja, dentro ou fora da sua organização, mesmo se o arquivo for renomeado.
- Fique criptografado tanto em repouso (por exemplo, em uma conta do OneDrive) quanto em trânsito (por exemplo, um email enviado).

Por fim, como administrador, quando você cria um rótulo de sensibilidade, há duas opções a escolher:

- **Atribuir permissões agora**, para que assim você possa determinar exatamente quais usuários podem obter quais permissões de conteúdo com esse rótulo.
- **Permitir que os usuários atribuam permissões** quando aplicam o rótulo ao conteúdo. Dessa forma, você pode conceder a pessoas em sua organização uma certa flexibilidade que elas possam precisar para colaborar e realizar o trabalho.

As configurações de criptografia estão disponíveis quando você cria um rótulo de confidencialidade no centro de conformidade do Microsoft 365, centro de segurança do Microsoft 365 ou Centro de Conformidade e Segurança do Office 365. Na barra de navegação à esquerda, escolha **Classificação** > ** Rótulo de sensibilidade** > **Criar um rótulo**.

## <a name="how-encryption-works"></a>Como funciona a criptografia

A criptografia usa o Azure Rights Management (Azure RMS). O Azure RMS usa identidade, criptografia e autorização políticas. Para saber mais, confira [O que é Azure Rights Management?](https://docs.microsoft.com/pt-BR/azure/information-protection/what-is-azure-rms)

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a>Como ativar a criptografia para um rótulo de confidencialidade

Para começar, basta no botão de alternância em**Criptografia**optar por**Ativar**, em seguida, escolha entre:

- **Atribuir permissões agora**, para assim determinar exatamente quais usuários podem obter quais permissões de conteúdo com esse rótulo. Para mais informações, consulte a próxima seção[Atribuir permissões agora](#assign-permissions-now).
- **Permitir que os usuários atribuam permissões** quando aplicam o rótulo ao conteúdo. Dessa forma, você pode conceder a pessoas em sua organização uma certa flexibilidade que elas possam precisar para colaborar e realizar o trabalho. Para mais informações, consulte a seção abaixo[ Permitir que usuários atribuam permissões](#let-users-assign-permissions).

Por exemplo, se você tiver um rótulo de sensibilidade denominado **Altamente Confidencial** que seria aplicado ao seu conteúdo mais confidencial, talvez você queira decidir agora quem recebe o tipo de permissão para esse conteúdo.

Como alternativa, se você tiver um rótulo de sensibilidade chamado **Contratos de Negócios**, e o fluxo de trabalho da sua organização exigir que as pessoas colaborem com outras pessoas de forma ad hoc, talvez você queira permitir que seus os usuários decidam quem receberá permissões quando atribui o rótulo. Essa flexibilidade auxilia não só a produtividade dos usuários como também reduz as solicitações dos seus administradores de atualizar ou criar novos rótulos de sensibilidade para cenários específicos.

![Opção para adicionar permissões definidas por usuários ou administradores](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>Atribuir permissões agora

Use as opções abaixo para controlar quem pode acessar os emails e documentos aos quais aquele rótulo foi aplicado. Você pode:

1. **Aplicar criptografia em emails e documentos, ou apenas em emails. ** Se quiser aplicar somente aos emails, as mensagens com esse rótulo serão criptografadas no Outlook, mas os documentos com este rótulo não serão criptografados em outros aplicativos, como Word ou PowerPoint. 
2. **Permitir que o acesso ao conteúdo rotulado expire**, em uma data específica ou depois de um número específico de dias após o rótulo ser aplicado. Após este período, os usuários não poderão abrir o item rotulado. Se você especificar uma data, isso será válido a partir da meia-noite da data em questão em seu fuso horário atual. (Observe que alguns clientes de email podem não impor expiração e exibir emails após a data de vencimento, devido a seus mecanismos de cache.)
3. **Permitir o acesso offline** nunca, sempre ou por um número específico de dias após o rótulo ser aplicado. Se você restringir o acesso offline para nunca ou por um número de dias, quando este limite for atingido, os usuários precisarão ser autenticados novamente e seu acesso será registrado. Para saber mais, confira a próxima seção na licença de uso de Gerenciamento de Direitos.

![Configurações de permissões de administrador definidas](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a>Licença de uso de Gerenciamento de Direitos para acesso offline

Quando o usuário abre um documento ou email offline protegido por um rótulo de confidencialidade, ele recebe uma licença de uso do Azure Rights Management para esse conteúdo. Essa licença de uso é um certificado com direitos de uso do usuário para o documento ou email e a chave de criptografia usada para criptografar o conteúdo. A licença de uso também contém uma data de vencimento, se tiver sido definida, e o período de validade da licença.

Se nenhuma data de vencimento tiver sido definida, o período de validade da licença de uso padrão para um locatário é de 30 dias. Pela duração da licença de uso, o usuário não precisa ser autenticado ou autorizado novamente para o conteúdo. Isso permite que o usuário continue a abrir o documento ou email protegido sem uma conexão de Internet. Quando expirar o período de validade da licença de uso, na próxima vez em que o usuário acessar o documento ou email protegido, ele precisará ser autenticado e autorizado novamente.

Além da nova autenticação, a política e a associação do grupo de usuários são reavaliados. Isso significa que os usuários pode experimentar diferentes resultados de acesso para o mesmo documento ou email se houver alterações na política ou na associação de grupo em relação à última vez em que acessaram o conteúdo.

Para saber como alterar a configuração padrão de 30 dias, confira [Licença de uso de Gerenciamento de Direitos](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-usage-rights#rights-management-use-license)..

### <a name="assign-permissions-to-specific-users-or-groups"></a>Atribuir permissões a usuários ou grupos específicos

Você pode conceder permissões para pessoas específicas para que somente elas possam interagir com o conteúdo rotulado.

Este é um processo de duas etapas simples:

1. Primeiro você adiciona usuários ou grupos que receberão permissões para o conteúdo rotulado.
2. Em seguida, escolhe quais permissões os usuários têm para o conteúdo rotulado.

![Opções para atribuir permissões para usuários](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>Adicionar usuários ou grupos

Quando você atribui permissões, pode escolher:

- Todos em sua organização (todos os membros locatários). Esta configuração exclui contas de convidados.
- Qualquer usuário específico ou grupo de segurança, grupo de distribuição, grupo do Office 365 ou grupo de distribuição dinâmico habilitado para email. 
- Qualquer endereço de email ou domínio fora da sua organização, como gmail.com, hotmail.com ou outlook.com.

Quando você escolhe todos os membros locatários e pesquisa o diretório, os usuários ou grupos devem ter um endereço de email.

Como prática recomendada, use grupos em vez de usuários. Essa estratégia mantém a configuração mais simples.

#### <a name="choose-permissions"></a>Escolher permissões

Quando você escolhe quais permissões atribuir para os usuários ou grupos, você pode selecionar:

- Um [nível de permissões predefinidas](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) com um grupo predefinido de direitos, como co-autor ou revisor.
- Um grupo de direitos personalizados, no qual você escolhe as permissões que desejar.

Para saber mais sobre cada permissão específica, confira [Direitos de uso e descrições](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).  

![Opções para escolher permissões predefinidas ou personalizadas](media/Sensitivity-Choose-permissions-settings.png)

Observe que o mesmo rótulo pode atribuir permissões diferentes a usuários diferentes. Por exemplo, um rótulo único pode definir alguns usuários como Revisores e um usuário diferente como Co-Autor, como mostrado abaixo.

Para fazer isso, adicione usuários ou grupos, atribua-lhes permissões e salve essas configurações. Depois repita essas etapas, adicionando usuários e atribuindo-lhes permissões, salvando as configurações a cada vez. Você pode fazer isso quantas vezes for necessário para definir permissões diferentes para usuários diferentes.

![Usuários diferentes com permissões diferentes](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>O emissor do Gerenciamento de Direitos (usuário que aplica o rótulo de confidencialidade) sempre tem o Controle Total

A criptografia de um rótulo de confidencialidade usa Azure RMS. Quando um usuário aplica um rótulo de confidencialidade para proteger um documento ou email usando o Azure RMS, esse usuário se torna o emissor do Gerenciamento de Direitos daquele conteúdo.

O emissor do Gerenciamento de Direitos sempre recebe as permissões de Controle Total para o documento ou email, e também:

- Se as configurações de proteção incluem uma data de vencimento, o emissor do Gerenciamento de Direitos ainda pode abrir e editar o documento ou email após essa data.
- O emissor do Gerenciamento de Direitos sempre pode acessar o documento ou email offline.
- O emissor do Gerenciamento de Direitos ainda consegue abrir um documento após sua revogação.

Para saber mais, confira [Emissor do Gerenciamento de Direitos e Proprietário do Gerenciamento de Direitos](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).

## <a name="let-users-assign-permissions"></a>Permitir que usuários atribuam permissões

Você pode usar essas opções para permitir que os usuários atribuam permissões quando os mesmos aplicarem manualmente um rótulo de sensibilidade ao conteúdo:

- No Outlook, um usuário pode aplicar restrições equivalente à opção**Não encaminhar**. Essa opção é compatível nativamente com o Outlook no Windows e não exige que você instale o cliente de rotulagem de Proteção de informações do Azure.
- No Word, no PowerPoint e no Excel, um usuário deve selecionar um nível de permissão para usuários, grupos ou organizações específicos. Essa opção não é compatível nativamente com esses aplicativos e portanto exige que você instale o cliente de rotulagem de Proteção de informações do Azure.

Essas opções determinam em quais aplicativos o rótulo de sensibilidade será exibido:

- Se o rótulo de sensibilidade tiver apenas a opção Outlook habilitada, o rótulo aparecerá para os usuários somente no Outlook.
- Se o rótulo de sensibilidade tiver apenas a opção Word, PowerPoint e Excel habilitada, o rótulo aparecerá para os usuários somente nesses aplicativos.
- Se o rótulo de sensibilidade tiver ambas as opções habilitadas, o rótulo aparecerá para os usuários em todos os aplicativos disponíveis: Outlook, Word, PowerPoint e Excel.

Um rótulo de sensibilidade que permite aos usuários atribuir permissões a conteúdo só poderá ser aplicado manualmente por usuários. Tal rótulo não pode ser aplicado automaticamente ou usado como um rótulo recomendado.

> [!NOTE]
> Permitir que os usuários atribuam permissões exige uma assinatura de Proteção de informações do Azure. Para usar esse recurso no Word, PowerPoint e Excel, você deve baixar e instalar o [cliente de rotulagem de Proteção de informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app). Estamos trabalhando na combatibilidade nativa desse recurso nestes aplicativos do Office, para que eles não exijam a instalação do cliente de Proteção de informações do Azure. Além disso, o cliente só é executado no Windows, portanto esse recurso ainda não é compatível com Mac, iOS, Android ou com o Office para a Web.

![Configurações de criptografia para permissões definidas pelo usuário](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Restrições do Outlook

No Outlook, quando um usuário aplica um rótulo de sensibilidade que permite atribuir permissões a uma mensagem, as restrições são as mesmas da opção Não Encaminhar. O usuário verá o nome e a descrição do rótulo na parte superior da mensagem, o que indica que o conteúdo é protegido. Diferentemente do Word, do PowerPoint e do Excel (confira a [ próxima seção](#word-powerpoint-and-excel-permissions)), os usuários não são solicitados a selecionar permissões específicas.

![Rótulo de confidencialidade aplicado a uma mensagem no Outlook](media/sensitivity-label-outlook-protection-applied.png)

Quando a opção Não Encaminhar for aplicada a um email, tal email será criptografado e os destinatários deverão ser autenticados. Subsequentemente, os destinatários não podem encaminhar, imprimir ou copiar esse email. Por exemplo, no cliente do Outlook, o botão Encaminhar não está disponível, as opções do menu Salvar Como e Imprimir não estão disponíveis, e você não pode adicionar ou alterar destinatários nas caixas Para, CC ou Cco.

Os documentos do Office desprotegidos que são anexados ao email herdam automaticamente as mesmas restrições. Os direitos de uso aplicados a esses documentos são Editar Conteúdo, Editar; Salvar, Exibir, Abrir, Ler; e Permitir Macros. Se o usuário quiser direitos de uso diferentes para um anexo, ou se o anexo não for um documento do Office compatível com essa proteção herdada, o usuário precisará proteger o arquivo antes de anexá-lo ao email.

### <a name="word-powerpoint-and-excel-permissions"></a>Permissões do Word, do PowerPoint e do Excel

No Word, no PowerPoint e no Excel, quando um usuário aplica um rótulo de sensibilidade que permite atribuir permissões a um documento, eles são solicitados a proteger o conteúdo conforme mostrado a seguir.

O usuário pode:

- Selecionar um nível de permissão, como o Visualizador (que atribui permissão Somente para Exibição) ou Coautor (que atribui permissões de Exibição, Edição, Cópia e Impressão).
- Selecione usuários, grupos ou organizações. Isso pode incluir pessoas tanto de dentro quanto de fora de sua organização.
- Defina uma data de vencimento, após a qual os usuários selecionados não poderão acessar o conteúdo. Para saber mais, confira a seção acima [Licença de uso do Gerenciamento de Direitos para acesso online](#rights-management-use-license-for-offline-access).

![Opções para o usuário proteger com permissões personalizadas](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>O que acontece com a criptografia existente quando um rótulo é aplicado

Antes de um rótulo de sensibilidade for aplicado ao conteúdo, é possível que um usuário já tenha criptografado o conteúdo ao aplicar outras configurações de proteção. Por exemplo, um usuário pode ter aplicado:

- A opção **Não Encaminhar**.
- Proteção personalizada usando a rotulagem de cliente unificado da Proteção de informações do Azure.
- Um modelo de Serviço de Gerenciamento de Direitos (RMS) do Azure que criptografa o conteúdo, mas não está associado um rótulo.

Esta tabela descreve o que acontece com uma criptografia preexistente quando um rótulo de sensibilidade é aplicado ao conteúdo.
<br/>
<br/>

| |**O usuário aplica um rótulo de sensibilidade com a criptografia desativada**|**O usuário aplica um rótulo de sensibilidade com a criptografia ativada**|**Usuário aplica um rótulo com Remover a Proteção**<sup>1</sup>|
|:-----|:-----|:-----|:-----|
|**Não Encaminhar**|Email – a proteção é removida<br/>Documento – a proteção é preservada|Proteção de rótulo é aplicada|**Não encaminhar** é removida|
|**Proteção personalizada**<sup>1</sup>|A proteção é preservada|Proteção de rótulo é aplicada|A proteção personalizada é removida|
|**Modelo do Azure RMS**|A proteção é preservada|Proteção de rótulo é aplicada|A proteção personalizada é removida|

<sup>1</sup>Isso tem suporte apenas na rotulagem de cliente da Proteção de informações do Azure.

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a>Armazenar conteúdo criptografado no OneDrive e no SharePoint

Saiba que quando a criptografia é aplicada aos arquivos armazenados no OneDrive e no SharePoint, o serviço não pode processar o conteúdo desses arquivos. Isso significa que recursos como co-autoria, Descoberta Eletrônica, pesquisa, Delve e outros recursos colaborativos não funcionam. Além disso, as políticas de prevenção de perda de dados (DLP) só funcionam com metadados (incluindo rótulos do Office 365), mas não com o conteúdo dos arquivos criptografados (como números de cartão de crédito dentro de arquivos).

Isso se aplica apenas ao conteúdo armazenado no OneDrive e no SharePoint. No Exchange Online, as regras de fluxo de emails (também conhecidas como regras de transporte) usam a [super conta de usuário](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-super-users) para que possam criptografar conteúdos e aplicar políticas DLP.

## <a name="important-prerequisites"></a>Pré-requisitos importantes

Antes de usar a criptografia, talvez seja necessário realizar essas tarefas.

### <a name="activating-azure-rights-management"></a>Ativar o Gerenciamento de Direitos do Azure

Para usar a criptografia em rótulos de confidencialidade, o serviço de Gerenciamento de Direitos do Azure precisa ser ativado em seu locatário. Nos locatários mais novos, o serviço fica ativo por padrão, mas você pode precisar ativá-lo manualmente. Para saber mais, confira [Ativar o Gerenciamento de Direitos do Azure](https://docs.microsoft.com/pt-BR/azure/information-protection/activate-service).

### <a name="configure-exchange-for-azure-information-protection"></a>Configurar o Exchange para a Proteção de Informações do Azure

O Exchange não precisa ser configurado para a Proteção de Informações do Azure antes que os usuários podem aplicar rótulos no Outlook para proteger seus emails. No entanto, até que o Exchange esteja configurado para a Proteção de Informações do Azure, você não conseguirá obter a funcionalidade completa do uso da proteção do Gerenciamento de Direitos do Azure com o Exchange.
 
Por exemplo, usuários não podem exibir emails protegidos em celulares ou com o Outlook na Web, os emails protegidos não podem ser indexados para pesquisa e você não pode configurar o DLP do Exchange Online para a proteção do Gerenciamento de Direitos. 

Para garantir que Exchange possa dar suporte a esses cenários adicionais, confira o seguinte:

- Para o Exchange Online, confira as instruções de [Exchange Online: configuração do IRM](https://docs.microsoft.com/pt-BR/azure/information-protection/configure-office365#exchange-online-irm-configuration).
- Para o Exchange local, é necessário implantar o [conector RMS e configurar seus servidores Exchange](https://docs.microsoft.com/pt-BR/azure/information-protection/deploy-rms-connector). 
