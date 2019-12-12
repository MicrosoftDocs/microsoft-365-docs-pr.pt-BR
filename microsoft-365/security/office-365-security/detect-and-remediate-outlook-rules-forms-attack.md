---
title: Detectar e corrigir as regras do Outlook e os ataques de injeção de formulários personalizados no Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Saiba como reconhecer e corrigir as regras do Outlook e os ataques de injeção de formulários personalizados no Office 365
ms.openlocfilehash: d5f4a653463f4105df025bf29679465ca5335098
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970787"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Detectar e corrigir ataques de injeção a regras e formulários personalizados do Outlook no Office 365

**Resumo** Saiba como reconhecer e corrigir as regras do Outlook e os ataques de injeção de formulários personalizados no Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Quais são as regras do Outlook e o ataque de injeção de formulários personalizados?

Depois que um invasor violar uma conta em sua locação e entrar, você tentará estabelecer uma maneira de permanecer ou uma maneira de entrar novamente após serem descobertas e removidas. Isso é chamado de estabelecimento de um mecanismo de persistência. Duas maneiras de fazer isso é explorar as regras do Outlook ou injetar formulários personalizados no Outlook.
Em ambos os casos, a regra ou o formulário é sincronizado a partir do serviço de nuvem para o cliente de desktop, portanto, um formato completo e a reinstalação do software cliente não eliminam o mecanismo de injeção. Isso ocorre porque, quando o software cliente do Outlook se reconecta à caixa de correio na nuvem, ele rebaixará as regras e formulários da nuvem. Depois que as regras e os formulários estiverem em vigor, o invasor o usará para executar códigos remotos ou personalizados, geralmente para instalar o malware na máquina local. O malware, então, reroubará as credenciais ou executará outras atividades ilícitas.
A boa notícia aqui é que, se você mantiver seus clientes corrigidos para a versão mais recente, não estará vulnerável à ameaça à medida que os padrões atuais do cliente do Outlook bloquearão ambos os mecanismos.

Os ataques geralmente seguem estes padrões:

**A exploração de regras**:

1. O invasor rouba o nome de usuário e a senha de um de seus usuários.

2. O invasor, em seguida, entra na caixa de correio dos usuários do Exchange. A caixa de correio pode estar no Exchange Online ou no Exchange no local.

3. O invasor cria uma regra de encaminhamento na caixa de correio que é disparada quando a caixa de correio recebe um email que corresponde aos critérios da regra. Os critérios de regra e o conteúdo do email de acionamento são adaptados para cada um.

4. O invasor envia o email de acionamento para o usuário que está usando a caixa de correio normalmente.

5. Quando o email é recebido, a regra é disparada. Normalmente, a ação da regra é iniciar um aplicativo em um servidor remoto (WebDAV).

