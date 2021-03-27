---
title: Aumente a proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
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
description: Obter ajuda para aumentar o nível de proteção no Microsoft 365
ms.openlocfilehash: a1f4714d5b7dcd8d6a22a07c118055e13b27e069
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398272"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Aumentar a proteção contra ameaças para a assinatura do Microsoft 365

Este artigo ajuda você a aumentar a proteção em sua assinatura do Microsoft 365 para proteger contra phishing, malware e outras ameaças. Essas recomendações são apropriadas para organizações com maior necessidade de segurança, como campanhas políticas, escritórios de advocacia e clínicas de saúde.

Antes de começar, verifique a Pontuação Segura da Microsoft. A Pontuação Segura da Microsoft analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Tomar as ações recomendadas neste artigo aumenta sua pontuação. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades de proteger seu ambiente que não afetam negativamente a produtividade de seus usuários.

Para obter mais informações, consulte [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar o nível de proteção contra malware no email

Seu ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção bloqueando anexos com tipos de arquivo comumente usados para malware. Para levantar a proteção contra malware no email:

1. Vá para <https://protection.office.com> e entre com suas credenciais de conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento de ameaças, **escolha** **Política** \> **Anti-Malware**.

3. Clique duas vezes na política padrão para editar essa política em toda a empresa.

4. Clique em **Configurações**.

5. Em **Filtro tipos de anexo comuns,** selecione **Em**. Os tipos de arquivo bloqueados estão listados na janela diretamente abaixo desse controle. Certifique-se de adicionar esses tipos de arquivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Você pode adicionar ou excluir tipos de arquivo mais tarde, se necessário.

6. Clique em **Salvar.**

Para obter mais informações, consulte [Proteção anti-malware no EOP](../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Proteção contra ransomware

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueio de telas de computador. Em seguida, ele tenta roubar dinheiro das vítimas solicitando "resgate", geralmente na forma de criptocurrencies como o Bitcoin, em troca de acesso a dados.

Você pode proteger contra ransomware criando uma ou mais regras de fluxo de emails para bloquear extensões de arquivo que são comumente usadas para ransomware (elas foram adicionadas no aumento do nível de proteção contra [malware](#raise-the-level-of-protection-against-malware-in-mail) na etapa de email) ou para avisar os usuários que recebem esses anexos no email.

Além dos arquivos que você bloqueou na etapa anterior, também é uma boa prática criar uma regra para avisar os usuários antes de abrir anexos de arquivo do Office que incluem macros. O ransomware pode estar oculto dentro de macros, portanto, alerte os usuários para não abrirem esses arquivos de pessoas que não conhecem.

Para criar uma regra de transporte de email:

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha Centros de **administração** \> **Exchange**.

2. Na categoria **fluxo de emails,** clique em **regras**.

3. Clique **+** em , e clique em Criar uma nova **regra.**

4. Clique **em Mais** opções na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir para a regra. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office|
|---|---|
|Nome|Regra anti-ransomware: avisar os usuários|
|Aplicar essa regra se . . .|Qualquer anexo . . . extensão de arquivo corresponde . . .|
|Especificar palavras ou frases|Adicione esses tipos de arquivo: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Faça o seguinte . . .|Notificar o destinatário com uma mensagem|
|Fornecer texto de mensagem|Não abra esses tipos de arquivos de pessoas que você não conhece porque elas podem conter macros com código mal-intencionado.|

Para mais informações, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar o OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Parar o encaminhamento automático para email

Os hackers que têm acesso à caixa de correio de um usuário podem roubar seu email definindo a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode impedir que isso aconteça configurando uma regra de fluxo de emails.

Para criar uma regra de transporte de email, assista [a este vídeo curto](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) ou siga estas etapas:

1. No Centro de administração do Microsoft 365, clique em **Centros de administração** \> **Exchange**.

2. Na categoria **fluxo de emails,** clique em **regras**.

3. Clique **+** em , e clique em Criar uma nova **regra.**

4. Clique **em Mais** opções na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir. Deixe o restante das configurações no padrão, a menos que você queira alterá-las.

6. Clique em **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office|
|---|---|
|Nome|Impedir o encaminhamento automático de emails para domínios externos|
|Aplicar essa regra se ...|O remetente . . . é externo/interno . . . Dentro da organização|
|Adicionar condição|As propriedades da mensagem . . . incluem o tipo de mensagem . . . Encaminhamento automático|
|Faça o seguinte...|Bloquear a mensagem . . . rejeitar a mensagem e incluir uma explicação.|
|Fornecer texto de mensagem|O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.|

## <a name="protect-your-email-from-phishing-attacks"></a>Proteger seu email contra ataques de phishing

Se você configurou um ou mais domínios personalizados para seu ambiente do Office 365 ou do Microsoft 365, você pode configurar a proteção anti-phishing direcionada. A proteção anti-phishing, parte do Microsoft Defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não precisa fazer isso.

Recomendamos que você seja iniciado com essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado.

Para criar uma política anti-phishing no Defender para Office 365, assista a este vídeo de treinamento curto [ou](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)conclua as seguintes etapas:

1. Vá para <https://protection.office.com>.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

3. Na página **Política,** escolha **Anti-phishing**.

4. Na página **Anti-phishing,** selecione **+ Criar**. Um assistente inicia essa etapa ao definir sua política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política conforme recomendado no gráfico abaixo. Para obter mais informações, [consulte Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Depois de revisar suas configurações, escolha **Criar essa política** ou **Salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Domínio e equipe mais valiosa|
|Descrição|Verifique se a equipe mais importante e nosso domínio não estão sendo personificados.|
|Adicionar usuários a proteger|Selecione **+ Adicionar uma condição, O destinatário é**. Digite nomes de usuário ou insira o endereço de email dos proprietários, parceiros ou candidatos, gerentes e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que deseja proteger contra representação.|
|Adicionar domínios para proteger|Selecione **+ Adicionar uma condição, O domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você definiu um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário personificado: Escolha **Redirecionar** mensagem para outro endereço de email e digite o endereço de email do administrador de segurança; por exemplo, *Alice <span> <span> @contoso.com*. <br/> Se o email for enviado por um domínio representado: escolha **Colocar mensagem em quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Aqui você pode adicionar seu próprio domínio ou qualquer outro domínio confiável.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, *contoso. <span> <span> com*, na lista e selecione **Adicionar**. Selecione **Concluído**.|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Defender para Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Proteger contra anexos, arquivos e links mal-intencionados com o Defender para Office 365

![Faixa que aponta para https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Primeiro, certifique-se de que, no centro de administração, você tenha a nova visualização do centro <https://admin.microsoft.com> de administração 2016. Ativar a alternância ao lado do texto **O novo centro de administração**.

   ![A nova visualização do centro de administração.](../media/previewon.png)

Se você ainda não  vir a página Instalação com cartões em seu locatário, confira como concluir essas etapas no Centro de Conformidade & Segurança. Consulte [Configurar Anexos Seguros](#set-up-safe-attachments-in-the-security--compliance-center) no Centro de Conformidade & Segurança e Configurar Links Seguros no Centro de Conformidade & [Segurança.](#set-up-safe-links-in-the-security--compliance-center)

1. Na nav esquerda, escolha **Configurar**.
2. Na página **Instalação,** escolha **Exibir no** cartão **Aumentar a proteção contra ameaças** avançadas.

   ![Escolha Exibir em Aumentar a proteção contra ameaças avançadas.](../media/startatp.png)

3. Na página **Aumentar a proteção contra ameaças avançadas,** escolha **Começar**.
4. No painel aberto, selecione as caixas de seleção ao lado de Links e anexos no email , Examinar arquivos no **SharePoint, OneDrive e Teams** e Verificar links em **aplicativos** da área de trabalho do Office e do **Office Online** em Verificar itens para conteúdo mal-intencionado . 

   Em **Links e anexos no email**, Digite Em Todos os Usuários ou os usuários específicos cujo email você deseja digitalizado.

   ![Selecione todas as caixas de seleção em Aumentar a proteção contra ameaças avançadas.](../media/setatp.png)

5. Escolha **Criar políticas para** ativar Anexos Seguros e Links Seguros.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Configurar anexos seguros no Centro de Conformidade & Segurança

As pessoas enviam, recebem e compartilham regularmente anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil saber se um anexo é seguro ou mal-intencionado apenas olhando para uma mensagem de email. O Microsoft Defender para Office 365 inclui proteção contra anexos seguros, mas essa proteção não está 100% ativas por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Essa proteção se estende aos arquivos do SharePoint, do OneDrive e do Microsoft Teams.

Para criar uma política de Anexo Seguro, assista [a este vídeo curto](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com> e entre com sua conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

3. Na página Política, escolha **Anexos Seguros.**

4. Na página Anexos seguros, aplique essa proteção amplamente selecionando a caixa de seleção Ativar ATP para **SharePoint, OneDrive e Microsoft Teams.**

5. Selecione **+** para criar uma nova política.

6. Aplique as configurações na tabela a seguir.

7. Depois de revisar suas configurações, escolha **Criar essa política** ou **Salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Bloquear emails atuais e futuros com malware detectado.|
|Descrição|Bloquear emails e anexos atuais e futuros com malware detectado.|
|Salvar anexos resposta de malware desconhecido|Selecione Bloquear - Bloquear os emails e anexos atuais **e futuros com malware detectado.**|
|Redirecionar anexo na detecção|Habilitar redirecionamento (selecione esta caixa) <br/> Insira a conta de administrador ou uma configuração de caixa de correio para quarentena. <br/> Aplique a seleção acima se ocorrer uma verificação de malware para anexos ou se ocorrer um erro (selecione esta caixa).|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Defender para Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Configurar Links Seguros no Centro de Conformidade & Segurança

Os hackers às vezes ocultam sites mal-intencionados em links no email ou em outros arquivos. Os Links Seguros, parte do Microsoft Defender para Office 365, podem ajudar a proteger sua organização fornecendo verificação de tempo de clique de endereços da Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio de políticas de Links Seguros.

Recomendamos que você faça o seguinte:

- Modifique a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para configurar Links Seguros, assista a [este breve vídeo de treinamento](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:

1. Vá para <https://protection.office.com> e entre com sua conta de administrador.

2. No Centro de Conformidade & segurança, no painel de navegação esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

3. Na página Política, escolha **Links Seguros.**

Para modificar a política padrão:

1. Na página Links seguros, em **Políticas que se aplicam a toda a organização,** selecione a **política** Padrão.

2. Em **Configurações que se aplicam ao conteúdo, exceto email,** selecione Aplicativos do **Microsoft 365 para empresas, Office para iOS e Android**.

3. Clique em **Salvar**.

Para criar uma nova política direcionada a todos os destinatários em seu domínio:

1. Na página Links seguros, em Políticas que se aplicam a toda a **organização,** clique **+** para criar uma nova política.

2. Aplique as configurações listadas na tabela a seguir.

3. Clique em **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Política de links seguros para todos os destinatários no domínio|
|Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Selecione **Em - AS URLs serão reescritas** e verificadas em uma lista de links mal-intencionados conhecidos quando o usuário clicar no link .|
|Usar Anexos Seguros para examinar o conteúdo baixável|Selecione essa caixa.|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, consulte [Links seguros no Defender para Office 365](../security/office-365-security/safe-links.md).

## <a name="turn-on-the-unified-audit-log"></a>Ativar o Log de Auditoria Unificada

Depois de ativar a pesquisa de log de auditoria no Centro de Conformidade & segurança, você poderá reter o administrador e outras atividades do usuário no log e pesquisá-lo.

Você deve ter a função Logs de Auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria em sua assinatura do Microsoft 365. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões no Centro de administração do Exchange. Os administradores globais no Microsoft 365 são membros desse grupo por padrão.

1. Para ativar a pesquisa de log de auditoria, vá para o centro de administração em e escolha Segurança em Centros de <https://admin.microsoft.com> administração na nav esquerda.  
2. Na página Segurança do **Microsoft 365,**  **escolha** Mais recursos e Abra no cartão centro de conformidade do **Office 365 Security &.**

    ![Escolha Abrir nos carros de conformidade & segurança.](../media/gotosecandcomp.png)
3. Na página segurança e conformidade, escolha **Pesquisar** e, em seguida, **Auditar pesquisa de log.**
4. Na parte superior da página de pesquisa **de log de** auditoria, escolha Ativar **auditoria**.

Depois que o recurso for ligado, você poderá pesquisar arquivos, pastas e muitas atividades. Para obter mais informações, consulte [pesquisar o log de auditoria](../compliance/search-the-audit-log-in-security-and-compliance.md).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Ajustar configurações de compartilhamento anônimo para arquivos e pastas do SharePoint e Do OneDrive

(altere a expiração padrão do link anônimo para 14 dias, altere o tipo de compartilhamento padrão para "Pessoas Específicas") Para alterar as configurações de compartilhamento do OneDrive e do SharePoint:

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha **SharePoint** em **Centros de administração** na nav esquerda.
2. No Centro de administração do SharePoint, vá para **Compartilhamento de** \> **Políticas**.
3. Na  página Compartilhamento, em Links de arquivo e **pasta,** selecione Pessoas específicas e, em Configurações avançadas para **links "Qualquer pessoa",** selecione Esses **links** devem expirar dentro desses muitos dias e digite em 14 (ou outro número de dias para o qual você deseja restringir o tempo de vida do link).

   ![Escolha Pessoas específicas e de definir a expiração do link como 14 dias.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Alertas de atividade

Você pode usar alertas de atividade para controlar as atividades do administrador e do usuário e detectar incidentes de prevenção contra malware e perda de dados em sua organização. Sua assinatura inclui um conjunto de políticas padrão, mas você também pode criar políticas personalizadas. Para obter mais informações, consulte [políticas de alerta](../compliance/alert-policies.md). Por exemplo, se você armazenar um arquivo importante no SharePoint que não deseja que ninguém compartilhe externamente, poderá criar uma notificação que o alertará se alguém o compartilhar.

A figura a seguir mostra as políticas padrão incluídas no Microsoft 365.

![Políticas de alerta padrão incluídas no Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Desabilitar ou gerenciar o compartilhamento de calendário

Você pode impedir que as pessoas em sua organização compartilhem seus calendários ou você também pode gerenciar o que elas podem compartilhar. Por exemplo, você só pode restringir o compartilhamento a horários de livre/ocupado.

1. Vá para o centro de administração em <https://admin.microsoft.com> e escolha **Configurações** \> **da Organização Configurações**.
2. Na página **Serviços,** escolha **Calendário** e escolha se as pessoas em sua organização podem compartilhar seus calendários com pessoas de fora que têm o Office 365 ou o Exchange ou com qualquer pessoa.

   Se você escolher a opção compartilhar com qualquer pessoa, poderá decidir também compartilhar apenas informações de livre/ocupado.

3. Escolha **Salvar alterações** na parte inferior da página.

   A figura a seguir mostra o compartilhamento de calendário não permitido.

   ![Captura de tela de exibição de compartilhamento de calendário externo como não permitido.](../media/nocalendarsharing.png)

   A figura a seguir mostra as configurações quando o compartilhamento de calendário é permitido com um link de email com apenas informações de livre/ocupado.

   ![Captura de tela do compartilhamento de tempo livre/ocupado com qualquer pessoa.](../media/sharefreebusy.png)

Se os usuários têm permissão para compartilhar seus calendários, [consulte](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) estas instruções sobre como compartilhar do Outlook na Web.
