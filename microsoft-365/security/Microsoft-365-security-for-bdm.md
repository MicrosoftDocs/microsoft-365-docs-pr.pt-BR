---
title: Segurança da Microsoft 365 para responsáveis por decisões de negócios (BDMs)
ms.author: bcarter
author: brendacarter
manager: ''
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: os cenários mais comuns de ameaças e ataques enfrentados pelas organizações para seus ambientes Microsoft 365 e as ações recomendadas para reduzir esses riscos.
ms.openlocfilehash: 3d2c7fc289930e3cc73deddcd43f25efc321a237
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801246"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Segurança da Microsoft 365 para responsáveis por decisões de negócios (BDMs)

Este artigo discute alguns dos cenários mais comuns de ameaça e ataque enfrentados pelas organizações para seus ambientes Microsoft 365 e as ações recomendadas para a redução desses riscos. Embora o Microsoft 365 seja fornecido com uma ampla variedade de recursos de segurança pré-configurados, ele também exige que o cliente realize a responsabilidade de proteger suas próprias identidades, dados e dispositivos usados para acessar os serviços de nuvem. Esta orientação foi desenvolvida por Kozeta feixe (Microsoft Cloud Security Architect) e Thiagaraj Sundararajan (consultor sênior da Microsoft).

Este artigo é organizado por prioridade de trabalho, começando com a proteção dessas contas usadas para administrar os serviços e ativos mais importantes, como seu locatário, email e SharePoint. Ele oferece uma maneira de método de abordagem de segurança e funciona em conjunto com a planilha a seguir para que você possa acompanhar o progresso dos participantes e das equipes em sua organização: [Microsoft 365 Security for BDMs](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![Imagem em miniatura planilha recomendações de segurança do Microsoft 365 BDM](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

A Microsoft fornece a ferramenta de Pontuação segura no seu locatário para analisar automaticamente a postura de segurança com base em suas atividades regulares, atribuir uma pontuação e fornecer recomendações de melhoria de segurança. Antes de executar as ações recomendadas neste artigo, anote sua pontuação e recomendações atuais. As ações recomendadas neste artigo aumentarão sua pontuação. O objetivo não é atingir a pontuação máxima, mas ter em mente as oportunidades de proteger seu ambiente de uma maneira que não afete negativamente a produtividade dos seus usuários. Confira a [Pontuação segura da Microsoft](mtp/microsoft-secure-score.md).

Mais uma coisa antes de começarmos. . . Certifique-se de [ativar o log de auditoria do Office 365](../compliance/search-the-audit-log-in-security-and-compliance.md). Você precisará desses dados mais tarde, no caso de você precisar investigar um incidente ou uma violação. 

## <a name="protect-privileged-accounts"></a>Proteger contas privilegiadas

Como primeira etapa, recomendamos garantir que as contas críticas no ambiente têm uma camada adicional de proteção, pois essas contas têm acesso e permissões para gerenciar e alterar serviços e recursos críticos que podem afetar negativamente a organização inteira, Se for comprometido. A proteção de contas privilegiadas é uma das maneiras mais eficazes de proteger-se contra um invasor que busca elevar as permissões de uma conta comprometida para um administrador. 

|Recomendação  |E3 |E5  |
|---------|---------|---------|
|Aplicar a MFA (autenticação multifator) para todas as contas administrativas.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)| 
|Implemente o Azure Active Directory (Azure AD) de gerenciamento de identidade privilegiado (PIM) para aplicar acesso privilegiado just-in-time aos recursos do Azure AD e do Azure. Você também pode descobrir quem tem acesso e examinar o acesso privilegiado.|         | ![marca de seleção verde](../images/green-check-mark.png)|
|Implemente o gerenciamento de acesso privilegiado no Office 365 para gerenciar o controle de acesso granular sobre tarefas administrativas privilegiadas no Office 365. |         | ![marca de seleção verde](../images/green-check-mark.png)|
|Configurar e usar pata (estações de trabalho privilegiadas) para administrar serviços. Não use as mesmas estações de trabalho para navegar na Internet e verificar emails não relacionados à sua conta administrativa.|  ![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png) | 

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção de contas privilegiadas](../images/m365-security-bdm-illustrations-privileged-accounts.png)

