---
title: Configurar políticas de supervisão
description: Configure as políticas de supervisão de comunicação no Office 365 para capturar comunicações de funcionários para verificação por revisores internos ou externos.
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
>Seguindo o lançamento da conformidade de comunicação no Microsoft 365 Compliance em fevereiro de 2020, a supervisão no Office 365 está sendo desativada. As políticas de supervisão não estarão mais disponíveis para a criação e as políticas eventualmente serão removidas, após um período estendido de acesso somente leitura.
>
>Se você usar a supervisão, lembre-se de que:
>
>- A partir de 15 de junho de 2020, os locatários não terão a capacidade de criar novas políticas de supervisão.
>- A partir de 31 de agosto de 2020, as políticas existentes deixarão de capturar novas mensagens.
>- A partir de outubro de 26th, 2020, as políticas existentes serão excluídas.
>
>Incentivamos ativamente os clientes que estão explorando ou usando a supervisão no Office 365 para usar a nova solução de [conformidade de comunicação](communication-compliance.md) para atender às suas necessidades de monitoramento de comunicações ou regulamentações com um conjunto muito mais avançado de recursos inteligentes.

Use políticas de supervisão para capturar comunicações de funcionários para verificação por revisores internos ou externos. Para obter mais informações sobre como as políticas de supervisão podem ajudá-lo a monitorar as comunicações em sua organização, consulte [políticas de supervisão no Office 365](supervision-policies.md).

