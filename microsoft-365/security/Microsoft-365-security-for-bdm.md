---
title: Microsoft 365 Security for Business Decision Makers (BDMs)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: os cenários de ameaça e ataque mais comuns atualmente enfrentados pelas organizações para seus ambientes do Microsoft 365 e ações recomendadas para reduzir esses riscos.
ms.openlocfilehash: 328bd4c079531ee57b41422fd2d3f2c53ef8dc18
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051085"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDMs)

Este artigo discute alguns dos cenários de ameaça e ataque mais comuns atualmente enfrentados pelas organizações para seus ambientes do Microsoft 365 e ações recomendadas para reduzir esses riscos. Embora o Microsoft 365 venha com uma ampla matriz de recursos de segurança pré-configurados, ele também exige que você como o cliente se responsabilizar por proteger suas próprias identidades, dados e dispositivos usados para acessar serviços de nuvem. Essa orientação foi desenvolvida por Kazeta Beam (Arquiteto de Segurança na Nuvem da Microsoft) e Thiagaraj Sundararajan (Consultor Sênior da Microsoft).

Este artigo é organizado por prioridade de trabalho, começando pela proteção dessas contas usadas para administrar os serviços e ativos mais críticos, como seu locatário, email e SharePoint. Ele fornece uma maneira metodista para abordar a segurança e funciona em conjunto com a seguinte planilha para que você possa acompanhar seu progresso com as partes interessadas e equipes em toda a sua organização: segurança do [Microsoft 365 para planilha BDMs.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) 

