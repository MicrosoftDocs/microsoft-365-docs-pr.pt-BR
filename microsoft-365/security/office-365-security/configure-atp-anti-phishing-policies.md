---
title: Configurar políticas anti-phishing no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing avançadas disponíveis em organizações com o Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2985766cf3388382dbe1d2217843504b2bfd1a1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906583"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas anti-phishing no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Políticas anti-phishing no [Microsoft Defender para Office 365](office-365-atp.md) podem ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros tipos de ataques de phishing. Para obter mais informações sobre as diferenças entre políticas anti-phishing no Exchange Online Protection (EOP) e políticas anti-phishing no Microsoft Defender para Office 365, consulte [Anti-phishing protection](anti-phishing-protection.md).

Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão. Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Você pode configurar políticas anti-phishing no Centro de Conformidade & segurança ou no PowerShell do Exchange Online.

Para obter informações sobre como configurar o mais limitado em políticas anti-phishing que estão disponíveis em organizações do Exchange Online Protection (ou seja, organizações sem o Microsoft Defender para Office 365), consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

Os elementos básicos de uma política anti-phishing são:

- **A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.
- **A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.

A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no Centro de Conformidade & Segurança:

- Ao criar uma política, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing. Todas as outras configurações modificam a política anti-phishing associada.
- Quando você remove uma política, a regra anti-phishing e a política anti-phishing associada são removidas.

No PowerShell do Exchange Online, você gerencia a política e a regra separadamente. Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online para configurar políticas [anti-phishing no Microsoft Defender para Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) mais adiante neste artigo.

Cada organização do Microsoft Defender para Office 365 tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:

- A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.
- A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.
- A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da proteção anti-phishing no Microsoft Defender para Office 365, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a **página anti-phishing atp,** use <https://protection.office.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:
  - Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.
  - Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O **grupo de função Gerenciamento de Organização** Somente Exibição no Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .
  - <sup>\*</sup> No Centro de Conformidade & segurança, o acesso somente leitura permite aos usuários exibir as configurações de políticas anti-phishing personalizadas. Os usuários somente leitura não podem ver as configurações na política anti-phishing padrão.

