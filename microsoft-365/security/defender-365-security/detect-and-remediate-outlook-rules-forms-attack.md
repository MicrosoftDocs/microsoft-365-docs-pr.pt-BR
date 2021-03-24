---
title: Detectar e remediar as regras do Outlook e ataques de injeções de formulários personalizados.
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
description: Saiba como reconhecer e remediar as regras do Outlook e ataques de injeções de formulários personalizados no Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053467"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Detectar e remediar as regras do Outlook e ataques de injeções de formulários personalizados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Resumo** Saiba como reconhecer e remediar as regras do Outlook e ataques de injeções personalizadas de Formulários no Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>O que é o ataque de injeção de Regras e Formulários Personalizados do Outlook?

Depois que um invasor obtém acesso à sua organização, eles tentarão estabelecer uma base para permanecer ou voltar depois que eles foram descobertos. Essa atividade é chamada *de estabelecimento de um mecanismo de persistência*. Há duas maneiras de um invasor usar o Outlook para estabelecer um mecanismo de persistência:

- Explorando as regras do Outlook.
- Injetando formulários personalizados no Outlook.

Reinstalar o Outlook ou até mesmo dar à pessoa afetada um novo computador não ajudará. Quando a nova instalação do Outlook se conecta à caixa de correio, todas as regras e formulários são sincronizados da nuvem. As regras ou formulários geralmente são projetados para executar código remoto e instalar malware no computador local. O malware rouba credenciais ou executa outras atividades ilícitas.

A boa notícia é: se você manter seus clientes do Outlook remendados para a versão mais recente, não será vulnerável à ameaça, pois os padrões atuais do cliente do Outlook bloqueiam ambos os mecanismos.

Normalmente, os ataques seguem estes padrões:

**The Rules Exploit**:

1. O invasor rouba as credenciais de um usuário.

2. O invasor faz o acesso à caixa de correio do Exchange desse usuário (Exchange Online ou Exchange local).

3. O invasor cria uma regra de Caixa de Entrada de encaminhamento na caixa de correio. A regra de encaminhamento é disparada quando a caixa de correio recebe uma mensagem específica do invasor que corresponde às condições da regra. As condições de regra e o formato da mensagem são personalizados um para o outro.

4. O invasor envia o email de gatilho para a caixa de correio comprometida, que ainda está sendo usada como normal pelo usuário não suspeito.

5. Quando a caixa de correio recebe uma mensagem que corresponde às condições de regra, a ação da regra é aplicada. Normalmente, a ação de regra é iniciar um aplicativo em um servidor remoto (WebDAV).

