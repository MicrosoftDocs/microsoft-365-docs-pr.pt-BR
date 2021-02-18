---
title: Detectar e remediar as regras do Outlook e ataques de injeção de formulários personalizados.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Saiba como reconhecer e remediar as regras do Outlook e os ataques de injeção de formulários personalizados no Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286388"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Detectar e remediar ataques de injeção de formulários personalizados e regras do Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Resumo** Saiba como reconhecer e remediar as regras do Outlook e os ataques de injeção de formulários personalizados no Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>O que é o ataque de injeção de formulários personalizados e regras do Outlook?

Depois que um invasor violar uma conta em seu local de adoção e entrar, haverá uma maneira de permanecer ou uma maneira de entrar novamente depois que eles são descobertos e removidos. Isso é chamado de estabelecer um mecanismo de persistência. Duas maneiras de fazer isso são explorando regras do Outlook ou injetando formulários personalizados no Outlook.
Em ambos os casos, a regra ou o formulário é sincronizado do serviço de nuvem para o cliente da área de trabalho, para que um formato completo e uma nova instalação do software cliente não elimine o mecanismo de injeção. Isso acontece porque, quando o software cliente do Outlook se reconecta à caixa de correio na nuvem, ele baixa novamente as regras e os formulários da nuvem. Depois que as regras e formulários estão em vigor, o invasor as usa para executar código remoto ou personalizado, geralmente para instalar malware no computador local. Em seguida, o malware roubará credenciais ou executará outra atividade ilícita ilícita.
A boa notícia aqui é que, se você manter seus clientes com patch para a versão mais recente, você não está vulnerável à ameaça, pois os padrões atuais do cliente do Outlook bloqueiam ambos os mecanismos.

Os ataques normalmente seguem estes padrões:

**The Rules Exploit**:

1. O invasor roubar o nome de usuário e a senha de um de seus usuários.

2. Em seguida, o invasor se ins loco na caixa de correio do Exchange dos usuários. A caixa de correio pode estar no Exchange Online ou no Exchange local.

3. Em seguida, o invasor cria uma regra de encaminhamento na caixa de correio que é disparada quando a caixa de correio recebe um email que corresponde aos critérios da regra. Os critérios de regra e o conteúdo do email de gatilho são personalizados um para o outro.

4. O invasor envia o email de gatilho para o usuário que está usando sua caixa de correio normalmente.

5. Quando o email é recebido, a regra é disparada. A ação da regra é geralmente iniciar um aplicativo em um servidor remoto (WebDAV).