- Para nossas configurações recomendadas para políticas anti-phishing no Microsoft Defender para Office 365, consulte [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

- Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Use o Centro de Conformidade & segurança para criar políticas anti-phishing no Microsoft Defender para Office 365

A criação de uma política anti-phishing personalizada no Centro de Conformidade e Segurança cria a regra anti-phishing e a política anti-phish & ing associada ao mesmo tempo usando o mesmo nome para ambos.

Ao criar uma política anti-phishing, você só pode especificar o nome da política, a descrição e o filtro de destinatário que identifica a quem a política se aplica. Depois de criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.

2. Na página **Anti-phishing,** clique em **Criar**.

3. O **assistente Criar uma nova política anti-phishing** é aberto. Na página **Nomear sua política,** configure as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   Clique **em Adicionar uma condição**. No menu suspenso exibido, selecione uma condição em **Aplicado se**:

   - **O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é membro de**: Especifica um ou mais grupos em sua organização.
   - **O domínio do destinatário é**: Especifica destinatários em um ou mais dos domínios aceitos configurados na organização.

   Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**

   - Clique na caixa e role a lista de valores a ser selecionado.
   - Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.
   - Para adicionar valores adicionais, clique em uma área vazia na caixa.
   - Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.
   - Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.

   Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.

   Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

5. Na página **Revisar suas configurações** que aparece, revise suas configurações. Você pode clicar **em Editar** em cada configuração para modificá-la.

   Quando terminar, clique em **Criar essa política.**

6. Clique **em OK** na caixa de diálogo de confirmação exibida.

Depois de criar a política anti-phishing com essas configurações gerais, use as instruções na próxima seção para definir as configurações de proteção na política.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Use o Centro de Conformidade & segurança para modificar políticas anti-phishing no Microsoft Defender para Office 365

Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalificou.

1. Se você ainda não estiver lá, abra o Centro de  Conformidade & Segurança e vá para Política de Gerenciamento de Ameaças \>  \> **atp anti-phishing**.

2. Selecione a política anti-phishing personalizada que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O **sobrevoo \<name\>** Editar sua política é exibido. Clicar em **Editar** em qualquer seção oferece acesso às configurações nessa seção.

   - As etapas a seguir são apresentadas na ordem em que as seções aparecem, mas elas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).

   - Depois de  clicar em Editar em uma seção, as configurações disponíveis são apresentadas em um formato  de assistente, mas  você  pode pular dentro das páginas em qualquer ordem, e você pode clicar em Salvar em qualquer página (ou ![ ](../../media/scc-remove-icon.png) **\<name\>** Cancelar ou Fechar Ícone para retornar à página Editar sua política (não é necessário visitar a última página do assistente para salvar ou sair).

4. **Configuração de** política : Clique em **Editar** para modificar as mesmas configurações que estavam disponíveis quando você criou a [política](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) na seção anterior:

   - **Nome**
   - **Descrição**
   - **Aplicado a**
   - **Revisar suas configurações**

   Quando terminar, clique em **Salvar** em qualquer página.

5. **Representação**: clique em **Editar** para modificar os senders protegidos e os domínios protegidos na política. Essas configurações são uma condição para a política que identifica remetentes com spoofed a procurar (individualmente ou por domínio) no endereço From de mensagens de entrada. Para obter mais informações, consulte [Configurações de representação em políticas anti-phishing no Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Adicionar usuários para proteger**: O valor padrão é **Off**. Para acioná-lo, deslize a alternância para **Ativar** e clique no botão **Adicionar usuário** que aparece.

     No **flyout Adicionar usuário** exibido, configure os seguintes valores:

     - **Endereço de email**:

       - Clique na caixa e role a lista de usuários para selecionar.
       - Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.
       - Para remover uma entrada, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) usuário.

     - **Nome**: Esse valor é preenchido com base no endereço de email selecionado, mas você pode alterá-lo.

     Quando terminar, clique em **Salvar** em qualquer página.

     Para editar uma entrada existente, selecione o usuário protegido na lista.

     > [!NOTE]
     >
     > - Em cada política anti-phishing, você pode especificar um máximo de 60 usuários protegidos (endereços de email do remetente). Não é possível especificar o mesmo usuário protegido em várias políticas.
     >
     > - A proteção de representação do usuário não funcionará se o remetente e o destinatário se comunicarem anteriormente por email. Se o remetente e o destinatário nunca se comunicarem por email, a mensagem será identificada como uma tentativa de representação.

   - **Adicionar domínios para proteger**: Configurar uma ou ambas as configurações a seguir:

     - **Inclua automaticamente os domínios que eu tenho**: O valor padrão é **Off**. Para a ativar, deslize a alternância para **Ativar**.
     - **Incluir domínios personalizados**: O valor padrão é **Off**. Para acioná-lo, deslize a alternância para **Ativar** e, na caixa Adicionar **domínios,** insira o nome de domínio (por exemplo, contoso.com), pressione ENTER e repita conforme necessário.

     > [!NOTE]
     > Você pode ter no máximo 50 domínios em todas as políticas anti-phishing.

   - **Ações**: Clique em **Editar**

     - **Se o email** for enviado por um usuário personificado : Configure uma das seguintes ações para mensagens em que o remetente spoofed é um dos usuários protegidos especificados em **Adicionar** usuários para proteger :

       - **Não aplique nenhuma ação**
       - **Redirecionar mensagem para outros endereços de email**
       - **Mover mensagem para a pasta Lixo Eletrônico**
       - **Colocar em quarentena a mensagem**
       - **Entregar a mensagem e adicionar outros endereços à linha Cc**
       - **Excluir a mensagem antes de ser entregue**

     - **Se o email** for enviado por um domínio personificado : Configure uma das seguintes ações para mensagens em que o remetente despojado está em um dos domínios protegidos especificados em **Adicionar domínios** para proteger :

       - **Não aplique nenhuma ação**
       - **Redirecionar mensagem para outros endereços de email**
       - **Mover mensagem para a pasta Lixo Eletrônico**
       - **Colocar em quarentena a mensagem**
       - **Entregar a mensagem e adicionar outros endereços à linha Cc**
       - **Excluir a mensagem antes de ser entregue**

   - Clique **em Ativar dicas de segurança de** representação e configure qualquer uma das seguintes configurações:

     - **Mostrar dica para usuários personificados**: O valor padrão é **Off**. Para a ativar, deslize a alternância para **Ativar**.
     - **Mostrar dica para domínios personificados**: O valor padrão é **Off**. Para a ativar, deslize a alternância para **Ativar**.
     - **Mostrar dica para caracteres incomuns**: O valor padrão é **Off**. Para a ativar, deslize a alternância para **Ativar**.

     Quando concluir, clique em **Salvar**.

   - **Inteligência de caixa de correio**:

     - **Habilitar a inteligência de** caixa de correio? : O valor padrão é **Ativado**. Para desativar, deslize a alternância para **Off**.

     - **Habilitar a proteção de** representação baseada em inteligência de caixa de correio? : Essa configuração só estará disponível se **Habilitar** a inteligência de caixa de correio? está **ativado**.

       In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):

       - **Não aplique nenhuma ação**
       - **Redirecionar mensagem para outros endereços de email**
       - **Mover mensagem para a pasta Lixo Eletrônico**
       - **Colocar em quarentena a mensagem**
       - **Entregar a mensagem e adicionar outros endereços à linha Cc**
       - **Excluir a mensagem antes de ser entregue**

   - **Adicionar senders e domínios confiáveis**: Especifique exceções para a política:

     - **Senders confiáveis**:

       - Clique na caixa e role a lista de usuários para selecionar.
       - Clique na caixa e comece a digitar para filtrar a lista e selecionar um usuário.
       - Para remover uma entrada, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) usuário.

     - **Domínios confiáveis**: insira o nome de domínio (por exemplo, contoso.com), pressione ENTER e repita conforme necessário.

   - **Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar **em Editar** em cada seção para voltar à página relevante.
     - Você pode alternar as seguintes configurações **On** ou **Off** diretamente nesta página:

       - **Usuários protegidos**
       - **Domínios protegidos** \> **Incluir domínios que eu tenho**
       - **Domínios protegidos** \> **Domínios protegidos** (domínios personalizados)
       - **Inteligência da caixa de correio**

   Quando terminar, clique em **Salvar** em qualquer página.

