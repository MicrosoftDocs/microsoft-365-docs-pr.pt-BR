---
title: Configurar políticas de links seguros de ATP do Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Configurar políticas de links seguros para proteger sua organização contra links mal-intencionados nos arquivos do Word, Excel, PowerPoint e Visio, bem como em mensagens de email.
ms.openlocfilehash: 76d0aba026b96251a64163ef7d7f518fe0b1e1b1
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279586"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Configurar políticas de links seguros de ATP do Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Os [links seguros de ATP](atp-safe-links.md) são um recurso da [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) que pode ajudar a proteger sua organização contra links mal-intencionados usados em phishing e outros ataques. Se você tiver as [permissões necessárias para o centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md), poderá configurar as políticas de links seguros de ATP para ajudar a garantir que quando as pessoas clicarem em endereços da Web (URLs), sua organização esteja protegida. As políticas de links seguros de ATP podem ser configuradas para verificar URLs em emails e URLs em documentos do Office. Os links seguros de ATP examinam o email de entrada para hiperlinks mal-intencionados conhecidos e anexos que contenham malware. Este recurso reconfigura URLs verificadas no prefixo de formato de URL padrão da Microsoft <https://nam01.safelinks.protection.outlook.com> . Depois que um link é reconfigurado, ele é analisado para qualquer conteúdo mal-intencionado em potencial. Com os links seguros de ATP habilitados, se um usuário clicar em um link em um email e a URL tiver sido bloqueada pela lista de URLs bloqueadas personalizada da sua organização ou se a URL for determinada como mal-intencionada, uma página de aviso será aberta.

Depois que o links de segurança ATP tiver reconfigurado uma URL, se a mensagem for encaminhada ou respondida, a URL permanecerá reconfigurada. Links adicionais adicionados à mensagem que estão sendo respondidas ou encaminhadas não serão reconfigurados.