[![Planilha de recomendações de segurança de BDM do Microsoft 365](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

A Microsoft fornece a ferramenta De pontuação segura em seu locatário para analisar automaticamente sua postura de segurança com base em suas atividades regulares, atribuir uma pontuação e fornecer recomendações de melhoria de segurança. Antes de tomar as ações recomendadas neste artigo, anote sua pontuação atual e recomendações. As ações recomendadas neste artigo aumentarão sua pontuação. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades de proteger seu ambiente de uma maneira que não afete negativamente a produtividade para seus usuários. Consulte [Microsoft Secure Score](defender/microsoft-secure-score.md).

![Siga estas etapas para reduzir os riscos para sua empresa.](../media/security/security-for-bdms-overview.png)

Mais uma coisa antes de começar. . . certifique-se [de ativar o log de auditoria](../compliance/search-the-audit-log-in-security-and-compliance.md). Você precisará dos dados mais tarde, caso precise investigar um incidente ou uma violação. 

## <a name="protect-privileged-accounts"></a>Proteger contas privilegiadas

Como primeira etapa, recomendamos garantir que contas críticas no ambiente tenham uma camada extra de proteção, pois essas contas têm acesso e permissões para gerenciar e alterar serviços e recursos críticos que podem afetar negativamente toda a organização, se comprometida. Proteger contas privilegiadas é uma das maneiras mais eficazes de se proteger contra um invasor que busca elevar as permissões de uma conta comprometida para uma administrativa. 

|Recomendação  |E3 |E5  |
|---------|---------|---------|
|Impor a autenticação multifa factor (MFA) para todas as contas administrativas.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)| 
|Implemente o Azure Active Directory (Azure AD) Privileged Identity Management (PIM) para aplicar o acesso privilegiado just-in-time aos recursos do Azure AD e do Azure. Você também pode descobrir quem tem acesso e revisar o acesso privilegiado.|         | ![marca de verificação verde](../media/green-check-mark.png)|
|Implemente o gerenciamento de acesso privilegiado para gerenciar o controle de acesso granular sobre tarefas de administrador privilegiado no Office 365. |         | ![marca de verificação verde](../media/green-check-mark.png)|
|Configure e use o Privileged Access Workstations (PAW) para administrar serviços. Não use as mesmas estações de trabalho para navegar na Internet e verificar emails não relacionados à sua conta administrativa.|  ![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png) | 

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteger contas privilegiadas](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Recomendações adicionais:
- Verifique se as contas sincronizadas do local não são atribuídas a funções de administrador para serviços de nuvem. Isso ajuda a impedir que um invasor se aproveitar de contas locais para obter acesso administrativo aos serviços de nuvem. 
- Verifique se as contas de serviço não são atribuídas a funções de administrador. Essas contas geralmente não são monitoradas e definidas com senhas que não expiram. Comece garantindo que as contas dos serviços AADConnect e ADFS não sejam Administradores Globais por padrão.
- Remover licenças de contas de administrador. A menos que haja um caso de uso específico para atribuir licenças a contas de administrador específicas, remova as licenças dessas contas. 

## <a name="reduce-the-surface-of-attack"></a>Reduzir a superfície de ataque

A próxima área de foco é reduzir a superfície de ataque. Isso pode ser feito com mínimo esforço e impacto para seus usuários e serviços. Ao reduzir a área de superfície de ataque, os invasores têm menos maneiras de iniciar um ataque contra sua organização.

Aqui estão alguns exemplos:
- Desabilite protocolos POP3, IMAP e SMTP. A maioria das organizações modernas não usa mais esses protocolos mais antigos. Você pode desabilitá-los com segurança e permitir exceções apenas conforme necessário. 
- Reduza e mantenha o número de Administradores Globais no locatário para o mínimo absoluto necessário. Isso reduz diretamente a área de superfície de ataque para todos os aplicativos Cloud. 
- Retire servidores e aplicativos que não são mais usados em seu ambiente. 
- Implemente um processo para desabilitar e excluir contas que não são mais usadas. 

## <a name="protect-against-known-threats"></a>Proteger contra ameaças conhecidas

As ameaças conhecidas incluem malware, contas comprometidas e phishing. Algumas proteções contra essas ameaças podem ser implementadas rapidamente sem impacto direto para seus usuários, enquanto outras exigem mais planejamento e treinamento do usuário. 

|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configure a autenticação multifacional e use políticas de** acesso condicional recomendadas, incluindo políticas de risco de entrada. A Microsoft recomenda e testou um conjunto de políticas que funcionam em conjunto para proteger todos os aplicativos de nuvem, incluindo os serviços do Office 365 e do Microsoft 365. Consulte [Configurações de identidade e acesso a dispositivos.](./defender-365-security/microsoft-365-policies-configurations.md) | |![marca de verificação verde](../media/green-check-mark.png)|
|**Exigir autenticação multifa factor para todos os usuários**. Se você não tiver o licenciamento necessário para implementar as políticas de acesso condicional recomendadas, no mínimo exigirá autenticação multifacional para todos os usuários.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|**Eleva o nível de proteção contra malware no email.** Seu ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção bloqueando anexos com tipos de arquivo comumente usados para malware.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|**Proteja seu email contra ataques de phishing direcionados.** Se você configurou um ou mais domínios personalizados para seu ambiente do Office 365 ou do Microsoft 365, você pode configurar a proteção anti-phishing direcionada. A proteção anti-phishing, parte do Defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não precisa fazer isso.| |![marca de verificação verde](../media/green-check-mark.png)|
|**Proteger contra ataques de ransomware no email**. O ransomware tira o acesso aos seus dados criptografando arquivos ou bloqueio de telas do computador. Em seguida, ele tenta roubar dinheiro das vítimas solicitando "resgate", geralmente em forma de criptocurrencies como o Bitcoin, em troca de retornar o acesso aos seus dados. Você pode ajudar a se defender contra ransomware criando uma ou mais regras de fluxo de emails para bloquear extensões de arquivo que são comumente usadas para ransomware ou para avisar os usuários que recebem esses anexos por email.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|**Bloquear conexões de países com os** que você não faz negócios. Crie uma política de acesso condicional do Azure AD para bloquear todas as conexões provenientes desses países, criando efetivamente um firewall geo ao redor do locatário.| |![marca de verificação verde](../media/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra ameaças conhecidas](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Proteger contra ameaças desconhecidas

Depois de adicionar proteções extras às suas contas privilegiadas e proteger contra ataques conhecidos, mude sua atenção para proteger contra ameaças desconhecidas. Os adversários mais determinados e avançados usam métodos inovadores e novos e desconhecidos para atacar organizações. Com a grande telemetria da Microsoft de dados coletados sobre bilhões de dispositivos, aplicativos e serviços, podemos executar o Defender para o Office 365 no Windows, No Office 365 e no Azure para evitar ataques do Dia Zero, utilizando ambientes de caixa de areia e verificando a validade antes de permitir o acesso ao seu conteúdo. 


|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configurar o Microsoft Defender para Office 365**:<br>* Anexos Seguros<br>* Links seguros<br>* ATP para SharePoint, OneDrive e Microsoft Teams<br>* Anti-phishing no Defender para Proteção do Office 365|         |![marca de verificação verde](../media/green-check-mark.png) |
|**Configurar o Microsoft Defender para recursos do Ponto de Extremidade:**<br>* Windows Defender Antivírus <br>* Proteção de exploração <br> * Redução de superfície de ataque <br> * Isolamento baseado em hardware <br>* Acesso controlado a pastas     |         |![marca de verificação verde](../media/green-check-mark.png) |
|**Use o Microsoft Cloud App Security** para descobrir aplicativos SaaS e começar a usar análise de comportamento e detecção de anomalias. |         |![marca de verificação verde](../media/green-check-mark.png) |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra ameaças desconhecidas](../media/m365-security-bdm-illustrations-unknown-threats.png)

Recomendações adicionais:
- Proteger comunicações de canal de parceiro, como emails usando TLS.
- Abra a Federação do Teams somente para parceiros com os que você se comunica.
- Não adicione domínios de remetente, remetentes individuais ou IPs de origem à sua lista de autorizações, pois isso permite ignorar verificações de spam e malware — uma prática comum com os clientes é adicionar seus próprios domínios aceitos ou vários outros domínios em que os problemas de fluxo de email podem ter sido relatados à lista de autorizações. Não adicione domínios na lista Filtragem de Spam e Conexão, pois isso pode ignorar todas as verificações de spam. 
- Habilitar notificações de spam de saída — Habilitar notificações de spam de saída para uma lista de distribuição internamente para a equipe do Helpdesk ou administrador de IT relatar se algum dos usuários internos está enviando emails de spam externamente. Isso pode ser um indicador de que a conta foi comprometida.
- Desabilitar o PowerShell Remoto para todos os usuários — o PowerShell remoto é usado principalmente pelos administradores para acessar serviços para fins administrativos ou acesso à API programática. Recomendamos desabilitar essa opção para usuários que não são administradores evitarem o reconhecimento, a menos que eles tenham um requisito comercial para acessá-la. 
- Bloqueie o acesso ao portal de Gerenciamento do Microsoft Azure para todos os não administradores. Você pode fazer isso criando uma regra de acesso condicional para bloquear todos os usuários, com exceção de administradores. 


## <a name="assume-breach"></a>Assumir violação

Embora a Microsoft adoeça todas as medidas possíveis para evitar ameaças e ataques, recomendamos sempre trabalhar sob o mindset "Assume Breach". Mesmo que um Invasor tenha conseguido invadir o ambiente, precisamos garantir que ele não consiga exfiltrar dados ou informações de identidade do ambiente. Por esse motivo, recomendamos a habilitação da proteção contra vazamentos de dados confidenciais, como números da Previdência Social, números de cartões de crédito, informações pessoais adicionais e outras informações confidenciais de nível organizacional. 

A mentalidade "Assumir Violação" requer a implementação de uma estratégia de rede de confiança zero, o que significa que os usuários não são totalmente confiáveis apenas porque são internos da rede. Em vez disso, como parte da autorização do que os usuários podem fazer, conjuntos de condições são especificados e, quando essas condições são atendidas, determinados controles são imposto. As condições podem incluir o status de saúde do dispositivo, o aplicativo que está sendo acessado, as operações que estão sendo executadas e o risco do usuário. Por exemplo, uma ação de registro de dispositivo sempre deve disparar a autenticação MFA para garantir que nenhum dispositivo vermelho seja adicionado ao seu ambiente. 

Uma estratégia de rede de confiança zero também exige que você saiba onde suas informações estão armazenadas e aplique controles apropriados para classificação, proteção e retenção. Para proteger efetivamente seus ativos mais críticos e confidenciais, você precisa primeiro identificar onde eles estão localizados e fazer inventário, o que pode ser desafiador. Em seguida, trabalhe com sua organização para definir uma estratégia de governança. Definir um esquema de classificação para uma organização e configurar políticas, rótulos e condições requer planejamento e preparação cuidadosos. É importante perceber que esse não é um processo orientado por IT. Certifique-se de trabalhar com sua equipe legal e de conformidade para desenvolver uma classificação apropriada e um esquema de rotulagem para os dados da sua organização.

Os recursos de proteção de informações do Microsoft 365 podem ajudá-lo a descobrir quais informações você tem, onde estão armazenadas e quais informações exigem proteção adicional. A proteção de informações é um processo contínuo e os recursos do Microsoft 365 fornecem visibilidade sobre como os usuários estão usando e distribuindo informações confidenciais, onde suas informações estão armazenadas no momento e onde elas fluem. Você também pode ver como os usuários manipulam informações regulamentadas para garantir que os rótulos e proteções apropriados sejam aplicados.


|Recomendação |E3|E5 |
|---------|---------|---------|
|**Revise e otimize seu acesso condicional e políticas relacionadas para** alinhar com seus objetivos para uma rede de confiança zero. A proteção contra ameaças conhecidas inclui a implementação de um conjunto de [políticas recomendadas.](./defender-365-security/microsoft-365-policies-configurations.md) Revise sua implementação dessas políticas para garantir que você esteja protegendo seus aplicativos e dados contra hackers que tiveram acesso à sua rede. Observe que a política de proteção de aplicativos do Intune recomendada para Windows 10 habilita a Wip (Proteção de Informações do Windows). A WIP protege contra vazamentos acidentais de dados da sua organização por meio de aplicativos e serviços, como email, mídia social e a nuvem pública. |         |![marca de verificação verde](../media/green-check-mark.png)|
|**Desabilitar o encaminhamento de email externo.** Os hackers que têm acesso à caixa de correio de um usuário podem roubar seu email definindo a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode impedir que isso aconteça configurando uma regra de fluxo de emails.|![marca de verificação verde](../media/green-check-mark.png) |![marca de verificação verde](../media/green-check-mark.png)|
|**Desabilitar o compartilhamento de calendário externo anônimo**. Por padrão, o compartilhamento de calendário anônimo externo é permitido. [Desabilite o compartilhamento](/exchange/sharing/sharing-policies/modify-a-sharing-policy) de calendário para reduzir possíveis vazamentos de informações confidenciais.|![marca de verificação verde](../media/green-check-mark.png) |![marca de verificação verde](../media/green-check-mark.png)|
|**Configurar políticas de prevenção contra perda de dados para dados confidenciais.** Crie uma Política de Prevenção contra Perda de Dados no Centro de Conformidade e Segurança para descobrir e proteger dados confidenciais, como números de cartão de crédito, números da Previdência Social e números &amp; de contas bancárias. O Microsoft 365 inclui muitos tipos de informações confidenciais predefinidos que você pode usar em políticas de prevenção contra perda de dados. Você também pode criar seus próprios tipos de informações confidenciais para dados confidenciais personalizados ao seu ambiente. |![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|**Implemente políticas de classificação de dados e proteção de informações.** Implemente rótulos de sensibilidade e use-os para classificar e aplicar proteção a dados confidenciais. Você também pode usar esses rótulos em políticas de prevenção contra perda de dados. Se você estiver usando rótulos da Proteção de Informações do Azure, recomendamos que você evite criar novos rótulos em outros centros de administração.|         |![marca de verificação verde](../media/green-check-mark.png)|
|**Proteja dados em aplicativos e** serviços de terceiros usando o Cloud App Security . Configure políticas de Segurança de Aplicativos na Nuvem para proteger informações confidenciais em aplicativos de nuvem de terceiros, como Salesforce, Box ou Dropbox. Você pode usar tipos de informações confidenciais e os rótulos de sensibilidade criados nas políticas de Segurança de Aplicativos na Nuvem e aplicá-los em seus aplicativos SaaS. <br><br>O Microsoft Cloud App Security permite impor uma ampla variedade de processos automatizados. As políticas podem ser definidas para fornecer verificações de conformidade contínuas, tarefas legais de Descoberta Digital, DLP para conteúdos confidenciais compartilhados publicamente e muito mais. O Cloud App Security pode monitorar qualquer tipo de arquivo com base em mais de 20 filtros de metadados (por exemplo, nível de acesso, tipo de arquivo). |         |![marca de verificação verde](../media/green-check-mark.png)|
|**Use [o Microsoft Defender para o Ponto de](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) Extremidade para identificar se os usuários armazenam informações confidenciais em seus dispositivos Windows.** |         |![marca de verificação verde](../media/green-check-mark.png)|
|**Use [o Scanner AIP](/azure/information-protection/deploy-aip-scanner) para identificar e classificar informações entre servidores e compartilhamentos de arquivos.** Use a ferramenta de relatório AIP para exibir os resultados e tomar as ações apropriadas.|         |![marca de verificação verde](../media/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra violação](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Monitoramento e auditoria contínuos

Por fim, mas não menos importante, o Monitoramento Contínuo e a Auditoria do ambiente do Microsoft 365 juntamente com o Windows e os Dispositivos é fundamental para garantir que você seja capaz de detectar e remediar rapidamente quaisquer invasões. Ferramentas como a Pontuação Segura, o Centro de Segurança e a análise avançada do Microsoft Intelligent Graph fornecem informações valiosas para seu locatário e vinculam grandes quantidades de dados de inteligência e segurança contra ameaças para fornecer proteção e detecção de ameaças incomparáveis.


|Recomendação |E3 |E5 |
|---------|---------|---------|
|Verifique se **o log de auditoria** está ligado.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|**Analisar a Pontuação Segura** semanalmente — A pontuação segura é um local central para acessar o status de Segurança da sua empresa e tomar ações com base em recomendações de pontuação segura. É recomendável realizar essa verificação semanalmente.|![marca de verificação verde](../media/green-check-mark.png)|![marca de verificação verde](../media/green-check-mark.png)|
|Use **as ferramentas do Microsoft Defender para Office 365:**<br>* Recursos de investigação e resposta contra ameaças<br> * Investigação e resposta automatizadas |         |![marca de verificação verde](../media/green-check-mark.png)|
|Use **o Microsoft Defender para Ponto de Extremidade**:<br> *    [Detecção e resposta do ponto de extremidade](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Pontuação segura de investigação e correção automatizada <br>*    [Busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![marca de verificação verde](../media/green-check-mark.png)|
|Use **o Microsoft Cloud App Security** para detectar comportamento incomum em aplicativos de nuvem para identificar ransomware, usuários comprometidos ou aplicativos desonestos, analisar o uso de alto risco e corrigi-lo automaticamente para limitar o risco à sua organização.|         |![marca de verificação verde](../media/green-check-mark.png)|
|Use **o Microsoft Azure Sentinel ou** sua ferramenta SIEM atual para monitorar ameaças em todo o seu ambiente. |         |![marca de verificação verde](../media/green-check-mark.png)|
|**Implante [o Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)** para monitorar e proteger contra ameaças direcionadas ao seu ambiente local do Active Directory.   |         |![marca de verificação verde](../media/green-check-mark.png) |
|Use o **Azure Defender** _ para monitorar ameaças em cargas de trabalho híbridas e na nuvem. O Azure Defender_ inclui uma camada gratuita de recursos e uma camada padrão de recursos que são pagos com base em horas de recursos ou transações.|         |         |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para monitoramento e auditoria contínuos](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Principais ações de monitoramento recomendadas:
- **Revise a Pontuação Segura da Microsoft** semanalmente — A pontuação segura é um local central para acessar o status de segurança do locatário e para tomar ações com base nas principais recomendações. É recomendável realizar essa verificação semanalmente. A Pontuação Segura inclui recomendações de todo o Azure AD, Intune, Cloud App Security e Microsoft Defender para Ponto de Extremidade, bem como o Office 365. 
- **Revise os logons arriscados semanalmente** — Use o Centro de administração do Azure AD para analisar as insuidades arriscadas semanalmente. O ruleset de identidade e acesso de dispositivo recomendado inclui uma política para impor a alteração de senha em logins arriscados.  
- **Revise os principais malwares** e usuários phished semanalmente — Use o Microsoft Defender para o Office 365 Threat Explorer para revisar os principais usuários direcionados com malware e phishing e para descobrir a causa raiz do motivo pelo qual esses usuários são afetados.