6. **Spoof**:  clique em Editar para ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação do remetente não autenticado no Outlook e configurar a ação a ser aplicada a mensagens de remetentes espojados bloqueados. Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

   Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no EOP.

   - **Configurações de filtro de spoofing**: O valor padrão é **On**, e recomendamos que você o deixe em. Para desativar, deslize a alternância para **Off**. Para obter mais informações, [consulte Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Você não precisa desabilitar a proteção anti-spoofing se seu registro MX não apontar para o Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores. Para obter instruções, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Habilitar o recurso Remetente Não Autenticado**: O valor padrão é **Ativado**. Para desativar, deslize a alternância para **Off**.

   - **Ações**: Especifique a ação a ser tomada em mensagens que falham na inteligência de spoof:

     **Se o email for enviado por alguém que não tenha permissão para spoofar seu domínio**:

     - **Mover mensagem para as pastas lixo eletrônico dos destinatários**
     - **Colocar em quarentena a mensagem**

   - **Revise suas configurações**: em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar **em Editar** em cada seção para voltar à página relevante.
     - Você pode alternar as seguintes configurações **On** ou **Off** diretamente nesta página:
       - **Habilitar proteção antispoofing**
       - **Habilitar o recurso Remetente Não Autenticado**

   Quando terminar, clique em **Salvar** em qualquer página.

7. **Configurações avançadas:** clique **em Editar** para configurar os limites avançados de phishing. Para obter mais informações, consulte [Limites avançados de phishing em políticas anti-phishing no Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Limites avançados de phishing:** selecione um dos seguintes valores:

   - **1 - Standard** (Este é o valor padrão.)
   - **2 - Agressivo**
   - **3 - Mais agressivo**
   - **4 - Mais agressivo**

   - **Revise suas configurações**: Clique em **Editar** para voltar à **página Limites avançados de phishing.**

   Quando terminar, clique em **Salvar** em qualquer página.

8. Volte à página **Editar sua política, \<Name\>** revise suas configurações e clique em **Fechar**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Use o Centro de Conformidade & segurança para modificar a política anti-phishing padrão no Microsoft Defender para Office 365

A política anti-phishing padrão no Microsoft Defender para Office 365 se chama Office365 AntiPhish Default e não aparece na lista de políticas. Para modificar a política anti-phishing padrão, faça as seguintes etapas:

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.

2. Na página **Anti-phishing,** clique em **Política padrão**.

3. A **página Editar sua política Padrão do Office365 AntiPhish** é exibida. As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):

   - **Representação**
   - **Spoof**
   - **Configurações avançadas**

   As configurações a seguir não estão disponíveis quando você modifica a política padrão:

   - Você pode  ver a seção Configuração de Política e valores, mas não há nenhum link **Editar,** portanto, não é possível modificar as configurações (nome da política, descrição e a quem a política se aplica (ela se aplica a todos os destinatários)).
   - Não é possível excluir a política padrão.
   - Não é possível alterar a prioridade da política padrão (ela sempre é aplicada por último).

4. Na página **Editar sua política Padrão do Office365 AntiPhish,** revise suas configurações e clique em **Fechar**.

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Habilitar ou desabilitar políticas anti-phishing personalizadas no Microsoft Defender para Office 365

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.

2. Observe o valor na coluna **Status:**

   - Deslize a alternância **para Off** para desabilitar a política.

   - Deslize a alternância para **Ativado** para habilitar a política.

Não é possível desabilitar a política anti-phishing padrão.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Definir a prioridade de políticas anti-phishing personalizadas no Microsoft Defender para Office 365

Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem **o valor priority** 0). A política anti-phishing padrão chamada Office365 AntiPhish Default tem o valor de prioridade personalizado **Mais** baixo e você não pode alterá-la.

 **Observação**: no Centro de Conformidade & segurança, você só pode alterar a prioridade da política anti-phishing após a criação. No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de  uma política, clique em Aumentar prioridade ou Diminuir prioridade  nas propriedades da política (não é possível modificar diretamente o número de prioridade no Centro de Conformidade & Segurança).  Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.

