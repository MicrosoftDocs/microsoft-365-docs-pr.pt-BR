---
title: Configurar políticas de supervisão
description: Configure as políticas de supervisão de comunicação no Office 365 para capturar as comunicações dos funcionários para exame pelos revisores internos ou externos.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74244b5288043a1d1bc62e0ae09ee8c25ff7d4e1
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546773"
---
# <a name="configure-supervision-policies-in-office-365"></a>Configurar políticas de supervisão no Office 365

>[!IMPORTANT]
>Após o lançamento da conformidade de comunicação no Microsoft 365 Compliance em fevereiro de 2020, a Supervisão no Office 365 será retirada. As políticas de supervisão não estarão mais disponíveis para criação, e as políticas serão eventualmente removidas, após um longo período de acesso somente leitura.
>
>Se você usar a Supervisão, esteja ciente de que:
>
>- A partir de 15 de junho de 2020, os locatários não terão a capacidade de criar novas políticas de Supervisão.
>- A partir de 31 de agosto de 2020, as políticas existentes deixarão de capturar novas mensagens.
>- A partir de 26 de outubro de 2020, as políticas existentes serão excluídas.
>
>Incentivamos ativamente os clientes que estão explorando ou usando a [](communication-compliance.md) Supervisão no Office 365 a usar a nova solução de conformidade de comunicação para atender aos requisitos regulatórios ou de monitoramento de comunicações com um conjunto muito mais rico de recursos inteligentes.

Use políticas de supervisão para capturar comunicações de funcionários para exame por revisores internos ou externos. Para obter mais informações sobre como as políticas de supervisão podem ajudá-lo a monitorar as comunicações em sua organização, consulte Políticas de [supervisão no Office 365.](supervision-policies.md)

>[!NOTE]
>Os usuários monitorados por políticas de supervisão devem ter uma licença de Conformidade do Microsoft 365 E5, uma licença do Office 365 Enterprise E3 com o complemento de Conformidade Avançada ou estar incluídos em uma assinatura do Office 365 Enterprise E5 ou estar incluídos em uma assinatura do Microsoft 365 E5.
>Se você não tiver um plano Enterprise E5 existente e quiser tentar a supervisão, inscreva-se para uma avaliação do [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)
  
Siga estas etapas para configurar e usar a supervisão em sua organização:
  