[Novos recursos estão sempre sendo adicionados à ATP](office-365-atp.md#new-features-in-office-365-atp). À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes em suas políticas de links seguros de ATP existentes.

## <a name="what-to-do"></a>O que fazer

1. Examine os pré-requisitos.

2. Revise e edite a política de links seguros padrão ATP que se aplica a todos. Por exemplo, você pode [configurar sua lista de URLs bloqueadas personalizada para links seguros de ATP](set-up-a-custom-blocked-urls-list-atp.md).

3. Adicione ou edite políticas para destinatários de email específicos, incluindo [a configuração da lista de URLs de "não reescrever" personalizada para links seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).

4. Saiba mais sobre as opções de política de links seguros de ATP (neste artigo), incluindo configurações para alterações recentes.

## <a name="step-1-review-the-prerequisites"></a>Etapa 1: revisar os pré-requisitos

- Certifique-se de que sua organização tenha a [proteção avançada contra ameaças do Office 365](office-365-atp.md).

- Verifique se você tem as permissões necessárias. Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída. Alguns exemplos são descritos na tabela a seguir:

    |Função|Onde/como a atribuição|
    |---|---|
    |administrador global|Por padrão, a pessoa que se inscreve para comprar a Microsoft 365 é um administrador global. (Consulte [about Microsoft 365 admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para saber mais.)|
    |Administrador de Segurança|Centro de administração do Azure Active Directory ( <https://aad.portal.azure.com> )|
    |Gerenciamento de Organização do Exchange Online|Centro de administração do Exchange ( <https://outlook.office365.com/ecp> ) <br>ou <br>  Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

    Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

- Certifique-se de que os clientes do Office estão configurados para usar a [autenticação moderna](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) (isso é para proteção de links de segurança ATP em documentos do Office).

- [Saiba mais sobre as opções de política de links seguros de ATP](#step-4-learn-about-atp-safe-links-policy-options) (neste artigo).

- Aguarde até 30 minutos para que a política nova ou atualizada se espalhe para todos os datacenters da Microsoft 365.

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Etapa 2: definir (ou revisar) a política de links seguros de ATP que se aplica a todos

Quando você tiver a [proteção avançada contra ameaças do Office 365](office-365-atp.md), terá uma política de links seguros padrão da ATP que se aplica a todas as pessoas em sua organização. Certifique-se de revisar e, se necessário, edite a política padrão.

1. Acesse <https://protection.office.com> e entre com sua conta corporativa ou de estudante.

2. Na navegação à esquerda, em **Gerenciamento de ameaças**, escolha **links seguros**de ** \> política** .

3. Na seção **políticas que se aplicam a toda a organização** , selecione **padrão**e, em seguida, escolha **Editar** (o botão Editar parece um lápis).

   ![Clique em Editar para editar a política padrão para proteção de links seguros](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. Na seção **bloquear as seguintes URLs** , especifique uma ou mais URLs que você deseja impedir que as pessoas em sua organização visitem. (Consulte [Configurar uma lista de URLs bloqueadas personalizada usando os links seguros de ATP](set-up-a-custom-blocked-urls-list-atp.md).)

5. Na seção **configurações que se aplicam a conteúdo exceto email** , marque (ou desmarque) as opções que você deseja usar. (Recomendamos que você selecione todas as opções.)

6. Escolha **Salvar**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients"></a>Etapa 3: Adicionar (ou editar) políticas de links seguros de ATP que se aplicam a todos os destinatários de email específicos

Após revisar (ou editar) a política padrão de links seguros de ATP que se aplica a todos, a próxima etapa é definir políticas adicionais que se apliquem a todos os destinatários de email específicos. Por exemplo, você pode especificar exceções à política padrão definindo uma política adicional ou criar restrições mais granulares para todos os funcionários.
  
1. Acesse <https://protection.office.com> e entre com sua conta corporativa ou de estudante. 
    
2. Na navegação à esquerda, em **Gerenciamento de ameaças**, escolha **política**.

3. Escolha **links seguros**.

4. Na seção **políticas que se aplicam a destinatários específicos** , escolha **novo** (o botão novo é semelhante a um sinal de adição ( **+** )).

   ![Escolha novo para adicionar uma política de links seguros para destinatários de email específicos](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. Especifique o nome, a descrição e as configurações da política.

   **Exemplo:** Para configurar uma política chamada "sem cliques diretos" que não permite que as pessoas de um determinado grupo em sua organização cliquem em um site específico sem proteção de links de ATP seguro, você pode especificar as seguintes configurações recomendadas:

   - Na caixa **nome** , digite sem clique direto em.

   - Na caixa **Descrição** , digite uma descrição como, para impedir que as pessoas em determinados grupos cliquem em um site sem verificação de links seguros de ATP.

   - Na seção **Selecionar ação** , escolha **ativado**.

   - Selecione **aplicar verificação de URL em tempo real para links suspeitos e links que apontam para os arquivos** se você quiser habilitar a URL acionamento para URLs suspeitas e de arquivo apontado (recomendado). E selecione **aguardar até que a verificação de URL seja concluída antes de entregar a mensagem** se você quiser que os usuários recebam mensagens depois que as URLs tiverem sido totalmente verificadas.

   - Selecione **aplicar links seguros a mensagens enviadas dentro da organização** se quiser habilitar links seguros para mensagens enviadas entre usuários dentro da sua organização (recomendado).

   - Selecione não **permitir que o usuário clique na URL original** se você não quiser que os usuários individuais substituam uma *verificação nas páginas de notificação de andamento ou de* *URL bloqueadas* .

   - (Isso é opcional) Na seção não **reescrever as seguintes URLs** , especifique uma ou mais URLs consideradas seguras para sua organização. (Consulte [Configurar uma lista de URLs "não reconfigurar" personalizada usando os links seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))

   - Na seção **aplica-se** a, escolha **o destinatário é um membro de**e, em seguida, escolha o (s) grupo (s) que você deseja incluir na política. Escolha **Adicionar**e, em seguida, escolha **OK**.

6. Escolha **Salvar**.

> [!NOTE]
> As políticas de links seguros de ATP com prioridade mais alta terão precedência. Se um usuário estiver sujeito a duas ou mais políticas, somente a política de prioridade mais alta entrará em vigor. Se quiser que a política do cliente tenha precedência, você precisará aumentar a prioridade da política.

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Etapa 4: Saiba mais sobre as opções de política de links seguros de ATP

À medida que você configura ou edita suas políticas de links seguros de ATP, algumas opções estão disponíveis. Caso você esteja se perguntando quais são essas opções, a tabela a seguir descreve cada uma e seu efeito. Lembre-se de que há dois tipos principais de políticas de links seguros de ATP para definir ou editar:

- uma [política padrão](#default-policy-options) que se aplica a todos; e
- [políticas adicionais para destinatários específicos](#policies-that-apply-to-specific-email-recipients)

### <a name="default-policy-options"></a>Opções de política padrão

As opções de política padrão se aplicam a todas as pessoas em sua organização.

****

|Essa opção|Faça isto|
|---|---|
|**Bloquear as seguintes URLs**|Permite que sua organização tenha uma lista personalizada de URLs bloqueadas automaticamente. Quando os usuários clicarem em uma URL nessa lista, serão levados a uma [página de aviso](atp-safe-links-warning-pages.md) que explica por que a URL é bloqueada. Para saber mais, confira [Configurar uma lista de URLs bloqueadas personalizada usando os links seguros de ATP do Office 365](set-up-a-custom-blocked-urls-list-atp.md).|
|**Microsoft 365 aplicativos para empresas, Office para iOS e Android**| Quando essa opção é selecionada, a proteção de links seguros de ATP é aplicada às URLs nos arquivos do Word, Excel e PowerPoint no Windows ou no Mac OS, mensagens de email no Outlook, documentos do Office em dispositivos iOS ou Android, arquivos do Visio 2016 no Windows e arquivos abertos nas versões Web dos aplicativos do Office (Word, PowerPoint, Excel, Outlook e OneNote), desde que o usuário tenha entrado no Office 365|
|**Não rastrear quando os usuários clicarem em links de ATP seguros**|Quando essa opção é selecionada, clique em dados para URLs no Word, Excel, PowerPoint, documentos do Visio e mensagens de email do Outlook não são armazenados.|
|**Não permitir que os usuários cliquem através de links seguros de ATP para a URL original**|Quando essa opção é selecionada, os usuários não podem continuar após uma [página de aviso](atp-safe-links-warning-pages.md) para uma URL que é determinada como mal-intencionada.|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a>Políticas que se aplicam a destinatários de email específicos

****

|Essa opção|Faça isto|
|---|---|
|**Desativar**|Não verifica URLs em mensagens de email.  <br/> Permite que você defina uma regra de exceção, como uma regra que não examina URLs em mensagens de email para um grupo específico de destinatários.|
|**On**|Reconfigura URLs para rotear usuários por meio de proteção de links seguros de ATP quando os usuários clicam em URLs em mensagens de email e habilita links seguros de ATP no Outlook (C2R) no Windows.  <br/> Verifica uma URL quando clicado em uma lista de URLs bloqueadas ou maliciosas e dispara um acionamento da URL em segundo plano de forma assíncrona se a URL não tiver uma reputação válida.|
|**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**|Quando essa opção é selecionada, URLs suspeitas e links que apontam para o conteúdo baixável são verificados.|
|**Aguarde a conclusão da verificação de URL antes de entregar a mensagem**|Quando essa opção é selecionada, as mensagens que contêm URLs a serem verificadas serão mantidas até que as URLs terminem a verificação e sejam confirmadas para serem seguras antes de as mensagens serem entregues.|
|**Aplicar links seguros a mensagens enviadas dentro da organização** <br/> | Quando essa opção está disponível e selecionada, a proteção de links de segurança ATP é aplicada a mensagens de email enviadas entre pessoas em sua organização, desde que as contas de email sejam hospedadas no Office 365.|
|**Não rastrear cliques do usuário**|Quando essa opção é selecionada, clique em dados para URLs em emails de remetentes externos não são armazenados. URL o acompanhamento de links em mensagens de email enviadas dentro da organização atualmente não tem suporte.|
|**Não permitir que os usuários cliquem através da URL original**|Quando essa opção é selecionada, os usuários não podem continuar após uma [página de aviso](atp-safe-links-warning-pages.md) para uma URL que é determinada como mal-intencionada.|
|**Não Reescreva as seguintes URLs**|Deixa as URLs como estão. Mantém uma lista personalizada de URLs seguras que não precisam de varredura para um grupo específico de destinatários de email em sua organização. Confira [Configurar uma lista de URLs de "não reconfigurar" personalizada usando links seguros de ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para obter mais detalhes, incluindo as alterações recentes de suporte para asteriscos curinga ( \* ).|
|

## <a name="next-steps"></a>Próximas etapas

Depois que as políticas de links seguros de ATP estiverem vigentes, você poderá ver como a ATP está trabalhando para sua organização exibindo relatórios. Confira os seguintes recursos para saber mais:

- [Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)

- [Usar o Explorer no centro de conformidade & segurança](threat-explorer.md)

Fique à frente dos novos recursos que chegam à ATP. Visite o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