6. O aplicativo normalmente instala malware, como [o Powershell Queliano](https://www.powershellempire.com/), localmente no computador do usuário.

7. O malware permite que o invasor roubo o nome de usuário e a senha do usuário ou outras credenciais do computador local e execute outras atividades mal-intencionadas.

**The Forms Exploit**:

1. O invasor roubar o nome de usuário e a senha de um de seus usuários.

2. Em seguida, o invasor entrará na caixa de correio do Exchange dos usuários. A caixa de correio pode estar no Exchange Online ou no Exchange local.

3. Em seguida, o invasor cria um modelo de formulário de email personalizado e o insere na caixa de correio do usuário. O formulário personalizado é acionado quando a caixa de correio recebe um email que exige que a caixa de correio carregue o formulário personalizado. O formulário personalizado e o formato do email são feitos de forma personalizada um para o outro.
4. O invasor envia o email de gatilho para o usuário, que está usando sua caixa de correio normalmente.

5. Quando o email é recebido, o formulário é carregado. O formulário inicia um aplicativo em um servidor remoto (WebDAV).

6. O aplicativo normalmente instala malware, como [o Powershell Queliano](https://www.powershellempire.com/), localmente no computador do usuário.

7. O malware permite que o invasor roubo o nome de usuário e a senha do usuário ou outras credenciais do computador local e execute outras atividades mal-intencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>O que um ataque de injeção de regras e formulários personalizados pode se parecer com o Office 365?

É improvável que esses mecanismos de persistência sejam percebidos por seus usuários e, em alguns casos, podem até mesmo ser invisíveis para eles. Este artigo mostra como procurar qualquer um dos sete sinais (indicadores de comprometimento) listados abaixo. Se encontrar algum deles, você precisará tomar as medidas de correção.

- Indicadores de comprometimento de regras:

  - A Ação de Regra é para iniciar um aplicativo.

  - A regra faz referência a um EXE, ZIP ou URL.

  - No computador local, procure novos inícios de processo que se originam do PID do Outlook.

- Indicadores de comprometimento de formulários personalizados:

  - Formulário personalizado presente salvo como sua própria classe de mensagem.

  - A classe Message contém código executável.

  - Geralmente armazenados nas pastas Biblioteca de Formulários Pessoais ou Caixa de Entrada.

  - O formulário é denominado IPM. Observação. [nome personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Etapas para encontrar sinais desse ataque e confirmá-lo

Você pode usar qualquer um desses dois métodos para confirmar o ataque:

- Examine manualmente as regras e os formulários de cada caixa de correio usando o cliente outlook. Esse método é completo, mas você só pode verificar o usuário de caixa de correio por vez, o que pode ser muito demorado se você tiver muitos usuários para verificar. Isso também pode resultar em uma violação do computador em que você está executando a verificação.

- Use o [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) script do PowerShell para despejar automaticamente todas as regras de encaminhamento de email e formulários personalizados para todos os usuários em sua loja. Esse é o método mais rápido e mais seguro com menos sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar o ataque de regras usando o cliente do Outlook

1. Abra o cliente do Outlook dos usuários como o usuário. O usuário pode precisar de ajuda para examinar as regras em sua caixa de correio.

2. Consulte Gerenciar [mensagens de email usando o artigo de](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) regras para os procedimentos sobre como abrir a interface de regras no Outlook.

3. Procure regras que o usuário não criou, ou quaisquer regras ou regras inesperadas com nomes suspeitos.

4. Procure na descrição da regra para ações de regra que iniciam e aplicativo ou se referem a um . EXE, . Arquivo ZIP ou para iniciar uma URL.

5. Procure novos processos que comecem a usar a ID de processo do Outlook. Consulte [Encontrar a ID do processo.](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Etapas para confirmar o ataque de formulários usando o cliente Outlook

1. Abra o cliente do Outlook do usuário como o usuário.

2. Siga as etapas em, [Mostrar a guia Desenvolvedor](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) para a versão de usuários do Outlook.

3. Abra a guia agora visível do desenvolvedor no Outlook e clique **em design de um formulário.**

4. Selecione a **Caixa de** Entrada na lista **Look In.** Procure formulários personalizados. Formulários personalizados são raros o suficiente para que, se você tiver formulários personalizados, vale a pena ter uma aparência mais profunda.

5. Investigue formulários personalizados, especialmente aqueles marcados como ocultos.

6. Abra todos os formulários personalizados e, **no** grupo formulário, clique em Exibir **Código** para ver o que é executado quando o formulário é carregado.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Etapas para confirmar o ataque de Regras e Formulários usando o PowerShell

A maneira mais simples de verificar regras ou ataques de formulários personalizados é executar o [ scriptGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell. Esse script se conecta a todas as caixas de correio em seu locatário e despeja todas as regras e formulários em dois arquivos .csv.

#### <a name="pre-requisites"></a>Pré-requisitos

Você precisará ter direitos de administrador global para executar o script, pois o script se conecta a todas as caixas de correio no local para ler as regras e os formulários.

1. Entre no computador em que você executará o script com direitos de administrador local.

2. Baixe ou copie o Get-AllTenantRulesAndForms.ps1 script do GitHub para uma pasta da qual você o executará. O script criará dois arquivos marcados de data para essa pasta, MailboxFormsExport-yyyy-mm-dd.csv e MailboxRulesExport-yyyy-mm-dd.csv.

3. Abra uma instância do PowerShell como administrador e abra a pasta em que você salvou o script.

4. Execute esta linha de comando do PowerShell da seguinte `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretar a saída

- **MailboxRulesExport-*yyyy-mm-dd*.csv:** examine as regras (uma por linha) para condições de ação que incluem aplicativos ou executáveis:

  - **ActionType (coluna A)**: se você vir o valor "ID_ACTION_CUSTOM", a regra provavelmente será mal-intencionada.

  - **IsPotentiallyMalicious (coluna D)**: Se esse valor for "VERDADEIRO", a regra provavelmente será mal-intencionada.

  - **ActionCommand (coluna G)**: se isso lista um aplicativo ou qualquer arquivo com uma extensão .exe, .zip ou uma entrada que se refere a uma URL, que não deveria estar lá, a regra provavelmente é mal-intencionada.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** em geral, o uso de formulários personalizados é muito raro. Se você encontrar alguma nessa área de trabalho, abra a caixa de correio desse usuário e examine o próprio formulário. Se sua organização não o colocou intencionalmente, provavelmente é mal-intencionado.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Como parar e remediar o ataque de Regras e Formulários do Outlook

Se você encontrar alguma evidência de qualquer um desses ataques, a correção é simples, basta excluir a regra ou o formulário da caixa de correio. Você pode fazer isso com o cliente do Outlook ou usando o PowerShell remoto para remover regras.

### <a name="using-outlook"></a>Usando o Outlook

1. Identifique todos os dispositivos que o usuário usou com o Outlook. Todos eles precisarão ser limpos de possíveis malwares. Não permita que o usuário entre e use emails até que todos os dispositivos sejam limpos.

2. Siga as etapas em [Excluir uma regra](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Se você não tiver certeza sobre a presença de outro malware, poderá formatar e instalar todos os softwares no dispositivo. Para dispositivos móveis, você pode seguir as etapas dos fabricantes para redefinir o dispositivo para a imagem de fábrica.

4. Instale as versões mais atualizadas do Outlook. Lembre-se de que a versão atual do Outlook bloqueia os dois tipos desse ataque por padrão.

5. Depois que todas as cópias offline da caixa de correio foram removidas, redefina a senha do usuário (use uma de alta qualidade) e siga as etapas na Configuração da autenticação [multifa](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) factor para os usuários se a MFA ainda não tiver sido habilitada. Isso garante que as credenciais do usuário não sejam expostas por outros meios (como phishing ou re-uso de senha).

### <a name="using-powershell"></a>Usando o PowerShell

Há dois cmdlets remotos do PowerShell que você pode usar para remover ou desabilitar regras perigosas. Basta seguir as etapas.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Etapas para caixas de correio que estão em um servidor Exchange

1. Conecte-se ao servidor Exchange usando o PowerShell remoto. Siga as etapas em [Conectar-se aos servidores Exchange usando o PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Se você quiser remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Se você quiser manter a regra e seu conteúdo para investigação posterior, use o cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Etapas para caixas de correio no Exchange Online

1. Siga as etapas em [Conectar-se ao Exchange Online usando o PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Se você quiser remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-Inbox Rule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Se você quiser manter a regra e seu conteúdo para investigação posterior, use o cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Como minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>Primeiro: proteja suas contas

As explorações de Regras e Formulários só são usadas por um invasor depois de eles roubarem ou violarem uma das contas de seu usuário. Portanto, sua primeira etapa para impedir o uso dessas explorações em sua organização é proteger agressivamente suas contas de usuário. Algumas das maneiras mais comuns pelas quais as contas são violadas são por meio de phishing ou [ataques de pulverização de](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) senha.

A melhor maneira de proteger suas contas de usuário e, especialmente, suas contas de administrador, é configurar a [autenticação multifa factor para os usuários.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Você também deve:

- Monitore como suas contas de usuário são [acessadas e usadas.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Você pode não impedir a violação inicial, mas reduzirá a duração e o impacto da violação detectando-a mais cedo. Você pode usar essas políticas do [Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para monitorar suas contas e alertar sobre atividades incomuns:

  - **Várias tentativas com** falha de logon: essa política perfilia seu ambiente e dispara alertas quando os usuários executam várias atividades de logon com falha em uma única sessão em relação à linha de base aprendida, o que pode indicar uma tentativa de violação.

  - **Viagem impossível:** essa política perfilia seu ambiente e dispara alertas quando atividades são detectadas do mesmo usuário em locais diferentes em um período de tempo menor do que o tempo de viagem esperado entre os dois locais. Isso pode indicar que um usuário diferente está usando as mesmas credenciais. A detecção desse comportamento anômalo requer um período inicial de aprendizagem de sete dias durante o qual ele aprende o padrão de atividade de um novo usuário.

  - Atividade representação incomum **(por usuário)**: essa política perfilia seu ambiente e dispara alertas quando os usuários executam várias atividades personificadas em uma única sessão com relação à linha de base aprendida, o que pode indicar uma tentativa de violação.

- Aproveite uma ferramenta como a Classificação de Segurança [do Office 365](https://securescore.office.com/) para gerenciar configurações e comportamentos de segurança de conta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: mantenha seus clientes do Outlook atualizados

As versões totalmente atualizadas e corrigidas do Outlook 2013 e 2016 desabilitam a ação de regra/formulário "Iniciar Aplicativo" por padrão. Isso garantirá que, mesmo que um invasor viole a conta, as ações de formulário e regra serão bloqueadas. Você pode instalar as atualizações e os patches de segurança mais recentes seguindo as etapas em [Instalar atualizações do Office.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Aqui estão as versões de patch para seus clientes do Outlook 2013 e 2016:

- **Outlook 2016**: 16.0.4534.1001 ou superior.

- **Outlook 2013**: 15.0.4937.1000 ou superior.

Para obter mais informações sobre os patches de segurança individuais, consulte:

- [Correção de segurança do Outlook 2016](https://support.microsoft.com/help/3191883)

- [Correção de segurança do Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Terceiro: monitorar seus clientes do Outlook

Observe que, mesmo com os patches e atualizações instalados, é possível que um invasor altere a configuração do computador local para reabilitar o comportamento "Iniciar Aplicativo". Você pode usar o [Gerenciamento Avançado de Política de](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) Grupo para monitorar e impor políticas de máquina local em seus clientes.

Você pode ver se "Iniciar Aplicativo" foi reabilitar por meio de uma substituição no Registro usando as informações em Como exibir o registro do sistema usando versões de [64](https://support.microsoft.com/help/305097)bits do Windows . Verifique estas sub-chaves:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Procure a chave EnableUnsafeClientMailRules. Se estiver lá e estiver definido como 1, o patch de segurança do Outlook foi substituído e o computador está vulnerável ao ataque de Formulário/Regras. Se o valor for 0, a ação "Iniciar Aplicativo" será desabilitada. Se a versão atualizada e corrigida do Outlook estiver instalada e essa chave do Registro não estiver presente, um sistema não estará vulnerável a esses ataques.

Os clientes com instalações locais do Exchange devem considerar o bloqueio de versões mais antigas do Outlook que não têm patches disponíveis. Detalhes sobre esse processo podem ser encontrados no artigo Configurar bloqueio de [cliente do Outlook.](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também:

- [As regras mal-intencionadas](https://silentbreaksecurity.com/malicious-outlook-rules/) do Outlook por postagem de segurança SilentBreak sobre vetor de regras fornece uma análise detalhada de como as regras do Outlook.

- [MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.

- [Formulários e shells do Outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) no blog Sensepost sobre Vetor de Ameaças de Formulários.

- [Base de código de régua](https://github.com/sensepost/ruler)

- [Indicadores de comprometimento de régua](https://github.com/sensepost/notruler/blob/master/iocs.md)
