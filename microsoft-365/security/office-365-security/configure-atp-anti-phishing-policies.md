---
title: Configurar políticas anti-phishing ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis em organizações com a proteção avançada contra ameaças do Office 365 (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726771"
---
# <a name="configure-atp-anti-phishing-policies"></a>Configurar políticas anti-phishing ATP

As políticas de anti-phishing do ATP fazem parte da [proteção avançada contra ameaças do Office 365](office-365-atp.md). As políticas de anti-phishing do ATP podem ajudar a proteger sua organização contra ataques de phishing baseados em personificação mal-intencionada e outros tipos de ataques de phishing. Para obter mais informações sobre as diferenças entre políticas anti-phishing no Exchange Online Protection (EOP) e nas políticas de anti-phishing do ATP, consulte [proteção contra phishing](anti-phishing-protection.md).

Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão da ATP. Para obter uma granularidade maior, você também pode criar políticas anti-phishing personalizadas da ATP que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Você pode configurar as políticas de anti-phishing do ATP no centro de conformidade & segurança ou no PowerShell do Exchange Online.

Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações do Exchange Online Protection (ou seja, Microsoft 365, organizações sem o Office 365 ATP), consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Políticas de anti-phishing do ATP no centro de conformidade e segurança & vs PowerShell

Os elementos básicos de uma política anti-phishing do ATP são:

- **A política de anti-golpe**: especifica as proteções de phishing a serem habilitadas ou desabilitadas e as ações para aplicar as opções.

- **A regra anti-Phish**: especifica a prioridade e os filtros de destinatário (com quem a política se aplica) para uma política de anti-phishing.

A diferença entre esses dois elementos não é óbvia quando você gerencia as políticas de anti-phishing do ATP no centro de conformidade de & de segurança:

- Ao criar uma política de anti-phishing do ATP no centro de conformidade de & de segurança, você está realmente criando uma regra anti-phishing e a política de anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.

- Quando você modifica uma política de anti-phishing do ATP no centro de conformidade de & de segurança, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing. Todas as outras configurações modificam a política de anti-phishing associada.

- Quando você remove uma política anti-phishing do ATP do centro de conformidade & segurança, a regra anti-Phish e a política de anti-phishing associada são removidas.

No PowerShell do Exchange Online, a diferença entre políticas de anti-phishing e regras antiphish é aparente. Você gerencia as políticas de anti-phishing usando os cmdlets ** \* -AntiPhishPolicy** e gerencia regras de anti-phishing usando os cmdlets ** \* -AntiPhishRule** .

- No PowerShell, você cria a política de anti-phishing primeiro e, em seguida, cria a regra anti-Phish que identifica a política à qual a regra se aplica.

- No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-Phish separadamente.

- Quando você remove uma política de anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.

### <a name="default-atp-anti-phishing-policy"></a>Política anti-phishing padrão ATP

Todas as organizações ATP têm uma política antiphishing interna da ATP chamada de padrão do Office365 antiphish que tem estas propriedades:

- A política de anti-phishing chamada padrão do Office365 antiphish é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de Phish (filtros de destinatário) associada à política.

- A política chamada padrão do Office365 antiphish tem o valor de prioridade personalizado **mais baixo** que não pode ser modificado (a política é sempre aplicada por último). Qualquer política personalizada que você criar sempre terá uma prioridade maior do que a política denominada padrão do Office365 antiphishing.

- A política denominada padrão do Office365 antiphish é a política padrão (a propriedade **IsDefault** tem o valor `True` ) e não é possível excluir a política padrão.

Para aumentar a eficácia da proteção contra phishing, você pode criar políticas anti-phishing personalizadas da ATP com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **anti-phishing do ATP** , use <https://protection.office.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa receber permissões antes de executar os procedimentos deste tópico:

  - Para adicionar, modificar e excluir as políticas de anti-phishing do ATP, você precisa ser membro de um dos seguintes grupos de função:

    - **Gerenciamento da organização** ou **administrador de segurança** no centro de conformidade de & de [segurança](permissions-in-the-security-and-compliance-center.md).
    - Gerenciamento da **organização** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura às políticas anti-phishing da ATP, você precisa ser membro de um dos seguintes grupos de função:

    - **Leitor de segurança** no [centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organização somente para exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter as configurações recomendadas para políticas de anti-phishing da ATP, confira [configurações de política de anti-phishing do Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).

- Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.

- Para saber mais sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, confira [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Usar o centro de conformidade de & de segurança para criar políticas de anti-phishing da ATP

Criar uma política antivírus ATP personalizada no centro de conformidade de & de segurança cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.

Ao criar uma política anti-phishing do ATP, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica. Após criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Na página **anti-phishing** , clique em **criar**.

3. O assistente para **criar uma nova política** de anti-phishing é aberto. Na página **nomear sua política** , defina as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   Clique em **Adicionar uma condição**. Na lista suspensa exibida, selecione uma condição em **aplicado se**:

   - **O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é um membro de**: especifica um ou mais grupos na sua organização.
   - **O domínio do destinatário é**: especifica destinatários em um ou mais dos domínios aceitos configurados na organização.

   Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.

   - Clique na caixa e role pela lista de valores para selecionar.
   - Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.
   - Para adicionar valores adicionais, clique em uma área vazia na caixa.
   - Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.
   - Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.

   Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.

   Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

5. Na página **revise suas configurações** exibidas, revise suas configurações. Você pode clicar em **Editar** em cada configuração para modificá-la.

   Quando tiver concluído, clique em **criar esta política**.

6. Clique em **OK** na caixa de diálogo de confirmação que aparece.

Após criar a política anti-phishing do ATP com estas configurações gerais de política, use as instruções na próxima seção para definir as configurações de proteção na política.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Usar o centro de conformidade de & de segurança para modificar as políticas de anti-phishing da ATP

Use os procedimentos a seguir para modificar as políticas de anti-phishing do ATP: uma nova política que você criou ou políticas existentes que você já personalizou.

1. Se você ainda não estiver lá, abra o centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-phishing da ATP**.

2. Selecione a política de anti-phishing padrão ATP que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O submenu **Editar \<name\> sua política** é exibido. Clicar em **Editar** em qualquer seção fornece acesso às configurações dessa seção.

   - As etapas a seguir são apresentadas na ordem em que as seções são exibidas, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).

   - Depois de clicar em **Editar** em uma seção, as configurações disponíveis são apresentadas em um formato de assistente, mas você pode saltar dentro das páginas em qualquer ordem, e você pode clicar em **salvar** em qualquer página (ou **Cancelar** ou **fechar** ![ o ícone fechar ](../../media/scc-remove-icon.png) para retornar à página **editar sua política \<name\> ** (não é necessário visitar a última página do assistente para salvar ou sair).

4. **Configuração de política**: clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você [criou a política](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) na seção anterior:

   - **Nome**
   - **Descrição**
   - **Aplicado a**
   - **Revisar suas configurações**

   Quando tiver terminado, clique em **salvar** em qualquer página.

5. **Representação**: clique em **Editar** para modificar os remetentes protegidos e os domínios protegidos na política. Essas configurações são uma condição para a política que identifica remetentes falsificados a serem procurados (individualmente ou por domínio) no endereço de das mensagens de entrada. Para obter mais informações, consulte [configurações de representação em políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).

   - **Adicionar usuários para proteger**: o valor padrão é **desativado**. Para ativá-la, deslize o botão de alternância para **ativado**e, em seguida, clique no botão **Adicionar usuário** que aparece.

     No submenu **Adicionar usuário** exibido, configure os seguintes valores:

     - **Endereço de email**:

        - Clique na caixa e role pela lista de usuários para selecionar.
        - Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.
        - Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.

     - **Nome**: esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.

     Quando tiver terminado, clique em **salvar** em qualquer página.

    Para editar uma entrada existente, selecione o usuário protegido na lista.

   - **Adicionar domínios para proteger**: Configure uma ou ambas as configurações a seguir:

     - **Incluir automaticamente os domínios que**possuo: o valor padrão é **desativado**. Para ativá-la, deslize o botão para **Ativar.**
     - **Incluir domínios personalizados**: o valor padrão é **desativado**. Para ativá-la, deslize o **botão para ativar e,** na caixa **adicionar domínios** , digite o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.

   - **Ações**: clique em **Editar**

     - **Se o email for enviado por um usuário representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado é um dos usuários protegidos que você especificou em **Adicionar usuários para proteger**:

       - **Não aplicar nenhuma ação**
       - **Redirecionar mensagem para outros endereços de email**
       - **Mover mensagem para a pasta Lixo Eletrônico**
       - **Colocar a mensagem em quarentena**
       - **Entregar a mensagem e adicionar outros endereços à linha Cco**
       - **Excluir a mensagem antes de ser entregue**

     - **Se o email for enviado por um domínio representado**: Configure uma das ações a seguir para mensagens em que o remetente falsificado está em um dos domínios protegidos que você especificou em **adicionar domínios para proteger**:

     - **Não aplicar nenhuma ação**
     - **Redirecionar mensagem para outros endereços de email**
     - **Mover mensagem para a pasta Lixo Eletrônico**
     - **Colocar a mensagem em quarentena**
     - **Entregar a mensagem e adicionar outros endereços à linha Cco**
     - **Excluir a mensagem antes de ser entregue**

   - Clique em **Ativar dicas de segurança de representação** e configure qualquer uma das seguintes configurações:

     - **Mostrar dica para usuários representados**: o valor padrão é **desativado**. Para ativá-la, deslize o botão para **Ativar.**
     - **Mostrar dica para domínios representados**: o valor padrão é **desativado**. Para ativá-la, deslize o botão para **Ativar.**
     - **Mostrar dica para caracteres incomuns**: o valor padrão está **desativado**. Para ativá-la, deslize o botão para **Ativar.**

     Quando concluir, clique em **Salvar**.

   - **Inteligência de caixa de correio**:

     - **Habilitar o Mailbox Intelligence?**: o valor padrão é **ativado**. Para desativá-la, deslize o botão de alternância para **desativado**.

     - **Habilitar proteção de representação baseada em inteligência de caixa de correio?**: essa configuração só estará disponível se **habilitar inteligência de caixa de correio?** estiver **ativado**.

       Em **se o email for enviado por um usuário representado**, você poderá especificar uma das ações a seguir para executar as mensagens que falham na inteligência de caixa de correio (as mesmas ações que estão disponíveis para usuários protegidos e domínios protegidos):

       - **Não aplicar nenhuma ação**
       - **Redirecionar mensagem para outros endereços de email**
       - **Mover mensagem para a pasta Lixo Eletrônico**
       - **Colocar a mensagem em quarentena**
       - **Entregar a mensagem e adicionar outros endereços à linha Cco**
       - **Excluir a mensagem antes de ser entregue**

   - **Adicionar remetentes e domínios confiáveis**: especifique exceções para a política:

     - **Remetentes confiáveis**:

       - Clique na caixa e role pela lista de usuários para selecionar.
       - Clique na caixa e comece a digitar para filtrar a lista e selecione um usuário.
       - Para remover uma entrada, clique em **remover** ![ ícone ](../../media/scc-remove-icon.png) de remoção no usuário.

     - **Domínios confiáveis**: Insira o nome do domínio (por exemplo, contoso.com), pressione Enter e repita conforme necessário.

   - **Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.
     - Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:

       - **Usuários protegidos**
       - **Domínios protegidos** \> **Incluir domínios que sou proprietário**
       - **Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)
       - **Inteligência da caixa de correio**

   Quando tiver terminado, clique em **salvar** em qualquer página.

6. **Spoof**: clique em **Editar** para ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação a ser aplicada às mensagens de remetentes falsificados bloqueados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

   Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.

   - **Falsificação de configurações de filtro**: o valor padrão é **ativado**e recomendamos que você o deixe ligado. Para desativá-la, deslize o botão de alternância para **desativado**. Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Você não precisa desabilitar a proteção contra falsificação se o registro MX não apontar para o Microsoft 365; em vez disso, habilite a filtragem avançada de conectores. Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar o recurso de remetente não autenticado**: o valor padrão é **ativado**. Para desativá-la, deslize o botão de alternância para **desativado**.

   - **Ações**: Especifique a ação a ser executada em mensagens que falham na inteligência de spoof:

     **Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio**:

     - **Mover mensagem para pastas de lixo eletrônico dos destinatários**
     - **Colocar a mensagem em quarentena**

   - **Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar em **Editar** em cada seção para saltar de volta para a página relevante.
     - Você pode ativar ou **desativar** as **seguintes** configurações diretamente nesta página:

       - **Habilitar proteção contra falsificação**
       - **Habilitar o recurso de remetente não autenticado**

   Quando tiver terminado, clique em **salvar** em qualquer página.

7. **Configurações avançadas**: clique em **Editar** para configurar os limites avançados de phishing. Para obter mais informações, consulte [limites de phishing avançados nas políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Limites de phishing avançados**: selecione um dos seguintes valores:

   - **1-padrão** (este é o valor padrão).
   - **2-agressivo**
   - **3-mais agressivo**
   - **4-mais agressivo**

   - **Revise suas configurações**: clique em **Editar** para voltar para a página de **limiares de phishing avançados** .

   Quando tiver terminado, clique em **salvar** em qualquer uma das páginas.

8. Novamente na página **editar sua política \<Name\> ** , revise suas configurações e clique em **Fechar**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Usar o centro de conformidade de & de segurança para modificar a política de anti-phishing padrão ATP

A política anti-phishing padrão ATP é chamada de padrão do Office365 antiphish, e não aparece na lista de políticas. Para modificar a política anti-phishing padrão da ATP, siga estas etapas:

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Na página **anti-phishing** , clique em **política padrão**.

3. A página **editar sua política padrão do Office365 antiphishing** é exibida. As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):

   - **Representação**
   - **Simulação**
   - **Configurações avançadas**

   As configurações a seguir não estão disponíveis quando você modifica a política padrão:

   - Você pode ver a seção e os valores da **configuração de política** , mas não há nenhum link de **edição** , portanto, não é possível modificar as configurações (nome da diretiva, descrição e a qual a política se aplica (ela se aplica a todos os destinatários).
   - Não é possível excluir a política padrão.
   - Você não pode alterar a prioridade da política padrão (ela é sempre aplicada por último).

4. Na página **editar sua política padrão do Office365 antiphishing** , revise suas configurações e clique em **fechar**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Habilitar ou desabilitar políticas antivírus ATP personalizadas

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Observe o valor na coluna **status** :

   - Deslize o botão de **alternância para desativar** a política.

   - Deslize o botão de **alternância para ativar** a política.

Não é possível desabilitar a política anti-phishing padrão.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>Definir a prioridade de políticas anti-phishing padrão da ATP

Por padrão, as políticas anti-phishing do ATP recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade.

As políticas anti-phishing padrão ATP são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0). A política anti-phishing padrão chamada do Office365 antiphish padrão tem o valor de prioridade personalizado **mais baixo**e não pode ser alterada.

 **Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política anti-phishing do ATP após criá-la. No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-Phish (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, clique em **aumentar** a prioridade ou **diminuir a prioridade** nas propriedades da política (não é possível modificar diretamente o número de **prioridade** no centro de conformidade do & de segurança). Alterar a prioridade de uma política faz sentido se você tiver várias políticas.

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Selecione a política que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O submenu **Editar \<name\> sua política** é exibido.

   - A política de anti-phishing padrão ATP com o valor **Priority** de prioridade **0** tem apenas o botão **diminuir prioridade** disponível.

   - A política de anti-phishing padrão ATP com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.

   - Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.

4. Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Usar o centro de conformidade de & de segurança para exibir as políticas de anti-phishing da ATP

1. No centro de conformidade & segurança e vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Execute uma das seguintes etapas:

   - Selecione uma política antivírus ATP personalizada que você deseja exibir. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

   - Clique em **política padrão** para exibir a política anti-phishing padrão.

3. O submenu **Editar \<name\> sua política** aparece, onde você pode exibir as configurações e os valores.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Usar o centro de conformidade de & de segurança para remover as políticas de anti-phishing da ATP

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**.

2. Selecione a política que você deseja remover. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. No submenu **editar sua \<name\> política** exibido, clique em **excluir política**e, em seguida, clique em **Sim** na caixa de diálogo de aviso que aparece.

Não é possível remover a política padrão.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Usar o PowerShell do Exchange Online para configurar as políticas de anti-phishing da ATP

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar o PowerShell para criar políticas anti-phishing

A criação de uma política anti-phishing no PowerShell é um processo de duas etapas:

1. Criar a política de anti-phishing.

2. Crie a regra anti-Phish que especifica a política de anti-phishing à qual a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e não associada a ela. Uma regra anti-Phish não pode ser associada a mais de uma política de phishing.

- Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:

  - Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-AntiPhishRule** ).

  - Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule** ).

- Uma nova política de Phish que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra anti-phishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Etapa 1: usar o PowerShell para criar uma política de anti-phishing

Para criar uma política de anti-golpe, use esta sintaxe:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Este exemplo cria uma política de anti-phishing chamada quarentena de pesquisa com as seguintes configurações:

- A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).
- A descrição é: política de departamento de pesquisa.
- Habilita a proteção de domínios de organização para todos os domínios aceitos e proteção de domínios direcionados para o fabrikam.com.
- Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário para proteger da representação.
- Habilita a inteligência de caixa de correio.
- Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.
- Permite dicas de segurança.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Etapa 2: usar o PowerShell para criar uma regra anti-phishing

