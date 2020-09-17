---
title: As 10 maneiras principais de proteger os planos do Microsoft 365 for Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Proteja seus emails e dados de negócios contra ameaças da Cyber, incluindo ransomware, phishing e anexos mal-intencionados. '
ms.openlocfilehash: c78e65e9a466fe8b95e83fa1791dd8f09fa0c541
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948731"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>As 10 maneiras principais de proteger os planos do Microsoft 365 for Business

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Se você é uma organização pequena ou média, usando um dos planos de negócios da Microsoft e seu tipo de organização é direcionado a criminosos virtuais e hackers, use as orientações deste artigo para aumentar a segurança da sua organização. Esta orientação ajuda sua organização a atingir as metas descritas no manual de [campanha do cybersecurity da](https://go.microsoft.com/fwlink/p/?linkid=2015598)faculdade do Harvard Kennedy.

A Microsoft recomenda que você conclua as tarefas listadas na tabela a seguir que se aplicam ao seu plano de serviço.

||Tarefas|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1 |[Configurar autenticação multifatorial](secure-your-business-data.md#setup)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[Treinar os usuários](secure-your-business-data.md#train)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3 |[Usar contas de administrador dedicadas](secure-your-business-data.md#admin)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Aumentar o nível de proteção contra malware no email](secure-your-business-data.md#malware)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Proteção contra ransomware](secure-your-business-data.md#ransomware)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Parar o encaminhamento automático para email](secure-your-business-data.md#forwarding)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Usar a criptografia de mensagem do Office](secure-your-business-data.md#encryption)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Proteger seu email contra ataques de phishing](secure-your-business-data.md#phishing)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Proteger contra anexos e arquivos mal-intencionados com anexos seguros de ATP](secure-your-business-data.md#atp)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[Proteger contra ataques de phishing com links seguros de ATP](secure-your-business-data.md#phishingatp)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Antes de começar, verifique sua pontuação de segurança do [microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) na central de segurança do Microsoft 365. A partir de um painel centralizado, você pode monitorar e aprimorar a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365. Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança (como exibir relatórios) ou endereçar recomendações com aplicativos ou software de terceiros. Com informações adicionais e mais visibilidade de um conjunto mais amplo de produtos e serviços da Microsoft, você pode se sentir com o relatório de confiança sobre a integridade de segurança da sua organização.

![Captura de tela da Pontuação segura da Microsoft](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: configurar a autenticação multifator
<a name="setup"> </a>

O uso da autenticação multifator é uma das maneiras mais fáceis e eficazes de aumentar a segurança da sua organização. É mais fácil do que parece, quando você faz logon, a autenticação multifator significa que você digitará um código de seu telefone para obter acesso ao Microsoft 365. Isso pode impedir que hackers assumam o controle se souberem sua senha. A autenticação multifator também é chamada de verificação em duas etapas. As pessoas podem adicionar a verificação em duas etapas à maioria das contas com facilidade, por exemplo, às contas do Google ou do Microsoft. Confira aqui como [Adicionar a verificação em duas etapas à sua conta pessoal da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=2016403).

Para empresas que usam o Microsoft 365, adicione uma configuração que exija que os usuários façam logon usando a autenticação multifator. Quando você fizer essa alteração, os usuários serão solicitados a configurar seu telefone para a autenticação de dois fatores na próxima vez em que fizerem logon.
Para ver um vídeo de treinamento sobre como configurar a MFA e como os usuários concluem a configuração, consulte [set up MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) and [User set up](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225).

Para configurar a autenticação multifator, ative os padrões de segurança:

Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança adicional de entrada. Para saber mais, confira [Quais são os padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se a sua assinatura for nova, os padrões de Segurança já poderão estar habilitados para você automaticamente.

Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.

1. Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.
2. Na barra de navegação à esquerda, escolha **Mostrar Tudo** e em **Centro de administração**, escolha ** Azure Active Directory**.
3. No **centro de administração do Azure Active Directory** escolha **Azure Active Directory** > **Propriedades**.
4. Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
5. Clique em **Sim** para habilitar os padrões de segurança ou **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

Após configurar a autenticação multifator da sua organização, os usuários precisarão configurar a verificação em duas etapas em seus dispositivos. Para obter mais informações, consulte [Configurar a verificação em duas etapas para o Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

Para obter detalhes completos e recomendações completas, consulte [Configurar a autenticação multifator para usuários](set-up-multi-factor-authentication.md).

## <a name="2-train-your-users"></a>2: treinar os usuários
<a name="train"> </a>

O [manual de campanha](https://go.microsoft.com/fwlink/p/?linkid=2015598) da Harvard Kennedy School cybersecurity fornece orientações excelentes sobre o estabelecimento de uma grande cultura de reconhecimento de segurança em sua organização, incluindo o treinamento de usuários para identificar ataques de phishing.

Além desta orientação, a Microsoft recomenda que os usuários executem as ações descritas neste artigo: [proteja sua conta e seus dispositivos contra hackers e malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Essas ações incluem:

- Usando senhas fortes

- Protegendo dispositivos

- Habilitar recursos de segurança nos PCs com Windows 10 e Mac

A Microsoft também recomenda que os usuários protejam suas contas de email pessoais executando as ações recomendadas nos seguintes artigos:

- [Ajudar a proteger sua conta de email do Outlook.com](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Proteger sua conta do Gmail com a verificação em duas etapas](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: usar contas de administrador dedicadas
<a name="admin"> </a>

As contas administrativas que você usa para administrar seu ambiente do Microsoft 365 incluem privilégios elevados. Estes são alvos valiosos para hackers e criminosos virtuais. Use contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e só usarem a conta administrativa, quando necessário, para concluir uma tarefa associada à função de trabalho. Recomendações adicionais:

- Certifique-se de que as contas de administrador também estão definidas para a autenticação multifator.

- Antes de usar contas de administrador, feche todas as sessões de navegador não relacionadas e aplicativos, incluindo contas de email pessoais.

- Após concluir as tarefas de administração, não deixe de fazer logout da sessão do navegador.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: elevar o nível de proteção contra malware no email
<a name="malware"> </a>

Seu ambiente do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção, bloqueando anexos com tipos de arquivo comumente usados para malware. Para resumir a proteção contra malware em email, veja um [pequeno vídeo de treinamento](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)ou conclua as seguintes etapas:

1. Acesse <https://protection.office.com> e entre com suas credenciais de conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação à esquerda, em **Gerenciamento de ameaças**, escolha **política** \> **anti-malware**.

3. Clique duas vezes na política padrão para editar a política em toda a empresa.

4. Selecione **Configurações**.

5. Em **filtro tipos de anexo comuns**, selecione **ativado**. Os tipos de arquivo bloqueados são listados na janela diretamente abaixo desse controle. Você pode adicionar ou excluir tipos de arquivo posteriormente, se necessário.

6. Selecione **salvar.**

Para obter mais informações, consulte [proteção Antimalware no EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="5-protect-against-ransomware"></a>5: proteger contra o ransomware
<a name="ransomware"> </a>

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueando telas de computador. Em seguida, tenta extort dinheiro de vítimas solicitando "resgate", geralmente na forma de cryptocurrencies como Bitcoin, no Exchange para acessar os dados.

Você pode se proteger contra o ransomware criando uma ou mais regras de fluxo de emails para bloquear extensões de arquivo comumente usadas para ransomware ou avisar os usuários que recebem esses anexos por email. Um bom ponto de partida é criar duas regras:

- Avisar os usuários antes de abrir os anexos de arquivo do Office que incluem macros. O ransomware pode ser oculto dentro de macros, portanto, avisaremos os usuários para não abrir esses arquivos de pessoas que eles não conhecem.

- Bloquear tipos de arquivo que podem conter ransomware ou outro código mal-intencionado. Começaremos com uma lista comum de executáveis (listados na tabela abaixo). Se sua organização usa qualquer um desses tipos de executáveis e você espera que eles sejam enviados por email, adicione-os à regra anterior (avisar os usuários).

Para criar uma regra de transporte de email, exiba um [vídeo de treinamento curto](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)ou conclua as seguintes etapas:

1. Vá até o [Centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Na categoria **fluxo de emails** , selecione **regras**.

3. Selecione **+** e, em seguida, **crie uma nova regra**.

4. Selecione * * * * na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplicar as configurações na tabela a seguir para cada regra. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.
    
| Configuração | Avisar os usuários antes de abrir anexos de arquivos do Office | Bloquear tipos de arquivo que podem conter ransomware ou outro código mal-intencionado |
|:-----|:-----|:-----|
|Nome  <br/> |Regra anti-ransomware: avisar os usuários  <br/> |Regra anti-ransomware: bloquear tipos de arquivo  <br/> |
|Aplicar esta regra se. . .  <br/> |Qualquer anexo. . . correspondências de extensão de arquivo. . .  <br/> |Qualquer anexo. . . correspondências de extensão de arquivo. . .  <br/> |
|Especificar palavras ou frases  <br/> |Adicione estes tipos de arquivos:  <br/> dotm, docm, xlsm, sltm, xla, xlam, XLL, pptm, potm, ppam, ppsm, sldm  <br/> |Adicione estes tipos de arquivos:  <br/> Ade, ADP, Ani, Bas, bat, CHM, cmd, com, CPL, CRT, HLP, HT, HTA, inf, ins, ISP, Job, js, jse, lnk, o mdb, o MDE, o registro, o MSC, o (a) msp, o. exe, o, o, o VB, vbe, vbs,  <br/> |
|Faça o seguinte. . .  <br/> |Preceder um aviso de isenção  <br/> |Bloquear a mensagem. . . rejeitar a mensagem e incluir uma explicação  <br/> |
|Fornecer texto da mensagem  <br/> |Não abra esses tipos de arquivos, a menos que você esteja esperando eles — porque os arquivos podem conter código mal-intencionado e saber que o remetente não é uma garantia de segurança.  <br/> ||
   
> [!TIP]
> Você também pode adicionar os arquivos que deseja bloquear à lista Antimalware na [etapa 4](#4-raise-the-level-of-protection-against-malware-in-mail).

Para saber mais, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar o OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: parar o encaminhamento automático para email
<a name="forwarding"> </a>

Hackers que obtêm acesso à caixa de correio de um usuário podem Exfiltrate emails Configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode evitar que isso aconteça Configurando uma regra de fluxo de emails.

Para criar uma regra de transporte de emails:

1. Vá até o [Centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Na categoria **fluxo de emails** , selecione **regras**.

3. Selecione **+** e, em seguida, **crie uma nova regra**.

4. Selecione **mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplicar as configurações na tabela a seguir. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.

|Configuração|Rejeitar emails de encaminhamento automático para domínios externos|
|---|---|
|Nome|Impedir o encaminhamento automático de emails para domínios externos|
|Aplicar esta regra se...|O remetente. . . é externo/interno. . . Dentro da organização|
|Adicionar condição|O destinatário. . . é externo/interno. . . Fora da organização|
|Adicionar condição|As propriedades da mensagem. . . inclua o tipo de mensagem. . . Avanço automático|
|Faça o seguinte...|Bloquear a mensagem. . . rejeitar a mensagem e incluir uma explicação.|
|Fornecer texto da mensagem|O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.|

## <a name="7-use-office-message-encryption"></a>7: usar a criptografia de mensagem do Office
<a name="encryption"> </a>

A criptografia de mensagem do Office está incluída no Microsoft 365. Já está configurada. Com a criptografia de mensagem do Office, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A criptografia de mensagem do Office 365 funciona com o Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagens de email ajuda a garantir que somente os destinatários pretendidos possam exibir o conteúdo da mensagem.

A criptografia de mensagem do Office fornece duas opções de proteção ao enviar emails:

- Não encaminhar

- EFS

Sua organização pode ter configurado opções adicionais que aplicam um rótulo a emails, como confidenciais.

### <a name="to-send-protected-email"></a>Para enviar email protegido

No Outlook para computador, selecione **Opções** no email e, em seguida, escolha **permissões**.

![Criptografia de mensagem de email no Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

No Outlook.com, selecione **proteger** no email. A proteção padrão **não é encaminhada**. Para alterar isso para criptografar, selecione **alterar permissões** \> **criptografar**.

![Criptografia de mensagem de email no Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Para receber emails criptografados

Se o destinatário tiver o Outlook 2013 ou o Outlook 2016 e uma conta de email da Microsoft, verá um alerta sobre as permissões restritas do item no painel de leitura. Após abrir a mensagem, o destinatário pode exibir a mensagem como qualquer outra.

Se o destinatário estiver usando outro cliente de email ou conta de email, como o Gmail ou o Yahoo, ele verá um link que permite que eles entrem em ler a mensagem de email ou solicitar uma senha de uso único para exibir a mensagem em um navegador da Web. Se os usuários não estiverem recebendo o email, peça que eles confiram a pasta spam ou lixo eletrônico.

Para obter mais informações, consulte [enviar, exibir e responder a mensagens criptografadas no Outlook para PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. proteger seu email contra ataques de phishing
<a name="phishing"> </a>

Se você configurou um ou mais domínios personalizados para seu ambiente do Microsoft 365, é possível configurar a proteção antiphishing dirigida. A proteção antiphishing da ATP, parte da proteção avançada contra ameaças do Office 365, pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não é necessário fazer isso.

Recomendamos que você comece a usar essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado.

![Criar uma política anti-phishing do ATP](../../media/security-and-compliance-center.png)

Para criar uma política anti-phishing do ATP, exiba um [vídeo de treinamento curto](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com>.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, selecione **política**.

3. Na página política, selecione a **ATP anti-phishing**.

4. Na página anti-phishing, selecione **+ criar**. Um assistente é iniciado que orienta você na definição da política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política, conforme recomendado na tabela abaixo. Consulte [saiba mais sobre as opções de política de anti-phishing do ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) para obter mais detalhes.

6. Depois de revisar suas configurações, selecione **criar esta política** ou **salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|O domínio e a equipe de campanha mais valiosa|
|Descrição|Garantir que a equipe mais importante e nosso domínio não estão sendo representados.|
|Adicionar usuários a proteger|Selecione **+ Adicionar uma condição, o destinatário é**. Digite nomes de usuário ou insira o endereço de email do candidato, o gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que você deseja proteger da representação.|
|Adicionar domínios para proteger|Selecione **+ Adicionar uma condição, o domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você tiver definido um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário representado: selecione **redirecionar mensagem para outro endereço de email**e digite o endereço de email do administrador de segurança; por exemplo, securityadmin@contoso.com. <br/> Se o email for enviado por um domínio representado: selecione **mensagem de quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Neste exemplo, não defina nenhuma substituição.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, contoso.com, na lista e selecione **Adicionar**. Selecione **Concluído**.|
|

Para obter mais informações, consulte [set up Office 365 ATP anti-phishing Policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).

## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: proteger contra anexos e arquivos mal-intencionados com anexos seguros de ATP
<a name="atp"> </a>

Pessoas costumam enviar, receber e compartilhar anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil dizer se um anexo é seguro ou mal-intencionado apenas olhando uma mensagem de email. O Office 365 proteção avançada contra ameaças inclui proteção de anexo seguro de ATP, mas essa proteção não é ativada por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Esta proteção estende-se aos arquivos no SharePoint, no OneDrive e no Microsoft Teams.

Para criar uma política de anexo seguro de ATP, veja um [breve vídeo de treinamento](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou Complete as seguintes etapas:

1. Acesse <https://protection.office.com> e entre com sua conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, selecione **política**.

3. Na página política, selecione **anexos seguros de ATP**.

4. Na página de anexos seguros, aplique essa proteção amplamente marcando a caixa de seleção **ativar a ATP para SharePoint, onedrive e Microsoft Teams** .

5. Selecione **+** para criar uma nova política.

6. Aplicar as configurações na tabela a seguir.

7. Depois de revisar suas configurações, selecione **criar esta política** ou **salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Bloquear emails atuais e futuros com malware detectado.|
|Descrição|Bloquear emails e anexos atuais e futuros com malware detectado.|
|Salvar anexos resposta desconhecida de malware|Selecione **Bloquear – bloquear emails e anexos atuais e futuros com malware detectado**.|
|Redirecionar o anexo na detecção|Habilitar o redirecionamento (Selecione esta caixa) <br/> Insira a conta de administrador ou uma configuração de caixa de correio para quarentena. <br/> Aplica a seleção acima se a verificação de malware por anexos expira ou quando ocorre um erro (Selecione esta caixa).|
|Aplicado a|O domínio do destinatário é. . . Selecione seu domínio.|
|

Para obter mais informações, consulte [set up Office 365 ATP anti-phishing Policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).

## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: proteger contra ataques de phishing com links seguros de ATP
<a name="phishingatp"> </a>

Os hackers às vezes ocultam sites mal-intencionados em links em email ou outros arquivos. Os links seguros de ATP do Office 365 (links seguros de ATP), parte da proteção avançada contra ameaças do Office 365, podem ajudar a proteger sua organização fornecendo a verificação de tempo de clique de endereços Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio das políticas de links seguros de ATP.

Recomendamos que você faça o seguinte:

- Modificar a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para obter links seguros de ATP, exiba um [vídeo de treinamento curto](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:

1. Acesse <https://protection.office.com> e entre com sua conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, selecione **política**.

3. Na página política, selecione **links seguros de ATP**.

Para modificar a política padrão:

1. Na página de links seguros, em **políticas que se aplicam a toda a organização**, clique duas vezes na política **padrão** .

2. Em **configurações que se aplicam ao conteúdo no Office 365**, insira uma URL a ser bloqueada, como _example.com_e selecione **+** .

3. Em **configurações que se aplicam ao conteúdo exceto email**, selecione **aplicativos do Office 365**, não **rastreie quando os usuários clicam em links seguros**e **não permitem que os usuários cliquem em links seguros para a URL original**.

4. Clique em **Salvar**.

Para criar uma nova política direcionada para todos os destinatários em seu domínio:

1. Na página de links seguros, em **políticas que se aplicam a destinatários específicos**, selecione **+** para criar uma nova política.

2. Aplicar as configurações listadas na tabela a seguir.

3. Clique em **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Política de links seguros para todos os destinatários no domínio|
|Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens|Selecione as **URLs que serão reconfiguradas e verificadas em relação a uma lista de links mal-intencionados conhecidos quando o usuário clicar no link**.|
|Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos|Selecione essa caixa.|
|Aplicado a|O domínio do destinatário é. . . Selecione seu domínio.|
|

Para obter mais informações, consulte [links seguros no Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).