Recomendações adicionais:
- Certifique-se de que as contas que estão sincronizadas no local não estão atribuídas a funções de administrador para serviços em nuvem. Isso ajuda a evitar que um invasor Aproveite contas locais para obter acesso administrativo aos serviços em nuvem. 
- Verifique se as contas de serviço não estão atribuídas a funções de administrador. Essas contas geralmente não são monitoradas e definidas com senhas que não expiram. Para começar, certifique-se de que as contas de serviços AADConnect e ADFS não sejam administradores globais por padrão.
- Remover licenças de contas de administrador. A menos que haja um caso de uso específico para atribuir licenças a contas de administrador específicas, remova as licenças dessas contas. 

## <a name="reduce-the-surface-of-attack"></a>Reduzir a superfície de ataque

A próxima área de foco está reduzindo a superfície de ataque. Isso pode ser feito com o mínimo de esforço e impacto para os seus usuários e serviços. Ao reduzir a área de superfície de ataque, os invasores têm menos meios de iniciar um ataque contra sua organização.

Aqui estão alguns exemplos:
- Desabilite os protocolos POP3, IMAP e SMTP. As organizações mais modernas não usam mais esses protocolos mais antigos. Você pode desabilitá-los com segurança e permitir exceções apenas quando necessário. 
- Reduza e mantenha o número de administradores globais no locatário para o mínimo necessário. Isso reduz diretamente a área de superfície de ataque para todos os aplicativos em nuvem. 
- Desative os servidores e aplicativos que não são mais usados em seu ambiente. 
- Implemente um processo para desabilitar e excluir contas que não são mais usadas. 

## <a name="protect-against-known-threats"></a>Proteger contra ameaças conhecidas

Ameaças conhecidas incluem malware, contas comprometidas e phishing. Algumas proteções contra essas ameaças podem ser implementadas rapidamente sem impacto direto nos seus usuários, enquanto outras exigem mais planejamento e treinamento do usuário. 

|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configurar a autenticação multifator e usar políticas de acesso condicional recomendadas, incluindo políticas de risco de entrada**. A Microsoft recomenda e testou um conjunto de políticas que trabalham em conjunto para proteger todos os aplicativos de nuvem, incluindo o Office 365 e os serviços do Microsoft 365. Confira [configurações de acesso de dispositivo e identidade](../enterprise/microsoft-365-policies-configurations.md). | |![marca de seleção verde](../images/green-check-mark.png)|
|**Exija a autenticação multifator para todos os usuários**. Se você não tiver o licenciamento necessário para implementar as políticas de acesso condicional recomendadas, pelo menos exija autenticação multifator para todos os usuários.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|**Aumente o nível de proteção contra malware no email**. O ambiente do Office 365 ou do Microsoft 365 inclui proteção contra malware, mas você pode aumentar essa proteção, bloqueando anexos com tipos de arquivo comumente usados para malware.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|**Proteger seu email contra ataques de phishing direcionados**. Se você configurou um ou mais domínios personalizados para o seu ambiente do Office 365 ou do Microsoft 365, é possível configurar a proteção antiphishing dirigida. A proteção antiphishing da ATP, parte da proteção avançada contra ameaças do Office 365, pode ajudar a proteger sua organização contra ataques de phishing baseados em representação mal-intencionada e outros ataques de phishing. Se você não configurou um domínio personalizado, não é necessário fazer isso.| |![marca de seleção verde](../images/green-check-mark.png)|
|**Proteger contra ataques de ransomware no email**. O ransomware retira o acesso aos seus dados criptografando arquivos ou bloqueando telas de computador. Em seguida, tenta extort dinheiro de vítimas solicitando "resgate", geralmente na forma de cryptocurrencies como Bitcoin, no Exchange para retornar o acesso aos seus dados. Você pode ajudar a se defender contra o ransomware criando uma ou mais regras de fluxo de email para bloquear extensões de arquivo comumente usadas para ransomware ou avisar os usuários que recebem esses anexos por email.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|**Bloquear conexões de países que você não faz negócios com**. Crie uma política de acesso condicional do Azure AD para bloquear qualquer conexão proveniente desses países, criando efetivamente um firewall geográfico em torno do seu locatário.| |![marca de seleção verde](../images/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra ameaças conhecidas](../images/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Proteção contra ameaças desconhecidas

Após adicionar proteções extras às suas contas privilegiadas e proteger contra ataques conhecidos, você deve mudar sua atenção para proteção contra ameaças desconhecidas. Os adversários mais determinados e avançados usam métodos inovadores e novos e desconhecidos para organizações de ataques. Com a grande telemetria de dados da Microsoft coletada por bilhões de dispositivos, aplicativos e serviços, podemos executar a proteção avançada contra ameaças no Windows, no Office 365 e no Azure para evitar ataques de dia zero, usando ambientes de caixa de areia e verificação da validade antes de permitir o acesso ao seu conteúdo. 


|Recomendação  |E3  |E5  |
|---------|---------|---------|
|**Configurar a proteção avançada contra ameaças do Office 365 (ATP)**:<br>• Anexos seguros de ATP<br>• Links seguros de ATP<br>• ATP para SharePoint, OneDrive e Microsoft Teams<br>• Proteção anti-phishing do ATP|         |![marca de seleção verde](../images/green-check-mark.png) |
|**Configure os recursos de proteção avançada contra ameaças do Microsoft defender**:<br>• Windows Defender Antivirus <br>• Proteção contra Exploit <br> • Redução da superfície de ataque <br> • Isolamento baseado em hardware <br>• Acesso a pastas controladas     |         |![marca de seleção verde](../images/green-check-mark.png) |
|**Use o Microsoft Cloud app Security** para descobrir aplicativos SaaS e começar a usar análise de comportamento e detecção de anomalias. |         |![marca de seleção verde](../images/green-check-mark.png) |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra ameaças desconhecidas](../images/m365-security-bdm-illustrations-unknown-threats.png)