- **Etapa 1 (opcional)**: [Configurar grupos para supervisão](#step-1-set-up-groups-for-supervision-optional)

    Antes de começar a usar políticas de supervisão, determine quem precisa de comunicações revisadas e quem realiza as revisões. Se você quiser começar a usar apenas alguns usuários para ver como funciona a supervisão, ignore a configuração de grupos por enquanto.

- **Etapa 2 (obrigatório)**: [Disponibilizar a supervisão em sua organização](#step-2-make-supervision-available-in-your-organization-required)

    Adicione a si mesmo ao grupo de funções Revisão de Supervisão para que você possa configurar políticas. Qualquer pessoa que tenha essa função atribuída pode acessar a página **Supervisão** no Centro de Conformidade e & Segurança. Se o email revisível estiver hospedado no Exchange Online, cada revisador deverá ter acesso ao [PowerShell remoto ao Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- **Etapa 3 (opcional)**: criar tipos de informações confidenciais personalizados [e dicionários de palavras-chave personalizados](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Se você precisar de um tipo personalizado de informações confidenciais ou de um dicionário de palavras-chave personalizado para sua política de supervisão, será necessário criar antes de iniciar o assistente de supervisão.

- **Etapa 4 (obrigatório)**: Configurar [uma política de supervisão](#step-4-set-up-a-supervision-policy-required)

    Você cria políticas de supervisão no Centro de Conformidade & segurança. Essas políticas definem quais comunicações estão sujeitas à revisão em sua organização e especifica quem realiza avaliações. As comunicações incluem emails e comunicações do Microsoft Teams e comunicações de plataformas de terceiros (como Facebook, Twitter, etc.). As políticas de supervisão criadas nas organizações não têm suporte na supervisão de comunicação nas assinaturas do Microsoft 365.

- **Etapa 5 (opcional)**: testar [sua política de supervisão de comunicação](#step-5-test-your-supervision-policy-optional)

    Teste sua política de supervisão para garantir que ela funcione conforme desejado. É importante garantir que sua estratégia de conformidade está de acordo com seus padrões.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Etapa 1: Configurar grupos para supervisão (opcional)

 Ao criar uma política de supervisão, você define quem tem suas comunicações examinadas e quem realiza as revisões. Na política, você usará endereços de email para identificar indivíduos ou grupos de pessoas. Para simplificar a configuração, você pode criar grupos para pessoas que têm suas comunicações examinadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, você deseja monitorar as comunicações entre dois grupos distintos de pessoas ou se deseja especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos em sua organização para políticas de supervisão de comunicação:

| **Membro da Política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários não supervisionados | Grupos de distribuição <br> Grupos do Microsoft 365 | Grupos dinâmicos de distribuição |
| Revisores | Grupos de segurança habilitados para email  | Grupos de distribuição <br> Grupos dinâmicos de distribuição |
  
Quando você seleciona um grupo do Microsoft 365 para usuários supervisionados, a política monitora o conteúdo da caixa de correio compartilhada e os canais do Microsoft Teams associados ao grupo. Quando você seleciona uma lista de distribuição, a política monitora caixas de correio de usuários individuais.

Para gerenciar usuários supervisionados em grandes organizações corporativas, talvez seja necessário monitorar todos os usuários em grandes grupos. Você pode usar o PowerShell para configurar um grupo de distribuição para uma política de supervisão global para o grupo atribuído. Isso permite monitorar milhares de usuários com uma única política e manter a política de supervisão atualizada à medida que novos funcionários ingressarem em sua organização.

1. Crie um [grupo](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) de distribuição dedicado para sua política de supervisão global com as seguintes propriedades: certifique-se de que esse grupo de distribuição não seja usado para outros fins ou outros serviços do Office 365.

    - **MemberDepartRestriction = Closed**. Garante que os usuários não podem se remover do grupo de distribuição.
    - **MemberJoinRestriction = Fechado**. Garante que os usuários não podem adicionar a si mesmos ao grupo de distribuição.
    - **ModerationEnabled = True**. Garante que todas as mensagens enviadas a esse grupo estejam sujeitas à aprovação e que o grupo não está sendo usado para se comunicar fora da configuração da política de supervisão.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selecione um atributo personalizado do [Exchange nãousado](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) para rastrear usuários adicionados à política de supervisão em sua organização.

3. Execute o seguinte script do PowerShell em uma agenda recorrente para adicionar usuários à política de supervisão:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obter mais informações sobre como configurar grupos, consulte:

- [Criar e gerenciar grupos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gerenciar grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Visão geral dos grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Etapa 2: Disponibilizar a supervisão em sua organização (obrigatório)

Para **disponibilizar** a Supervisão como uma opção de menu no Centro de Conformidade e & Segurança, você deve ter a função Administrador de Revisão de Supervisão.
  
Para fazer isso, você pode adicionar a si mesmo como membro do grupo de funções Revisão de Supervisão ou pode criar um grupo de funções.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Adicionar membros ao grupo de função Revisão de Supervisão

1. Entre usando [https://protection.office.com](https://protection.office.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Conformidade & segurança, vá para **Permissões.**

3. Selecione o **grupo de funções Revisão** de Supervisão e clique no ícone Editar.

4. Na seção **Membros,** adicione as pessoas que você deseja gerenciar a supervisão de comunicação para sua organização.

### <a name="create-a-new-role-group"></a>Criar um novo grupo de funções

1. Entre usando [https://protection.office.com/permissions](https://protection.office.com/permissions) credenciais para uma conta de administrador em sua organização.

2. No Centro de Conformidade & segurança, vá para **Permissões** e clique em Adicionar ( **+** ).

3. Na seção **Funções,** clique em Adicionar ( **+** ) e role para baixo até Administrador de Revisão de **Supervisão.** Adicione esta função ao grupo de função.

4. Na seção **Membros,** adicione as pessoas que você deseja gerenciar a supervisão de comunicação para sua organização.

Para obter mais informações sobre grupos de função e permissões, consulte [Permissões no Centro de Conformidade.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar o acesso ao PowerShell remoto para revisadores (se o email estiver hospedado no Exchange Online)

1. Siga as orientações em [Habilitar ou desabilitar o acesso ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Etapa 3: Criar tipos de informações confidenciais personalizados e dicionários de palavras-chave personalizados (opcional)

Para escolher entre tipos de informações confidenciais personalizados existentes ou dicionários de palavras-chave personalizados no assistente de política de supervisão, você primeiro precisa criar esses itens, se necessário.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Criar dicionário/léxico de palavra-chave personalizado (opcional)

Use um editor de texto (como o Bloco de Notas) para criar um arquivo que inclua os termos de palavra-chave que você gostaria de monitorar em uma política de supervisão. Certifique-se de que cada termo está em uma linha separada e salve o arquivo no formato **Unicode/UTF-16 (Little Endian).**

### <a name="create-custom-sensitive-information-types"></a>Criar tipos personalizados de informações confidenciais

1. Crie um novo tipo de informação confidenciais e adicione seu dicionário personalizado no Centro de Conformidade & Segurança. Navegue **até Classificações Tipos** de informações confidenciais e siga as etapas no assistente novo tipo de informação \>  **confidenciais.** Aqui você vai:

    - Definir um nome e uma descrição para o tipo de informações confidenciais
    - Definir os elementos de proximidade, nível de confiança e padrão principal
    - Importar seu dicionário personalizado como um requisito para o elemento correspondente
    - Revise suas seleções e crie o tipo de informação sensível

    Para obter informações mais detalhadas, consulte [Criar um tipo personalizado de informação confidenciais](create-a-custom-sensitive-information-type.md) e criar um dicionário de [palavras-chave](create-a-keyword-dictionary.md)

    Depois que o dicionário/lexicon personalizado é criado, você pode exibir as palavras-chave configuradas com o cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) ou adicionar e remover termos usando o cmdlet [Set-DlpKeywordDictionary.](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary)

## <a name="step-4-set-up-a-supervision-policy-required"></a>Etapa 4: Configurar uma política de supervisão (obrigatório)
  
1. Entre usando [https://protection.office.com](https://protection.office.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Conformidade & segurança, selecione **Supervisão.**
  
3. Selecione **Criar** e siga o assistente para definir a configuração de política. Usando o assistente, você irá:

    - Dê um nome e uma descrição à política.
    - Escolha os usuários ou grupos para supervisionar, incluindo escolher usuários ou grupos que você gostaria de excluir.
    - Defina as condições da política de [supervisão.](supervision-policies.md#ConditionalSettings) Você pode escolher entre o endereço da mensagem, a palavra-chave, os tipos de arquivo e as condições de tamanho de acordo.
    - Escolha se você gostaria de incluir tipos de informações confidenciais. É aqui que você pode selecionar tipos de informações confidenciais padrão e personalizadas.
    - Escolha se você gostaria de habilitar o modelo de idioma ofensivo. Isso detecta linguagem inadequada enviada ou recebida no corpo das mensagens de email.
    - Defina a porcentagem de comunicações a analisar.
    - Escolha os revisadores da política. Os revisadores podem ser usuários individuais ou grupos [de segurança habilitados para email.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group) Todos os revisadores devem ter caixas de correio hospedadas no Exchange Online.
    - Revise suas seleções de política e crie a política.

## <a name="step-5-test-your-supervision-policy-optional"></a>Etapa 5: Testar sua política de supervisão (opcional)

Depois de criar uma política de supervisão de comunicação, é uma boa ideia testar para garantir que as condições definidas estão sendo impostas corretamente pela política. Você também pode querer testar suas políticas de prevenção contra perda de dados [(DLP)](create-test-tune-dlp-policy.md) se suas políticas de supervisão incluem tipos de informações confidenciais. Siga estas etapas para testar sua política de supervisão:

1. Abra um cliente de email ou o Microsoft Teams conectado como um usuário supervisionado definido na política que você deseja testar.
2. Envie um email ou um chat do Microsoft Teams que atenda aos critérios definidos na política de supervisão. Pode ser uma palavra-chave, tamanho do anexo, domínio etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito brandas.

    >[!NOTE]
    >Emails sujeitos a políticas definidas são processados quase em tempo real e podem ser testados imediatamente após a configuração da política. Os chats no Microsoft Teams podem levar até 24 horas para processar totalmente em uma política. 

3. Faça logoff no Microsoft 365 como um revisador designado na política de supervisão de comunicação. Navegue **até Supervisão** de Sua Política  >  *Personalizada*  >  **Aberta** para exibir o relatório da política.

