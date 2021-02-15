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
description: os cenários mais comuns de ameaças e ataques enfrentados atualmente pelas organizações para seus ambientes do Microsoft 365 e ações recomendadas para reduzir esses riscos.
ms.openlocfilehash: 64f4491db3dc4ef18411b166fb23c4388383dae2
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944293"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDMs)

Este artigo discute alguns dos cenários mais comuns de ameaças e ataques enfrentados atualmente pelas organizações para seus ambientes do Microsoft 365 e as ações recomendadas para reduzir esses riscos. Embora o Microsoft 365 tenha uma ampla variedade de recursos de segurança pré-configurados, ele também exige que você, como cliente, tome a responsabilidade de proteger suas próprias identidades, dados e dispositivos usados para acessar serviços de nuvem. Essas diretrizes foram desenvolvidas pelo Grupo Desdobrete (Arquiteto de Segurança de Nuvem da Microsoft) e Thiagaaga Sundararajan (Consultor Sênior da Microsoft).

Este artigo é organizado por prioridade de trabalho, começando pela proteção dessas contas usadas para administrar os serviços e ativos mais importantes, como seu locatário, email e SharePoint. Ele fornece uma maneira metométrica para abordar a segurança e funciona em conjunto com a seguinte planilha para que você possa acompanhar o progresso com as partes interessadas e equipes em toda a sua organização: segurança do Microsoft 365 para planilha [BDMs.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) 