>[!NOTE]
>Os usuários monitorados pelas políticas de supervisão devem ter uma licença de conformidade do Microsoft 365 e5, uma licença do Office 365 Enterprise E3 com o complemento de conformidade avançada ou ser incluída em uma assinatura do Office 365 Enterprise E5 ou ser incluída em uma assinatura do Microsoft 365 e5.
>Se você não tem um plano Enterprise E5 existente e deseja tentar a supervisão, você pode [se inscrever para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estas etapas para configurar e usar a supervisão em sua organização:
  
- **Etapa 1 (opcional)**: [configurar grupos de supervisão](#step-1-set-up-groups-for-supervision-optional)

    Antes de começar a usar as políticas de supervisão, determine quem precisa de comunicações revisadas e quem realiza as revisões. Se você quiser começar com apenas alguns usuários para ver como a supervisão funciona, você pode ignorar a configuração de grupos por enquanto.

- **Etapa 2 (obrigatório)**: [tornar a supervisão disponível em sua organização](#step-2-make-supervision-available-in-your-organization-required)

    Adicione a si mesmo ao grupo de função de análise de supervisão para que você possa configurar políticas. Qualquer pessoa que tenha essa função atribuída pode acessar a página de **supervisão** no centro de conformidade do & de segurança. Se o email reviewable estiver hospedado no Exchange Online, cada revisor deverá ter [acesso ao PowerShell remoto para o Exchange Online](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).

- **Etapa 3 (opcional)**: [criar tipos de informações confidenciais personalizadas e dicionários de palavras-chave personalizados](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Se você precisar de um tipo de informação confidencial personalizado ou de um dicionário de palavras-chave personalizado para sua política de supervisão, você precisará criá-lo antes de iniciar o assistente de supervisão.

- **Etapa 4 (obrigatório)**: [Configurar uma política de supervisão](#step-4-set-up-a-supervision-policy-required)

    Você cria políticas de supervisão no centro de conformidade e segurança &. Essas políticas definem quais comunicações estão sujeitas a análise em sua organização e especifica quem realiza as revisões. As comunicações incluem email e comunicações do Microsoft Teams e comunicações de plataforma de terceiros (como Facebook, Twitter, etc.). Políticas de supervisão criadas em organizações não são suportadas na supervisão de comunicação nas assinaturas do Microsoft 365.

- **Etapa 5 (opcional)**: [testar sua política de supervisão de comunicação](#step-5-test-your-supervision-policy-optional)

    Teste sua política de supervisão para garantir que ela funcione conforme desejado. É importante garantir que sua estratégia de conformidade esteja atendendo aos padrões.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Etapa 1: configurar grupos de supervisão (opcional)

 Ao criar uma política de supervisão, você define quem tem suas comunicações verificadas e quem realiza revisões. Na política, você usará endereços de email para identificar pessoas ou grupos de pessoas. Para simplificar a configuração, você pode criar grupos para pessoas que tenham suas comunicações verificadas e grupos de pessoas que revisam essas comunicações. Se você estiver usando grupos, poderá precisar de vários. Por exemplo, você deseja monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos na sua organização para políticas de supervisão de comunicação:

| **Membro de política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários não supervisionados | Grupos de distribuição <br> Grupos do Microsoft 365 | Grupos dinâmicos de distribuição |
| Revisores | Grupos de segurança habilitados para email  | Grupos de distribuição <br> Grupos dinâmicos de distribuição |
  
Quando você seleciona um grupo do Microsoft 365 para usuários supervisionados, a política monitora o conteúdo da caixa de correio compartilhada e dos canais do Microsoft Teams associados ao grupo. Quando você seleciona uma lista de distribuição, a política monitora caixas de correio de usuários individuais.

Para gerenciar usuários supervisionados em grandes organizações corporativas, talvez seja necessário monitorar todos os usuários em grupos grandes. Você pode usar o PowerShell para configurar um grupo de distribuição para uma política de supervisão global para o grupo atribuído. Isso permite monitorar milhares de usuários com uma única política e manter a política de supervisão atualizada à medida que novos funcionários ingressam em sua organização.

1. Crie um [grupo de distribuição](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) dedicado para sua política de supervisão global com as seguintes propriedades: Certifique-se de que esse grupo de distribuição não seja usado para outros fins ou outros serviços do Office 365.

    - **MemberDepartRestriction = Closed**. Garante que os usuários não possam se remover de um grupo de distribuição.
    - **MemberJoinRestriction = Closed**. Garante que os usuários não possam se adicionar ao grupo de distribuição.
    - **ModerationEnabled = true**. Garante que todas as mensagens enviadas a esse grupo estejam sujeitas à aprovação e que o grupo não esteja sendo usado para se comunicar fora da configuração da política de supervisão.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selecione um [atributo personalizado do Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) não usado para controlar os usuários adicionados à política de supervisão em sua organização.

3. Execute o seguinte script do PowerShell em um agendamento recorrente para adicionar usuários à política de supervisão:

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

Para obter mais informações sobre a configuração de grupos, consulte:

- [Criar e gerenciar grupos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gerenciar grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Visão geral dos grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Etapa 2: tornar a supervisão disponível em sua organização (obrigatório)

Para tornar a **supervisão** disponível como uma opção de menu no centro de conformidade e segurança &, você deve receber a função de administrador de análise de supervisão.
  
Para fazer isso, você pode adicionar a si mesmo como um membro do grupo de função de análise de supervisão ou pode criar um grupo de função.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Adicionar membros ao grupo de função de análise de supervisão

1. Entre [https://protection.office.com](https://protection.office.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de conformidade & segurança, acesse **permissões**.

3. Selecione o grupo de função de **análise de supervisão** e clique no ícone Editar.

4. Na seção **Membros** , adicione as pessoas que você deseja gerenciar a supervisão de comunicação para sua organização.

### <a name="create-a-new-role-group"></a>Criar um novo grupo de função

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de conformidade & segurança, vá para **permissões** e clique em Adicionar ( **+** ).

3. Na seção **funções** , clique em Adicionar ( **+** ) e role para baixo até **administrador de análise de supervisão**. Adicione esta função ao grupo de função.

4. Na seção **Membros** , adicione as pessoas que você deseja gerenciar a supervisão de comunicação para sua organização.

Para obter mais informações sobre grupos de funções e permissões, consulte [permissões no centro de conformidade](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar o acesso ao PowerShell remoto para revisores (se o email estiver hospedado no Exchange Online)

1. Siga as orientações em [habilitar ou desabilitar o acesso ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Etapa 3: criar tipos de informações confidenciais personalizados e dicionários de palavras-chave personalizados (opcional)

Para escolher entre os tipos de informações confidenciais personalizadas existentes ou os dicionários de palavras-chave personalizados no assistente de política de supervisão, primeiro você precisará criar esses itens, se necessário.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Criar dicionário de palavras-chave personalizado/léxico (opcional)

Use um editor de texto (como o bloco de notas) para criar um arquivo que inclui os termos de palavra-chave que você gostaria de monitorar em uma política de supervisão. Certifique-se de que cada termo está em uma linha separada e salve o arquivo no formato **Unicode/UTF-16 (little endian)** .

### <a name="create-custom-sensitive-information-types"></a>Criar tipos de informações confidenciais personalizados

1. Crie um novo tipo de informação confidencial e adicione seu dicionário personalizado no centro de conformidade & segurança. Navegue até **classificações** de \> **tipos de informações confidenciais** e siga as etapas no **Assistente novo tipo de informação confidencial**. Aqui você irá:

    - Definir um nome e uma descrição para o tipo de informações confidenciais
    - Definir os elementos de proximidade, nível de confiança e padrão primário
    - Importe seu dicionário personalizado como um requisito para o elemento correspondente
    - Revisar suas seleções e criar o tipo de informações confidenciais

    Para obter informações mais detalhadas, consulte [criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md) e [criar um dicionário de palavras-chave](create-a-keyword-dictionary.md)

    Depois que o dicionário personalizado/léxico é criado, você pode exibir as palavras-chave configuradas com o cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) ou adicionar e remover termos usando o cmdlet [set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary) .

## <a name="step-4-set-up-a-supervision-policy-required"></a>Etapa 4: configurar uma política de supervisão (obrigatório)
  
1. Entre [https://protection.office.com](https://protection.office.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de conformidade & segurança, selecione **supervisão**.
  
3. Selecione **criar** e siga o assistente para definir a configuração da política. Usando o assistente, você irá:

    - Forneça um nome e uma descrição para a política.
    - Escolha os usuários ou grupos para supervisionar, incluindo a escolha de usuários ou grupos que você gostaria de excluir.
    - Definir as [condições](supervision-policies.md#ConditionalSettings)da política de supervisão. Você pode escolher entre as condições endereço da mensagem, palavra-chave, tipos de arquivo e correspondência de tamanho.
    - Escolha se você deseja incluir tipos de informações confidenciais. É aí que você pode selecionar os tipos de informações confidenciais padrão e personalizadas.
    - Escolha se você deseja habilitar o modelo de linguagem ofensiva. Isso detecta o idioma inadequado enviado ou recebido no corpo de mensagens de email.
    - Defina a porcentagem de comunicação a ser revisada.
    - Escolha os revisores da política. Os revisores podem ser usuários individuais ou [grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos os revisores devem ter caixas de correio hospedadas no Exchange Online.
    - Revise suas seleções de política e crie a política.

## <a name="step-5-test-your-supervision-policy-optional"></a>Etapa 5: testar sua política de supervisão (opcional)

Depois de criar uma política de supervisão de comunicação, é uma boa ideia testar para garantir que as condições definidas estejam sendo aplicadas corretamente pela política. Você também pode querer [testar suas políticas de DLP (prevenção de perda de dados)](create-test-tune-dlp-policy.md) se suas políticas de supervisão incluírem tipos de informações confidenciais. Siga estas etapas para testar sua política de supervisão:

1. Abra um cliente de email ou o Microsoft Teams conectado como um usuário supervisionado definido na política que você deseja testar.
2. Envie um email ou chat do Microsoft Teams que atendam aos critérios definidos na política de supervisão. Pode ser uma palavra-chave, o tamanho do anexo, o domínio, etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito lenients.

    >[!NOTE]
    >Os emails sujeitos às políticas definidas são processados quase em tempo real e podem ser testados imediatamente após a configuração da política. Os chats no Microsoft Teams podem levar até 24 horas para processar totalmente em uma política. 

3. Faça logon no Microsoft 365 como um revisor designado na política de supervisão de comunicação. Navegue até a **supervisão**da  >  *política personalizada*  >  **aberta** para exibir o relatório da política.

