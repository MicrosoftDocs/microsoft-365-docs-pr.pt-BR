---
title: Top 10 maneiras de proteger Microsoft 365 para planos de negócios
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: Proteja seus emails e dados de negócios contra ameaças cibernéticas, incluindo ransomware, phishing e anexos mal-intencionados.
ms.openlocfilehash: b274bb6bcdf71641ff8b196921a501bae9cbba28
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635957"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Top 10 maneiras de proteger Microsoft 365 para planos de negócios

Se você for uma organização de pequeno ou médio porte usando um dos planos de negócios da Microsoft e seu tipo de organização for direcionado por criminosos cibernéticos e hackers, use as diretrizes neste artigo para aumentar a segurança da sua organização. Essas diretrizes ajudam sua organização a atingir as metas descritas no Manual da Campanha de [Segurança Cibernética](https://go.microsoft.com/fwlink/p/?linkid=2015598)da Escola De Harvard.

A Microsoft recomenda que você conclua as tarefas listadas na tabela a seguir que se aplicam ao seu plano de serviço.

||Tarefa|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[Configurar autenticação multifatorial](secure-your-business-data.md#setup)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Treinar os usuários](secure-your-business-data.md#train)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Usar contas de administrador dedicadas](secure-your-business-data.md#admin)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Aumentar o nível de proteção contra malware no email](secure-your-business-data.md#malware)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Proteção contra ransomware](secure-your-business-data.md#ransomware)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Parar o encaminhamento automático para email](secure-your-business-data.md#forwarding)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Usar Office criptografia de mensagem](secure-your-business-data.md#encryption)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Proteger seu email contra ataques de phishing](secure-your-business-data.md#phishing)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Proteger contra anexos e arquivos mal-intencionados com Cofre Anexos](secure-your-business-data.md#atp)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[Proteger contra ataques de phishing com Cofre Links](secure-your-business-data.md#phishingatp)||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Se você tem o Microsoft Business Premium, a maneira mais rápida para configurar a segurança e iniciar a colaborar com segurança é seguir as orientações nesta biblioteca:[Microsoft 365 para pequenas empresas e campanhas](../../campaigns/index.md). Essa diretriz foi criada em parceria com a equipe do Microsoft Defendering Democracy para proteger todos os clientes de pequenas empresas contra ameaças cibernéticas iniciadas por hackers sofisticados.

Antes de começar, verifique sua [Microsoft 365 Pontuação Segura](../../security/defender/microsoft-secure-score.md) no centro Microsoft 365 segurança. Em um painel centralizado, você pode monitorar e melhorar a segurança de suas identidades Microsoft 365, dados, aplicativos, dispositivos e infraestrutura. Você recebe pontos para configurar recursos de segurança recomendados, executar tarefas relacionadas à segurança (como exibir relatórios) ou endereçamento de recomendações com um aplicativo ou software de terceiros. Com informações adicionais e mais visibilidade sobre um conjunto mais amplo de produtos e serviços da Microsoft, você pode sentir relatórios confiantes sobre a saúde de segurança da sua organização.

![Captura de tela da Pontuação Segura da Microsoft](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Configurar a autenticação multifa factor
<a name="setup"> </a>

O uso da autenticação multifaionária é uma das maneiras mais fáceis e eficazes de aumentar a segurança da sua organização. É mais fácil do que parece - quando você faz logoff, a autenticação multifafação significa que você digitará um código do telefone para obter acesso ao Microsoft 365. Isso pode impedir que os hackers assumiam o controle se eles conhecem sua senha. A autenticação multifa factor também é chamada de verificação em duas etapas. Os indivíduos podem adicionar verificação em duas etapas à maioria das contas facilmente, por exemplo, às contas do Google ou da Microsoft. Veja como adicionar verificação [em duas etapas à sua conta pessoal da Microsoft.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

Para empresas que usam Microsoft 365, adicione uma configuração que exija que os usuários faça logoff usando a autenticação multifa factor. Quando você fizer essa alteração, os usuários serão solicitados a configurar seu telefone para autenticação de dois fatores na próxima vez que fizerem logoff.
Para ver um vídeo de treinamento sobre como configurar o MFA e como os usuários concluem a configuração, consulte [configurar o MFA](../../business-video/turn-on-mfa.md) e [a configuração do usuário](../../business-video/set-up-mfa.md).

Para configurar a autenticação multifatente, você a ativará os padrões de segurança:

Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança adicional de entrada. Para saber mais, confira [Quais são os padrões de segurança?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se a sua assinatura for nova, os padrões de Segurança já poderão estar habilitados para você automaticamente.

Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.

1. Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.
2. Na barra de navegação à esquerda, escolha **Mostrar Tudo** e em **Centro de administração**, escolha **Azure Active Directory**.
3. No **centro de administração do Azure Active Directory** escolha **Azure Active Directory** > **Propriedades**.
4. Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
5. Clique em **Sim** para habilitar os padrões de segurança ou **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

Após configurar a autenticação multifator da sua organização, os usuários precisarão configurar a verificação em duas etapas em seus dispositivos. Para obter mais informações, [consulte Set up 2-step verification for Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).

Para obter detalhes completos e recomendações completas, consulte [Set up multi-factor authentication for users](set-up-multi-factor-authentication.md).

## <a name="2-train-your-users"></a>2: Treinar seus usuários
<a name="train"> </a>

O Manual de Campanha de [Segurança](https://go.microsoft.com/fwlink/p/?linkid=2015598) Cibernética da Escola De Harvard Kennedy fornece excelentes diretrizes sobre como estabelecer uma forte cultura de reconhecimento de segurança em sua organização, incluindo treinamento para que os usuários identifiquem ataques de phishing.

Além dessas orientações, a Microsoft recomenda que seus usuários tomem as ações descritas neste artigo: Proteger sua conta e dispositivos [contra hackers e malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Essas ações incluem:

- Usando senhas fortes

- Protegendo dispositivos

- Habilitando recursos de segurança em computadores Windows 10 e Mac

A Microsoft também recomenda que os usuários protejam suas contas de email pessoais, seguindo as ações recomendadas nos seguintes artigos:

- [Ajudar a proteger sua conta de email Outlook.com](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Proteger sua conta do Gmail com verificação em duas etapas](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Usar contas de administrador dedicadas
<a name="admin"> </a>

As contas administrativas que você usa para administrar seu ambiente Microsoft 365 incluem privilégios elevados. Esses são alvos valiosos para hackers e criminosos cibernéticos. Use contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e usar somente sua conta administrativa quando necessário para concluir uma tarefa associada à função de trabalho. Recomendações adicionais:

- Certifique-se de que as contas de administrador também estão configuradas para autenticação multifa factor.

- Antes de usar contas de administrador, feche todas as sessões e aplicativos do navegador não relacionados, incluindo contas de email pessoais.

- Depois de concluir as tarefas de administrador, certifique-se de sair da sessão do navegador.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: aumentar o nível de proteção contra malware no email
<a name="malware"> </a>

Seu Microsoft 365 ambiente inclui proteção contra malware, mas você pode aumentar essa proteção bloqueando anexos com tipos de arquivo que são comumente usados para malware. Para levantar a proteção contra malware no email, veja um breve vídeo [de](../../business-video/anti-malware.md)treinamento ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com> e entre com suas credenciais de conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento de ameaças, **escolha** **Política** \> **Anti-Malware**.

3. Clique duas vezes na política padrão para editar essa política em toda a empresa.

4. Selecione **Configurações**.

5. Em **Filtro tipos de anexo comuns,** selecione **Em**. Os tipos de arquivo bloqueados estão listados na janela diretamente abaixo desse controle. Você pode adicionar ou excluir tipos de arquivo mais tarde, se necessário.

6. Selecione **Salvar.**

Para obter mais informações, consulte [Proteção anti-malware no EOP](../../security/office-365-security/anti-malware-protection.md).

## <a name="5-protect-against-ransomware"></a>5: Proteger contra ransomware
<a name="ransomware"> </a>

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueio de telas de computador. Em seguida, ele tenta roubar dinheiro das vítimas solicitando "resgate", geralmente em forma de criptocurrencies como o Bitcoin, em troca de acesso a dados.

Você pode se proteger contra ransomware criando uma ou mais regras de fluxo de emails para bloquear extensões de arquivo que são comumente usadas para ransomware ou para avisar os usuários que recebem esses anexos por email. Um bom ponto de partida é criar duas regras:

- Avisar os usuários antes de Office anexos de arquivo que incluem macros. O ransomware pode estar oculto dentro de macros, portanto, avisaremos os usuários para não abrirem esses arquivos de pessoas que não conhecem.

- Bloquear tipos de arquivo que podem conter ransomware ou outro código mal-intencionado. Vamos começar com uma lista comum de executáveis (listada na tabela abaixo). Se a sua organização usa qualquer um desses tipos executáveis e você espera que eles sejam enviados por email, adicione-os à regra anterior (avisar os usuários).

Para criar uma regra de transporte de email, veja um [vídeo de](../../business-video/prevent-ransom-in-email.md)treinamento curto ou conclua as seguintes etapas:

1. Vá até o [Centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Na categoria **fluxo de emails,** selecione **regras**.

3. Selecione **+** e crie uma nova **regra.**

4. Selecione **** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir para cada regra. Deixe o restante das configurações no padrão, a menos que você queira alterá-los.

6. Selecione **Salvar**.
    
| Configuração | Avisar os usuários antes de abrir anexos Office arquivos | Bloquear tipos de arquivo que podem conter ransomware ou outro código mal-intencionado |
|:-----|:-----|:-----|
|Nome  <br/> |Regra anti-ransomware: avisar os usuários  <br/> |Regra anti-ransomware: bloquear tipos de arquivo  <br/> |
|Aplicar essa regra se . . .  <br/> |Qualquer anexo . . . extensão de arquivo corresponde . . .  <br/> |Qualquer anexo . . . extensão de arquivo corresponde . . .  <br/> |
|Especificar palavras ou frases  <br/> |Adicione esses tipos de arquivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Adicione esses tipos de arquivo:  <br/> ade, adp, ani, bas, bat, chm, cmd.com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, sct, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Faça o seguinte . . .  <br/> |Pré-anexar um aviso de isenção de responsabilidade  <br/> |Bloquear a mensagem . . . rejeitar a mensagem e incluir uma explicação  <br/> |
|Fornecer texto de mensagem  <br/> |Não abra esses tipos de arquivos, a menos que você esteja esperando por eles, porque os arquivos podem conter código mal-intencionado e saber que o remetente não é uma garantia de segurança.  <br/> ||
   
> [!TIP]
> Você também pode adicionar os arquivos que deseja bloquear à lista Anti-malware na [etapa 4](#4-raise-the-level-of-protection-against-malware-in-mail).

Para mais informações, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaure sua OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Pare o encaminhamento automático para email
<a name="forwarding"> </a>

Os hackers que têm acesso à caixa de correio de um usuário podem exfiltrar emails configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode impedir que isso aconteça configurando uma regra de fluxo de emails.

Para criar uma regra de transporte de email:

1. Vá até o [Centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Na categoria **fluxo de emails,** selecione **regras**.

3. Selecione **+** e crie uma nova **regra.**

4. Selecione **Mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir. Deixe o restante das configurações no padrão, a menos que você queira alterá-los.

6. Selecione **Salvar**.

|Configuração|Rejeitar emails de encaminhamento automático para domínios externos|
|---|---|
|Nome|Impedir o encaminhamento automático de emails para domínios externos|
|Aplicar essa regra se ...|O remetente . . . é externo/interno . . . Dentro da organização|
|Adicionar condição|O destinatário . . . é externo/interno . . . Fora da organização|
|Adicionar condição|As propriedades da mensagem . . . incluem o tipo de mensagem . . . Encaminhamento automático|
|Faça o seguinte...|Bloquear a mensagem . . . rejeitar a mensagem e incluir uma explicação.|
|Fornecer texto de mensagem|O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.|

## <a name="7-use-office-message-encryption"></a>7: Usar Office de mensagens
<a name="encryption"> </a>

Office A Criptografia de Mensagens está incluída Microsoft 365. Ele já está definido. Com Office Criptografia de Mensagens, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. A Criptografia de Mensagens do Office 365 funciona com o Outlook.com, Yahoo!, Gmail e outros serviços de email. A criptografia de mensagem de email ajuda a garantir que somente os destinatários pretendido possam exibir o conteúdo da mensagem.

Office A Criptografia de Mensagens fornece duas opções de proteção ao enviar emails:

- Não encaminhar

- Criptografar

Sua organização pode ter configurado opções adicionais que aplicam um rótulo a emails, como Confidencial.

### <a name="to-send-protected-email"></a>Para enviar emails protegidos

Em Outlook para pc, selecione **Opções** no email e escolha **Permissões**.

![Criptografia de mensagem de email em Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

Em Outlook.com, selecione **Proteger** no email. A proteção padrão é **Não encaminhar**. Para alterar isso para criptografar, selecione **Alterar Permissões** \> **Criptografar**.

![Criptografia de mensagem de email em Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Para receber emails criptografados

Se o destinatário tiver Outlook 2013 ou Outlook 2016 e uma conta de email da Microsoft, ele verá um alerta sobre as permissões restritas do item no painel Leitura. Depois de abrir a mensagem, o destinatário poderá exibir a mensagem como qualquer outra.

Se o destinatário estiver usando outro cliente de email ou conta de email, como Gmail ou Yahoo, ele verá um link que permite que ele entre para ler a mensagem de email ou solicitar uma senha única para exibir a mensagem em um navegador da Web. Se os usuários não estão recebendo o email, verifique sua pasta Spam ou Lixo Eletrônico.

Para obter mais informações, [consulte Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Proteja seu email contra ataques de phishing
<a name="phishing"> </a>

Se você configurou um ou mais domínios personalizados para seu ambiente Microsoft 365, você pode configurar a proteção anti-phishing direcionada. A proteção anti-phishing, uma parte do Microsoft Defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não precisa fazer isso.

Recomendamos que você seja iniciado com essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado.

![Criar uma política anti-phishing no Microsoft Defender para Office 365](../../media/security-and-compliance-center.png)

Para criar uma política anti-phishing no Defender para Office 365, veja um breve vídeo de treinamento [ou](../../business-video/setup-anti-phishing.md)conclua as seguintes etapas:

1. Vá para <https://protection.office.com>.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de** ameaças, selecione **Política**.

3. Na página Política, selecione **Anti-phishing**.

4. Na página Anti-phishing, selecione **+ Criar**. Um assistente inicia essa etapa ao definir sua política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política conforme recomendado no gráfico abaixo. Consulte [Saiba mais sobre a política anti-phishing no Microsoft Defender para](../../security/office-365-security/set-up-anti-phishing-policies.md) obter Office 365 para obter mais detalhes.

6. Depois de revisar suas configurações, selecione **Criar essa política** ou **Salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Domínio e equipe de campanha mais valiosa|
|Descrição|Verifique se a equipe mais importante e nosso domínio não estão sendo personificados.|
|Adicionar usuários a proteger|Selecione **+ Adicionar uma condição, O destinatário é**. Digite nomes de usuário ou insira o endereço de email do candidato, gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que deseja proteger contra representação.|
|Adicionar domínios para proteger|Selecione **+ Adicionar uma condição, O domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura Microsoft 365, se você definiu um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário personificado: selecione **Redirecionar** mensagem para outro endereço de email e digite o endereço de email do administrador de segurança; por exemplo, securityadmin@contoso.com. <br/> Se o email for enviado por um domínio personificado: selecione **Mensagem de quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Neste exemplo, não defina nenhuma substituição.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, contoso.com, na lista e selecione **Adicionar**. Selecione **Concluído**.|
|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Defender para Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Proteger contra anexos e arquivos mal-intencionados com Cofre Anexos
<a name="atp"> </a>

As pessoas enviam, recebem e compartilham regularmente anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil saber se um anexo é seguro ou mal-intencionado apenas olhando para uma mensagem de email. O Microsoft Defender para Office 365 inclui Cofre proteção de anexos, mas essa proteção não está 100% ativas por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Essa proteção se estende a arquivos em SharePoint, OneDrive e Microsoft Teams.

Para criar uma política Cofre de anexos, veja um [vídeo de](../../business-video/safe-attachments.md)treinamento curto ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com> e entre com sua conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de** ameaças, selecione **Política**.

3. Na página Política, selecione **Cofre Anexos**.

4. Na página Cofre anexos, aplique essa proteção amplamente selecionando a caixa de seleção Ativar a ATP para **SharePoint, OneDrive** e Microsoft Teams.

5. Selecione **+** para criar uma nova política.

6. Aplique as configurações na tabela a seguir.

7. Depois de revisar suas configurações, selecione **Criar essa política** ou **Salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Bloquear emails atuais e futuros com malware detectado.|
|Descrição|Bloquear emails e anexos atuais e futuros com malware detectado.|
|Salvar anexos resposta de malware desconhecido|Selecione Bloquear - Bloquear os emails e anexos atuais **e futuros com malware detectado.**|
|Redirecionar anexo na detecção|Habilitar redirecionamento (selecione esta caixa) <br/> Insira a conta de administrador ou uma configuração de caixa de correio para quarentena. <br/> Aplique a seleção acima se ocorrer uma verificação de malware para anexos ou se ocorrer um erro (selecione esta caixa).|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|
|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Defender para Office 365](../../security/office-365-security/configure-atp-anti-phishing-policies.md).

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Proteger contra ataques de phishing com Cofre Links
<a name="phishingatp"> </a>

Os hackers às vezes ocultam sites mal-intencionados em links no email ou em outros arquivos. Cofre Os links, parte do Microsoft Defender para Office 365, podem ajudar a proteger sua organização fornecendo a verificação de tempo de clique de endereços da Web (URLs) em mensagens de email e documentos Office. A proteção é definida por meio Cofre Políticas de Links.

Recomendamos que você faça o seguinte:

- Modifique a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para obter links Cofre, veja um [vídeo de](../../business-video/safe-links.md)treinamento curto ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com> e entre com sua conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de** ameaças, selecione **Política**.

3. Na página Política, selecione Cofre **Links**.

Para modificar a política padrão:

1. Na página Cofre links, em **Políticas** que se aplicam a toda a organização, clique duas vezes na **política** Padrão.

2. Em **Configurações que se aplicam** ao conteúdo no Office 365 , insira uma URL a ser bloqueada, como example.com , e selecione  **+** .

3. Em **Configurações** que se aplicam ao conteúdo, exceto **email,** selecione Office 365 **aplicativos**, Não rastree quando os usuários clicarem em **links** seguros e Não permitir que os usuários cliquem em links seguros para a URL original .

4. Selecione **Salvar**.

Para criar uma nova política direcionada a todos os destinatários em seu domínio:

1. Na página Cofre links, em Políticas que se aplicam a **destinatários específicos,** selecione **+** para criar uma nova política.

2. Aplique as configurações listadas na tabela a seguir.

3. Selecione **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Cofre política de links para todos os destinatários no domínio|
|Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Selecione **Em - AS URLs serão reescritas** e verificadas em uma lista de links mal-intencionados conhecidos quando o usuário clicar no link .|
|Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos|Selecione essa caixa.|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|
|

Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](../../security/office-365-security/atp-safe-links.md).

## <a name="related-content"></a>Conteúdo relacionado

[Autenticação multifafação para Microsoft 365](multi-factor-authentication-microsoft-365.md) (artigo)\
[Gerenciar e monitorar contas de prioridade](../setup/priority-accounts.md) (artigo)\
[Microsoft 365 relatórios no centro de administração](../activity-reports/activity-reports.md) (vídeo)