2. Selecione a política que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O **sobrevoo \<name\>** Editar sua política é exibido.

   - A política anti-phishing personalizada com o **valor Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.

   - A política anti-phishing personalizada com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar** prioridade disponível.

   - Se você tiver três ou mais políticas anti-phishing personalizadas, as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.

4. Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Use o Centro de Conformidade & segurança para exibir políticas anti-phishing no Microsoft Defender para Office 365

1. No Centro de Conformidade & segurança e  vá para Política de Gerenciamento de Ameaças \>  \> **anti-phishing atp**.

2. Faça uma das seguintes etapas:

   - Selecione uma política anti-phishing personalizada que você deseja exibir. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

   - Clique **em Política padrão** para exibir a política anti-phishing padrão.

3. O **flyout \<name\> Editar sua** política é exibido, onde você pode exibir as configurações e os valores.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Use o Centro de Conformidade & segurança para remover políticas anti-phishing no Microsoft Defender para Office 365

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**.

2. Selecione a política que você deseja remover. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. No **sobrevoo \<name\> Editar sua política** que aparece, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.

Não é possível remover a política padrão.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usar o PowerShell do Exchange Online para configurar políticas anti-phishing no Microsoft Defender para Office 365

Conforme descrito anteriormente, uma política anti-spam consiste em uma política anti-phishing e uma regra anti-phish.

No PowerShell do Exchange Online, a diferença entre políticas anti-phishing e regras anti-phishing é aparente. Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**

- No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.
- Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar o PowerShell para criar políticas anti-phishing

Criar uma política anti-phishing no PowerShell é um processo de duas etapas:

1. Crie a política anti-phishing.
2. Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela. Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.

- Você pode configurar as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:

  - Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**
  - De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**

- Uma nova política anti-phishing que você cria no PowerShell não fica visível no Centro de Conformidade & Segurança até que você atribua a política a uma regra anti-phishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Etapa 1: Usar o PowerShell para criar uma política anti-phishing

Para criar uma política anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:

- A política está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).
- A descrição é: Política do departamento de pesquisa.
- Habilita a proteção de domínios da organização para todos os domínios aceitos e a proteção de domínios direcionados para fabrikam.com.
- Especifica Mai Fujito (mfujito@fabrikam.com) como o usuário a ser protegido contra representação.
- Habilita a inteligência de caixa de correio.
- Habilita a proteção de inteligência de caixa de correio e especifica a ação de quarentena.
- Habilita dicas de segurança.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra anti-phishing

Para criar uma regra anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:

- A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.
- A regra se aplica aos membros do grupo chamado Departamento de pesquisa.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usar o PowerShell para exibir políticas anti-phishing

Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar o PowerShell para exibir regras anti-phishing

Para exibir regras anti-phishing existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.

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

Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar o PowerShell para modificar políticas anti-phishing

Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria a política conforme descrito na Etapa [1: Usar o PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) para criar uma seção de política anti-phishing anteriormente neste artigo.

- A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.

- Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._ Quando você renomeia uma política anti-phish & ing no Centro de Conformidade e Segurança, você só renomeia a regra _anti-phishing._

Para modificar uma política anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar o PowerShell para modificar regras anti-phishing

A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.

Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra anti-phishing no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na Etapa 2: Use o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.

Para modificar uma regra anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras anti-phishing

Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída). Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar o PowerShell para definir a prioridade das regras anti-phishing

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

- Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**

- A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usar o PowerShell para remover políticas anti-phishing

Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.

Para remover uma política anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política anti-phishing chamada Departamento de Marketing.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usar o PowerShell para remover regras anti-phishing

Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.

Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito políticas anti-phishing no Microsoft Defender para Office 365, faça uma das seguintes etapas:

- No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **anti-phishing atp**. Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.** Para exibir mais detalhes, faça uma das seguintes etapas:

  - Selecione a política na lista e veja os detalhes no sobremenu.
  - Clique **em Política padrão** e veja os detalhes no sobremenu.

- No PowerShell do Exchange Online, substitua pelo nome da política ou regra e execute o seguinte comando e \<Name\> verifique as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```