Recomendações adicionais:
- Comunicações de canal de parceiros seguros, como emails usando TLS.
- Abra a Federação do Microsoft Teams apenas para parceiros com os quais você se comunica.
- Não listar domínios de remetente, remetentes individuais ou IPs de origem como isso permite que eles ignorem as verificações de spam e malware — uma prática comum com os clientes é a lista de seus próprios domínios aceitos ou vários outros domínios nos quais os problemas de fluxo de emails podem ter sido informação. Não adicione domínios na lista de filtragem de spam e de conexão, pois isso potencialmente ignora todas as verificações de spam. 
- Habilitar notificações de spam de saída — habilitar notificações de spam de saída para uma lista de distribuição internamente para a equipe de assistência técnica ou administrador de ti para relatar se algum dos usuários internos estão enviando emails de spam externamente. Pode ser um indicador de que a conta foi comprometida.
- Desabilitar o PowerShell remoto para todos os usuários – o PowerShell remoto é usado principalmente por administradores para acessar os serviços do Office 365 para fins administrativos ou acesso programático à API. Recomendamos desabilitar essa opção para usuários que não são administradores para evitar o reconhecimento, a menos que eles tenham uma necessidade de negócios para acessá-lo. 
- Bloquear o acesso ao portal de gerenciamento do Microsoft Azure para todos os não administradores. Você pode fazer isso criando uma regra de acesso condicional para bloquear todos os usuários, com exceção de administradores. 


## <a name="assume-breach"></a>Assumir violação

Embora a Microsoft considere todas as medidas possíveis para evitar ameaças e ataques, recomendamos sempre trabalhar sob a mentalidade "supor a violação". Mesmo que um invasor tenha sido gerenciado para invadir o ambiente, precisamos garantir que eles não consigam Exfiltrate dados ou informações de identidade do ambiente. Por esse motivo, recomendamos habilitar a proteção contra vazamentos de dados confidenciais, como números de seguridade social, números de cartões de crédito, informações pessoais adicionais e outras informações confidenciais de nível organizacional. 

A mentalidade "supor violação" requer a implementação de uma estratégia de rede de confiança zero, o que significa que os usuários não são totalmente confiáveis apenas porque eles são internos da rede. Em vez disso, como parte da autorização do que os usuários podem fazer, os conjuntos de condições são especificados e, quando essas condições forem atendidas, certos controles serão impostos. As condições podem incluir o status de integridade do dispositivo, o aplicativo que está sendo acessado, operações que estão sendo executadas e o risco Por exemplo, uma ação de registro de dispositivo sempre deve disparar a autenticação MFA para garantir que nenhum dispositivo Rouge seja adicionado ao seu ambiente. 