[![Planilha de recomendações de segurança de BDM do Microsoft 365 BDM com imagem em miniatura](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

A Microsoft fornece a ferramenta Classificação de Segurança em seu locatário para analisar automaticamente a postura de segurança com base em suas atividades regulares, atribuir uma pontuação e fornecer recomendações de melhoria de segurança. Antes de tomar as ações recomendadas neste artigo, anote sua pontuação atual e recomendações. As ações recomendadas neste artigo aumentarão sua pontuação. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades de proteger seu ambiente de maneira que não afete negativamente a produtividade dos usuários. Confira [o Microsoft Secure Score.](mtp/microsoft-secure-score.md)

![Siga estas etapas para reduzir os riscos para sua empresa.](../media/security/security-for-bdms-overview.png)

Mais uma coisa antes de começar. . . Certifique-se [de ativar o log de auditoria.](../compliance/search-the-audit-log-in-security-and-compliance.md) Você precisará esses dados mais tarde, caso precise investigar um incidente ou uma violação. 

## <a name="protect-privileged-accounts"></a>Proteger contas privilegiadas

Como primeira etapa, recomendamos garantir que contas críticas no ambiente tenham uma camada extra de proteção, pois essas contas têm acesso e permissões para gerenciar e alterar serviços e recursos críticos que podem afetar negativamente toda a organização, se comprometidas. Proteger contas privilegiadas é uma das maneiras mais eficazes de se proteger contra um invasor que procura elevar as permissões de uma conta comprometida para uma administrativa. 

|Recomendação  |E3 |E5  |
|---------|---------|---------|
|Impor a MFA (autenticação multifatória) para todas as contas administrativas.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)| 
|Implemente o PiM (Privileged Identity Management) do Azure Active Directory (Azure AD) para aplicar o acesso privilegiado just-in-time aos recursos do Azure AD e do Azure. Você também pode descobrir quem tem acesso e revisar o acesso privilegiado.|         | ![marca de seleção verde](../media/green-check-mark.png)|
|Implemente o gerenciamento de acesso privilegiado para gerenciar o controle de acesso granular sobre tarefas de administração privilegiadas no Office 365. |         | ![marca de seleção verde](../media/green-check-mark.png)|
|Configurar e usar Estações de Trabalho com Acesso Privilegiado (PAW) para administrar serviços. Não use as mesmas estações de trabalho para navegar na Internet e verificar emails não relacionados à sua conta administrativa.|  ![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png) | 

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteger contas privilegiadas](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Recomendações adicionais:
- Certifique-se de que as contas sincronizadas a partir do local não sejam atribuídas funções de administrador para serviços de nuvem. Isso ajuda a impedir que um invasor 800 contas locais obtenham acesso administrativo aos serviços de nuvem. 
- Verifique se as contas de serviço não têm funções de administrador atribuídas. Essas contas geralmente não são monitoradas e definidas com senhas que não expiram. Comece garantindo que as contas de serviços AADConnect e ADFS não sejam Administradores Globais por padrão.
- Remover licenças de contas de administrador. A menos que haja um caso de uso específico para atribuir licenças a contas de administrador específicas, remova as licenças dessas contas. 

## <a name="reduce-the-surface-of-attack"></a>Reduzir a superfície de ataque

A próxima área de foco é reduzir a superfície de ataque. Isso pode ser feito com o mínimo de esforço e impacto para seus usuários e serviços. Ao reduzir a área de superfície de ataque, os invasores têm menos maneiras de iniciar um ataque contra sua organização.

Aqui estão alguns exemplos:
- Desabilite os protocolos POP3, IMAP e SMTP. A maioria das organizações modernas não usa mais esses protocolos mais antigos. Você pode desabilitá-los com segurança e permitir exceções somente conforme necessário. 
- Reduza e mantenha o número de Administradores Globais no locatário para o mínimo absoluto necessário. Isso reduz diretamente a área de superfície de ataque para todos os aplicativos de nuvem. 
- Retire servidores e aplicativos que não são mais usados em seu ambiente. 
- Implemente um processo para desabilitar e excluir contas que não são mais usadas. 

## <a name="protect-against-known-threats"></a>Proteger-se contra ameaças conhecidas

As ameaças conhecidas incluem malware, contas comprometidas e phishing. Algumas proteções contra essas ameaças podem ser implementadas rapidamente sem impacto direto para os usuários, enquanto outras exigem mais planejamento e treinamento do usuário. 

|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configure a autenticação multifacional e use políticas de acesso condicional recomendadas, incluindo políticas de risco de entrada.** A Microsoft recomenda e testou um conjunto de políticas que funcionam em conjunto para proteger todos os aplicativos de nuvem, incluindo os serviços do Office 365 e do Microsoft 365. Consulte [Configurações de acesso a identidades e dispositivos.](./office-365-security/microsoft-365-policies-configurations.md) | |![marca de seleção verde](../media/green-check-mark.png)|
|**Exigir autenticação multifa factor para todos os usuários.** Se você não tiver o licenciamento necessário para implementar as políticas de acesso condicional recomendadas, no mínimo exigirá a autenticação multifacional para todos os usuários.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|**Eleva o nível de proteção contra malware no email.** Seu ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção bloqueando anexos com tipos de arquivo comumente usados para malware.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|**Proteja seu email contra ataques de phishing direcionados.** Se você tiver configurado um ou mais domínios personalizados para seu ambiente do Office 365 ou do Microsoft 365, poderá configurar a proteção anti-phishing direcionada. A proteção anti-phishing, parte do Defender para Office 365, pode ajudar a proteger sua organização contra ataques de phishing com base em representação mal-intencionada e outros ataques de phishing. Se você ainda não configurou um domínio personalizado, não é necessário fazer isso.| |![marca de seleção verde](../media/green-check-mark.png)|
|**Proteger-se contra ataques de ransomware no email.** O ransomware retira o acesso aos seus dados criptografando arquivos ou bloquear telas do computador. Em seguida, ele tenta armazenar dinheiro de vítima, solicitando "resgate", geralmente na forma de cryptocurrencies como Mila, em troca de retornar o acesso aos seus dados. Você pode ajudar a se defender contra ransomware criando uma ou mais regras de fluxo de emails para bloquear extensões de arquivo comumente usadas para ransomware ou para avisar os usuários que recebem esses anexos por email.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|**Bloqueie conexões de países com os que você não faz negócios.** Crie uma política de acesso condicional do Azure AD para bloquear todas as conexões provenientes desses países, criando efetivamente um firewall geográfica em torno de seu locatário.| |![marca de seleção verde](../media/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteger contra ameaças conhecidas](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Proteger-se contra ameaças desconhecidas

Depois de adicionar proteções extras às suas contas privilegiadas e proteger contra ataques conhecidos, mude sua atenção para a proteção contra ameaças desconhecidas. Os adversários mais determinados e avançados usam métodos inovadores e novos e desconhecidos para atacar as organizações. Com a ampla telemetria de dados da Microsoft coletada em mais de bilhões de dispositivos, aplicativos e serviços, podemos executar o Defender para Office 365 no Windows, Office 365 e Azure para evitar ataques de Dia Zero, usando ambientes de áreas de segurança e verificando a validade antes de permitir o acesso ao seu conteúdo. 


|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configurar o Microsoft Defender para Office 365:**<br>* Anexos seguros<br>* Links seguros<br>* ATP para SharePoint, OneDrive e Microsoft Teams<br>* Anti-phishing no Defender para proteção do Office 365|         |![marca de seleção verde](../media/green-check-mark.png) |
|**Configurar o Microsoft Defender para recursos de ponto de extremidade:**<br>* Windows Defender Antivírus <br>* Exploit Protection <br> * Redução de superfície de ataque <br> * Isolamento baseado em hardware <br>* Acesso controlado a pastas     |         |![marca de seleção verde](../media/green-check-mark.png) |
|**Use o Microsoft Cloud App Security** para descobrir aplicativos SaaS e começar a usar análise de comportamento e detecção de anomalias. |         |![marca de seleção verde](../media/green-check-mark.png) |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra ameaças desconhecidas](../media/m365-security-bdm-illustrations-unknown-threats.png)

Recomendações adicionais:
- Comunicações seguras de canal de parceiros, como emails usando TLS.
- Abra a Federação do Teams somente para parceiros com quem você se comunica.
- Não adicione domínios de remetente, remetentes individuais ou IPs de origem à sua lista de autorizações, pois isso permite que eles ignorem verificações de spam e malware — Uma prática comum com os clientes é adicionar seus próprios domínios aceitos ou vários outros domínios em que os problemas de fluxo de email podem ter sido relatados à lista de autorizações. Não adicione domínios à lista filtragem de spam e conexão, pois isso potencialmente ignora todas as verificações de spam. 
- Habilitar notificações de spam de saída — Habilita as notificações de spam de saída para uma lista de distribuição internamente para a equipe de helpdesk ou administrador de IT para relatar se algum dos usuários internos está enviando emails de spam externamente. Isso pode ser um indicador de que a conta foi comprometida.
- Desabilitar o PowerShell Remoto para todos os usuários — o PowerShell Remoto é usado principalmente por administradores para acessar serviços para fins administrativos ou acesso programático à API. Recomendamos desabilitar essa opção para que os usuários que não são administradores evitem o abuso, a menos que eles tenham um requisito comercial para acessá-la. 
- Bloqueie o acesso ao portal de Gerenciamento do Microsoft Azure para todos os não administradores. Você pode fazer isso criando uma regra de acesso condicional para bloquear todos os usuários, com exceção dos administradores. 


## <a name="assume-breach"></a>Presumir violação

Embora a Microsoft toma todas as medidas possíveis para evitar ameaças e ataques, recomendamos sempre trabalhar sob a mentalidade "Presumir violação". Mesmo que um invasor consiga se desafocar no ambiente, precisamos garantir que ele não consiga exfiltrar dados ou informações de identidade do ambiente. Por esse motivo, recomendamos a habilitação da proteção contra vazamentos de dados confidenciais, como números de PREVIDÊNCIA SOCIAL, números de cartões de crédito, informações pessoais adicionais e outras informações confidenciais no nível organizacional. 

A mentalidade "Presumir violação" requer a implementação de uma estratégia de rede de confiança zero, o que significa que os usuários não são totalmente confiáveis apenas porque são internos da rede. Em vez disso, como parte da autorização do que os usuários podem fazer, conjuntos de condições são especificados e, quando essas condições são atendidas, determinados controles são aplicados. As condições podem incluir o status de saúde do dispositivo, o aplicativo que está sendo acessado, as operações sendo executadas e o risco do usuário. Por exemplo, uma ação de registro de dispositivo deve sempre disparar a autenticação MFA para garantir que nenhum dispositivo de rede seja adicionado ao seu ambiente. 

Uma estratégia de rede de confiança zero também exige que você saiba onde suas informações estão armazenadas e aplique os controles apropriados para classificação, proteção e retenção. Para proteger efetivamente seus ativos mais importantes e confidenciais, você precisa primeiro identificar onde eles estão localizados e fazer inventário, o que pode ser desafiador. Em seguida, trabalhe com sua organização para definir uma estratégia de governança. Definir um esquema de classificação para uma organização e configurar políticas, rótulos e condições requer planejamento e preparação cuidadosos. É importante perceber que esse não é um processo orientado por IT. Certifique-se de trabalhar com sua equipe jurídica e de conformidade para desenvolver uma classificação apropriada e um esquema de rotulagem para os dados da sua organização.

Os recursos de proteção de informações do Microsoft 365 podem ajudá-lo a descobrir quais informações você tem, onde estão armazenadas e quais informações exigem proteção adicional. A proteção de informações é um processo contínuo e os recursos do Microsoft 365 fornecem visibilidade de como os usuários estão usando e distribuindo informações confidenciais, onde suas informações estão armazenadas no momento e onde elas fluem. Você também pode ver como os usuários manipulam informações regulamentadas para garantir que os rótulos e proteções apropriados sejam aplicados.


|Recomendação |E3|E5 |
|---------|---------|---------|
|**Revise e otimize o acesso condicional e as políticas relacionadas para se alinhar com seus objetivos para uma rede de confiança zero.** A proteção contra ameaças conhecidas inclui a implementação de um conjunto de [políticas recomendadas.](./office-365-security/microsoft-365-policies-configurations.md) Revise sua implementação dessas políticas para garantir que você esteja protegendo seus aplicativos e dados contra hackers que tenham acesso à sua rede. Observe que a política de proteção de aplicativo recomendada do Intune para Windows 10 habilita a WIP (Proteção de Informações do Windows). A WIP protege contra vazamentos acidentais de dados da sua organização por meio de aplicativos e serviços, como email, mídias sociais e a nuvem pública. |         |![marca de seleção verde](../media/green-check-mark.png)|
|**Desabilitar o encaminhamento de email externo.** Os hackers que têm acesso à caixa de correio de um usuário podem roubar seus emails configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem o reconhecimento do usuário. Você pode impedir que isso aconteça configurando uma regra de fluxo de emails.|![marca de seleção verde](../media/green-check-mark.png) |![marca de seleção verde](../media/green-check-mark.png)|
|**Desabilitar o compartilhamento de calendário externo anônimo.** Por padrão, o compartilhamento de calendário anônimo externo é permitido. [Desabilite o compartilhamento](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) de calendário para reduzir possíveis vazamentos de informações confidenciais.|![marca de seleção verde](../media/green-check-mark.png) |![marca de seleção verde](../media/green-check-mark.png)|
|**Configurar políticas de prevenção contra perda de dados para dados confidenciais.** Crie uma Política de Prevenção contra Perda de Dados no Centro de Conformidade de Segurança para descobrir e proteger dados confidenciais, como números de cartão de crédito, números de previdência social e números &amp; de contas bancárias. O Microsoft 365 inclui muitos tipos predefinidos de informações confidenciais que você pode usar em políticas de prevenção contra perda de dados. Você também pode criar seus próprios tipos de informações confidenciais para dados confidenciais que são personalizados para seu ambiente. |![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|**Implemente a classificação de dados e as políticas de proteção de informações.** Implemente rótulos de sensibilidade e use-os para classificar e aplicar proteção a dados confidenciais. Você também pode usar esses rótulos em políticas de prevenção contra perda de dados. Se você estiver usando rótulos da Proteção de Informações do Azure, recomendamos que você evite criar novos rótulos em outros centros de administração.|         |![marca de seleção verde](../media/green-check-mark.png)|
|**Proteger dados em aplicativos e serviços de terceiros usando o Cloud App Security.** Configure as políticas do Cloud App Security para proteger informações confidenciais em aplicativos de nuvem de terceiros, como Salesforce, Box ou Dropbox. Você pode usar os tipos de informações confidenciais e os rótulos de sensibilidade criados nas políticas do Cloud App Security e aplicá-los em seus aplicativos SaaS. <br><br>O Microsoft Cloud App Security permite impor uma ampla variedade de processos automatizados. As políticas podem ser definidas para fornecer verificações de conformidade contínuas, tarefas legais de DescobertaScoberta, DLP para conteúdos confidenciais compartilhados publicamente e muito mais. O Cloud App Security pode monitorar qualquer tipo de arquivo com base em mais de 20 filtros de metadados (por exemplo, nível de acesso, tipo de arquivo). |         |![marca de seleção verde](../media/green-check-mark.png)|
|**Use [o Microsoft Defender para o Ponto de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) Extremidade para identificar se os usuários armazenam informações confidenciais em seus dispositivos Windows.** |         |![marca de seleção verde](../media/green-check-mark.png)|
|**Use [o Scanner AIP para](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) identificar e classificar informações entre servidores e compartilhamentos de arquivos.** Use a ferramenta de relatório do AIP para exibir os resultados e tomar as ações apropriadas.|         |![marca de seleção verde](../media/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteger contra violações](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Monitoramento e auditoria contínuos

Por último, mas não menos a Auditoria e Monitoramento Contínuo do ambiente do Microsoft 365, juntamente com o Windows e os Dispositivos, é fundamental para garantir que você seja capaz de detectar e remediar rapidamente as invasões. Ferramentas como a Classificação de Segurança, a Central de Segurança e a análise avançada do Microsoft Intelligent Graph fornecem informações valiosas para seu locatário e vinculam grandes quantidades de inteligência contra ameaças e dados de segurança para fornecer proteção e detecção de ameaças inigualáveis.


|Recomendação |E3 |E5 |
|---------|---------|---------|
|Verifique se **o log de auditoria** está ligado.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|**Analisar a Classificação de** Segurança semanalmente — A Pontuação Segura é um local central para acessar o status de segurança da sua empresa e tomar ações com base nas recomendações da Classificação de Segurança. É recomendável executar essa verificação semanalmente.|![marca de seleção verde](../media/green-check-mark.png)|![marca de seleção verde](../media/green-check-mark.png)|
|Use **as ferramentas do Microsoft Defender para Office 365:**<br>* Recursos de investigação e resposta a ameaças<br> * Investigação e resposta automatizadas |         |![marca de seleção verde](../media/green-check-mark.png)|
|Use **o Microsoft Defender para o ponto de extremidade:**<br> *    [Detecção e resposta do ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Classificação de segurança de investigação e correção automatizadas <br>*    [Busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![marca de seleção verde](../media/green-check-mark.png)|
|Use **o Microsoft Cloud App Security** para detectar comportamento incomum em aplicativos de nuvem para identificar ransomware, usuários comprometidos ou aplicativos não autorizados, analisar o uso de alto risco e remediar automaticamente para limitar o risco à sua organização.|         |![marca de seleção verde](../media/green-check-mark.png)|
|Use **o Microsoft Azure Sentinel ou sua** ferramenta SIEM atual para monitorar ameaças em seu ambiente. |         |![marca de seleção verde](../media/green-check-mark.png)|
|**Implante [o Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)** para monitorar e proteger contra ameaças direcionadas ao seu ambiente local do Active Directory.   |         |![marca de seleção verde](../media/green-check-mark.png) |
|Use o **Azure Defender** _ para monitorar ameaças em cargas de trabalho híbridas e na nuvem. O Azure Defender_ inclui uma camada gratuita de recursos e uma camada padrão de recursos que são pagos com base em horas de recursos ou transações.|         |         |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para monitoramento e auditoria contínuos](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Principais ações de monitoramento recomendadas:
- **Revise o Microsoft Secure Score semanalmente** — A Classificação de Segurança é um local central para acessar o status de segurança do seu locatário e para tomar ações com base nas principais recomendações. É recomendável executar essa verificação semanalmente. O Secure Score inclui recomendações de todo o Azure AD, Intune, Cloud App Security e Microsoft Defender para o Ponto de Extremidade, bem como o Office 365. 
- **Revise os logons arriscados** semanalmente — Use o Centro de administração do Azure AD para revisar as entrada arriscadas semanalmente. O ruleset de acesso de dispositivo e identidade recomendado inclui uma política para impor a alteração de senha em logins arriscados.  
- Revise os principais usuários de malware e **phished** semanalmente — Use o Microsoft Defender para o Explorador de Ameaças do Office 365 para revisar os principais usuários direcionados a malware e phishing e descobrir a causa raiz do motivo pelo qual esses usuários são afetados.
