---
title: Simulador de Ataque no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o Simulador de Ataque para executar ataques simulados de phishing e senha em suas organizações do Microsoft 365 E5 ou Microsoft Defender for Office 365 Plano 2.
ms.openlocfilehash: a53ffee29ce928910b8c4add245c002ae6eb03da
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49788106"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulador de Ataque no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Se sua organização tiver o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o Simulador de Ataques no Centro de Conformidade e Segurança & para executar cenários de ataque realistas em sua organização. Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real a impacte seu resultado final. Leia este artigo para saber mais.

> [!NOTE]
> Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para os serviços do Microsoft 365. Para saber mais, confira [locais de dados do Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)

> [!TIP]
> O treinamento de simulação de ataque está disponível para visualização pública no centro de segurança do Microsoft 365. Confira [Simular um ataque de phishing com o Microsoft Defender para Office 365](attack-simulation-training.md) para saber mais.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com/>. Simulador de ataque está disponível no Simulador **de ataques de gerenciamento** de \> **ameaças.** Vá diretamente para o simulador de ataques, <https://protection.office.com/attacksimulator> abra.

- Para saber mais sobre a disponibilidade do Simulador de Ataque em diferentes assinaturas do Microsoft 365, confira a descrição do serviço do [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Você precisa ser membro dos grupos de função Gerenciamento da Organização **ou** **Administrador de** Segurança. Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

- Sua conta precisa ser configurada para autenticação multifatória (MFA) para criar e gerenciar campanhas no Simulador de Ataques. Para obter instruções, [consulte Configurar a autenticação multifa factor.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)

- As campanhas de phishing coletarão e processarão eventos por 30 dias. Os dados históricos da campanha estarão disponíveis por até 90 dias após o lançamento da campanha.

- Não há cmdlets do PowerShell correspondentes para o Simulador de Ataque.

## <a name="spear-phishing-campaigns"></a>Campanhas de phishing em banda

*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis. *O phishing* em busca de phishing é um ataque de phishing direcionado que usa conteúdo focado e personalizado especificamente adaptado aos destinatários de alvo (normalmente, após a ida e volta aos destinatários pelo invasor).

No Simulador de Ataques, dois tipos diferentes de campanhas de phishing de phishing estão disponíveis:

- **Phishing de nome (coleta de credenciais)**: o ataque tenta convencer os destinatários a clicar em uma URL na mensagem. Se eles clicarem no link, serão solicitados a inserir suas credenciais. Se o fizerem, eles serão levados para um dos seguintes locais:

  - Uma página padrão que explica que isso foi apenas um teste e fornece dicas para reconhecer mensagens de phishing.

    ![O que os usuários verão se clicarem no link de phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - Uma página personalizada (URL) que você especificar.

- **Phishing (anexo)**: o ataque tenta convencer os destinatários a abrir um anexo .docx ou .pdf na mensagem. O anexo contém o mesmo conteúdo do link de phishing padrão, mas a primeira frase começa com " \<Display Name\> , you are seeing this message as a recent email message you opened...".

> [!NOTE]
> Atualmente, as campanhas de phishing em um Simulador de Ataques não expiram.

### <a name="create-a-spear-phishing-campaign"></a>Criar uma campanha de phishing em forma de phishing

Uma parte importante de qualquer campanha de phishing de phishing é a aparência da mensagem de email que é enviada aos destinatários de alvo. Para criar e configurar a mensagem de email, você tem estas opções:

- **Use um modelo de email integrado:** dois modelos integrados estão disponíveis: **Giveaway e Payroll** **Update.** Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.

- **Crie um modelo de email** reutilizável: depois de criar e salvar o modelo de email, você poderá usá-lo novamente em futuras campanhas de phishing. Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.

- **Crie a mensagem de email no** assistente: você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de phishing.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Etapa 1 (opcional): criar um modelo de email personalizado

Se você for usar um dos modelos integrados ou criar a mensagem de email diretamente no assistente, ignore esta etapa.

1. No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** nas seções Phishing de Phishing de Phishing (Credenciais **de Coleta)** ou Phishing de **Phishing (Anexo),** clique em **Detalhes do Ataque.**

   Não importa onde você criar o modelo. As opções disponíveis no modelo são as mesmas para ambos os tipos de ataques de phishing.

3. Na página Detalhes **do** ataque que é aberta, na  seção Modelos de **Phishing,** na área Criar Modelos, clique em **Novo Modelo.**

4. O **assistente Configurar Modelo de Phishing** é iniciado em um novo flyout. Na etapa **Iniciar,** insira um nome de exibição exclusivo para o modelo e clique em **Próximo.**

5. Na etapa **Configurar detalhes de email,** de configure as seguintes configurações:

   - **De (Nome)**: o nome de exibição usado para o remetente da mensagem.

   - **De (Email)**: o endereço de email do remetente.

   - **URL do Servidor de Logon de Phishing:** clique no drop down e selecione uma das URLs disponíveis na lista. Esta é a URL em que os usuários serão tentados a clicar. As opções são:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras. Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.

   - **URL da Página de** Aterrissagem Personalizada: insira uma página inicial opcional onde os usuários serão levados se clicarem no link de phishing e inserirem suas credenciais. Esse link substitui a página de aterrissagem padrão. Por exemplo, se você tiver treinamento interno de reconhecimento, poderá especificar essa URL aqui.

   - **Categoria**: Atualmente, essa configuração não é usada (qualquer coisa que você inserir será ignorada).

   - **Assunto**: o **campo Assunto** da mensagem de email.

   Quando terminar, clique em **Avançar**.

6. Na etapa **Redigir email,** crie o corpo da mensagem de email. Você pode usar a **guia Email** (um editor de HTML rico) ou a guia **Fonte** (código HTML bruto).

   A formatação HTML pode ser tão simples ou complexa quanto você precisa. Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.

   - `${username}` insere o nome do destinatário.

   - `${loginserverurl}` insere o valor da URL do Servidor de Logon de **Phishing** da etapa anterior.

   Quando terminar, clique em **Avançar**.

7. Na etapa **Confirmar,** clique em **Concluir.**

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Etapa 2: criar e iniciar a campanha de phishing de phishing

1. No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:

   - Na seção **Phishing de Phishing (Coleta de Credenciais),** clique em **Iniciar** Ataque ou em **Ataque de Detalhes** de \> **Ataque.**

   - Na seção **Phishing de Phishing (Anexo),** clique em **Iniciar Ataque** ou em **Ataque de Detalhes** de \> **Ataque.**

3. O **assistente Configurar Ataque de Phishing** é iniciado em um novo flyout. Na etapa **Iniciar,** faça uma das seguintes etapas:

   - Na caixa **Nome,** insira um nome de exibição exclusivo para a campanha. Não clique em **Usar Modelo,** pois você criará a mensagem de email posteriormente no assistente.

   - Clique **em Usar** Modelo e selecione um modelo de email personalizado ou integrado. Depois de selecionar o modelo, a **caixa** Nome será preenchida automaticamente com base no modelo, mas você poderá alterar o nome.

   ![Página Inicial de Phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Quando terminar, clique em **Avançar**.

4. Na etapa **Destinatários de** destino, faça uma das seguintes etapas:

   - Clique **no Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha. Cada destinatário de alvo deve ter uma caixa de correio do Exchange Online. Se você clicar em **Filtrar** **e Aplicar** sem inserir critérios de pesquisa, todos os destinatários serão retornados e adicionados à campanha.

   - Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email. Cada linha deve conter o endereço de email do destinatário.

   Quando terminar, clique em **Avançar**.

5. Na etapa **Configurar detalhes de email,** de configure as seguintes configurações:

   Se você selecionou um modelo **na** etapa Iniciar, a maioria desses valores já está configurada, mas você pode alterá-los.

   - **De (Nome)**: o nome de exibição usado para o remetente da mensagem.

   - **De (Email)**: o endereço de email do remetente. Você pode inserir um endereço de email real ou falso do domínio de email da sua organização ou pode inserir um endereço de email externo real ou falso. Um endereço de email válido do remetente da sua organização será, na verdade, resolvido no cliente de email do destinatário.

   - **URL do Servidor de Logon de Phishing:** clique no drop down e selecione uma das URLs disponíveis na lista. Esta é a URL em que os usuários serão tentados a clicar. As opções são:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Todas as URLs são intencionalmente http, não https.
     >
     > - Um serviço de reputação de URL pode identificar uma ou mais dessas URLs como não seguras. Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.
     >
     > - Você precisa selecionar uma URL. Para **campanhas** de Phishing de Phishing (Anexo), você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um **link** e um anexo).

   - **Tipo de anexo:** essa configuração só está disponível em campanhas **de Phishing de Phishing (Anexo).** Clique no drop down e selecione **. DOCX** ou **. PDF** da lista.

   - **Nome do** anexo: essa configuração só está disponível em campanhas **de Phishing de Phishing (Anexo).** Insira um nome de arquivo para o anexo .docx ou .pdf.

   - **URL da Página de** Aterrissagem Personalizada: insira uma página inicial opcional onde os usuários serão levados se clicarem no link de phishing e inserirem suas credenciais. Esse link substitui a página de aterrissagem padrão. Por exemplo, se você tiver treinamento interno de reconhecimento, poderá especificar essa URL aqui.

   - **Assunto**: o **campo Assunto** da mensagem de email.

   Quando terminar, clique em **Avançar**.

6. Na etapa **Redigir email,** crie o corpo da mensagem de email. Se você selecionou um modelo **na** etapa Iniciar, o corpo da mensagem já está configurado, mas você pode personalizá-lo. Você pode usar a **guia Email** (um editor de HTML rico) ou a guia **Fonte** (código HTML bruto).

   A formatação HTML pode ser tão simples ou complexa quanto você precisa. Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.

   - `${username}` insere o nome do destinatário.

   - `${loginserverurl}`insere o valor da URL do Servidor de **Logon de Phishing.**

   Para campanhas de **Phishing** de Phishing (Anexo), você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um **link** e um anexo, e os cliques de link não serão rastreados em uma campanha de anexo).

   ![Corpo do email de composição](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Quando terminar, clique em **Avançar**.

7. Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha. A mensagem de phishing é entregue aos destinatários de alvo.

## <a name="password-attack-campaigns"></a>Campanhas de ataque de senha

Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente depois que o invasor identifica uma ou mais contas de usuário válidas.

No Simulador de Ataques, dois tipos diferentes de campanhas de ataque de senha estão disponíveis para você testar a complexidade das senhas dos usuários:

- Senha de força bruta (ataque  de  **dicionário)**: um ataque de força bruta ou de dicionário usa um arquivo de dicionário grande de senhas em uma conta de usuário com a expectativa de que uma delas funcione (muitas senhas em uma conta). Bloqueios de senha incorretos ajudam a impedir ataques de senha de força bruta.

  Para o ataque de dicionário, você pode especificar uma ou várias senhas a tentar (inseridas manualmente ou em um arquivo carregado) e pode especificar um ou vários usuários.

- **Ataque de pulverização de** senha: um ataque de *pulverização* de senha usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em várias contas). Ataques de pulverização de senha são mais difíceis de detectar do que ataques de senha de força bruta (a probabilidade de sucesso aumenta quando um invasor tenta uma senha em dezenas ou centenas de contas sem o risco de bloquear a senha incorreta do usuário).

  Para o ataque de pulverização de senha, você só pode especificar uma senha para tentar, e você pode especificar um ou vários usuários.

> [!NOTE]
> Os ataques de senha no Simulador de Ataque passam o nome de usuário e a senha Solicitações de autenticação básicas para um ponto de extremidade, para que também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.). Para os usuários que têm a MFA habilitada, mesmo que o ataque de senha tente sua senha real, a tentativa sempre se registrará como uma falha (em outras palavras, os usuários da MFA nunca aparecerão na contagem de tentativas bem-sucedidas da campanha).  Esse é o resultado esperado. A MFA é um método principal para ajudar a proteger contra ataques de senha.

