---
title: Aumentar a proteção contra ameaças para o Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Configurar a proteção avançada contra ameaças do Office 365 e proteger dados confidenciais contra phishing, malware e outras ameaças.
ms.openlocfilehash: 17425de3f6e0022945899a559cf88575b6315a56
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561601"
---
# <a name="increase-threat-protection"></a>Aumente a proteção contra ameaças

Este artigo ajuda você a aumentar a proteção em sua assinatura do Microsoft 365 para proteção contra phishing, malware e outras ameaças. Essas recomendações são apropriadas para organizações com uma necessidade maior de segurança, como escritórios de advocacia e clínicas de assistência médica.

Antes de começar, verifique sua pontuação segura do Office 365. A pontuação segura do Office 365 analisa a segurança da sua organização do Office 365 com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Para aumentar sua pontuação, conclua as ações recomendadas neste artigo. O objetivo não é atingir a pontuação máxima, mas para estar ciente das oportunidades de proteger seu ambiente que não afete negativamente a produtividade dos seus usuários. 

Para obter mais informações, consulte [Microsoft Secure Score](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentar o nível de proteção contra malware no email

O ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware. Você pode aumentar essa proteção, bloqueando anexos com tipos de arquivo comumente usados para malware. Para aumentar a proteção contra malware no email:
  
1. Acesse [https://protection.office.com](https://protection.office.com) e entre com suas credenciais de conta de administrador. 
    
2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política** \> **anti-malware**.
    
3. Clique duas vezes na política padrão para editar a política em toda a empresa.
    
4. Selecione **Configurações**.
    
5. Em **filtro tipos de anexo comuns**, selecione **ativado**. Os tipos de arquivo bloqueados são listados na janela diretamente abaixo desse controle. Certifique-se de adicionar esses tipos de arquivos:
   - Ade, ADP, Ani, Bas, bat, CHM, cmd, com, CPL, CRT, HLP, HT, HTA, inf, ins, ISP, Job, js, jse, lnk, o mdb, o MDE, o registro, o MSC, o (a) msp, o. exe, o, o, o VB, vbe, vbs,  <br/> 
   
   Se necessário, você pode adicionar ou excluir tipos de arquivo mais tarde.
    
6. Selecione **salvar.**
    
Para obter mais informações, consulte [proteção Antimalware](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Proteger contra ransomware

O ransomware restringe o acesso aos dados criptografando arquivos ou bloqueando telas de computador. Em seguida, tenta extort dinheiro de vítimas solicitando "resgate", geralmente na forma de cryptocurrencies como Bitcoin, no Exchange para acessar os dados. 
  
Para proteger contra o ransomware, crie uma ou mais regras de fluxo de email para bloquear extensões de arquivo comumente usadas para ransomware. (Você adicionou essas regras na etapa [aumentar o nível de proteção contra malware no email](#raise-the-level-of-protection-against-malware-in-mail) .) Você também pode avisar os usuários que recebem esses anexos por email.

Além dos arquivos que você bloqueou na etapa anterior, é uma boa prática criar uma regra para avisar os usuários antes de abrir os anexos de arquivo do Office que incluem macros. O ransomware pode ser oculto dentro de macros, portanto, avisar os usuários que não devem abrir esses arquivos de pessoas que não conhecem.

Para criar uma regra de transporte de emails:
  
1. Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>em e escolha central de **Administração** \> do **Exchange**.
    
2. Na categoria **fluxo de emails** , selecione **regras**.
    
3. Selecione **+** e, em seguida, selecione **criar uma nova regra**.
    
4. Selecione **mais opções** na parte inferior da caixa de diálogo para ver o conjunto completo de opções. 
    
5. Aplicar as configurações da tabela a seguir para a regra. Use os valores padrão para o restante das configurações, a menos que você queira alterá-las.
    
6. Selecione **Salvar**.
    
|**Configuração**|**Avisar os usuários antes de abrir anexos de arquivos do Office**||
|:-----|:-----|:-----|
|Nome  <br/> |Regra anti-ransomware: avisar os usuários  <br/>  |
|Aplicar esta regra se. . .  <br/> |Qualquer anexo. . . correspondências de extensão de arquivo. . .  <br/> |
|Especificar palavras ou frases  <br/> |Adicione estes tipos de arquivos:  <br/> dotm, docm, xlsm, sltm, xla, xlam, XLL, pptm, potm, ppam, ppsm, sldm  <br/>|
|Faça o seguinte. . .  <br/> |Notificar o destinatário com uma mensagem  <br/> |
|Fornecer texto da mensagem  <br/> |Não abra esses tipos de arquivos de pessoas que você não sabe porque eles podem conter macros com código mal-intencionado.  <br/> |
   
Para saber mais, confira:
  
- [Como lidar com o ransomware](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [Restaurar o OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Parar o encaminhamento automático para email

Hackers que obtêm acesso à caixa de correio de um usuário podem roubar emails Configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Para evitar que isso aconteça, configure uma regra de fluxo de emails. 
  
Para criar uma regra de transporte de email, Assista [a este vídeo curto](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) ou siga estas etapas:
  
1. No centro de administração do Microsoft 365, selecione Central de **Administração** \> do **Exchange**.
    
2. Na categoria **fluxo de emails** , selecione **regras**.
    
3. Selecione **+** e, em seguida, selecione **criar uma nova regra**.
    
4. Para ver todas as opções, selecione **mais opções** na parte inferior da caixa de diálogo. 
    
5. Aplicar as configurações na tabela a seguir. Use os valores padrão para o restante das configurações, a menos que você queira alterá-las.
    
6. Selecione **Salvar**.
    
|**Configuração**|**Avisar os usuários antes de abrir anexos de arquivos do Office**|
|:-----|:-----|
|Nome  <br/> |Impedir o encaminhamento automático de emails para domínios externos  <br/> |
|Aplicar esta regra se...  <br/> |O remetente. . . é externo/interno. . . Dentro da organização  <br/> |
|Adicionar condição  <br/> |As propriedades da mensagem. . . inclua o tipo de mensagem. . . Avanço automático  <br/> |
|Faça o seguinte...  <br/> |Bloquear a mensagem. . . rejeitar a mensagem e incluir uma explicação.  <br/> |
|Fornecer texto da mensagem  <br/> |O encaminhamento automático de emails fora dessa organização é impedido por motivos de segurança.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Proteger seu email contra ataques de phishing

Se você configurou um ou mais domínios personalizados para o seu ambiente do Office 365 ou do Microsoft 365, é possível configurar a proteção antiphishing dirigida. A proteção antiphishing da ATP, parte da proteção avançada contra ameaças do Office 365, pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não é necessário fazer isso.
  
Recomendamos que você comece a usar essa proteção criando uma política para proteger seus usuários mais importantes e seu domínio personalizado. 

Para criar uma política anti-phishing do ATP, Assista a [este vídeo de treinamento curto](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)ou conclua as seguintes etapas:
  
1. Acesse [https://protection.office.com](https://protection.office.com). 
    
2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.
    
3. Na página **política** , escolha o **anti-phishing ATP**.
    
4. Na página **anti-phishing** , selecione **+ criar**. Um assistente é iniciado que orienta você na definição da política anti-phishing.
    
5. Especifique o nome, a descrição e as configurações da política, conforme recomendado na tabela a seguir. Para obter mais detalhes, consulte [saiba mais sobre opções de política de anti-phishing do ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options). 
    
6. Após revisar as configurações, escolha **criar esta política** ou **salvar**, conforme apropriado.
    

|**Configuração ou opção**<br/>|**Configuração recomendada** <br/>|
|:-----|:-----|
|Nome  <br/> |O domínio e a equipe de campanha mais valiosa  <br/> |
|Descrição  <br/> |Garantir que a equipe mais importante e nosso domínio não estão sendo representados.  <br/> |
|Adicionar usuários para proteger  <br/> |Selecione **+ Adicionar uma condição, o destinatário é**. Digite nomes de usuário ou insira o endereço de email do candidato, o gerente de campanha e outros membros importantes da equipe. Você pode adicionar até 20 endereços internos e externos que você deseja proteger da representação.  <br/> |
|Adicionar domínios para proteger  <br/> |Selecione **+ Adicionar uma condição, o domínio do destinatário é**. Insira o domínio personalizado associado à sua assinatura do Microsoft 365, se você tiver definido um. Você pode inserir mais de um domínio.  <br/> |
|Escolher ações  <br/> |Se o email for enviado por um usuário representado: escolha **redirecionar mensagem para outro endereço de email**e digite o endereço de email do administrador de segurança; por exemplo, *Ana<span><span>Maria @contoso. com*. Se o email for enviado por um domínio representado: escolher **mensagem de quarentena**.  <br/> |
|Inteligência de caixa de correio  <br/> |Por padrão, a inteligência de caixa de correio é selecionada quando você cria uma nova política anti-phishing. Deixe esta configuração **em** para obter os melhores resultados.  <br/> |
|Adicionar domínios e remetentes confiáveis  <br/> |Aqui você pode adicionar seu próprio domínio ou qualquer outro domínio confiável.  <br/> |
|Aplicado a  <br/> |Selecione **o domínio do destinatário**. Em **qualquer um dos seguintes**, selecione **escolher**. Selecione **+ Adicionar**. Marque a caixa de seleção ao lado do nome do domínio, por exemplo, *contoso.<span> com <span>*, na lista e selecione **Adicionar**. Selecione **Concluído**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Proteger contra anexos e arquivos mal-intencionados com anexos seguros de ATP

Pessoas costumam enviar, receber e compartilhar anexos, como documentos, apresentações, planilhas e muito mais. Nem sempre é fácil dizer se um anexo é seguro ou mal-intencionado apenas olhando uma mensagem de email. O Office 365 proteção avançada contra ameaças inclui proteção de anexo seguro de ATP, mas essa proteção não é ativada por padrão. Recomendamos que você crie uma nova regra para começar a usar essa proteção. Esta proteção estende-se aos arquivos no SharePoint, no OneDrive e no Microsoft Teams.
  
Para criar uma política de anexo seguro ATP, Assista a [este breve vídeo](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)ou conclua as seguintes etapas:
  
1. Vá até [https://protection.office.com](https://protection.office.com)e entre com sua conta de administrador. 
    
2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.
    
3. Na página política, escolha **anexos seguros de ATP**.
    
4. Na página de anexos seguros, aplique essa proteção amplamente marcando a caixa de seleção **ativar a ATP para SharePoint, onedrive e Microsoft Teams** . 
    
5. Selecione **+** para criar uma nova política. 
    
6. Aplicar as configurações na tabela a seguir. 
    
7. Depois de revisar as configurações, escolha **criar esta política** ou **salvar**, conforme apropriado.
    

|**Configuração ou opção**|**Configuração recomendada** <br/>|
|:-----|:-----|
|Nome  <br/> |Bloquear emails atuais e futuros com malware detectado.  <br/> |
|Descrição  <br/> |Bloquear emails e anexos atuais e futuros com malware detectado.  <br/> |
|Salvar anexos resposta desconhecida de malware  <br/> |Selecione **Bloquear – bloquear emails e anexos atuais e futuros com malware detectado**.  <br/> |
|Redirecionar o anexo na detecção  <br/> |Habilitar o redirecionamento (Selecione esta caixa) Insira a conta de administrador ou uma configuração de caixa de correio para quarentena.          Aplica a seleção acima se a verificação de malware por anexos expira ou quando ocorre um erro (Selecione esta caixa).  <br/> |
|Aplicado a  <br/> |O domínio do destinatário é. . . Selecione seu domínio.  <br/> |
   
Para obter mais informações, consulte [set up Office 365 ATP anti-phishing Policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Proteger contra ataques de phishing com links seguros de ATP

Os hackers às vezes ocultam sites mal-intencionados em links em email ou outros arquivos. Os links seguros de ATP do Office 365 (links seguros de ATP), parte da proteção avançada contra ameaças do Office 365, podem ajudar a proteger sua organização fornecendo a verificação de tempo de clique de endereços Web (URLs) em mensagens de email e documentos do Office. A proteção é definida por meio das políticas de links seguros de ATP.
  
Recomendamos que você faça o seguinte:
  
- Modificar a política padrão para aumentar a proteção.
    
- Adicione uma nova política direcionada a todos os destinatários em seu domínio.
    
Para configurar links de ATP seguros, Assista a [este vídeo de treinamento curto](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)ou conclua as seguintes etapas:
  
1. Vá até [https://protection.office.com](https://protection.office.com)e entre com sua conta de administrador. 
    
2. No centro de conformidade com &amp; segurança do Office 365, no painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política**.
    
3. Na página política, escolha **links seguros de ATP**.
    
Para modificar a política padrão:
  
1. Na página de links seguros, em **políticas que se aplicam a toda a organização**, selecione a política **padrão** . 
    
2. Em **configurações que se aplicam ao conteúdo exceto email**, selecione **Office 365 ProPlus, Office para IOS e Android**.
    
3. Selecione **Salvar**. 
    
Para criar uma nova política direcionada para todos os destinatários em seu domínio:
  
1. Na página de links seguros, em **políticas que se aplicam a toda a organização**, selecione **+** para criar uma nova política. 
    
2. Aplicar as configurações listadas na tabela a seguir.
    
3. Selecione **Salvar**. 

|**Configuração ou opção**|**Configuração recomendada** <br/>|
|:-----|:-----|
|Nome  <br/> |Política de links seguros para todos os destinatários no domínio  <br/> |
|Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens  <br/> |Selecione as **URLs que serão reconfiguradas e verificadas em relação a uma lista de links mal-intencionados conhecidos quando o usuário clicar no link**.  <br/> |
|Usar anexos seguros para examinar Conteúdo baixável  <br/> |Selecione essa caixa.  <br/> |
|Aplicado a  <br/> |O domínio do destinatário é. . . Selecione seu domínio.  <br/> |
   
Para obter mais informações, consulte [Office 365 ATP Safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Vá para o centro de administração do Intune

1. Entre no [portal do Azure](https://portal.azure.com/).

2. Selecione **todos os serviços** e digite no *Intune* na **caixa de pesquisa**.

3. Depois que os resultados são exibidos, selecione Iniciar ao lado do **Microsoft Intune** para torná-lo favorito e fácil de localizar mais tarde.

Além do centro de administração, você pode usar o Intune para registrar e gerenciar os dispositivos de sua organização. Para saber mais, confira [recursos por método de inscrição para dispositivos do Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) e [Opções de registro para dispositivos gerenciados pelo Intune](https://docs.microsoft.com/intune/enrollment-options).
