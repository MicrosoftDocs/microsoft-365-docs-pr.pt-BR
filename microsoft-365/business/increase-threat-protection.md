---
title: Aumentar a proteção contra ameaças do Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842247"
---
# <a name="increase-threat-protection"></a>Aumente a proteção contra ameaças

Este artigo ajuda a aumentar a proteção em sua assinatura do Microsoft 365 para proteger contra phishing, malware e outras ameaças. Essas recomendações são apropriadas para organizações com maior necessidade de segurança, como escritórios de lei e instituições de saúde.

Antes de começar, verifique sua Classificação de Segurança do Office 365. O Office 365 Secure Score analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Para aumentar sua pontuação, conclua as ações recomendadas neste artigo. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades para proteger seu ambiente que não afetem negativamente a produtividade dos usuários.

Para obter mais informações, consulte [o Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar o nível de proteção contra malware no email

Seu ambiente do Office 365 ou microsoft 365 inclui proteção contra malware. Você pode aumentar essa proteção bloqueando anexos com tipos de arquivo comumente usados para malware. Para aumentar a proteção contra malware no email:

1. Acesse e [https://protection.office.com](https://protection.office.com) entre com suas credenciais de conta de administrador.

2. No Centro de Conformidade de Segurança, no painel de navegação esquerdo, em Gerenciamento de &amp; Ameaças, escolha **Política**  \> **Anti-Malware.**

3. Clique duas vezes na política padrão para editar essa política em toda a empresa.

4. Selecione **Configurações**.

5. Under **Common Attachment Types Filter**, select **On**. Os tipos de arquivo bloqueados são listados na janela diretamente abaixo desse controle. Certifique-se de adicionar estes tipos de arquivo:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Se necessário, você pode adicionar ou excluir tipos de arquivo mais tarde.

6. Selecione **Salvar.**

Para obter mais informações, consulte [Proteção anti-malware no EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="protect-against-ransomware"></a>Proteção contra ransomware

O ransomware restringe o acesso aos dados criptografando arquivos ou travando telas do computador. Em seguida, ele tenta armazenar dinheiro de vítima, solicitando "resgate", geralmente na forma de cryptocurrencies como Mila, em troca de acesso aos dados.

Para se proteger contra ransomware, crie uma ou mais regras de fluxo de emails para bloquear extensões de arquivo comumente usadas para ransomware. (Você adicionou essas regras para aumentar [o nível de proteção contra malware na etapa de](#raise-the-level-of-protection-against-malware-in-mail) email.) Você também pode avisar os usuários que recebem esses anexos por email.

Além dos arquivos bloqueados na etapa anterior, é uma boa prática criar uma regra para avisar os usuários antes de abrir anexos de arquivo do Office que incluem macros. Ransomware pode ficar oculto dentro de macros, portanto, avise os usuários para não abrirem esses arquivos de pessoas que não conhecem.

Para criar uma regra de transporte de email:

1. Vá para o centro de administração em <https://admin.microsoft.com> , e escolha Centros de **administração** \> **Exchange**.

2. Na categoria **de fluxo de** emails, selecione **regras.**

3. Selecione **+** e, em seguida, **selecione Criar uma nova regra.**

4. Selecione **Mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções.

5. Aplique as configurações na tabela a seguir para a regra. Use os valores padrão para o restante das configurações, a menos que você queira alterá-los.

6. Selecione **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office||
|---|---|---|
|Nome|Regra anti-ransomware: avisar os usuários|
|Aplicar esta regra se . . .|Qualquer anexo . . . file extension matches . . .|
|Especificar palavras ou frases|Adicione estes tipos de arquivo:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Faça o seguinte. . .|Notificar o destinatário com uma mensagem|
|Fornecer texto da mensagem|Não abra esses tipos de arquivos de pessoas que você não conhece porque elas podem conter macros com código mal-intencionado.|

Para saber mais, confira:

- [Ransomware: como reduzir o risco](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Restaurar o OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Parar o encaminhamento automático de email

Os hackers que têm acesso à caixa de correio de um usuário podem roubar emails configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem o reconhecimento do usuário. Para evitar que isso aconteça, configure uma regra de fluxo de emails.

Para criar uma regra de transporte de email, assista [a este breve vídeo](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) ou siga estas etapas:

1. No Centro de administração do Microsoft 365, selecione **Centros de administração do** \> **Exchange.**

2. Na categoria **de fluxo de** emails, selecione **regras.**

3. Selecione **+** e, em seguida, **selecione Criar uma nova regra.**

4. Para ver todas as opções, selecione **Mais opções** na parte inferior da caixa de diálogo.

5. Aplique as configurações na tabela a seguir. Use os valores padrão para o restante das configurações, a menos que você queira alterá-los.

6. Selecione **Salvar**.

|Setting|Avisar os usuários antes de abrir anexos de arquivos do Office|
|---|---|
|Nome|Impedir o encaminhamento automático de email para domínios externos|
|Aplicar esta regra se...|O remetente . . . é externo/interno . . . Dentro da organização|
|Adicionar condição|As propriedades da mensagem. . . inclua o tipo de mensagem. . . Encaminhamento automático|
|Faça o seguinte...|Bloquear a mensagem. . . rejeitar a mensagem e incluir uma explicação.|
|Fornecer texto da mensagem|O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger seu email contra ataques de phishing

Se você configurou um ou mais domínios personalizados para seu ambiente do Office 365 ou microsoft 365, você pode configurar a proteção anti-phishing direcionada. A proteção anti-phishing, parte do Microsoft Defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros ataques de phishing. Se você ainda não configurou um domínio personalizado, não é necessário fazer isso.

Recomendamos que você começar a usar essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado.

Para criar uma política anti-phishing no Microsoft Defender [](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)para Office 365, assista a este breve vídeo de treinamento ou conclua as seguintes etapas:

1. Acesse [https://protection.office.com](https://protection.office.com).

2. No Centro de &amp; Conformidade de Segurança, no painel de navegação esquerdo, em Gerenciamento **de Ameaças,** escolha **Política.**

3. Na página **Política,** escolha **Anti-phishing.**

4. Na página **Anti-phishing,** selecione **+ Criar**. Um assistente inicia essa etapa para definir sua política anti-phishing.

5. Especifique o nome, a descrição e as configurações da política, conforme recomendado na tabela a seguir. Para obter mais detalhes, [consulte Saiba mais sobre a política anti-phishing no Microsoft Defender para opções do Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. Depois de revisar suas configurações, escolha **Criar esta política** ou **Salvar,** conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Domínio e equipe de campanha mais valiosa|
|Descrição|Verifique se a equipe mais importante e nosso domínio não estão sendo personificados.|
|Adicionar usuários a proteger|Select **+ Add a condition, The recipient is**. Digite nomes de usuário ou insira o endereço de email do candidato, gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que deseja proteger contra representação.|
|Adicionar domínios para proteger|Select **+ Add a condition, The recipient domain is**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você tiver definido um. Você pode inserir mais de um domínio.|
|Escolher ações|Se o email for enviado por um usuário personificado: Escolha **Redirecionar** mensagem para outro endereço de email e digite o endereço de email do administrador de segurança; por exemplo, *Alice <span> <span> @contoso.com*. Se o email for enviado por um domínio representado: escolha **Colocar mensagem em quarentena**.|
|Inteligência da caixa de correio|Por padrão, a caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe essa configuração **Ativada** para obter melhores resultados.|
|Adicionar remetentes e domínios confiáveis|Aqui você pode adicionar seu próprio domínio ou qualquer outro domínio confiável.|
|Aplicado a|Selecione **O domínio do destinatário é**. Em **Qualquer um desses**, selecione **Escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, *contoso. <span> <span> com*, na lista e, em seguida, selecione **Adicionar**. Selecione **Concluído**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Proteger contra anexos mal-intencionados e arquivos com Anexos Seguros

As pessoas enviam, recebem e compartilham anexos regularmente, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil saber se um anexo é seguro ou mal-intencionado apenas olhando para uma mensagem de email. O Microsoft Defender para Office 365 inclui a proteção de Anexo Seguro, mas essa proteção não está 1000 por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Essa proteção se estende a arquivos no SharePoint, No OneDrive e no Microsoft Teams.

Para criar uma política de Anexo Seguro, assista [a este breve vídeo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou conclua as seguintes etapas:

1. Vá para [https://protection.office.com](https://protection.office.com) e entre com sua conta de administrador.

2. No Centro de &amp; Conformidade de Segurança, no painel de navegação esquerdo, em Gerenciamento **de Ameaças,** escolha **Política.**

3. Na página Política, escolha **Anexos Seguros.**

4. Na página Anexos seguros, aplique essa proteção amplamente, selecionando a caixa de seleção Ativar ATP para **SharePoint, OneDrive** e Microsoft Teams.

5. Selecione **+** para criar uma nova política.

6. Aplique as configurações na tabela a seguir.

7. Depois de revisar suas configurações, escolha **Criar esta política** ou **Salvar,** conforme apropriado.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Bloquear emails atuais e futuros com malware detectado.|
|Descrição|Bloquear emails e anexos atuais e futuros com malware detectado.|
|Salvar anexos resposta de malware desconhecido|Select **Block - Block the current and future emails and attachments with detected malware**.|
|Redirecionar anexo na detecção|Habilitar redirecionamento (selecione esta caixa) Insira a conta de administrador ou uma configuração de caixa de correio para quarentena.          Aplique a seleção acima se a verificação de anexos de malware e o erro ocorrer (marque esta caixa).|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, [consulte Configurar políticas anti-phishing no Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteger-se contra ataques de phishing com Links seguros

Às vezes, os hackers ocultam sites mal-intencionados em links de email ou outros arquivos. Os Links Seguros, parte do Microsoft Defender para Office 365, podem ajudar a proteger sua organização fornecendo verificação de hora de clique de endereços da Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio de políticas de Links seguros.

Recomendamos que você faça o seguinte:

- Modifique a política padrão para aumentar a proteção.

- Adicione uma nova política direcionada a todos os destinatários em seu domínio.

Para configurar links seguros, assista a [este breve vídeo de treinamento](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:

1. Vá para [https://protection.office.com](https://protection.office.com) e entre com sua conta de administrador.

2. No Centro de &amp; Conformidade de Segurança, no painel de navegação esquerdo, em Gerenciamento **de Ameaças,** escolha **Política.**

3. Na página Política, escolha Links **Seguros.**

Para modificar a política padrão:

1. Na página Links seguros, em **Políticas que se aplicam a toda a organização,** selecione a **política** Padrão.

2. Em **Configurações que se aplicam ao conteúdo,** exceto email, selecione Aplicativos do **Microsoft 365 para empresas, Office para iOS e Android.**

3. Selecione **Salvar**.

Para criar uma nova política direcionada a todos os destinatários em seu domínio:

1. Na página Links seguros, em Políticas que se aplicam a toda a **organização,** selecione **+** para criar uma nova política.

2. Aplique as configurações listadas na tabela a seguir.

3. Selecione **Salvar**.

|Configuração ou opção|Configuração recomendada|
|---|---|
|Nome|Política de links seguros para todos os destinatários no domínio|
|Selecionar a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.|
|Usar Anexos Seguros para verificar o conteúdo baixável|Marque essa caixa.|
|Aplicado a|O domínio do destinatário é . . . selecione seu domínio.|

Para obter mais informações, consulte [Links seguros.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)

## <a name="go-to-intune-admin-center"></a>Ir para o Centro de administração do Intune

1. Entre no [portal do Azure.](https://portal.azure.com/)

2. Selecione **Todos os serviços** e digite no *Intune* na caixa **de pesquisa.**

3. Depois que os resultados aparecerem, selecione o início ao lado do **Microsoft Intune** para torná-lo um favorito e fácil de encontrar mais tarde.

Além do centro de administração, você pode usar o Intune para registrar e gerenciar os dispositivos da sua organização. Para obter mais informações, consulte Recursos pelo método de registro para [dispositivos Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) e opções de registro [para dispositivos gerenciados pelo Intune.](https://docs.microsoft.com/intune/enrollment-options)
