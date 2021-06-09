---
title: Simulador de Ataque no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o Simulador de Ataques para executar ataques simulados de phishing e senha em suas Microsoft 365 E5 ou no Microsoft Defender para organizações do Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73ad3501ed9818261c9fbec6ba12b4dc884da84f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624820"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulador de Ataque no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)

Se sua organização tiver o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o Simulador de Ataque no Centro de Conformidade & Segurança para executar cenários de ataque realistas em sua organização. Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real impacte sua linha inferior. Leia este artigo para saber mais.

> [!NOTE]
>
> O Simulador de Ataque, conforme descrito neste artigo,  agora é somente leitura e foi substituído pelo treinamento de simulação de ataque no nó de colaboração **Email &** no centro de segurança [do Microsoft 365.](https://security.microsoft.com) Para obter mais informações, consulte [Começar a usar o treinamento de simulação de ataque](attack-simulation-training-get-started.md).
>
> A capacidade de iniciar novas simulações dessa versão do Simulador de Ataque foi desabilitada. No entanto, você ainda pode acessar relatórios por até 90 dias a partir de 24 de janeiro de 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com/>. Simulador de ataque está disponível no simulador **de ataques de gerenciamento** de \> **ameaças.** Para ir diretamente ao simulador de ataque, abra <https://protection.office.com/attacksimulator> .

- Para obter mais informações sobre a disponibilidade do Simulador de Ataque em diferentes Microsoft 365 assinaturas, consulte Microsoft Defender para obter Office 365 [descrição do serviço](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Você precisa ser membro dos grupos de função Gerenciamento da **Organização** ou **Administrador de** Segurança. Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

- Sua conta precisa ser configurada para a autenticação multifato (MFA) para criar e gerenciar campanhas no Simulador de Ataques. Para obter instruções, consulte [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- O Simulador de Ataque só funciona em caixas de correio baseadas em nuvem.

- As campanhas de phishing coletarão e processarão eventos por 30 dias. Os dados históricos da campanha estarão disponíveis por até 90 dias após o início da campanha.

- Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para Microsoft 365 serviços. Para obter mais informações, [consulte Microsoft 365 data locations](../../enterprise/o365-data-locations.md).

- Não há cmdlets do PowerShell correspondentes para Simulador de Ataque.

## <a name="spear-phishing-campaigns"></a>Campanhas de phishing de lança

*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis. *Phishing de* lança é um ataque de phishing direcionado que usa conteúdo focado e personalizado especificamente personalizado para os destinatários direcionados (normalmente, após o reconhecimento nos destinatários pelo invasor).

No Simulador de Ataques, dois tipos diferentes de campanhas de phishing de lança estão disponíveis:

- **Phishing de lança (coleta de credenciais)**: o ataque tenta convencer os destinatários a clicar em uma URL na mensagem. Se eles clicarem no link, serão solicitados a inserir suas credenciais. Se fizerem isso, serão levados para um dos seguintes locais:

  - Uma página padrão que explica que isso foi apenas um teste e fornece dicas para reconhecer mensagens de phishing.

    ![O que os usuários verão se clicarem no link de phishing e inserirem suas credenciais](../../media/attack-simulator-phishing-result.png)

  - Uma página personalizada (URL) que você especificar.

- **Phishing de lança (anexo)**: O ataque tenta convencer os destinatários a abrir um .docx ou .pdf anexo na mensagem. O anexo contém o mesmo conteúdo do link padrão de phishing, mas a primeira frase começa com " , você está vendo essa mensagem como uma mensagem de email recente que você \<Display Name\> abriu...".

> [!NOTE]
> Atualmente, as campanhas de phishing de lança no Simulador de Ataques não expiram.

### <a name="create-a-spear-phishing-campaign"></a>Criar uma campanha de phishing de lança

Uma parte importante de qualquer campanha de phishing de lança é a aparência da mensagem de email enviada aos destinatários direcionados. Para criar e configurar a mensagem de email, você tem estas opções:

- **Use um modelo de email integrado:** Dois modelos integrados estão disponíveis: **Oferta de** Prêmio e **Atualização de Folha de Pagamento.** Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.

- **Criar um modelo de email** reutilizável : depois de criar e salvar o modelo de email, você pode usá-lo novamente em campanhas futuras de phishing de lança. Você pode personalizar ainda mais algumas, todas ou nenhuma das propriedades de email do modelo ao criar e iniciar a campanha.

- **Crie a mensagem de email no assistente**: Você pode criar a mensagem de email diretamente no assistente ao criar e iniciar a campanha de phishing de lança.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Etapa 1 (Opcional): Criar um modelo de email personalizado

Se você vai usar um dos modelos integrados ou criar a mensagem de email diretamente no assistente, ignore esta etapa.

1. No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** nas seções Phishing de Lança (Coleta de **Credenciais)** ou **Phishing** de Lança (Anexo), clique em **Detalhes de Ataque**.

   Não importa onde você cria o modelo. As opções disponíveis no modelo são as mesmas para ambos os tipos de ataques de phishing.

3. Na página **Detalhes de** ataque que é aberta, na seção Modelos **de Phishing,** na área **Criar Modelos,** clique em **Novo Modelo**.

4. O **assistente Configurar Modelo de Phishing** começa em um novo flyout. Na etapa **Iniciar,** insira um nome de exibição exclusivo para o modelo e clique em **Próximo**.

5. Na etapa **Configurar detalhes de email,** configure as seguintes configurações:

   - **De (Nome)**: o nome de exibição usado para o remetente da mensagem.

   - **De (Email)**: o endereço de email do remetente.

   - **URL do Servidor de Logon de Phishing**: clique no drop-down e selecione uma das URLs disponíveis na lista. Esta é a URL em que os usuários serão tentados a clicar. As opções são:

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
     > Um serviço de reputação de URL pode identificar uma ou mais DESSAS URLs como não seguras. Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.

   - **URL da Página inicial personalizada**: insira uma página de aterrissagem opcional onde os usuários são levados se clicarem no link de phishing e inserirem suas credenciais. Este link substitui a página de aterrissagem padrão. Por exemplo, se você tiver treinamento de reconhecimento interno, poderá especificar essa URL aqui.

   - **Categoria**: Atualmente, essa configuração não é usada (tudo o que você inserir é ignorado).

   - **Assunto**: O **campo Assunto** da mensagem de email.

   Ao terminar, clique em **Avançar**.

6. Na etapa **Escrever email,** crie o corpo da mensagem da mensagem de email. Você pode usar a guia **Email** (um editor HTML rico) ou a guia **Origem** (código HTML bruto).

   A formatação HTML pode ser tão simples ou complexa quanto você precisa. Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.

   - `${username}` insere o nome do destinatário.

   - `${loginserverurl}` insere o valor de URL do Servidor de **Logon de Phishing** da etapa anterior.

   Ao terminar, clique em **Avançar**.

7. Na etapa **Confirmar,** clique em **Concluir**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Etapa 2: Criar e iniciar a campanha de phishing de lança

1. No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:

   - Na seção **Phishing de Lança (Coleta de Credenciais),** clique em **Iniciar Ataque** ou clique em **Ataque de Detalhes de** \> **Ataque.**

   - Na seção **Phishing de Lança (Anexo),** clique em **Iniciar Ataque** ou clique em **Ataque de Início de Detalhes de** \> **Ataque**.

3. O **assistente Configurar Ataques de Phishing** começa em um novo flyout. Na etapa **Iniciar,** faça uma das seguintes etapas:

   - Na caixa **Nome,** insira um nome de exibição exclusivo para a campanha. Não clique em **Usar Modelo**, pois você criará a mensagem de email posteriormente no assistente.

   - Clique **em Usar Modelo** e selecione um modelo de email integrado ou personalizado. Depois de selecionar o modelo, a caixa **Nome** é preenchida automaticamente com base no modelo, mas você pode alterar o nome.

   > [!div class="mx-imgBorder"]
   > ![Página inicial de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Ao terminar, clique em **Avançar**.

4. Na etapa **Destinatários de** destino, faça uma das seguintes etapas:

   - Clique **em Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha. Cada destinatário direcionado deve ter uma caixa Exchange Online caixa de correio. Se você clicar **em Filtrar** **e Aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.

   - Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email. Cada linha deve conter o endereço de email do destinatário.

   Ao terminar, clique em **Avançar**.

5. Na etapa **Configurar detalhes de email,** configure as seguintes configurações:

   Se você selecionou um modelo **na** etapa Iniciar, a maioria desses valores já está configurada, mas você pode alterá-los.

   - **De (Nome)**: o nome de exibição usado para o remetente da mensagem.

   - **De (Email)**: o endereço de email do remetente. Você pode inserir um endereço de email real ou falso do domínio de email da sua organização ou inserir um endereço de email externo real ou falso. Um endereço de email de remetente válido da sua organização será resolvido no cliente de email do destinatário.

   - **URL do Servidor de Logon de Phishing**: clique no drop-down e selecione uma das URLs disponíveis na lista. Esta é a URL em que os usuários serão tentados a clicar. As opções são:

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
     > - Um serviço de reputação de URL pode identificar uma ou mais DESSAS URLs como não seguras. Verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.
     >
     > - Você deve selecionar uma URL. Para **campanhas de Phishing** de Lança (Anexo), você pode remover o link do corpo da mensagem na próxima etapa (caso contrário, a mensagem conterá um **link** e um anexo).

   - **Tipo de** anexo : essa configuração só está disponível em campanhas **de Phishing de Lança (Anexo).** Clique na lista lista e selecione **.DOCX** ou **.PDF** na lista.

   - **Nome do** anexo : essa configuração só está disponível em campanhas de Phishing de Lança **(Anexo).** Insira um nome de arquivo para o .docx ou .pdf anexo.

   - **URL da Página inicial personalizada**: insira uma página de aterrissagem opcional onde os usuários são levados se clicarem no link de phishing e inserirem suas credenciais. Este link substitui a página de aterrissagem padrão. Por exemplo, se você tiver treinamento de reconhecimento interno, poderá especificar essa URL aqui.

   - **Assunto**: O **campo Assunto** da mensagem de email.

   Ao terminar, clique em **Avançar**.

6. Na etapa **Escrever email,** crie o corpo da mensagem da mensagem de email. Se você selecionou um modelo na etapa **Iniciar,** o corpo da mensagem já está configurado, mas você pode personalizá-lo. Você pode usar a guia **Email** (um editor HTML rico) ou a guia **Origem** (código HTML bruto).

   A formatação HTML pode ser tão simples ou complexa quanto você precisa. Você pode inserir imagens e texto para melhorar a capacidade de acreditar da mensagem no cliente de email do destinatário.

   - `${username}` insere o nome do destinatário.

   - `${loginserverurl}`insere o **valor de URL do Servidor de Logon de Phishing.**

   Para **campanhas de Phishing** de Lança (Anexo), você deve remover o link do corpo da mensagem (caso contrário, a mensagem conterá um **link** e um anexo e os cliques de link não serão rastreados em uma campanha de anexo).

   > [!div class="mx-imgBorder"]
   > ![Corpo do Email de Composição](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Ao terminar, clique em **Avançar**.

7. Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha. A mensagem de phishing é entregue aos destinatários direcionados.

## <a name="password-attack-campaigns"></a>Campanhas de ataque de senha

Um *ataque de senha* tenta adivinhar senhas para contas de usuário em uma organização, normalmente depois que o invasor identifica uma ou mais contas de usuário válidas.

No Simulador de Ataques, dois tipos diferentes de campanhas de ataque de senha estão disponíveis para você testar a complexidade das senhas dos usuários:

- **Senha de força** bruta (ataque  de  dicionário) : Um ataque de força bruta ou dicionário usa um grande arquivo de dicionário de senhas em uma conta de usuário com a esperança de que uma delas funcione (muitas senhas em uma conta). Bloqueios de senha incorretos ajudam a impedir ataques de senha de força bruta.

  Para o ataque de dicionário, você pode especificar uma ou muitas senhas a tentar (inseridas manualmente ou em um arquivo carregado) e você pode especificar um ou muitos usuários.

- **Ataque de pulverização de** senha : Um ataque de *pulverização* de senha usa a mesma senha cuidadosamente considerada em uma lista de contas de usuário (uma senha em várias contas). Os ataques de pulverização de senha são mais difíceis de detectar do que ataques de senha de força bruta (a probabilidade de sucesso aumenta quando um invasor tenta uma senha entre dezenas ou centenas de contas sem o risco de bloquear a senha incorreta do usuário).

  Para o ataque de pulverização de senha, você só pode especificar uma senha a ser tentada e pode especificar um ou muitos usuários.

> [!NOTE]
> Os ataques de senha no Simulador de Ataque passam o nome de usuário e a senha Solicitações básicas de autenticação para um ponto de extremidade, para que eles também funcionem com outros métodos de autenticação (AD FS, sincronização de hash de senha, passagem, PingFederate, etc.). Para usuários que têm a MFA habilitada, mesmo que o ataque de senha tente sua senha real,  a tentativa sempre se registrará como uma falha (em outras palavras, os usuários MFA nunca aparecerão na contagem de tentativas bem-sucedidas da campanha). Esse é o resultado esperado. O MFA é um método principal para ajudar a proteger contra ataques de senha.

### <a name="create-and-launch-a-password-attack-campaign"></a>Criar e iniciar uma campanha de ataque de senha

1. No Centro de Conformidade & segurança, vá para Simulador de ataque **de gerenciamento** \> **de ameaças.**

2. Na página **Simular ataques,** faça uma das seguintes seleções com base no tipo de campanha que você deseja criar:

   - Na seção **Senha de Força Bruta (Ataque de Dicionário),** clique em Iniciar **Ataque** ou em Ataque De Início **de Detalhes** de \> **Ataque.**

   - na seção **Ataque de pulverização de senha,** clique em **Iniciar Ataque ou** em Ataque De Início de **Detalhes** de \> **Ataque**.

3. O **assistente Configurar Ataque de Senha** é iniciado em um novo sobrevoo. Na etapa **Iniciar,** insira um nome de exibição exclusivo para a campanha e clique em **Próximo**.

4. Na etapa **Usuários de destino,** faça uma das seguintes etapas:

   - Clique **em Livro de** Endereços para selecionar os destinatários (usuários ou grupos) da campanha. Cada destinatário direcionado deve ter uma caixa Exchange Online caixa de correio. Se você clicar **em Filtrar** **e Aplicar** sem inserir um critério de pesquisa, todos os destinatários serão retornados e adicionados à campanha.

   - Clique **em Importar** e **Importar** Arquivo para importar um valor separado por vírgula (CSV) ou arquivo separado por linha de endereços de email. Cada linha deve conter o endereço de email do destinatário.

   Ao terminar, clique em **Avançar**.

5. Na etapa **Escolher configurações de** ataque, escolha o que fazer com base no tipo de campanha:

   - **Senha de Força Bruta (Ataque de Dicionário)**: Faça uma das seguintes etapas:

     - **Insira senhas manualmente**: Na caixa Pressionar **digite** para adicionar uma senha, digite uma senha e pressione ENTER. Repita essa etapa quantas vezes forem necessárias.

     - **Upload senhas** de um arquivo de  dicionário: clique em Upload para importar um arquivo de texto existente que contém uma senha em cada linha e uma última linha em branco. O arquivo de texto deve ter 10 MB ou menos de tamanho e não pode conter mais de 30.000 senhas.

   - **Ataque de pulverização de** senha : Em As senhas a ser **usadas na caixa de** ataque, insira uma senha.

   Ao terminar, clique em **Avançar**.

6. Na etapa **Confirmar,** clique em **Concluir** para iniciar a campanha. As senhas especificadas são tentadas nos usuários especificados.

## <a name="view-campaign-results"></a>Exibir resultados da campanha

Depois de iniciar uma campanha, você pode verificar o progresso e os resultados na página principal **simular ataques.**

As campanhas ativas mostrarão uma barra de status, um valor percentual concluído e a contagem "(usuários concluídos) de (total de usuários)". Clicar no botão **Atualizar** atualizará o progresso de todas as campanhas ativas. Você também pode clicar **em Encerrar** para interromper uma campanha ativa.

Quando a campanha é concluída, o status muda para **Ataque concluído**. Você pode exibir os resultados da campanha fazendo uma das seguintes ações:

- Na página principal **Simular ataques,** clique em **Exibir Relatório** com o nome da campanha.

- Na página principal **Simular ataques,** clique em **Detalhes de** Ataque na seção para o tipo de ataque. Na página **Detalhes de** ataque aberta, selecione a campanha na seção **Histórico de** Ataques.

Qualquer uma das ações anteriores levará você a uma página chamada **Detalhes de ataque.** As informações disponíveis nesta página para cada tipo de campanha são descritas nas seções a seguir.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultados da campanha Phishing de Lança (Coleta de Credenciais)

As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas : o número de usuários que clicaram no **link** e entraram em suas credenciais (*qualquer nome de* usuário e valor de senha).

- **Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.

- **Clique mais** rápido: quanto tempo o primeiro usuário levou para clicar no link depois de iniciar a campanha.

- **Clique em** Média : a soma de quanto tempo todos demoraram para clicar no link dividido pelo número de usuários que clicaram no link.

- **Clique em Taxa de** Sucesso : Uma porcentagem calculada por (número de usuários que clicaram no link) / **Total de usuários direcionados**.

- **Credenciais mais rápidas:** quanto tempo o primeiro usuário levou para inserir suas credenciais depois de iniciar a campanha.

- **Credenciais médias**: a soma de quanto tempo todos demoraram para inserir suas credenciais divididas pelo número de usuários que inseriram suas credenciais.

- **Taxa de Sucesso de** Credenciais : Uma porcentagem calculada por (número de usuários que entraram em suas credenciais) / **Total de usuários direcionados**.

- Um gráfico de barras que mostra **o Link clicado e** os números **fornecidos por** dia por credencial.

- Um gráfico de círculo que mostra **as porcentagens Link clicou**, **Credencial fornecida** e **Nenhuma** para a campanha.

- A **seção Usuários Comprometidos** lista os detalhes dos usuários que clicaram no link:

  - O endereço de email do usuário

  - A data/hora em que eles clicaram no link.

  - O endereço IP do cliente.

  - Detalhes sobre a versão do usuário do Windows e navegador da Web.

  Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Resultados da campanha Phishing de Lança (Anexo)

As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas : o número de usuários que abriram ou baixaram e abriram o anexo (a visualização não conta).

- **Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.

- **Tempo de abertura de anexo mais** rápido: quanto tempo o primeiro usuário levou para abrir o anexo depois de iniciar a campanha.

- **Tempo médio de** abertura de anexo : a soma de quanto tempo todos demoraram para abrir o anexo dividido pelo número de usuários que abriram o anexo.

- **Taxa de sucesso de** abertura de anexo: uma porcentagem calculada por (número de usuários que abriram o anexo) / Total de usuários **direcionados**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Resultados da campanha Senha de Força Bruta (Ataque de Dicionário)

As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas : o número de usuários que foram encontrados usando uma das senhas especificadas.

- **Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.

- A **seção Usuários Comprometidos** lista os endereços de email dos usuários afetados. Você pode clicar **em Exportar** para exportar os resultados para um arquivo CSV.

### <a name="password-spray-attack-campaign-results"></a>Resultados da campanha de ataque de pulverização de senha

As informações a seguir estão disponíveis na página **Detalhes de** ataque para cada campanha:

- A duração (data/hora de início e data/hora de término) da campanha.

- **Total de usuários direcionados**

- **Tentativas** bem-sucedidas : o número de usuários que foram encontrados usando a senha especificada.

- **Taxa de Sucesso Geral**: Uma porcentagem calculada por tentativas bem-sucedidas   /  **Total de usuários direcionados**.