### <a name="create-and-launch-a-password-attack-campaign"></a>Criar e iniciar uma campanha de ataque de senha

1. No Centro de Conformidade & segurança, vá para o simulador de ataques **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:

   - Na seção **Senha de Força Bruta (Ataque de** Dicionário), clique em **Iniciar** Ataque ou em Ataque **de Detalhes** \> **de Ataque.**

   - na seção **Ataque de pulverização de** senha, clique em Iniciar **Ataque** ou em Ataque **de Detalhes** \> **de Ataque.**

3. O **assistente Configurar Ataque de** Senha é iniciado em um novo flyout. Na etapa **Iniciar,** insira um nome de exibição exclusivo para a campanha e clique em **Próximo.**

4. Na etapa **Usuários de** destino, faça uma das seguintes etapas:

   - Clique **no Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha. Cada destinatário de alvo deve ter uma caixa de correio do Exchange Online. Se você clicar em **Filtrar** **e Aplicar** sem inserir critérios de pesquisa, todos os destinatários serão retornados e adicionados à campanha.

   - Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email. Cada linha deve conter o endereço de email do destinatário.

   Quando terminar, clique em **Avançar**.

5. Na etapa **Escolher configurações de ataque,** escolha o que fazer com base no tipo de campanha:

   - **Senha de Força Bruta (Ataque de Dicionário)**: faça uma das seguintes etapas:

     - **Insira senhas manualmente:** pressione Enter **para adicionar uma caixa** de senha, digite uma senha e pressione ENTER. Repita essa etapa quantas vezes forem necessárias.

     - **Carregar senhas de um** arquivo  de dicionário: clique em Carregar para importar um arquivo de texto existente que contenha uma senha em cada linha e uma última linha em branco. O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30.000 senhas.

   - **Ataque de pulverização** de senha: **nas senhas a usar na caixa de** ataque, insira uma senha.

   Quando terminar, clique em **Avançar**.

6. Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha. As senhas especificadas são tentadas nos usuários especificados.

## <a name="view-campaign-results"></a>Exibir resultados da campanha

Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal **simular ataques.**

As campanhas ativas mostrarão uma barra de status, um valor percentual concluído e a contagem "(usuários concluídos) de (usuários totais)". Clicar no botão **Atualizar** atualizará o progresso de quaisquer campanhas ativas. Você também pode clicar **em Encerrar** para interromper uma campanha ativa.

Quando a campanha é concluída, o status muda para **Ataque concluído.** Você pode exibir os resultados da campanha fazendo uma das seguintes ações:

- Na página principal **Simular ataques,** clique **em Exibir Relatório** com o nome da campanha.

- Na página principal **Simular ataques,** clique em **Detalhes** do Ataque na seção para o tipo de ataque. Na página **Detalhes do ataque** que é aberta, selecione a campanha na seção Histórico **de** Ataques.

Qualquer uma das ações anteriores levará você a uma página chamada **Detalhes do ataque.** As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultados da campanha de Phishing de Phishing (Coleta de Credenciais)

As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas: o número de usuários que clicaram no **link** e forneceram suas credenciais (qualquer valor *de* nome de usuário e senha).

- **Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**

- **Clique mais** rápido: quanto tempo o primeiro usuário levou para clicar no link depois de iniciar a campanha.