6. O aplicativo normalmente instala malware, como o [PowerShell Empires](https://www.powershellempire.com/), localmente no computador do usuário.

7. O malware permite que o invasor reroubar o nome de usuário e a senha do usuário ou outras credenciais da máquina local e realizar outras atividades mal-intencionadas.

**A exploração de formulários**:

1. O invasor rouba o nome de usuário e a senha de um de seus usuários.

2. O invasor e, em seguida, entrar em uma caixa de correio dos usuários do Exchange. A caixa de correio pode estar no Exchange Online ou no Exchange no local.

3. O invasor cria um modelo de formulário de email personalizado e o insere na caixa de correio do usuário. O formulário personalizado é disparado quando a caixa de correio recebe um email que requer a caixa de correio para carregar o formulário personalizado. O formulário personalizado e o formato de email são adaptados para cada um.
4. O invasor envia o email de acionamento para o usuário, que está usando a caixa de correio normalmente.

5. Quando o email é recebido, o formulário é carregado. O formulário inicia um aplicativo em um servidor remoto (WebDAV).

6. O aplicativo normalmente instala malware, como o [PowerShell Empires](https://www.powershellempire.com/), localmente no computador do usuário.

7. O malware permite que o invasor reroubar o nome de usuário e a senha do usuário ou outras credenciais da máquina local e realizar outras atividades mal-intencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>O que um ataque de injeção de formulários personalizados e regras pode parecer com o Office 365?

Esses mecanismos de persistência provavelmente serão observados por seus usuários e, em alguns casos, podem ser invisíveis para eles. Este artigo mostra como procurar qualquer um dos sete sinais (indicadores de comprometimento) listados abaixo. Se você encontrar qualquer um desses, precisará realizar etapas de correção.

- Indicadores de comprometimento de regras:

  - A ação de regra é iniciar um aplicativo.

  - A regra faz referência a um EXE, ZIP ou URL.

  - Na máquina local, procure o novo processo que se origina do PID do Outlook.

- Indicadores de comprometimento de formulários personalizados:

  - Apresentação de formulário personalizada salva como sua própria classe de mensagem.

  - A classe Message contém código executável.

  - Geralmente armazenado na biblioteca de formulários particulares ou em pastas de caixa de entrada.

  - O formulário é denominado IPM. Observação. [nome personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Etapas para encontrar sinais desse ataque e confirmá-lo

Você pode usar um destes dois métodos para confirmar o ataque:

- Examine manualmente as regras e os formulários para cada caixa de correio usando o cliente do Outlook. Esse método é completo, mas você só pode verificar o usuário de caixa de correio de cada vez, o que pode ser muito demorado se você tiver muitos usuários para verificar. Também pode resultar em uma violação do computador a partir do qual você está executando a verificação.

- Use o script do PowerShell [Get-AllTenantRulesAndForms. ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) para despejar automaticamente todas as regras de encaminhamento de email e formulários personalizados para todos os usuários em sua locação. Esse é o método mais rápido e mais seguro com a menor quantidade de sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar o ataque de regras usando o cliente Outlook

1. Abra o cliente do Outlook dos usuários como o usuário. Talvez o usuário precise da ajuda para examinar as regras em suas caixas de correio.

2. Consulte [gerenciar mensagens de email usando](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) o artigo de regras para obter os procedimentos sobre como abrir a interface de regras no Outlook.

3. Procure regras que o usuário não criou ou regras ou regras inesperadas com nomes suspeitos.

4. Procure na descrição da regra as ações de regra que iniciam e fazem o aplicativo ou se referem a um. EXE,. ZIP ou para iniciar uma URL.

5. Procure os novos processos que começam a usar a ID de processo do Outlook. Consulte [localizar a ID de processo](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Etapas para confirmar o ataque de formulários usando o cliente Outlook

1. Abra o cliente do Outlook do usuário como o usuário.

2. Siga as etapas em, [mostrar a guia desenvolvedor](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) da versão dos usuários do Outlook.

3. Abra a guia desenvolvedor agora visível no Outlook e clique em **criar um formulário**.

4. Selecione a **caixa de entrada** na lista **examinar** . Procure formulários personalizados. Formulários personalizados são raros o suficiente se você tiver qualquer formulário personalizado, vale a pena ter uma aparência mais profunda.

5. Investigue todos os formulários personalizados, especialmente aqueles marcados como ocultos.

6. Abra todos os formulários personalizados e, no grupo de **formulários** , clique em **Exibir código** para ver o que é executado quando o formulário é carregado.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Etapas para confirmar as regras e o ataque de formulários usando o PowerShell

A maneira mais simples de verificar uma regra ou um ataque de formulários personalizados é executar o script do PowerShell [Get-AllTenantRulesAndForms. ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) . Esse script se conecta a todas as caixas de correio em seu locatário e despeja todas as regras e formulários em dois arquivos. csv.

#### <a name="pre-requisites"></a>Pré-requisitos

Você precisará ter direitos de administrador global para executar o script porque o script se conecta a cada caixa de correio na locação para ler as regras e formulários.

1. Entre na máquina que você executará o script com direitos de administrador local.

2. Baixe ou copie o script Get-AllTenantRulesAndForms. ps1 do GitHub para uma pasta a partir da qual será executado. O script criará dois arquivos com carimbo de data para esta pasta, MailboxFormsExport-yyyy-mm-dd. csv e MailboxRulesExport-yyyy-mm-dd. csv.

3. Abra uma instância do PowerShell como administrador e abra a pasta para a qual você salvou o script.

4. Execute esta linha de comando do PowerShell `.\Get-AllTenantRulesAndForms.ps1`da seguinte maneira .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretação da saída

- **MailboxRulesExport-*aaaa-mm-dd*. csv**: examine as regras (uma por linha) para condições de ação que incluem aplicativos ou executáveis:

  - **ActionType (coluna A)**: se você vir o valor "ID_ACTION_CUSTOM", a regra provavelmente será mal-intencionada.

  - **IsPotentiallyMalicious (coluna D)**: se esse valor for "true", a regra provavelmente será mal-intencionada.

  - **ActionCommand (coluna G)**: se isso listar um aplicativo ou qualquer arquivo com uma extensão. exe,. zip ou uma entrada referente a uma URL, que não deveria estar lá, a regra provavelmente será mal-intencionada.

- **MailboxFormsExport-*aaaa-mm-dd*. csv**: em geral, o uso de formulários personalizados é muito raro. Se você encontrar algum nesta pasta de trabalho, abra a caixa de correio desse usuário e examine o próprio formulário. Se sua organização não a colocou intencionalmente, provavelmente é mal-intencionado.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Como interromper e corrigir o ataque de regras e formulários do Outlook

Se você encontrar evidências de qualquer um desses ataques, a correção será simples, basta excluir a regra ou o formulário da caixa de correio. Você pode fazer isso com o cliente do Outlook ou usando o PowerShell remoto para remover regras.

### <a name="using-outlook"></a>Usando o Outlook

1. Identifique todos os dispositivos que o usuário usou com o Outlook. Todos eles precisarão ser limpos de possíveis malwares. Não permita que o usuário entre e use email até que todos os dispositivos sejam limpos.

2. Siga as etapas em [excluir uma regra](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Se não tiver certeza sobre a presença de outros tipos de malware, você poderá Formatar e reinstalar todos os softwares no dispositivo. Para dispositivos móveis, você pode seguir as etapas do fabricante para redefinir o dispositivo para a imagem de fábrica.

4. Instale as versões mais recentes do Outlook. Lembre-se de que a versão atual do Outlook bloqueia os dois tipos desse ataque por padrão.

5. Após a remoção de todas as cópias offline da caixa de correio, redefina a senha do usuário (use uma de alta qualidade) e siga as etapas em [Configurar a autenticação multifator para usuários do Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) , se a MFA ainda não tiver sido habilitada. Isso garante que as credenciais do usuário não sejam expostas por outros meios (como phishing ou reutilização de senha).

### <a name="using-powershell"></a>Usando o PowerShell

Há dois cmdlets do PowerShell remoto que você pode usar para remover ou desabilitar regras perigosas. Basta seguir as etapas.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Etapas para caixas de correio que estão em um servidor Exchange

1. Conecte-se ao servidor do Exchange usando o PowerShell remoto. Siga as etapas em [conectar-se aos servidores Exchange usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Se você deseja remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) .

3. Se você deseja manter a regra e seu conteúdo para uma investigação adicional, use o cmdlet [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) .

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Etapas para caixas de correio no Exchange Online

1. Siga as etapas em [conectar ao Exchange Online usando o PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Se você deseja remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-inbox Rule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) .

3. Se você deseja manter a regra e seu conteúdo para uma investigação adicional, use o cmdlet [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) .

## <a name="how-to-minimize-future-attacks"></a>Como minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>Primeiro: proteger suas contas

As regras e os exploits de formulários são usados apenas por um invasor depois que eles roubam ou violaram uma das contas do usuário. Portanto, a primeira etapa para impedir o uso dessas explorações em relação à sua organização é proteger agressivamente suas contas de usuário. Algumas das maneiras mais comuns pelas quais as contas são violadas são por meio de ataques de fraude de [senha](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) ou phishing.

A melhor maneira de proteger suas contas de usuário e, especialmente suas contas de administrador, é [Configurar a autenticação multifator para usuários do Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication). Você também deve:

- Monitorar como suas contas de usuário são [acessadas e usadas](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports). Não é possível impedir a violação inicial, mas você diminuirá a duração e o impacto da violação detectando-a antes. Você pode usar essas [políticas de segurança do aplicativo nuvem do Office 365](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para monitorar suas contas e alertar sobre atividades incomuns:

  - **Várias tentativas de logon com falha**: esta política faz o perfil de seu ambiente e dispara alertas quando os usuários executam várias atividades de logon com falha em uma única sessão com relação à linha de base aprendida, o que pode indicar uma falha na tentativa.

  - **Impossível viagens**: esta política faz o perfil de seu ambiente e dispara alertas quando as atividades são detectadas do mesmo usuário em diferentes locais dentro de um período de tempo menor do que o tempo de viagem esperado entre os dois locais. Isso pode indicar que um usuário diferente está usando as mesmas credenciais. Detectar esse comportamento anômala exige um período de aprendizado inicial de sete dias durante o qual ele aprende o padrão de atividade de um novo usuário.

  - **Atividade representada não usual (por usuário)**: esta política faz o perfil de seu ambiente e dispara alertas quando os usuários executam várias atividades representadas em uma única sessão com relação à linha de base conhecida, o que pode indicar uma falha na tentativa.

- Aproveite uma ferramenta como o [Office 365 a pontuação segura](https://securescore.office.com/) para gerenciar as configurações e os comportamentos de segurança da conta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: Mantenha seus clientes do Outlook atualizados

Versões totalmente atualizadas e corrigidas do Outlook 2013 e 2016 desabilite a ação de regra/formulário "Iniciar aplicativo" por padrão. Isso garantirá que, mesmo que um invasor viole a conta, as ações de regra e formulário serão bloqueadas. Você pode instalar as atualizações e os patches de segurança mais recentes seguindo as etapas em [instalar atualizações do Office](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5).

Veja a seguir as versões de patch para os clientes do Outlook 2013 e 2016:

- **Outlook 2016**: 16.0.4534.1001 ou superior.

- **Outlook 2013**: 15.0.4937.1000 ou superior.

Para obter mais informações sobre os patches de segurança individuais, consulte:

- [Patch de segurança do Outlook 2016](https://support.microsoft.com/help/3191883)

- [Patch de segurança do Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Terceiro: monitorar seus clientes Outlook

Observe que, mesmo com os patches e atualizações instalados, é possível que um invasor altere a configuração da máquina local para reabilitar o comportamento de "Iniciar aplicativo". Você pode usar o [gerenciamento avançado de política de grupo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) para monitorar e impor políticas de máquina local em seus clientes.

Você pode ver se "Iniciar aplicativo" foi habilitado novamente por meio de uma substituição no registro usando as informações em [como exibir o registro do sistema usando as versões de 64 bits do Windows](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows). Verifique estas subchaves:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Procure a chave EnableUnsafeClientMailRules. Se ele estiver lá e estiver definido como 1, o patch de segurança do Outlook foi substituído e o computador está vulnerável ao ataque de formulários/regras. Se o valor for 0, a ação "Iniciar aplicativo" estará desabilitada. Se a versão atualizada e corrigida do Outlook estiver instalada e essa chave do registro não estiver presente, um sistema não estará vulnerável a esses ataques.

Os clientes com instalações do Exchange no local devem considerar o bloqueio de versões mais antigas do Outlook que não possuem patches disponíveis. Os detalhes sobre esse processo podem ser encontrados no artigo [Configurar o bloqueio de cliente do Outlook](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteja o Office 365 como um profissional de cibersegurança

Sua assinatura do Office 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [mapa de segurança do Office 365-principais prioridades para os primeiros 30 dias, 90 dias e além](security-roadmap.md) de implementar as práticas recomendadas da Microsoft para proteger seu locatário do Office 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também:

- [Regras mal-intencionadas do Outlook](https://silentbreaksecurity.com/malicious-outlook-rules/) por postagem de segurança do SilentBreak sobre o vetor de regras fornece uma revisão detalhada de como as regras do Outlook.

- [MAPI sobre http e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) no blog do Sensepost sobre Mailrule Pwnage discute uma ferramenta chamada Ruler que permite explorar caixas de correio por meio de regras do Outlook.

- [Formulários do Outlook e shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) no blog do Sensepost sobre o vetor de ameaça de formulários.

- [Codebase da régua](https://github.com/sensepost/ruler)

- [Indicadores da régua de comprometimento](https://github.com/sensepost/notruler/blob/master/iocs.md)