Uma estratégia de rede de confiança zero também exige que você saiba onde suas informações estão armazenadas e aplique os controles apropriados para classificação, proteção e retenção. Para proteger efetivamente seus ativos mais importantes e confidenciais, você precisa primeiro identificar onde eles estão localizados e fazer o estoque, o que pode ser desafiador. Em seguida, trabalhe com sua organização para definir uma estratégia de governança. A definição de um esquema de classificação para uma organização e a configuração de políticas, rótulos e condições exigem planejamento e preparação cuidadosos. É importante perceber que esse não é um processo orientado por ti. Certifique-se de trabalhar com sua equipe jurídica e de conformidade para desenvolver uma classificação apropriada e o esquema de rotulação para os dados da sua organização.

Os recursos de proteção de informações do Microsoft 365 podem ajudá-lo a descobrir quais informações você tem, onde elas estão armazenadas e quais informações exigem proteção adicional. A proteção de informações é um processo contínuo e os recursos do Microsoft 365 fornecem visibilidade de como os usuários estão usando e distribuindo informações confidenciais, onde suas informações estão armazenadas no momento e onde elas fluem. Você também pode ver como os usuários manipulam informações regulamentadas para garantir que os rótulos e proteções apropriados sejam aplicados.


|Recomendação |E3|E5 |
|---------|---------|---------|
|**Revise e otimize o acesso condicional e as políticas relacionadas para alinhar seus objetivos para uma rede de confiança zero**. A proteção contra ameaças conhecidas inclui a implementação de um conjunto de [políticas recomendadas](../enterprise/microsoft-365-policies-configurations.md). Revise sua implementação dessas políticas para garantir que você esteja protegendo seus aplicativos e dados contra hackers que obtiveram acesso à sua rede. Observe que a política de proteção de aplicativos do Intune recomendada para o Windows 10 permite o WIP (proteção de informações do Windows). O WIP protege contra vazas acidentais de seus dados da sua organização por meio de aplicativos e serviços, como email, mídia social e nuvem pública. |         |![marca de seleção verde](../images/green-check-mark.png)|
|**Desative o encaminhamento de email externo**. Hackers que obtêm acesso à caixa de correio de um usuário podem roubar seus emails Configurando a caixa de correio para encaminhar emails automaticamente. Isso pode acontecer mesmo sem a conscientização do usuário. Você pode evitar que isso aconteça Configurando uma regra de fluxo de emails.|![marca de seleção verde](../images/green-check-mark.png) |![marca de seleção verde](../images/green-check-mark.png)|
|**Desabilite o compartilhamento de calendário externo anônimo**. Por padrão, o compartilhamento de calendário anônimo externo é permitido. [Desabilite o compartilhamento de calendário](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) para reduzir possíveis vazamentos de informações confidenciais.|![marca de seleção verde](../images/green-check-mark.png) |![marca de seleção verde](../images/green-check-mark.png)|
|**Configure as políticas de prevenção contra perda de dados para dados confidenciais**. Crie uma política de prevenção de perda de dados no centro de segurança e conformidade do Office 365 para descobrir e proteger dados confidenciais, como números de cartão de crédito, números de seguridade social e números de contas bancárias. O Office 365 inclui muitos tipos de informações confidenciais predefinidos que podem ser usados em políticas de prevenção contra perda de dados. Você também pode criar seus próprios tipos de informações confidenciais para dados confidenciais personalizados para seu ambiente. |![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|**Implementar políticas de classificação de dados e proteção de informações**. Implemente rótulos de confidencialidade no Office 365 e use-os para classificar e aplicar proteção a dados confidenciais. Você também pode usar esses rótulos em políticas de prevenção contra perda de dados. Se você estiver usando os rótulos de proteção de informações do Azure, recomendamos que você evite criar novos rótulos em outros centros de administração.|         |![marca de seleção verde](../images/green-check-mark.png)|
|**Proteger dados em aplicativos e serviços de terceiros usando o Cloud app Security**. Configure as políticas de segurança de aplicativos de nuvem para proteger informações confidenciais entre aplicativos de nuvem de terceiros, como Salesforce, caixa ou dropbox. Você pode usar tipos de informações confidenciais e os rótulos de confidencialidade que você criou no Office 365 nas políticas de segurança do Cloud app e aplicá-los em seus aplicativos SaaS. <br><br>O Microsoft Cloud app Security permite que você aplique uma ampla variedade de processos automatizados. As políticas podem ser definidas para fornecer varreduras de conformidade contínua, tarefas de eDiscovery legais, DLP para conteúdo confidencial compartilhado publicamente e muito mais. Cloud app Security pode monitorar qualquer tipo de arquivo com base em mais de 20 filtros de metadados (por exemplo, nível de acesso, tipo de arquivo). |         |![marca de seleção verde](../images/green-check-mark.png)|
|**Use [o Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) para identificar se os usuários armazenam informações confidenciais em seus dispositivos Windows**. |         |![marca de seleção verde](../images/green-check-mark.png)|
|**Use o [scanner AIP](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) para identificar e classificar informações entre servidores e compartilhamentos de arquivos**. Use a ferramenta de relatório do AIP para exibir os resultados e tomar as ações apropriadas.|         |![marca de seleção verde](../images/green-check-mark.png)|

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para proteção contra violação](../images/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Monitoramento e auditoria contínuos

Por fim, mas não a monitoração e a auditoria menos contínuas do ambiente do Microsoft 365 junto com as janelas e dispositivos são fundamentais para garantir que você possa detectar e corrigir rapidamente qualquer invasão. Ferramentas como Pontuação segura, central de segurança e análises avançadas do Microsoft Intelligent Graph fornecem informações valiosas para seu locatário e vinculam quantidades maciças de dados de inteligência e segurança de ameaças para fornecer proteção contra ameaças sem paralelo e detecção.


|Recomendação |E3 |E5 |
|---------|---------|---------|
|Verifique se o **log de auditoria do Office 365** está ativado.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|**Revisar Pontuação segura semanalmente** , a pontuação segura é um local central para acessar o status de segurança do seu locatário do Office 365 e realizar ações com base nas recomendações de Pontuação segura. É recomendável executar essa verificação semanal.|![marca de seleção verde](../images/green-check-mark.png)|![marca de seleção verde](../images/green-check-mark.png)|
|Usar as ferramentas de **ATP do Office 365** :<br>• Recursos de investigação e resposta contra ameaças<br> • Investigação e resposta automatizadas |         |![marca de seleção verde](../images/green-check-mark.png)|
|Usar **o Microsoft defender ATP**:<br> • [Detecção e resposta de ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> • Pontuação segura de investigação e correção automatizada <br>• [Busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![marca de seleção verde](../images/green-check-mark.png)|
|Use **o Microsoft Cloud app Security** para detectar um comportamento incomum nos aplicativos de nuvem para identificar o ransomware, usuários comprometidos ou aplicativos mal-intencionados, analisar o uso de alto risco e corrigi-lo automaticamente para limitar o risco à sua organização.|         |![marca de seleção verde](../images/green-check-mark.png)|
|Use o **Microsoft Azure Sentinel** ou sua ferramenta **Siem atual** para monitorar ameaças em todo o seu ambiente. O Azure Sentinel é gratuito para uso durante o período de visualização. |         |![marca de seleção verde](../images/green-check-mark.png)|
|**Implantar o [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** para monitorar e proteger contra ameaças direcionadas ao seu ambiente local do Active Directory.   |         |![marca de seleção verde](../images/green-check-mark.png) |
|Use a **central de segurança do Azure** para monitorar ameaças em cargas de trabalho híbridas e de nuvem. A central de segurança do Azure inclui uma camada gratuita de recursos e uma camada padrão de recursos que são pagos com base em horas ou transações de recurso.|         |         |

O diagrama a seguir ilustra esses recursos.
![Recursos recomendados para monitoramento contínuo e auditoria](../images/m365-security-bdm-illustrations-monitoring-auditing.png)

Principais ações de monitoramento recomendadas:
- **Analisar a pontuação segura da Microsoft semanalmente** , a pontuação segura é um local central para acessar o status de segurança do seu locatário do Office 365 e realizar ações com base nas principais recomendações. É recomendável executar essa verificação semanal. A pontuação segura inclui recomendações de entre o Azure AD, o Intune, o Cloud app Security e a proteção avançada contra ameaças do Microsoft defender, bem como o Office 365. 
- **Revisar logons arriscados semanalmente** — use o centro de administração do Azure ad para analisar semanalmente os logins arriscados. O RuleSet de identidade e de acesso ao dispositivo recomendado inclui uma política para impor a alteração de senha em entradas arriscadas.  
- **Revisar os principais programas de malware e golpes por semana** — use o Office Advanced Threat Protection Threat Explorer para analisar os principais usuários direcionados com malware e Phish e para descobrir a causa raiz do motivo pelo qual esses usuários são afetados.