- **Clique médio**: a soma de quanto tempo todos demoraram para clicar no link dividido pelo número de usuários que clicaram no link.

- **Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.

- **Credenciais mais rápidas:** quanto tempo o primeiro usuário levou para inserir suas credenciais depois de iniciar a campanha.

- **Credenciais médias:** a soma do tempo que todos demoraram para inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.

- **Taxa de Sucesso da** Credencial: Uma porcentagem calculada por (número de usuários que ins inseridas em suas credenciais) / **Total de usuários direcionados.**

- Um gráfico de barras que mostra **o link clicado** e os **números fornecidos de credencial** por dia.

- Um gráfico em círculo que mostra **as porcentagens Link clicado**, **Credencial** fornecida e Nenhuma para a campanha. 

- A **seção Usuários** Comprometidos lista os detalhes dos usuários que clicaram no link:

  - O endereço de email do usuário

  - A data/hora em que eles clicaram no link.

  - O endereço IP do cliente.

  - Detalhes sobre a versão do usuário do Windows e do navegador da Web.

  Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Resultados da campanha de Phishing de Phishing (Anexo)

As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas: o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).

- **Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**

- **Tempo de abertura do anexo mais** rápido: quanto tempo o primeiro usuário levou para abrir o anexo depois que você iniciou a campanha.

- **Tempo médio de abertura do anexo:** a soma de quanto tempo todos demoraram para abrir o anexo dividido pelo número de usuários que abriram o anexo.

- **Taxa de sucesso de abertura de** anexos: Uma porcentagem calculada por (número de usuários que abriram o anexo) / Total de usuários **direcionados.**

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Resultados da campanha senha de força bruta (ataque de dicionário)

As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas: o número de usuários que foram encontrados usando uma das senhas especificadas.

- **Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**

- A **seção Usuários Comprometidos** lista os endereços de email dos usuários afetados. Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.

### <a name="password-spray-attack-campaign-results"></a>Resultados da campanha de ataque de pulverização de senha

As informações a seguir estão disponíveis na página **Detalhes do** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas: o número de usuários que foram encontrados usando a senha especificada.

- **Taxa de Sucesso Geral**: Uma porcentagem calculada pelas tentativas bem-sucedidas total de  /  **usuários direcionados.**
