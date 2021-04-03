---
title: Aumentar a proteção contra ameaças para o Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurar o Microsoft Defender para Office 365 e proteger dados confidenciais contra phishing, malware e outras ameaças.
ms.openlocfilehash: 8fb2c3881876cabea6d8907a85bc9397212126dc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580185"
---
# <a name="increase-threat-protection"></a>Aumente a proteção contra ameaças

Este artigo ajuda você a aumentar a proteção em sua assinatura do Microsoft 365 para proteger contra phishing, malware e outras ameaças. Essas recomendações são apropriadas para organizações com uma necessidade maior de segurança, como escritórios de lei e clínicas de saúde.

Antes de começar, verifique sua Pontuação Segura do Office 365. A Pontuação Segura do Office 365 analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Para aumentar sua pontuação, conclua as ações recomendadas neste artigo. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades de proteger seu ambiente que não afetam negativamente a produtividade de seus usuários.

Para obter mais informações, consulte [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar o nível de proteção contra malware no email

Seu ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware. Você pode aumentar essa proteção bloqueando anexos com tipos de arquivo que são comumente usados para malware. Para aumentar a proteção contra malware no email:

1. Vá para [https://protection.office.com](https://protection.office.com) e entre com suas credenciais de conta de administrador.

2. No Centro de Conformidade de Segurança, no painel de navegação esquerdo, em Gerenciamento &amp; **de** Ameaças, escolha **Política** \> **Anti-Malware**.

3. Clique duas vezes na política padrão para editar essa política em toda a empresa.

4. Selecione **Configurações**.

5. Em **Filtro tipos de anexo comuns,** selecione **Em**. Os tipos de arquivo bloqueados estão listados na janela diretamente abaixo desse controle. Certifique-se de adicionar esses tipos de arquivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Se necessário, você pode adicionar ou excluir tipos de arquivo posteriormente.

6. Selecione **Salvar.**

Para obter mais informações, consulte [Proteção anti-malware no EOP](../security/office-365-security/anti-malware-protection.md).

## <a name="protect-against-ransomware"></a>Proteção contra ransomware

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueio de telas de computador. Em seguida, ele tenta roubar dinheiro das vítimas solicitando "resgate", geralmente na forma de criptocurrencies como o Bitcoin, em troca de acesso a dados.

Para proteger contra ransomware, crie uma ou mais regras de fluxo de emails para bloquear extensões de arquivo que são comumente usadas para ransomware. (Você adicionou essas regras no aumento [do nível de proteção contra malware na etapa de email.)](#raise-the-level-of-protection-against-malware-in-mail) Você também pode avisar os usuários que recebem esses anexos por email.

Além dos arquivos que você bloqueou na etapa anterior, é uma boa prática criar uma regra para avisar os usuários antes de abrir anexos de arquivo do Office que incluem macros. O ransomware pode estar oculto dentro de macros, portanto, alerte os usuários para não abrirem esses arquivos de pessoas que não conhecem.

Para criar uma regra de transporte de email:

1. Vá para o centro de administração em <https://admin.microsoft.com> , e escolha Centros de **administração** \> **Exchange**.

2. Na categoria **fluxo de emails,** selecione **regras**.

3. Selecione **+** e selecione Criar uma nova **regra.**

4. Selecione **Mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir para a regra. Use os valores padrão para o restante das configurações, a menos que você queira alterá-los.

6. Selecione **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office||
|---|---|---|
|Nome|Regra anti-ransomware: avisar os usuários|
|Aplicar essa regra se . . .|Qualquer anexo . . . extensão de arquivo corresponde . . .|
|Especificar palavras ou frases|Adicione esses tipos de arquivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Faça o seguinte . . .|Notificar o destinatário com uma mensagem|
|Fornecer texto de mensagem|Não abra esses tipos de arquivos de pessoas que você não conhece porque elas podem conter macros com código mal-intencionado.|

Para saber mais, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar o OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Parar o encaminhamento automático para email

Os hackers que têm acesso à caixa de correio de um usuário podem roubar emails definindo a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Para impedir que isso aconteça, configure uma regra de fluxo de emails.

Para criar uma regra de transporte de email, assista [a este vídeo curto](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) ou siga estas etapas:

1. No Centro de administração do Microsoft 365, selecione **Centros de administração** \> **Exchange**.

2. Na categoria **fluxo de emails,** selecione **regras**.

3. Selecione **+** e selecione Criar uma nova **regra.**

4. Para ver todas as opções, selecione **Mais opções** na parte inferior da caixa de diálogo.

5. Aplique as configurações na tabela a seguir. Use os valores padrão para o restante das configurações, a menos que você queira alterá-los.

6. Selecione **Salvar**.

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

Para criar uma política anti-phishing no Microsoft Defender para Office 365, assista a este breve vídeo de treinamento  [ou](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)conclua as seguintes etapas:

1. Acesse [https://protection.office.com](https://protection.office.com).

2. No Centro de Conformidade de Segurança, no painel de navegação &amp; esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

3. Na página **Política,** escolha **Anti-phishing**.

4. Na página **Anti-phishing,** selecione **+ Criar**. Um assistente inicia essa etapa ao definir sua política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política conforme recomendado na tabela a seguir. Para obter mais detalhes, [consulte Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Depois de revisar suas configurações, escolha **Criar essa política** ou **Salvar**, conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Domínio e equipe de campanha mais valiosa|
|Descrição|Verifique se a equipe mais importante e nosso domínio não estão sendo personificados.|
|Adicionar usuários a proteger|Selecione **+ Adicionar uma condição, O destinatário é**. Digite nomes de usuário ou insira o endereço de email do candidato, gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que deseja proteger contra representação.|
|Adicionar domínios para proteger|Selecione **+ Adicionar uma condição, O domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você definiu um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário personificado: Escolha **Redirecionar** mensagem para outro endereço de email e digite o endereço de email do administrador de segurança; por exemplo, *Alice <span> <span> @contoso.com*. Se o email for enviado por um domínio representado: escolha **Colocar mensagem em quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Aqui você pode adicionar seu próprio domínio ou qualquer outro domínio confiável.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, *contoso. <span> <span> com*, na lista e selecione **Adicionar**. Selecione **Concluído**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Proteger contra anexos mal-intencionados e arquivos com anexos seguros

As pessoas enviam, recebem e compartilham regularmente anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil saber se um anexo é seguro ou mal-intencionado apenas olhando para uma mensagem de email. O Microsoft Defender para Office 365 inclui proteção contra anexos seguros, mas essa proteção não está 100% ativas por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Essa proteção se estende aos arquivos do SharePoint, do OneDrive e do Microsoft Teams.

Para criar uma política de Anexo Seguro, assista [a este vídeo curto](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou conclua as seguintes etapas:

1. Vá para [https://protection.office.com](https://protection.office.com) , e entre com sua conta de administrador.

2. No Centro de Conformidade de Segurança, no painel de navegação &amp; esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

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
|Redirecionar anexo na detecção|Habilitar redirecionamento (selecione esta caixa) Insira a conta de administrador ou uma configuração de caixa de correio para quarentena.          Aplique a seleção acima se ocorrer uma verificação de malware para anexos ou se ocorrer um erro (selecione esta caixa).|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Microsoft Defender para Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteger contra ataques de phishing com Links Seguros

Os hackers às vezes ocultam sites mal-intencionados em links no email ou em outros arquivos. Os Links Seguros, parte do Microsoft Defender para Office 365, podem ajudar a proteger sua organização fornecendo verificação de tempo de clique de endereços da Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio de políticas de Links Seguros.

Recomendamos que você faça o seguinte:

- Modifique a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para configurar Links Seguros, assista a [este breve vídeo de treinamento](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:

1. Vá para [https://protection.office.com](https://protection.office.com) , e entre com sua conta de administrador.

2. No Centro de Conformidade de Segurança, no painel de navegação &amp; esquerdo, em Gerenciamento **de ameaças,** escolha **Política**.

3. Na página Política, escolha **Links Seguros.**

Para modificar a política padrão:

1. Na página Links seguros, em **Políticas que se aplicam a toda a organização,** selecione a **política** Padrão.

2. Em **Configurações que se aplicam ao conteúdo, exceto email,** selecione Aplicativos do **Microsoft 365 para empresas, Office para iOS e Android**.

3. Selecione **Salvar**.

Para criar uma nova política direcionada a todos os destinatários em seu domínio:

1. Na página Links seguros, em **Políticas que se aplicam** a toda a organização, selecione para criar uma nova **+** política.

2. Aplique as configurações listadas na tabela a seguir.

3. Selecione **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Política de links seguros para todos os destinatários no domínio|
|Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Selecione **Em - AS URLs serão reescritas** e verificadas em uma lista de links mal-intencionados conhecidos quando o usuário clicar no link .|
|Usar Anexos Seguros para examinar o conteúdo baixável|Selecione essa caixa.|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, consulte [Links seguros.](../security/office-365-security/safe-links.md)

## <a name="go-to-intune-admin-center"></a>Vá para o Centro de administração do Intune

1. Entre no [portal do Azure.](https://portal.azure.com/)

2. Selecione **Todos os serviços** e digite no *Intune* na Caixa de **Pesquisa**.

3. Depois que os resultados aparecerem, selecione o início ao lado do **Microsoft Intune** para torná-lo um favorito e fácil de encontrar mais tarde.

Além do centro de administração, você pode usar o Intune para registrar e gerenciar os dispositivos da sua organização. Para obter mais informações, consulte [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and Enrollment options for devices managed by [Intune](/intune/enrollment-options).