6. Normalmente, o aplicativo instala malware no computador do usuário (por exemplo, [o PowerShell Empire](https://www.powershellempire.com/)).

7. O malware permite que o invasor roube (ou roube novamente) o nome de usuário e a senha ou outras credenciais do computador local e execute outras atividades mal-intencionadas.

**The Forms Exploit**:

1. O invasor rouba as credenciais de um usuário.

2. O invasor faz o acesso à caixa de correio do Exchange desse usuário (Exchange Online ou Exchange local).

3. O invasor insere um modelo de formulário de email personalizado na caixa de correio do usuário. O formulário personalizado é acionado quando a caixa de correio recebe uma mensagem específica do invasor que exige que a caixa de correio carregue o formulário personalizado. O formulário personalizado e o formato da mensagem são personalizados um para o outro.

4. O invasor envia o email de gatilho para a caixa de correio comprometida, que ainda está sendo usada como normal pelo usuário não suspeito.

5. Quando a caixa de correio recebe a mensagem, a caixa de correio carrega o formulário necessário. O formulário inicia um aplicativo em um servidor remoto (WebDAV).

6. Normalmente, o aplicativo instala malware no computador do usuário (por exemplo, [o PowerShell Empire](https://www.powershellempire.com/)).

7. O malware permite que o invasor roube (ou roube novamente) o nome de usuário e a senha ou outras credenciais do computador local e execute outras atividades mal-intencionadas.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>O que um ataque de Injeção de Regras e Formulários Personalizados pode se parecer com o Office 365?

Esses mecanismos de persistência são improváveis de serem percebidos por seus usuários e podem, em alguns casos, até mesmo serem invisíveis para eles. Este artigo informa como procurar qualquer um dos sete sinais (indicadores de comprometimento) listados abaixo. Se você encontrar qualquer um desses, precisará tomar medidas de correção.

- **Indicadores do comprometimento de regras:**
  - Ação de Regra é iniciar um aplicativo.
  - Referências de regra a EXE, ZIP ou URL.
  - No computador local, procure novas iniciações de processo que se originam do Outlook PID.

- **Indicadores dos formulários personalizados comprometem**:
  - Formulários personalizados presentes salvos como sua própria classe de mensagem.
  - A classe Message contém código executável.
  - Normalmente, os formulários mal-intencionados são armazenados em pastas da Biblioteca de Formulários Pessoais ou da Caixa de Entrada.
  - O formulário é denominado IPM. Observação. [nome personalizado].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Etapas para encontrar sinais desse ataque e confirmá-lo

Você pode usar um dos seguintes métodos para confirmar o ataque:

- Examine manualmente as regras e formulários de cada caixa de correio usando o cliente do Outlook. Esse método é completo, mas você só pode verificar uma caixa de correio por vez. Esse método pode ser muito demorado se você tiver muitos usuários para verificar e também pode infectar o computador que você está usando.

- Use o [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) do PowerShell para despejar automaticamente todas as regras de encaminhamento de email e formulários personalizados para todos os usuários em sua área de espera. Este é o método mais rápido e mais seguro com a menor quantidade de sobrecarga.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confirmar o Ataque de Regras Usando o cliente do Outlook

1. Abra o cliente do Outlook dos usuários como o usuário. O usuário pode precisar de sua ajuda para examinar as regras em sua caixa de correio.

2. Consulte [Gerenciar mensagens de email usando o artigo regras](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para os procedimentos sobre como abrir a interface de regras no Outlook.

3. Procure regras que o usuário não criou, ou quaisquer regras ou regras inesperadas com nomes suspeitos.

4. Procure na descrição da regra ações de regra que iniciam e solicitam ou se referem a um . EXE, . Arquivo ZIP ou para iniciar uma URL.

5. Procure por novos processos que comecem a usar a ID do processo do Outlook. Consulte [Find the Process ID](/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Etapas para confirmar o ataque forms usando o cliente do Outlook

1. Abra o cliente do Outlook do usuário como o usuário.

2. Siga as etapas em, [Mostrar a guia Desenvolvedor](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) para a versão do usuário do Outlook.

3. Abra a guia desenvolvedor agora visível no Outlook e clique **em projetar um formulário**.

4. Selecione a **Caixa de Entrada** na lista **Procurar.** Procure por formulários personalizados. Formulários personalizados são raros o suficiente para que, se você tiver formulários personalizados, vale uma olhada mais profunda.

5. Investigue quaisquer formulários personalizados, especialmente aqueles marcados como ocultos.

6. Abra quaisquer formulários personalizados e, no grupo **Formulário,** clique em **Exibir Código** para ver o que é executado quando o formulário é carregado.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Etapas para confirmar o ataque Regras e Formulários usando o PowerShell

A maneira mais simples de verificar um ataque [](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) de regras ou formulários personalizados é executar o scriptGet-AllTenantRulesAndForms.ps1PowerShell. Esse script se conecta a todas as caixas de correio em seu locatário e despeja todas as regras e formulários em dois arquivos .csv.

#### <a name="pre-requisites"></a>Pré-requisitos

Você precisará ter direitos de administrador global para executar o script porque o script se conecta a todas as caixas de correio no local para ler as regras e formulários.

1. Entre no computador de onde você executará o script com direitos de administrador local.

2. Baixe ou copie o Get-AllTenantRulesAndForms.ps1 do GitHub para uma pasta da qual você o executará. O script criará dois arquivos carimbados de data para esta pasta, MailboxFormsExport-yyyy-mm-dd.csv e MailboxRulesExport-yyyy-mm-dd.csv.

3. Abra uma instância do PowerShell como administrador e abra a pasta na que você salvou o script.

4. Execute esta linha de comando do PowerShell da seguinte `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretando a saída

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine as regras (uma por linha) para as condições de ação que incluem aplicativos ou executáveis:

  - **ActionType (coluna A)**: Se você vir o valor "ID_ACTION_CUSTOM", a regra provavelmente será mal-intencionada.

  - **IsPotentiallyMalicious (coluna D)**: Se esse valor for "VERDADEIRO", a regra provavelmente será mal-intencionada.

  - **ActionCommand (coluna G)**: Se essa coluna lista um aplicativo ou qualquer arquivo com extensões .exe ou .zip ou uma entrada desconhecida que se refere a uma URL, a regra provavelmente será mal-intencionada.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: Em geral, o uso de formulários personalizados é raro. Se você encontrar alguma nesta caixa de trabalho, abra a caixa de correio desse usuário e examine o próprio formulário. Se sua organização não o colocou intencionalmente, provavelmente será mal-intencionado.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Como parar e remediar o ataque de Regras e Formulários do Outlook

Se você encontrar qualquer evidência de um desses ataques, a correção será simples, basta excluir a regra ou o formulário da caixa de correio. Você pode fazer isso com o cliente do Outlook ou usando o PowerShell remoto para remover regras.

### <a name="using-outlook"></a>Usando o Outlook

1. Identifique todos os dispositivos que o usuário usou com o Outlook. Todos eles precisarão ser limpos de malware em potencial. Não permita que o usuário entre e use email até que todos os dispositivos sejam limpos.

2. Siga as etapas em [Excluir uma regra](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) para cada dispositivo.

3. Se você não tiver certeza sobre a presença de outro malware, poderá formatar e reinstalar todo o software no dispositivo. Para dispositivos móveis, você pode seguir as etapas do fabricante para redefinir o dispositivo para a imagem de fábrica.

4. Instale as versões mais atualizadas do Outlook. Lembre-se de que a versão atual do Outlook bloqueia os dois tipos desse ataque por padrão.

5. Depois que todas as cópias offline da caixa de correio foram removidas, redefina a senha do usuário (use uma de alta qualidade) e siga as etapas em Configurar autenticação [multifatória](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) para usuários se o MFA ainda não tiver sido habilitado. Isso garante que as credenciais do usuário não sejam expostas por outros meios (como phishing ou re-uso de senha).

### <a name="using-powershell"></a>Usando o PowerShell

Há dois cmdlets remotos do PowerShell que você pode usar para remover ou desabilitar regras perigosas. Basta seguir as etapas.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Etapas para caixas de correio que estão em um servidor Exchange

1. Conecte-se ao servidor Exchange usando o PowerShell remoto. Siga as etapas em [Conectar-se a servidores Exchange usando o PowerShell remoto.](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Se você quiser remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-InboxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Se você quiser manter a regra e seu conteúdo para investigação posterior, use o cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Etapas para caixas de correio no Exchange Online

1. Siga as etapas em [Conectar-se ao Exchange Online usando o PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Se você quiser remover completamente uma única regra, várias regras ou todas as regras de uma caixa de correio, use o cmdlet [Remove-Inbox Rule.](/powershell/module/exchange/Remove-InboxRule)

3. Se você quiser manter a regra e seu conteúdo para investigação posterior, use o cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Como minimizar ataques futuros

### <a name="first-protect-your-accounts"></a>Primeiro: proteja suas contas

As explorações de Regras e Formulários só são usadas por um invasor depois de roubar ou violar uma das contas do usuário. Portanto, sua primeira etapa para impedir o uso dessas explorações contra sua organização é proteger agressivamente suas contas de usuário. Algumas das maneiras mais comuns pelas quais as contas são violadas são por meio de ataques de phishing ou [pulverização de senha.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

A melhor maneira de proteger suas contas de usuário e, especialmente, suas contas de administrador, é configurar a [autenticação multifa factor para os usuários.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Você também deve:

- Monitore como suas contas de usuário são [acessadas e usadas.](/azure/active-directory/active-directory-view-access-usage-reports) Você pode não impedir a violação inicial, mas reduzirá a duração e o impacto da violação detectando-a mais cedo. Você pode usar essas políticas de Segurança de Aplicativos na Nuvem do [Office 365](/cloud-app-security/what-is-cloud-app-security) para monitorar suas contas e alertar sobre atividades incomuns:

  - **Várias tentativas de logon** com falha: essa política faz perfis de seu ambiente e dispara alertas quando os usuários executam várias atividades de logon com falha em uma única sessão em relação à linha de base aprendida, o que pode indicar uma tentativa de violação.

  - **Viagem impossível**: essa política faz perfis de seu ambiente e dispara alertas quando as atividades são detectadas do mesmo usuário em locais diferentes em um período de tempo menor do que o tempo de viagem esperado entre os dois locais. Isso pode indicar que um usuário diferente está usando as mesmas credenciais. Detectar esse comportamento anômalo requer um período de aprendizado inicial de sete dias durante o qual ele aprende o novo padrão de atividade do usuário.

  - Atividade representação incomum **(por usuário)**: essa política faz perfis de seu ambiente e dispara alertas quando os usuários executam várias atividades personificados em uma única sessão em relação à linha de base aprendida, o que pode indicar uma tentativa de violação.

- Use uma ferramenta como a Pontuação Segura do [Office 365](https://securescore.office.com/) para gerenciar configurações e comportamentos de segurança da conta.

### <a name="second-keep-your-outlook-clients-current"></a>Segundo: mantenha seus clientes do Outlook atualizados

Versões totalmente atualizadas e corrigidas do Outlook 2013 e 2016 desabilitam a ação de regra/formulário "Iniciar Aplicativo" por padrão. Isso garantirá que, mesmo que um invasor viole a conta, as ações de regra e formulário serão bloqueadas. Você pode instalar as atualizações mais recentes e os patches de segurança seguindo as etapas em [Instalar atualizações do Office.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Aqui estão as versões de patch para seus clientes do Outlook 2013 e 2016:

- **Outlook 2016**: 16.0.4534.1001 ou superior.

- **Outlook 2013**: 15.0.4937.1000 ou superior.

Para obter mais informações sobre os patches de segurança individuais, consulte:

- [Patch de Segurança do Outlook 2016](https://support.microsoft.com/help/3191883)

- [Patch de Segurança do Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Terceiro: Monitorar seus clientes do Outlook

Observe que, mesmo com os patches e atualizações instalados, é possível que um invasor altere a configuração do computador local para habilitar o comportamento "Iniciar Aplicativo". Você pode usar o [Gerenciamento Avançado de Política de Grupo](/microsoft-desktop-optimization-pack/agpm/) para monitorar e impor políticas de máquina local em seus clientes.

Você pode ver se "Iniciar Aplicativo" foi reabilitar por meio de uma substituição no Registro usando as informações em Como exibir o registro do sistema usando versões de [64 bits](https://support.microsoft.com/help/305097)do Windows . Verifique estas sub-chaves:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Procure a chave EnableUnsafeClientMailRules. Se ele estiver lá e estiver definido como 1, o patch de segurança do Outlook foi substituído e o computador está vulnerável ao ataque Form/Rules. Se o valor for 0, a ação "Iniciar Aplicativo" será desabilitada. Se a versão atualizada e corrigida do Outlook estiver instalada e essa chave do Registro não estiver presente, um sistema não estará vulnerável a esses ataques.

Os clientes com instalações locais do Exchange devem considerar o bloqueio de versões mais antigas do Outlook que não têm patches disponíveis. Detalhes sobre esse processo podem ser encontrados no artigo [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários. Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias. Elas têm efeito imediato e são de baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também:

- [As Regras mal-intencionadas](https://silentbreaksecurity.com/malicious-outlook-rules/) do Outlook pelo SilentBreak Security Post sobre o Vetor de Regras fornece uma revisão detalhada de como as Regras do Outlook.

- [MAPI sobre HTTP e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) no blog do Sensepost sobre Mailrule Pwnage discute uma ferramenta chamada Ruler que permite explorar caixas de correio por meio de regras do Outlook.

- [Formulários e shells do Outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) no blog sensepost sobre o Vetor de Ameaças de Formulários.

- [Base de código de régua](https://github.com/sensepost/ruler)

- [Indicadores de comprometimento de régua](https://github.com/sensepost/notruler/blob/master/iocs.md)