Para criar uma regra anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma regra anti-phishing chamada departamento de pesquisa com as seguintes condições:

- A regra é associada à política de anti-phishing chamada quarentena de pesquisa.
- A regra se aplica aos membros do grupo chamado Departamento de pesquisa.
- Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usar o PowerShell para exibir políticas antispam

Para exibir as políticas antispam existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de anti-phishing junto com as propriedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

Este exemplo retorna todos os valores de propriedade da política anti-Phish chamada executivos.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar o PowerShell para exibir regras de anti-golpe

Para exibir regras anti-phishing existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as regras de anti-phishing junto com as propriedades especificadas.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

Este exemplo retorna todos os valores de propriedade da regra anti-Phish chamada executivos da contoso.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar o PowerShell para modificar políticas antispam

Além dos seguintes itens, as mesmas configurações estão disponíveis quando você modifica uma política de anti-phishing no PowerShell como quando você cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anti-golpe](#step-1-use-powershell-to-create-an-anti-phish-policy) , anteriormente neste tópico.

- A opção _MakeDefault_ que transforma a política especificada na política padrão (aplicada a todos, sempre a prioridade **mais baixa** e não é possível excluí-la) só está disponível quando você modifica uma política de Phish no PowerShell.

- Não é possível renomear uma política anti-phishing (o cmdlet **set-AntiPhishPolicy** não tem nenhum parâmetro _Name_ ). Ao renomear uma política anti-phishing no centro de conformidade & segurança, você estará apenas renomeando a _regra_anti-phishing.

Para modificar uma política de anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar o PowerShell para modificar as regras de anti-golpe

A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite que você crie uma regra desabilitada. Para habilitar ou desabilitar regras antispam existentes, confira a próxima seção.

Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) , anteriormente neste tópico.

Para modificar uma regra anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de Phish

Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política de anti-phishing atribuídas). Você não pode habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra anti-Phish chamada departamento de marketing.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar o PowerShell para definir a prioridade de regras de Phish

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Observações**:

- Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule** .

- A política de anti-phishing padrão não tem uma regra antiphishing correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usar o PowerShell para remover políticas antispam

Quando você usa o PowerShell para remover uma política de Phish, a regra anti-Phish correspondente não é removida.

Para remover uma política de anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de anti-golpe chamada departamento de marketing.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usar o PowerShell para remover regras de Phish

Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-Phish correspondente não é removida.

Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

Este exemplo remove a regra anti-Phish chamada departamento de marketing.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito as políticas de anti-phishing do ATP, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de anti-phishing do \> **Policy** \> **ATP**. Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** . Para exibir mais detalhes, execute uma das seguintes etapas:

  - Selecione a política na lista e exiba os detalhes no submenu.
  - Clique em **política padrão** e visualize os detalhes no submenu.

- No PowerShell do Exchange Online, substitua \<Name\> o nome da política ou regra e execute o seguinte comando e verifique as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
