---
title: Aumente a proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Obter ajuda com o aumento do nível de proteção no Microsoft 365
ms.openlocfilehash: 2078f9b40f6f556b2aacee28d6ff3c25be90fcc4
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698446"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Aumentar a proteção contra ameaças para a assinatura do Microsoft 365

Este artigo ajuda você a aumentar a proteção em sua assinatura do Microsoft 365 para proteção contra phishing, malware e outras ameaças. Essas recomendações são apropriadas para organizações com uma maior necessidade de segurança, como campanhas políticas, escritórios de advocacia e clínicas de assistência médica.

Antes de começar, verifique sua pontuação segura da Microsoft. A pontuação segura da Microsoft analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. A realização das ações recomendadas neste artigo aumenta sua pontuação. O objetivo não é atingir a pontuação máxima, mas para estar ciente das oportunidades de proteger seu ambiente que não afete negativamente a produtividade dos seus usuários.

Para obter mais informações, consulte [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar o nível de proteção contra malware no email

O ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção, bloqueando anexos com tipos de arquivo comumente usados para malware. Para aumentar a proteção contra malware no email:

1. Acesse <https://protection.office.com> e entre com suas credenciais de conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação à esquerda, em **Gerenciamento de ameaças**, escolha **política** \> **anti-malware**.

3. Clique duas vezes na política padrão para editar a política em toda a empresa.

4. Clique em **Configurações**.

5. Em **filtro tipos de anexo comuns**, selecione **ativado**. Os tipos de arquivo bloqueados são listados na janela diretamente abaixo desse controle. Certifique-se de adicionar estes tipos de filetype:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Você pode adicionar ou excluir tipos de arquivo posteriormente, se necessário.

6. Clique em **Salvar.**

Para obter mais informações, consulte [proteção Antimalware no EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Proteção contra ransomware

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueando telas de computador. Em seguida, tenta extort dinheiro de vítimas solicitando "resgate", geralmente na forma de cryptocurrencies como Bitcoin, no Exchange para acessar os dados.

Você pode se proteger contra o ransomware criando uma ou mais regras de fluxo de email para bloquear extensões de arquivo comumente usadas para ransomware (elas foram adicionadas na etapa [aumentar o nível de proteção contra malware no email](#raise-the-level-of-protection-against-malware-in-mail) ) ou para avisar os usuários que recebem esses anexos por email.

Além dos arquivos que você bloqueou na etapa anterior, também é recomendável criar uma regra para avisar os usuários antes de abrir os anexos de arquivo do Office que incluem macros. O ransomware pode ser oculto dentro de macros, portanto, avisar os usuários para não abrir esses arquivos de pessoas que não conhecem.

Para criar uma regra de transporte de emails:

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha central de **Administração** do \> **Exchange**.

2. Na categoria **fluxo de emails** , clique em **regras**.

3. Clique em **+** e em **criar uma nova regra**.

4. Clique em **mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplicar as configurações da tabela a seguir para a regra. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office|
|---|---|
|Nome|Regra anti-ransomware: avisar os usuários|
|Aplicar esta regra se. . .|Qualquer anexo. . . correspondências de extensão de arquivo. . .|
|Especificar palavras ou frases|Adicione estes tipos de arquivos: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Faça o seguinte. . .|Notificar o destinatário com uma mensagem|
|Fornecer texto da mensagem|Não abra esses tipos de arquivos de pessoas que você não sabe porque eles podem conter macros com código mal-intencionado.|

Para saber mais, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar o OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Parar o encaminhamento automático para email

Hackers que obtêm acesso à caixa de correio de um usuário podem roubar seus emails Configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode evitar que isso aconteça Configurando uma regra de fluxo de emails.

Para criar uma regra de transporte de email, Assista [a este vídeo curto](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) ou siga estas etapas:

1. No centro de administração do Microsoft 365, clique em **centrais de administração** do \> **Exchange**.

2. Na categoria **fluxo de emails** , clique em **regras**.

3. Clique em **+** e em **criar uma nova regra**.

4. Clique em **mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplicar as configurações na tabela a seguir. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office|
|---|---|
|Nome|Impedir o encaminhamento automático de emails para domínios externos|
|Aplicar esta regra se...|O remetente. . . é externo/interno. . . Dentro da organização|
|Adicionar condição|As propriedades da mensagem. . . inclua o tipo de mensagem. . . Avanço automático|
|Faça o seguinte...|Bloquear a mensagem. . . rejeitar a mensagem e incluir uma explicação.|
|Fornecer texto da mensagem|O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.|

## <a name="protect-your-email-from-phishing-attacks"></a>Proteger seu email contra ataques de phishing

Se você configurou um ou mais domínios personalizados para o seu ambiente do Office 365 ou do Microsoft 365, é possível configurar a proteção antiphishing dirigida. A proteção anti-phishing, parte do Microsoft defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não é necessário fazer isso.

Recomendamos que você comece a usar essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado.

Para criar uma política anti-phishing no defender para Office 365, Assista a [este vídeo de treinamento curto](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com>.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.

3. Na página **política** , escolha **anti-phishing**.

4. Na página **anti-phishing** , selecione **+ criar**. Um assistente é iniciado que orienta você na definição da política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política, conforme recomendado na tabela abaixo. Para obter mais informações, consulte [saiba mais sobre a política anti-phishing no Microsoft defender para Office 365 Options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Após revisar as configurações, escolha **criar esta política** ou **salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|O domínio e a equipe de campanha mais valiosa|
|Descrição|Garantir que a equipe mais importante e nosso domínio não estão sendo representados.|
|Adicionar usuários a proteger|Selecione **+ Adicionar uma condição, o destinatário é**. Digite nomes de usuário ou insira o endereço de email do candidato, o gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que você deseja proteger da representação.|
|Adicionar domínios para proteger|Selecione **+ Adicionar uma condição, o domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você tiver definido um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário representado: escolha **redirecionar mensagem para outro endereço de email** e digite o endereço de email do administrador de segurança; por exemplo, *ana maria <span> <span> @contoso. com*. <br/> Se o email for enviado por um domínio representado: escolha **Colocar mensagem em quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Aqui você pode adicionar seu próprio domínio ou qualquer outro domínio confiável.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, *contoso. <span> <span> com*, na lista e selecione **Adicionar**. Selecione **Concluído**.|

Para obter mais informações, consulte [set up anti-phishing Policies in defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Proteção contra anexos mal-intencionados, arquivos e links com o defender para Office 365

![Faixa que aponta para https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Primeiro, verifique se <https://admin.microsoft.com> a nova visualização do centro de administração está ativada no centro de administração. Ative a alternância ao lado do texto **o novo centro de administração**.

   ![A nova visualização do centro de administração.](../media/previewon.png)

Se você ainda não vir a página de **instalação** com cartões no seu locatário, consulte como concluir essas etapas no centro de conformidade e segurança &. Confira [Configurar anexos seguros no centro de conformidade de & de segurança](#set-up-safe-attachments-in-the-security--compliance-center) e [Configurar links seguros no centro de conformidade de & de segurança](#set-up-safe-links-in-the-security--compliance-center).

1. No painel de navegação esquerdo, escolha **configuração**.
2. Na página **configuração** , escolha **Exibir** no cartão **aumentar a proteção contra ameaças avançadas** .

   ![Escolha Exibir na barra de aumento de proteção contra ameaças avançadas.](../media/startatp.png)

3. Na página **aumentar a proteção contra ameaças avançadas** , escolha **introdução**.
4. No painel que é aberto, marque as caixas de seleção ao lado de **links e anexos em email**, **examinar arquivos no SharePoint, no onedrive e no Microsoft Teams** e **examinar links no Office Desktop e aplicativos do Office Online** em **itens de varredura de conteúdo mal-intencionado**.

   Em **links e anexos em email**, digite todos os usuários ou os usuários específicos cujo email você deseja verificar.

   ![Marque todas as caixas de seleção em aumentar a proteção contra ameaças avançadas.](../media/setatp.png)

5. Escolha **criar políticas** para ativar anexos seguros e links seguros.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Configurar anexos seguros no centro de conformidade & segurança

Pessoas costumam enviar, receber e compartilhar anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil dizer se um anexo é seguro ou mal-intencionado apenas olhando uma mensagem de email. O Microsoft defender para Office 365 inclui proteção de anexo seguro, mas essa proteção não está ativada por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Esta proteção estende-se aos arquivos no SharePoint, no OneDrive e no Microsoft Teams.

Para criar uma política de anexo segura, Assista a [este breve vídeo](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou conclua as seguintes etapas:

1. Acesse <https://protection.office.com> e entre com sua conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.

3. Na página política, escolha **anexos seguros**.

4. Na página de anexos seguros, aplique essa proteção amplamente marcando a caixa de seleção **ativar a ATP para SharePoint, onedrive e Microsoft Teams** .

5. Selecione **+** para criar uma nova política.

6. Aplicar as configurações na tabela a seguir.

7. Depois de revisar as configurações, escolha **criar esta política** ou **salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Bloquear emails atuais e futuros com malware detectado.|
|Descrição|Bloquear emails e anexos atuais e futuros com malware detectado.|
|Salvar anexos resposta desconhecida de malware|Selecione **Bloquear – bloquear emails e anexos atuais e futuros com malware detectado**.|
|Redirecionar o anexo na detecção|Habilitar o redirecionamento (Selecione esta caixa) <br/> Insira a conta de administrador ou uma configuração de caixa de correio para quarentena. <br/> Aplica a seleção acima se a verificação de malware por anexos expira ou quando ocorre um erro (Selecione esta caixa).|
|Aplicado a|O domínio do destinatário é. . . Selecione seu domínio.|

Para obter mais informações, consulte [set up anti-phishing Policies in defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Configurar links seguros no centro de conformidade & segurança

Os hackers às vezes ocultam sites mal-intencionados em links em email ou outros arquivos. Os links seguros, parte do Microsoft defender para Office 365, podem ajudar a proteger sua organização fornecendo a verificação de tempo de clique de endereços Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio de políticas de links seguros.

Recomendamos que você faça o seguinte:

- Modificar a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para configurar links seguros, Assista a [este pequeno vídeo de treinamento](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:

1. Acesse <https://protection.office.com> e entre com sua conta de administrador.

2. No centro de conformidade & segurança, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.

3. Na página política, escolha **links seguros**.

Para modificar a política padrão:

1. Na página de links seguros, em **políticas que se aplicam a toda a organização**, selecione a política **padrão** .

2. Em **configurações que se aplicam ao conteúdo exceto email**, selecione **Microsoft 365 aplicativos para empresas, Office para IOS e Android**.

3. Clique em **Salvar**.

Para criar uma nova política direcionada para todos os destinatários em seu domínio:

1. Na página de links seguros, em **políticas que se aplicam a toda a organização**, clique em **+** para criar uma nova política.

2. Aplicar as configurações listadas na tabela a seguir.

3. Clique em **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Política de links seguros para todos os destinatários no domínio|
|Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens|Selecione as **URLs que serão reconfiguradas e verificadas em relação a uma lista de links mal-intencionados conhecidos quando o usuário clicar no link**.|
|Usar anexos seguros para examinar Conteúdo baixável|Selecione essa caixa.|
|Aplicado a|O domínio do destinatário é. . . Selecione seu domínio.|

Para obter mais informações, consulte [links seguros no defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="turn-on-the-unified-audit-log"></a>Ativar o log de auditoria unificada

Depois de ativar a pesquisa de log de auditoria no centro de conformidade e segurança &, você pode manter o administrador e outras atividades do usuário no log e pesquisá-lo.

Você deve receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria em sua assinatura do Microsoft 365. Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página permissões no centro de administração do Exchange. Os administradores globais no Microsoft 365 são membros desse grupo por padrão.

1. Para ativar a pesquisa de log de auditoria, vá para o centro de administração em <https://admin.microsoft.com> e, em seguida, escolha **segurança** em **centros de administração** no painel de navegação esquerdo.
2. Na página de **segurança do Microsoft 365** , escolha **mais recursos** e, em seguida, **abra** no cartão **centro de conformidade & segurança do Office 365** .

    ![Escolha abrir nos carros de conformidade com segurança &.](../media/gotosecandcomp.png)
3. Na página segurança e conformidade, escolha **Pesquisar** e, em seguida, **pesquisa log de auditoria**.
4. Na parte superior da página **pesquisa de log de auditoria** , escolha **ativar a auditoria**.

Após o recurso ser ativado, você pode pesquisar arquivos, pastas e muitas atividades. Para obter mais informações, consulte [Search the Audit Log](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Ajustar configurações de compartilhamento anônimo para arquivos e pastas do SharePoint e do OneDrive

(altere o padrão de validade do link anônimo para 14 dias, altere o tipo de compartilhamento padrão para "pessoas específicas") Para alterar as configurações de compartilhamento do OneDrive e do SharePoint:

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha **SharePoint** em **centros de administração** no painel de navegação esquerdo.
2. No centro de administração do SharePoint, vá para compartilhamento de **políticas** \> .
3. Na página **compartilhamento** , em **links de arquivo e pasta**, selecione **pessoas específicas** e, em **Configurações avançadas para links "qualquer pessoa"**, selecione **estes links devem expirar dentro de vários dias** e digite 14 (ou outro número de dias em que você deseja restringir o tempo de vida do link).

   ![Escolha pessoas específicas e defina o término do link como 14 dias.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Alertas de atividade

Você pode usar os alertas de atividade para rastrear as atividades de administrador e de usuário e detectar incidentes de prevenção contra perda de dados e malware em sua organização. Sua assinatura inclui um conjunto de políticas padrão, mas você também pode criar itens personalizados. Para obter mais informações, consulte [políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies). Por exemplo, se você armazenar um arquivo importante no SharePoint que você não deseja que todos compartilhem externamente, você pode criar uma notificação que o alertará se alguém o compartilhar.

A figura a seguir mostra as políticas padrão incluídas no Microsoft 365.

![Políticas de alerta padrão incluídas no Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Desabilitar ou gerenciar o compartilhamento de calendário

Você pode impedir que as pessoas em sua organização compartilhem seus calendários ou também pode gerenciar o que eles podem compartilhar. Por exemplo, você pode restringir o compartilhamento somente para horários disponíveis/ocupados.

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha **configurações** \> **org** Settings.
2. Na página **Serviços** , escolha **calendário** e escolha se as pessoas em sua organização podem compartilhar seus calendários com pessoas de fora que tenham o Office 365 ou Exchange, ou com qualquer pessoa.

   Se você escolher a opção compartilhar com qualquer pessoa, você pode decidir também compartilhar apenas informações de disponibilidade.

3. Escolha **salvar alterações** na parte inferior da página.

   A figura a seguir mostra o compartilhamento de calendários não permitido.

   ![Captura de tela mostrando o compartilhamento de calendário externo como não permitido.](../media/nocalendarsharing.png)

   A figura a seguir mostra as configurações quando o compartilhamento de calendário é permitido com um link de email com apenas informações de disponibilidade.

   ![Captura de tela do compartilhamento de disponibilidade do calendário com qualquer pessoa.](../media/sharefreebusy.png)

Se os usuários tiverem permissão para compartilhar seus calendários, confira [estas instruções](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) sobre como compartilhar do Outlook na Web.
