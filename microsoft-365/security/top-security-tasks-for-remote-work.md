---
title: As 12 principais tarefas para equipes de segurança dar suporte ao trabalho de casa
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- remotework
description: 'Proteja seus emails e dados de negócios contra ameaças da Cyber, incluindo ransomware, phishing e anexos mal-intencionados. '
ms.openlocfilehash: 0730f4df4f6e9e72f024b35729909df309826625
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630792"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>As 12 principais tarefas para equipes de segurança dar suporte ao trabalho de casa

Se você é como a [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) e, de repente, está dando suporte a uma força de trabalho essencialmente baseada em casa, queremos ajudá-lo a garantir que sua organização esteja trabalhando o mais seguro possível. Este artigo prioriza tarefas para ajudar as equipes de segurança a implementar os recursos de segurança mais importantes o mais rápido possível. 

Se você for uma organização de pequeno e médio porte usando um dos planos de negócios da Microsoft, consulte estes recursos:
- [As 10 maneiras principais de proteger o Office 365 e o Microsoft 365 para planos de negócios](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 para campanhas](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (inclui uma configuração de segurança recomendada para o Microsoft 365 Business)

  
Para os clientes que usam nossos planos corporativos, a Microsoft recomenda que você conclua as tarefas listadas na tabela a seguir que se aplicam ao seu plano de serviço. Se, em vez de comprar um plano Microsoft 365 Enterprise, você está combinando assinaturas, observe o seguinte:
- O Microsoft 365 E3 inclui o Enterprise Mobility + Security (EMS) E3 e o Azure AD P1
- O Microsoft 365 E5 inclui o EMS E5 e o Azure AD P2
  
||**Task**| Todos os planos empresariais do Office 365|**Microsoft 365 E3** |**Microsoft 365 e5**|
|:-----|:-----|:-----|:-----|:-----|
|1      |[Habilitar a MFA (autenticação multifator do Azure)](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|duas     | [Proteção contra ameaças](#2-protect-against-threats) |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3D      |  [Configurar a proteção avançada contra ameaças do Office 365](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4       | [Configurar a proteção avançada contra ameaças (ATP) do Azure](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5      |   [Ativar a proteção avançada contra ameaças da Microsoft](#5-turn-on-microsoft-advanced-threat-protection)  |  |      | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6       | [Configurar a proteção de aplicativos móveis do Intune para telefones e tablets](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7      | [Configurar a MFA e o acesso condicional para convidados, incluindo a proteção de aplicativos do Intune](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8       |  [Registrar PCs no gerenciamento de dispositivos e exigir computadores compatíveis](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9       | [Otimizar sua rede para conectividade de nuvem](#9-optimize-your-network-for-cloud-connectivity)  |  ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10    | [Treinar usuários](#10-train-users) |    ![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11 |[Introdução ao Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security) |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12  |[Monitorar ameaças e tomar ações](#12-monitor-for-threats-and-take-action) |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Incluído](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Antes de começar, verifique sua pontuação de segurança do [microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) na central de segurança do Microsoft 365. A partir de um painel centralizado, você pode monitorar e aprimorar a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365. Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança (como exibir relatórios) ou endereçar recomendações com aplicativos ou software de terceiros. As tarefas recomendadas neste artigo aumentarão sua pontuação.
  
![Captura de tela da Pontuação segura da Microsoft](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: habilitar a MFA (autenticação multifator do Azure)
A melhor coisa que você pode fazer para melhorar a segurança de funcionários que trabalham em casa é ativar a MFA. Se você ainda não tem processos no lugar, trate isso como um piloto de emergência e certifique-se de que você tem suporte para pessoas prontas para ajudar os funcionários que se encontram presas. Como provavelmente, você não pode distribuir dispositivos de segurança de hardware, usar aplicativos de autenticação de biometria e Smartphone do Windows Hello como o Microsoft Authenticator.

Normalmente, a Microsoft recomenda que você forneça aos usuários 14 dias para registrar o dispositivo para autenticação multifator antes de exigir a MFA. No entanto, se sua força de trabalho estiver trabalhando de repente, vá em frente e exija MFA como uma prioridade de segurança e prepare-se para ajudar os usuários que precisarem. 

A aplicação dessas políticas levará apenas alguns minutos, mas estará preparada para dar suporte aos usuários nos próximos dias.  


|Plano  |Recomendação  |
|---------|---------|
|Microsoft 365 Plans (sem o Azure AD P1 ou P2)     |[Habilitar padrões de segurança no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Os padrões de segurança no Azure AD incluem MFA de usuários e administradores.   |
|Microsoft 365 E3 (com o Azure AD P1)     | Use [políticas de acesso condicional comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas: <br>- [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (com o Azure AD P2)     | Aproveitando a proteção de identidade do Azure AD, comece a implementar o [conjunto recomendado de acesso condicional e políticas relacionadas](../enterprise/identity-access-policies.md) da Microsoft, criando estas duas políticas:<br> - [Exigir MFA quando o risco de entrada for médio ou alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloquear clientes que não dão suporte à autenticação moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Usuários de alto risco devem alterar a senha](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: proteger contra ameaças

Todos os planos do Microsoft 365 incluem vários recursos de proteção contra ameaças. O relevo da proteção desses recursos leva apenas alguns minutos.
- Proteção antimalware
- Proteção de arquivos e URLs maliciosos
- Proteção anti-phishing
- Proteção antispam

Consulte [proteger contra ameaças no Office 365](office-365-security/protect-against-threats.md) para obter orientações que você pode usar como ponto de partida.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: configurar a proteção avançada contra ameaças do Office 365

A proteção avançada contra ameaças (ATP) do Office 365, incluída no Microsoft 365 E5 e no Office 365 e5, protege sua organização contra ameaças maliciosas representadas por mensagens de email, links (URLs) e ferramentas de colaboração. Isso pode levar várias horas para configurar.

Office 365 ATP:
- Protege sua organização contra ameaças de email desconhecidas em tempo real usando sistemas inteligentes que inspecionam anexos e links de conteúdo mal-intencionado. Esses sistemas automatizados incluem uma plataforma robusta do acionamento, heurística e modelos de aprendizado de máquina. 
- Protege sua organização quando os usuários colaboram e compartilham arquivos, identificando e bloqueando arquivos mal-intencionados em sites de equipe e bibliotecas de documentos. 
- Aplica modelos de aprendizado de máquina e algoritmos avançados de detecção de representação a ataques de phishing da AVERT. 

Para obter uma visão geral, incluindo um resumo dos planos, confira [proteção avançada contra ameaças do Office 365](office-365-security/office-365-atp.md).

O administrador global pode configurar essas proteções:
- [Configurar links seguros de ATP](office-365-security/set-up-atp-safe-links-policies.md)
- [Configurar uma política de Anexos Seguros de ATP](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Configurar uma lista personalizada de URLs do tipo "não reconfigurar" ](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Configurar uma lista personalizada de URLs bloqueadas](office-365-security/set-up-a-custom-blocked-urls-list-wtih-atp.md)

Você precisará trabalhar com seu administrador do Exchange Online e administrador do SharePoint Online para configurar a ATP para essas cargas de trabalho:
- [Ativar a ATP para SharePoint, OneDrive e Microsoft Teams](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: configurar a proteção avançada contra ameaças do Azure

A [proteção avançada contra ameaças do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) é uma solução de segurança baseada em nuvem que aproveita seus sinais do Active Directory local para identificar, detectar e investigar ameaças avançadas, identidades comprometidas e ações mal-intencionadas intencionais direcionadas para sua organização. Concentre-se nesse próximo porque ele protege sua infraestrutura local e de nuvem, não tem dependências ou pré-requisitos e pode fornecer benefícios imediatos.


- Confira o [início rápido do Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) para obter a configuração rapidamente 
- Assista [ao vídeo: Introduction to Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Analisar as [três fases da implantação do Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-advanced-threat-protection"></a>5: ativar a proteção avançada contra ameaças da Microsoft

Agora que você tem o Office 365 ATP e o Azure ATP configurados, você pode exibir os sinais combinados desses recursos em um painel. A [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) reúne alertas, incidentes, investigação e resposta automatizadas e busca avançada entre cargas de trabalho (Azure ATP, Office 365 ATP, Microsoft defender ATP e Microsoft Cloud app Security) em um único painel em [Security.Microsoft.com](https://security.microsoft.com). 
<br>

![Ilustração do painel MTP](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
Depois de configurar um ou mais serviços avançados de proteção contra ameaças, ative o MTP. Novos recursos são adicionados continuamente ao MTP; Considere optar por receber recursos de visualização.

- [Saiba mais sobre MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Ativar MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Aceitar recursos de visualização](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: configurar a proteção de aplicativos móveis do Intune para telefones e tablets

O Microsoft Intune Mobile Application Management (MAM) permite que você gerencie e proteja os dados da sua organização em telefones e tablets sem gerenciar esses dispositivos. Veja como funciona:
- Você cria uma política de proteção de aplicativo (aplicativo) que determina quais aplicativos em um dispositivo são gerenciados e quais comportamentos são permitidos (por exemplo, impedir que os dados de um aplicativo gerenciado sejam copiados para um aplicativo não gerenciado). Você cria uma política para cada platorm (iOS, Android).
- Depois de criar as políticas de proteção de aplicativo, você as aplica criando uma regra de acesso condicional no Azure AD para exigir aplicativos aprovados e proteção de dados de aplicativos.

As políticas de proteção de aplicativos incluem muitas configurações. Felizmente, você não precisa saber mais sobre cada configuração e avaliar as opções. A Microsoft facilita a aplicação de uma configuração de configurações, recomendando pontos iniciais. A [estrutura de proteção de dados usando políticas de proteção de aplicativo](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) inclui três níveis que você pode escolher. 

O melhor é que a Microsoft coordena essa estrutura de proteção do aplicativo com um conjunto de acesso condicional e políticas relacionadas que recomendamos que todas as organizações usem como ponto de partida. Se você implementou o MFA usando as orientações deste artigo, você é meio caminho lá!

Para configurar a proteção de aplicativos móveis, use as orientações em [políticas comuns de acesso a dispositivos e identidades](../enterprise/identity-access-policies.md):
 1. Use a guia [aplicar políticas de proteção de dados de aplicativos](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) para criar políticas para IOS e Android. O nível 2 (proteção avançada de dados) é recomendado para a proteção de linha de base. 
 2. Crie uma regra de acesso condicional para [exigir aplicativos aprovados e proteção de aplicativos](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection). 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Configure a MFA e o acesso condicional para convidados, incluindo a proteção de aplicativos móveis do Intune

Em seguida, vamos garantir que você possa continuar colaborar e trabalhar com convidados. Se você estiver usando o Microsoft 365 E3 Plan e implementou a MFA para todos os usuários, você está pronto. 

Se você estiver usando o Microsoft 365 E5 Plan e estiver tirando proveito da proteção de identidade do Azure para a MFA baseada em risco, precisará fazer alguns ajustes (porque a proteção de identidade do Azure AD não é estendida para convidados):
- Crie uma nova regra de acesso condicional para exigir a MFA sempre para convidados e usuários externos.
- Atualize a regra de acesso condicional do MFA com base em risco para excluir convidados e usuários externos.

Use as orientações sobre como [atualizar as políticas comuns para permitir e proteger o acesso externo e de convidados](../enterprise/identity-access-policies-guest-access.md) para entender como o acesso de convidados funciona com o Azure AD e para atualizar as políticas afetadas. 

As políticas de proteção de aplicativos móveis do Intune criadas, junto com a regra de acesso condicional para exigir aplicativos e proteção de aplicativos aprovados, se aplicam às contas de convidados e ajudarão a proteger os dados da organização. 

**Observação**: se você já registrou os computadores no gerenciamento de dispositivos para exigir computadores compatíveis, você também precisará excluir as contas de convidados da regra de acesso condicional que impõe a conformidade do dispositivo. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: registrar os PCs no gerenciamento de dispositivos e exigir computadores compatíveis

Há vários métodos para registrar os dispositivos de sua força de funcionários. Cada método depende da propriedade (pessoal ou corporativa) do dispositivo, do tipo de dispositivo (iOS, Windows, Android) e dos requisitos de gerenciamento (redefinições, afinidade, bloqueio). Isso pode levar algum tempo para ser classificado. Confira: [registrar dispositivos no Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

A maneira mais rápida de se começar é [Configurar o registro automático para dispositivos Windows 10](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment). 

Você também pode aproveitar estes tutoriais:
- [Usar o piloto automático para registrar dispositivos Windows no Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Usar os recursos de registro de dispositivo corporativo da Apple no Apple Business Manager (ABM) para registrar dispositivos iOS/iPadOS no Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Após registrar os dispositivos, use as orientações em [políticas comuns de acesso de dispositivo e identidade](../enterprise/identity-access-policies.md) para criar essas políticas:
- [Definir políticas de conformidade de dispositivo](../enterprise/identity-access-policies.md#define-device-compliance-policies) : as configurações recomendadas para o Windows 10 incluem a proteção antivírus. Se você tiver o Microsoft 365 e5, use a proteção avançada contra ameaças do Microsoft defender para monitorar a integridade dos dispositivos dos funcionários. Certifique-se de que as políticas de conformidade para outros sistemas operacionais incluem proteção antivírus e software de proteção de ponto final. 
- [Exigir computadores compatíveis](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) -esta é a regra de acesso condicional no Azure AD que impõe as políticas de conformidade do dispositivo.

Somente uma organização pode gerenciar um dispositivo, portanto, certifique-se de excluir as contas de convidado da regra de acesso condicional no Azure AD. Se você não excluir usuários convidados e externos de políticas que exigem conformidade de dispositivos, essas políticas bloquearão esses usuários. Para obter mais informações, consulte [atualizando as políticas comuns para permitir e proteger o acesso externo e convidado](../enterprise/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Otimize sua rede para conectividade de nuvem

Se você estiver rapidamente permitindo que a maior parte dos seus funcionários trabalhe de casa, essa opção repentina de padrões de conectividade pode ter um impacto significativo na infraestrutura de rede corporativa. Muitas redes foram dimensionadas e projetadas antes da adoção dos serviços em nuvem. Em muitos casos, as redes são tolerantes a funcionários remotos, mas não foram projetadas para serem usadas remotamente por todos os usuários simultaneamente.

Elementos de rede, como concentradores VPN, equipamentos de saída de rede central (como proxies e dispositivos de prevenção contra perda de dados), largura de banda da Internet central, circuitos MPLS backhaul, recurso NAT e assim por diante, são colocados em grande sobrecarga devido à carga de toda a empresa que os usa. O resultado final é desempenho e produtividade insatisfatórios, juntamente com uma experiência de usuário ruim para usuários que estão se adaptando para trabalhar de casa.

Algumas das proteções que foram fornecidas tradicionalmente por meio de tráfego de roteamento de entrada em uma rede corporativa são fornecidas pelos aplicativos de nuvem que seus usuários estão acessando. Se você tiver atingido esta etapa neste artigo, implementou um conjunto de controles de segurança de nuvem sofisticados para os serviços e dados do Microsoft 365. Com esses controles in-loco, você pode estar pronto para rotear o tráfego de usuários remotos diretamente para o Office 365. Se ainda precisar de um link VPN para acessar outros aplicativos, você poderá melhorar muito o desempenho e a experiência do usuário implementando o túnel de divisão. Depois de obter o contrato no oganization, isso pode ser realizado dentro de um dia por uma equipe de rede bem coordenada.


Confira estes recursos em docs para obter mais informações:
- [Visão geral: otimizar a conectividade para usuários remotos usando o túnel dividido VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementando o tunelamento dividido de VPN para Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Artigos recentes do blog sobre este tópico:
- [Como otimizar rapidamente o tráfego para a equipe remota & reduzir a carga em sua infraestrutura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Maneiras alternativas para profissionais de segurança e ti obter controles de segurança modernos nos cenários de trabalho remoto exclusivos de hoje](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: treinar os usuários

Quando os usuários não sabem sobre os recursos de proteção contra ameaças no trabalho em sua organização, eles podem se frustrar por recursos de proteção que são percebidos e diminuí-los ou impedindo que eles realizem o trabalho. Além disso, se eles sabem com antecedência o que observar com relação a mensagens de email suspeitas ou URLs, eles serão muito menos prováveis de abrir artefatos questionáveis. O treinamento de usuários pode economizar seus usuários e a equipe de operações de segurança de uma grande quantidade de tempo e frustração.

O [manual de campanha](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) da Harvard Kennedy School cybersecurity fornece orientações excelentes sobre o estabelecimento de uma grande cultura de reconhecimento de segurança em sua organização, incluindo o treinamento de usuários para identificar ataques de phishing. 

A Microsoft 365 fornece os seguintes recursos para ajudar a informar os usuários em sua organização:

|Conceito  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminhos de aprendizado personalizáveis](https://docs.microsoft.com/office365/customlearning/) <p>Esses recursos podem ajudá-lo a reunir o treinamento para os usuários finais em sua organização        |
|Segurança do Microsoft 365 |[Módulo de aprendizado: proteger sua organização com segurança integrada e interna da Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Este módulo permite descrever como os recursos de segurança da Microsoft 365 trabalham juntos e articulam os benefícios desses recursos de segurança. |
|Autenticação multifator     | [Verificação em duas etapas: o que é a página de verificação adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artigo ajuda os usuários finais a entender o que é a autenticação multifator e por que ela está sendo usada na sua organização.    |
| | |

Além desta orientação, a Microsoft recomenda que os usuários executem as ações descritas neste artigo: [proteja sua conta e seus dispositivos contra hackers e malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Essas ações incluem:
  
- Usando senhas fortes
    
- Protegendo dispositivos 
    
- Habilitar recursos de segurança nos PCs com Windows 10 e Mac (para dispositivos não gerenciados)
    
A Microsoft também recomenda que os usuários protejam suas contas de email pessoais executando as ações recomendadas nos seguintes artigos:
  
- [Ajudar a proteger sua conta de email do Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [Proteger sua conta do Gmail com a verificação em duas etapas](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: introdução ao Microsoft Cloud app Security

[O Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security) oferece visibilidade avançada, controle sobre a viagem de dados e análises sofisticadas para identificar e combater o ciberataques em todos os seus serviços de nuvem. Depois de começar a usar o Cloud app Security, as políticas de detecção de anomalias são habilitadas automaticamente, mas o Cloud app Security tem um período de aprendizado inicial de sete dias durante o qual nem todos os alertas de detecção de anomalias são gerados.

Introdução ao Cloud app Security agora. Posteriormente, você pode configurar monitoramento e controles mais sofisticados.

- [Início rápido: introdução à segurança do Cloud app](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Obter análise de comportamento instantâneo e detecção de anomalias](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Saiba mais sobre o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Analisar novos recursos e funcionalidades](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Consulte instruções básicas de instalação](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: monitorar ameaças e tomar ações

O Microsoft 365 inclui várias maneiras de monitorar o status e tomar as ações apropriadas. O melhor ponto de partida é o centro de segurança do[https://security.microsoft.com](https://security.microsoft.com)Microsoft 365 (), onde você pode exibir a [Pontuação segura](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)da sua organização e todos os alertas ou entidades que exigem sua atenção.

- [Introdução à central de segurança do Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Monitorar e exibir relatórios](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Consulte os portais de segurança no Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Próximas etapas

Parabéns! Você implementou rapidamente algumas das proteções de segurança mais importantes e sua organização é muito mais segura. Agora você está pronto para prosseguir ainda mais com os recursos de proteção contra ameaças (incluindo proteção avançada contra ameaças do Microsoft defender), classificação de dados e recursos de proteção e proteção de contas administrativas. Para obter um conjunto mais profundo e detalhado de recomendações de segurança para o Microsoft 365, consulte [Microsoft 365 Security for Business decisionship (BDMs)](Microsoft-365-security-for-bdm.md). 

Além disso, visite a nova central de segurança da Microsoft no [docs.Microsoft.com/Security](https://docs.microsoft.com/security). 
