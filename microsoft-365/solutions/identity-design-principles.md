---
title: 'Para identificar e além disso: o ponto de vista de um arquiteto'
description: Descrição.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 99112b70715770b24c1454fbd9442d2b5b6f08ea
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800126"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Para identificar e além disso: o ponto de vista de um arquiteto

Neste artigo, [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), arquiteto técnico principal da Microsoft, discute as principais estratégias de design para organizações empresariais que adotam o Microsoft 365 e outros serviços de nuvem da Microsoft.

## <a name="about-the-author"></a>Sobre o autor

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Foto Alex Shteynberg":::

Sou um arquiteto técnico principal no centro de tecnologia da [Microsoft](https://www.microsoft.com/mtc?rtc=1)Nova York. Na maioria dos casos, eu trabalho com grandes clientes e requisitos complexos. Meu ponto de vista e opiniões são baseados nessas interações e podem não se aplicar a todas as situações. No entanto, caso possamos ajudar os clientes com os desafios mais complexos, podemos ajudar todos os clientes. 

Geralmente eu trabalho com mais de 100 clientes por ano. Embora cada organização tenha características exclusivas, é interessante ver tendências e commonalities. Por exemplo, uma tendência é o interesse entre setores de vários clientes. Afinal, uma ramificação do banco também pode ser uma lanchonete e um centro comunitário. 

Em minha função, me depara ajudar os clientes a chegar na melhor solução técnica para lidar com seu conjunto exclusivo de objetivos de negócios. Oficialmente, quero me concentrar na identidade, segurança, privacidade e conformidade. Adoro o fato de que esses toques fazem tudo o que fazemos. Isso me dá a oportunidade de ser envolvida com a maioria dos projetos. Isso me mantém muito ocupado e aproveita essa função. 

Vivemos em Nova York City (o melhor!) e realmente aproveita a diversidade de sua cultura, comida e pessoas (não tráfego). Adoro viajar quando posso e espero ver a maior parte do mundo em minha vida útil. Estou atualmente procurando uma viagem para saber mais sobre o Wildlife.

## <a name="guiding-principles"></a>Princípios de orientação 

- **Simples geralmente é melhor** : você pode fazer (quase) qualquer coisa com tecnologia. Não significa que você deve. Especialmente no espaço de segurança, vários clientes soluções de supermecanismoes. Gosto [deste vídeo](https://www.youtube.com/watch?v=SOQgABDSYZE) da conferência de faixa do Google para enfatizar esse ponto.
- **Pessoas, processos, tecnologia** — [design para pessoas](https://en.wikipedia.org/wiki/Human-centered_design) para melhorar o processo, não o técnico primeiro. Não há soluções "perfeitos". Precisamos equilibrar vários fatores de risco e as decisões serão diferentes para cada empresa. Muitos clientes projetam uma abordagem que seus usuários posteriormente evitam.
- **Concentre-se em ' por quê ' primeiro e ' como ' mais tarde** — seja o velho infantil de 7 anos com um milhão de perguntas. Não podemos chegar à resposta certa se não soubermos as perguntas certas a fazer. Muitos clientes fazem suposições sobre como as coisas precisam funcionar em vez de definir o problema de negócios. Há sempre vários caminhos que podem ser realizados.
- **Cauda longa das práticas recomendadas anteriores** , reconhecemos que as práticas recomendadas estão mudando à velocidade da luz. Se você observou o Azure AD há mais de 3 meses, provavelmente está desatualizado. Tudo aqui está sujeito a alterações após a publicação. A opção "melhor" hoje pode não ser a mesma de seis meses a partir de agora.

## <a name="baseline-concepts"></a>Conceitos da linha de base

Não ignore esta seção. Muitas vezes, acho que eu deve voltar para esses tópicos, mesmo para clientes que estão usando serviços em nuvem por anos.
Infelizmente, o idioma não é uma ferramenta precisa. Muitas vezes, usamos a mesma palavra para significar diferentes conceitos ou palavras diferentes para significar o mesmo conceito. Costumo usar este diagrama abaixo para estabelecer uma terminologia de linha de base e "modelo de hierarquia".
<br><br>

![Ilustração de locatário, assinatura, serviço e dados](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Quando você aprender a recomeçar, é melhor começar no pool e não no meio do oceano. Não estou tentando ser tecnicamente preciso com este diagrama. É um modelo para discutir alguns conceitos básicos. 

No diagrama:
- Locatário = uma instância do Azure AD. Ele está no "topo" de uma hierarquia ou no nível 1 do diagrama. Podemos considerar que esse é o "[limite](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)", onde tudo o mais ocorre (o[Azure ad B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) ). Todos os serviços de nuvem corporativa da Microsoft fazem parte de um desses locatários. Os serviços de consumidor são separados. "Locatário" aparece na documentação como locatário do Office 365, locatário do Azure, locatário do WVD, etc. Muitas vezes, acho que essas variações causam confusão para os clientes.
- Serviços/assinaturas, nível 2 no diagrama, pertencem a um e apenas um locatário. A maioria dos serviços de SaaS é 1:1 e não pode ser movido sem migração. O Azure é diferente, você pode [mover a cobrança](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) e/ou uma [assinatura](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) para outro locatário. Há muitos clientes que precisam migrar assinaturas do Azure. Isso tem várias implicações. Os objetos que existem fora da assinatura (por exemplo, objetos RBAC e AD do Azure, incluindo grupos, aplicativos, políticas, etc.) não são movidos. Além disso, alguns serviços (Azure Key Vault, tijolos de dados, etc.) são movidos em um estado não funcional. Não migre serviços sem uma boa necessidade de negócios. Alguns scripts que podem ser úteis para a migração são [compartilhados no GitHub](https://github.com/lwajswaj/azure-tenant-migration). 
- Um determinado serviço geralmente tem algum tipo de limite de "subnível" ou nível 3 (L3). Isso é útil para entender a diferenciação de segurança, políticas, governança, etc. Infelizmente, não há um nome uniforme que eu sei. Alguns exemplos de nomes para L3 são: Azure Subscription = [Resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instância](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [espaço de trabalho](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Aplicativos de energia = [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview); etc.
- O nível 4 é onde residem os dados reais. Este ' plano de dados ' é um tópico complexo. Alguns serviços estão usando o Azure AD para RBAC, outros não. Falarei um pouco quando chegarmos nos tópicos de delegação.

Alguns conceitos adicionais que encontrei muitos clientes (e funcionários da Microsoft) são confusos ou têm dúvidas sobre como incluir o seguinte:


- Qualquer pessoa pode [criar](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) muitos locatários [sem nenhum custo](https://azure.microsoft.com/pricing/details/active-directory/). Você não precisa de um serviço provisionado nele. Tenho dezenas. Cada nome de locatário é exclusivo no serviço de nuvem Mundial da Microsoft (ou seja, dois locatários podem ter o mesmo nome). Todos eles estão no formato de TenantName.onmicrosoft.com. Também há processos que criam locatários automaticamente ([locatários não gerenciados](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)). Por exemplo, isso pode ocorrer quando um usuário se inscreve para um serviço corporativo com um domínio de email que não existe em nenhum outro locatário. 
- Em um locatário gerenciado, vários [domínios DNS](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) podem ser registrados nele. Isso não altera o nome original do locatário. No momento, não há uma maneira fácil de renomear um locatário (diferente de migração). Embora o nome do locatário tecnicamente não seja crítico para esses dias, alguns podem achar que isso deve ser limitado.
- Você deve reservar um nome de locatário para sua organização mesmo se ainda não estiver planejando implantar qualquer serviço. Caso contrário, alguém pode fazê-lo de você e não há um processo simples para refazê-lo (mesmo problema que os nomes DNS). Ouço essa forma com muita frequência dos clientes. O que o nome do seu locatário deve ser também é um tópico de debate.
- Se você possuir namespaces de DNS, deverá adicionar todos eles ao (s) locatários. Caso contrário, um pode criar um [locatário não gerenciado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) com esse nome, que causará a interrupção para [torná-lo gerenciado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover).
- O namespace DNS (por exemplo, contoso.com) pode pertencer a um e apenas um locatário. Isso tem implicação em vários cenários (por exemplo, compartilhar um domínio de email durante uma fusão ou aquisição, etc.) Há uma maneira de registrar um DNS sub (por exemplo, div.contoso.com) em um locatário diferente, mas isso deve ser evitado. Ao registrar um nome de domínio de nível superior, todos os subdomínios são considerados para pertencer ao mesmo locatário. Em cenários de vários locatários (veja abaixo), normalmente recomendo o uso de outro nome de domínio de nível superior (por exemplo, contoso.ch ou ch-contoso.com).
- Quem deve "pertencer" um locatário? Costumo ver clientes que não sabem quem atualmente é proprietário de seu locatário. Este é um grande sinalizador vermelho. Ligue para o suporte da Microsoft. Assim como é problemático quando um proprietário de serviço (geralmente, um administrador do Exchange) é designado para gerenciar um locatário. O locatário conterá todos os serviços que você pode querer no futuro. O proprietário do locatário deve ser um grupo que pode tomar decisão para a habilitação de todos os serviços em nuvem em uma organização. Outro problema é quando um grupo de proprietário do locatário é solicitado a gerenciar todos os serviços. Isso não é dimensionado para grandes organizações.
- Não há nenhum conceito de um locatário de subconjunto/super. Por algum motivo, esse Myth continua a ser repetido. Isso também se aplica aos locatários [do Azure ad B2C](https://docs.microsoft.com/azure/active-directory-b2c/) . Ouço muitas vezes, "meu ambiente B2C está no meu locatário XYZ" ou "como faço para mover meu locatário do Azure para o meu locatário do Office 365?"
- Este documento se concentra principalmente na nuvem mundial comercial, pois é isso o que a maioria dos clientes está usando. Algumas vezes é útil saber sobre [nuvens soberana](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud). As nuvens soberana têm implicações adicionais para discutir que estão fora do escopo para esta discussão.


## <a name="baseline-identity-topics"></a>Tópicos de identidade da linha de base

Há muita documentação sobre a plataforma de identidade da Microsoft – Azure Active Directory (Azure AD). Para aqueles que começam a ser iniciados, geralmente fica mais difícil. Mesmo depois de aprender, acompanhar a inovação e a mudança constantes podem ser desafiadores. Em minhas interações com o cliente, muitas vezes acho que servem como "Tradutor" entre as metas de negócios e as abordagens "boa, melhor, melhores" para lidar com elas (bem como "observações do Cliff") para estes tópicos. Raramente há uma resposta perfeita e a decisão "certa" é um equilíbrio de vários fatores de risco. Veja a seguir algumas das áreas comuns de perguntas e confusão que eu tenho para discutir com os clientes.

### <a name="provisioning"></a>Provisioning
O Azure AD não resolve a falta de governança no seu mundo de identidade! A [governança de identidade](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) deve ser um elemento crítico independente de qualquer decisão na nuvem. Os requisitos de governança mudam com o tempo, por que ele é um programa e não uma ferramenta. 

[Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (mim) vs. outro (terceiro ou personalizado)? Economize muita dor de problemas agora e no futuro e vá para o Azure AD Connect. Há todos os tipos de Smarts nesta ferramenta para lidar com as configurações do cliente peculiar e inovações contínuas. 

Alguns casos de borda que podem levar em direção a uma arquitetura mais complexa:
- Tenho várias florestas do AD sem conectividade de rede entre elas. Há uma nova opção chamada [provisionamento em nuvem](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Não tenho o Active Directory, nem quero instalá-lo. O Azure AD Connect pode ser configurados para [sincronizar de LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (pode ser necessário um parceiro).
- Preciso provisionar os mesmos objetos para vários locatários. Isso não é tecnicamente suportado, mas depende da definição de "mesmo".

Devo personalizar as regras de sincronização padrão ([objetos Filter](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [Change Attributes](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [Alternate ID de logon](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname), etc.)? Evitar! Uma plataforma de identidade é apenas tão valiosa quanto os serviços que o utilizam. Embora seja possível fazer todos os tipos de configurações do Nutty, para responder a essa pergunta, você precisa examinar o impacto sobre os aplicativos. Se você filtrar objetos habilitados para email, a GAL para serviços online estará incompleta; Se o aplicativo depender de atributos específicos, a filtragem deles terá um impacto imprevisível; etc. Não é uma decisão da equipe de identidade.

O SaaS XYZ oferece suporte ao provisionamento just-in-time (JIT), por que você está solicitando a sincronização? Veja acima. Muitos aplicativos precisam de informações de "perfil" para a funcionalidade. Você não pode ter uma GAL se todos os objetos habilitados para email não estiverem disponíveis. O mesmo se aplica ao [provisionamento de usuário](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) em aplicativos integrados ao Azure AD.


### <a name="authentication"></a>Autenticação

[Sincronização de hash de senha](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) vs. [autenticação de passagem](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) vs. [Federation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Normalmente, há um [debate](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) apaixonado em relação à Federação. Normalmente, é mais simples e usa o PHS, a menos que você tenha uma boa razão para não fazer isso. Também é possível configurar diferentes métodos de autenticação para domínios DNS diferentes no mesmo locatário. 

Alguns clientes habilitam a Federação + PHS principalmente para:
- Uma opção de retorno (para [recuperação de desastre](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) ) se o serviço de Federação não estiver disponível.
- Recursos adicionais (ex.: [Azure AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) e serviços de segurança (ex.: [credenciais vazadas](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Suporte para serviços no Azure que não entendem a autenticação federada (ex.: [arquivos do Microsoft Azure](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)).

Muitas vezes, eu passo os clientes por meio do fluxo de autenticação de cliente para esclarecer algumas concepções erradas. O resultado se parece com a imagem abaixo, que não é tão boa quanto o processo interativo de chegar lá.

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="conversa de exemplo de quadro de comunicações":::

Esse tipo de desenho de quadro de comunicações ilustra onde as políticas de segurança são aplicadas no fluxo de uma solicitação de autenticação. Neste exemplo, as políticas impostas pelo serviço de Federação do Active Directory (AD FS) são aplicadas à primeira solicitação de serviço, mas não às solicitações de serviço subsequentes. Esse é pelo menos um motivo para mover os controles de segurança para a nuvem o máximo possível.

Estamos diante do sonho de [logon único](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO), contanto que eu possa me lembrar. Alguns clientes acreditam que podem conseguir isso, escolhendo o provedor de Federação (STS) "à direita". O Azure AD pode ajudar significativamente a habilitar recursos de [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) , mas nenhum STS é Magical. Há muitos métodos de autenticação "herdados" que ainda são usados para aplicativos críticos. Estender o Azure AD com [soluções de parceiros](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) pode resolver muitos desses cenários. SSO é uma estratégia e uma jornada. Você não pode fazer isso sem mudar [de volta para os padrões de aplicativos](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types). Relacionado a este tópico é uma jornada para autenticação sem [senha](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) que também não tem uma resposta Magical. 

[A MFA (autenticação multifator](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) ) é essencial atualmente ([aqui](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) para mais). Adicione à [análise de comportamento do usuário](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) de ti e você tem uma solução que impede a maioria dos ataques comuns à CyberSource. Até mesmo os serviços de consumidor estão mudando para a solicitação de MFA. Ainda assim, ainda encontro com muitos clientes que não querem migrar para as abordagens de [autenticação modernas](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) . O maior argumento que ouço é que afetará os usuários e os aplicativos herdados. Às vezes, um bom ponto de partida pode ajudar os clientes a mudar de acordo com [as alterações](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)do Exchange Online. Muitos [relatórios](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) do Azure ad agora estão disponíveis para ajudar os clientes nessa transição.



### <a name="authorization"></a>Autorização

Por [Wikipédia](https://en.wikipedia.org/wiki/Authorization), "para autorizar" é definir uma política de acesso. Muitas pessoas o examinam como a capacidade de definir controles de acesso a um objeto (arquivo, serviço, etc.). No mundo atual das ameaças de cyber, esse conceito está evoluindo rapidamente para uma política dinâmica que pode reagir a vários vetores de ameaça e ajustar rapidamente os controles de acesso em resposta a eles. Por exemplo, se eu acessar minha conta bancária de um local incomum, obtenho etapas de confirmação adicionais. Para abordar isso, precisamos considerar não só a política em si, mas o ecossistema das metodologias de detecção de ameaças e de correlação de sinais.

O mecanismo de política do Azure AD é implementado usando [políticas de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Esse sistema depende das informações de vários outros sistemas de detecção de ameaças para tomar decisões dinâmicas. Um modo de exibição simples seria algo semelhante à ilustração a seguir.

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Mecanismo de política no Azure AD":::

Combinar todos esses sinais juntos permite políticas dinâmicas como estas:
- Se uma ameaça for detectada no dispositivo, seu acesso aos dados será reduzido apenas para Web, sem a capacidade de baixar.
- Se você estiver baixando um volume excepcionalmente alto de dados, tudo o que baixar será criptografado e restringido.
- Se você acessar um serviço de um dispositivo não gerenciado, você será bloqueado de dados altamente confidenciais, mas com permissão para acessar dados não restritos sem a capacidade de copiá-los para outro local.

Se você concordar com essa definição expandida de autorização, precisará implementar soluções adicionais. As soluções que você implementar dependerão de como dinâmica você deseja que a política seja e quais ameaças você deseja priorizar. Alguns exemplos desses sistemas são:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Proteção avançada contra ameaças do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/) (Azure ATP)
- [Proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (Microsoft defender ATP)
- [Proteção avançada contra ameaças do office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP)
- MCAS ( [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/) )
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Proteção de informações da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Obviamente, além do Azure AD, vários serviços e aplicativos têm seus próprios modelos de autorização específicos. Algumas delas serão discutidas posteriormente na seção delegação.

### <a name="audit"></a>Auditoria
O Azure AD tem recursos detalhados [de auditoria e relatórios](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) . No entanto, geralmente não é a única fonte de informações necessárias para tomar decisões de segurança. Veja mais discussões sobre isso na seção Delegation.

## <a name="there-is-no-exchange"></a>Não há um Exchange

Não se assuste! Isso não significa que o Exchange está sendo preterido (ou o SharePoint etc.) Ele ainda é um serviço principal. O que eu quis dizer é, por muito tempo, os fornecedores de tecnologia fizeram a transição da experiência do usuário (UX) para englobar componentes de vários serviços. No Microsoft 365, um exemplo simples é "[anexos modernos](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)", onde os anexos de email são armazenados no SharePoint Online ou no onedrive for Business. 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="anexar um arquivo a um email":::


Olhando para o cliente do Outlook, você pode ver vários serviços que estão "conectados" como parte dessa experiência, e não apenas o Exchange. Isso inclui o Azure AD, o Microsoft Search, aplicativos, perfil, conformidade e grupos do Office 365. 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="Interface do Outlook com textos explicativos":::

Leia sobre a [estrutura fluida da Microsoft](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) para visualização dos recursos futuros. Na visualização agora, posso ler e responder às conversas do Microsoft Teams diretamente no Outlook. Na verdade, o [cliente do teams](https://products.office.com/microsoft-teams/download-app) é um dos exemplos mais proeminentes dessa estratégia. 

Em geral, está se tornando mais difícil desenhar uma linha clara entre o Office 365 e outros serviços em nuvens da Microsoft. Posso visualizá-lo como um grande benefício para os clientes, uma vez que eles podem se beneficiar da inovação total em tudo o que fazemos, mesmo que usem um componente. Muito legal e tem implicações muito distantes para muitos clientes.

Hoje, acho que muitos grupos de ti de clientes estão estruturados em torno de "produtos". É lógico para um mundo local, pois você precisa de um especialista para cada produto específico. No entanto, estou totalmente satisfeito por não ter que depurar um banco de dados do Active Directory ou do Exchange já que esses serviços foram movidos para a nuvem. Automação (o tipo de nuvem de is) remove certos trabalhos manuais repetitivos (Observe o que aconteceu com as fábricas). No entanto, eles são substituídos por requisitos mais complexos para entender a interação entre serviços, impacto, necessidades comerciais, etc. Se você estiver disposto a [aprender](https://docs.microsoft.com/learn/), há excelentes oportunidades habilitadas pela transformação em nuvem. Antes de entrar em tecnologia, costumo falar com clientes sobre o gerenciamento de mudanças nas habilidades de ti e estruturas de equipe.

Para todas as pessoas e desenvolvedores do SharePoint, pare de perguntar "como faço para fazer a XYZ no SharePoint Online?" Use a [automatização de energia](https://docs.microsoft.com/power-automate/) (com o fluxo de forma conhecida) para fluxo de trabalho, é uma plataforma muito mais poderosa. Use o [Azure bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) para criar uma experiência melhor para a sua lista de itens do com 500 mil. Comece a usar [o Microsoft Graph](https://developer.microsoft.com/graph/) em vez de CSOM. [O Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) inclui o SharePoint, mas também um mundo mais. Há muitos outros exemplos que posso listar. Há um universo vasto e maravilhosa lá. Abra a porta e [comece a explorar](https://docs.microsoft.com).

O outro impacto comum está na área de conformidade. Essa abordagem entre serviços parece totalmente confundir muitas políticas de conformidade. Continuo vendo as organizações que estado, "Preciso registrar todas as comunicações de email em um sistema de descoberta eletrônica". O que isso realmente significa quando o email não está mais enviando emails, mas uma janela para outros serviços? O Office 365 tem uma abordagem abrangente para [conformidade](https://docs.microsoft.com/microsoft-365/compliance/), mas alterar pessoas e processos costuma ser muito mais difícil do que a tecnologia.

Há muitas outras implicações de pessoas e processos. Em minha opinião, esta é uma área crítica e indiscutida. Talvez mais em outro artigo.

## <a name="tenant-structure-options"></a>Opções de estrutura do locatário

### <a name="single-tenant-vs-multi-tenant"></a>Locatário único vs. multilocatário

Em geral, a maioria dos clientes deve ter apenas um locatário de produção. Há muitas razões pelas quais vários locatários são desafiadores (dê a ele uma [pesquisa do Bing](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) ou leia este [White Paper](https://aka.ms/multi-tenant-user). Ao mesmo tempo, muitos clientes corporativos com os quais eu trabalhar têm outro locatário (pequeno) locatário para aprendizado de ti, teste e experimentação. O acesso ao Azure entre locatários é simplificado com o [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/). O Office 365 e muitos outros serviços de SaaS têm limites para cenários de vários locatários. Há muito o que considerar nos cenários [B2B do Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) .

Muitos clientes terminam com vários locatários de produção após uma fusão e aquisição (M&A) e querem consolidar. Hoje, isso não é simples e exigiria o MCS (serviços de consultoria da Microsoft) ou um software de terceiros. Há um trabalho contínuo de engenharia para lidar com vários cenários com clientes de vários locatários no futuro. 

Alguns clientes optam por usar mais de um locatário. Isso deve ser uma decisão muito cuidadosa e, quase sempre, motivos comerciais orientados! Alguns exemplos incluem o seguinte:
- Uma estrutura de empresa de tipo de retenção onde A colaboração fácil entre diferentes entidades não é necessária e há necessidades administrativas e de isolamento fortes.
- Após uma aquisição, é feita uma decisão de negócios para manter duas entidades separadas.
- Simulação do ambiente de um cliente que não altera o ambiente de produção do cliente. 
- Desenvolvimento de software para clientes.

Nesses cenários de vários locatários, os clientes freqüentemente querem manter algumas configurações iguais em locatários ou relatar alterações de configuração e descompassos. Isso geralmente significa mover de alterações manuais para a configuração como código. O suporte do Microsoft Premiere oferece um workshop para esses tipos de requisitos com base neste IP público: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .


### <a name="multi-geo"></a>Multi-Geo 

Para [várias geografias](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) ou não para várias geografias, essa é a pergunta. Com o Office 365 multigeográfico, você pode provisionar e armazenar dados em repouso nos locais geográficos que você escolheu para atender aos requisitos de [residência de dados](https://docs.microsoft.com/office365/enterprise/o365-data-locations) . Há muitas concepções erradas sobre esse recurso. Lembre-se do seguinte: 
- Ele não fornece benefícios de desempenho. Isso pode tornar o desempenho pior se o [design de rede](https://aka.ms/office365networking) não estiver correto. Obtenha os dispositivos "Close" para a rede da Microsoft, não necessariamente aos seus dados.
- Não é uma solução para conformidade com o [rgpd](https://www.microsoft.com/trust-center/privacy/gdpr-overview). O RGPD não se concentra nos locais da soberania ou de armazenamento de dados. Há outras estruturas de conformidade para isso.
- Ele não resolve a delegação de administração (veja abaixo) ou [as barreiras de informação](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).
- Não é o mesmo que multilocatário e requer fluxos de trabalho adicionais de [provisionamento do usuário](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) .
- Ele não [move seu locatário](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) (seu Azure AD) para outra geografia. 

## <a name="delegation-of-administration"></a>Delegação de administração

Na maioria das grandes organizações, a separação entre as obrigações e o controle de acesso baseado em função (RBAC) é uma realidade necessária. Estou em desculpas antes do tempo. Isso não é tão simples quanto alguns clientes querem ser. Os requisitos de cliente, legal, conformidade e outros são diferentes e, às vezes, estão em conflito em todo o mundo. Simplicidade e flexibilidade geralmente estão nos lados opostos uns dos outros. Não me preocupe, podemos fazer um trabalho melhor para isso. Há (e serão) melhorias significativas ao longo do tempo. Visite seu [centro de tecnologia](https://www.microsoft.com/mtc) local da Microsoft para solucionar o modelo que atende às suas necessidades de negócios sem ler 379230 documentos! Aqui, me concentrarei no que você deve pensar e por que ela é dessa forma. Veja a seguir cinco áreas diferentes para planejar e algumas das dúvidas comuns que eu encontrei.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Centros de administração do Azure AD e do Microsoft 365

Há uma longa e crescente lista de [funções internas](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Cada função consiste em uma lista de permissões de função agrupadas para permitir que ações específicas sejam executadas. Você pode ver essas permissões na guia "Descrição" dentro de cada função. Como alternativa, você pode ver uma versão mais legível dessas pessoas no centro de administração do Microsoft 365. As definições para funções internas não podem ser modificadas. Geralmente, agrupe-as em três categorias:

- **Administrador global** — essa função "tudo poderoso" deve ser [altamente protegida](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) da mesma forma que faria em outros sistemas. As recomendações típicas incluem: nenhuma atribuição permanente e usar o gerenciamento de identidade privilegiado (PIM) do Azure AD; autenticação forte; etc. Curiosamente, essa função não lhe dá acesso a tudo por padrão. Normalmente, vejo confusão sobre acesso de conformidade e acesso do Azure, discutidas mais tarde. No entanto, essa função sempre pode atribuir acesso a outros serviços no locatário. 
- **Administradores de serviço específicos** — alguns serviços (Exchange, SharePoint, Power bi etc.) consomem funções de administração de alto nível do Azure AD. Isso não é consistente em todos os serviços e há mais funções específicas de serviço discutidas posteriormente.
- **Funcional** — há uma longa (e crescente) lista de funções voltadas para operações específicas (convidado convidados, etc.). Periodicamente, mais delas são adicionadas com base nas necessidades do cliente.

Não é possível delegar tudo (embora a lacuna esteja decrescente), o que significa que a função de administrador global precisaria ser usada às vezes. O código de configuração e a automação devem ser considerados em vez da Associação de pessoas dessa função.

**Observação**: o centro de administração do Microsoft 365 tem uma interface mais amigável, mas tem subconjunto de recursos em comparação com a experiência de administração do Azure AD. Ambos os portais usam as mesmas funções do Azure AD, portanto, as alterações estão ocorrendo no mesmo local. Dica: se você quiser uma interface do usuário de administração focada no gerenciamento de identidades sem toda a organização do Azure, use [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

O que há no nome? Não faça suposições com o nome da função. O idioma não é uma ferramenta muito precisa. O objetivo deve ser definir operações que precisam ser delegadas antes de examinar quais funções são necessárias. A adição de alguém à função "leitor de segurança" não faz com que eles vejam as configurações de segurança em todos os itens. 

A capacidade de criar [funções personalizadas](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) é uma pergunta comum. Isso é limitado no Azure AD atualmente (veja abaixo), mas aumentará os recursos com o tempo. Acho que isso se aplica a funções no Azure AD e que não pode abranger o modelo de hierarquia (discutido acima). Sempre que eu estiver lidando com "personalizado", eu tendem a voltar para a minha entidade de segurança "é melhor."

Outra pergunta comum é a capacidade de escopo de funções em um subconjunto de um diretório. Um exemplo é algo como "administrador de assistência técnica para usuários somente na União Européia". As [unidades administrativas](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (au) se destinam a lidar com isso. Como acima, acho que isso se aplica a funções no Azure AD e que não pode se estender "para baixo". Obviamente, determinadas funções não fazem sentido para o escopo (administradores globais, administradores de serviços, etc.)

Atualmente, todas essas funções exigem associação direta (ou atribuição dinâmica se você usar o [PIM do Azure ad](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)). Isso significa que os clientes devem gerenciá-los diretamente no Azure AD, e eles não podem ser baseados em uma associação de grupo de segurança. Não sou um fã de criar scripts para gerenciá-los como seria necessário executar com direitos elevados. Geralmente, recomendo a integração da API com sistemas de processo como o ServiceNow ou usando ferramentas de governança de parceiros como o Saviynt. Há trabalho de engenharia em andamento para lidar com o tempo.

Mencionei algumas vezes o [PIM AD do Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) . Há uma solução de [Gerenciamento de acesso privilegiado](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (do mim) do Microsoft Identity Manager (PAM) para controles no local. Você também pode querer examinar as [estações de trabalho privilegiadas](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) e o [controle de identidade do Azure ad](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview). Há uma variedade de ferramentas de terceiros, bem como que pode habilitar a elevação just-in-time, apenas o suficiente e a função dinâmica. Isso geralmente faz parte de uma discussão maior para proteger um ambiente. 

Às vezes, os cenários chamam a adição de um usuário externo a uma função (consulte a seção multilocatário, acima). Isso funciona bem. O [Azure ad B2B](https://docs.microsoft.com/azure/active-directory/b2b/) é outro tópico grande e divertido para movimentar os clientes, talvez em outro artigo.

### <a name="security-and-compliance-center-scc"></a>Centro de segurança e conformidade (SCC)

[Permissões no centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) são uma coleção de "grupos de função" que são separados e diferentes das funções do Azure AD. Isso pode ser confuso, pois alguns desses grupos de função têm o mesmo nome que as funções do Azure AD (por exemplo, leitor de segurança), ainda que possam ter associações diferentes. Prefiro o uso de funções do Azure AD. Cada grupo de função consiste em uma ou mais "funções" (Veja o que eu quero dizer de reutilizar o mesmo Word?) e ter membros do Azure AD que são objetos habilitados para email. Além disso, você pode criar um grupo de função com o mesmo nome de uma função que pode ou não conter essa função (Evite esta confusão).

De certa forma, essas são uma evolução do modelo de grupos de função do Exchange. No entanto, o Exchange Online tem sua própria interface de [Gerenciamento de grupo de função](https://docs.microsoft.com/exchange/permissions-exo) . Alguns grupos de função no Exchange Online são bloqueados e gerenciados do Azure AD ou do centro de conformidade & segurança, mas outros podem ter nomes iguais ou semelhantes e são gerenciados no Exchange Online (adicionando à confusão). Recomendo que você evite usar a interface do usuário do Exchange Online, a menos que precise de escopos para o gerenciamento do Exchange.

Você não pode criar funções personalizadas. As funções são definidas por serviços criados pela Microsoft e serão expandidas à medida que novos serviços forem introduzidos. Isso é semelhante em conceito a [funções definidas por aplicativos](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) no Azure AD. Quando novos serviços estão habilitados, geralmente novos grupos de função precisam ser criados para conceder ou delegar o acesso a eles (por exemplo, [Gerenciamento de risco do insider](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

Esses grupos de função também exigem associação direta e não podem conter grupos do Azure AD. Infelizmente, hoje não há suporte para esses grupos de função no PIM AD do Azure. Assim como as funções do Azure AD, é recomendável que você recomende o gerenciamento desses recursos por meio de APIs ou de um produto de governança de parceiros como o Saviynt ou outros.

As funções do centro de conformidade do & de segurança abrangem o Microsoft 365 e não é possível escopor esses grupos de função para um subconjunto do ambiente (como você pode ter unidades administrativas no Azure AD). Muitos clientes perguntam como eles podem subdelegar. Por exemplo, "criar uma política de DLP somente para usuários da UE". Hoje, se você tiver direitos para uma função específica no centro de conformidade com segurança &, terá direitos para todos os itens cobertos por essa função no locatário. No entanto, muitas políticas têm recursos para direcionar um subconjunto do ambiente (por exemplo, "tornar esses [Rótulos](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) disponíveis apenas para estes usuários"). O controle e a comunicação adequados são um componente essencial para evitar conflitos. Alguns clientes optam por implementar uma abordagem de "configuração como código" para lidar com a subdelegação no centro de conformidade do & de segurança. Alguns serviços específicos oferecem suporte a subdelegação (veja abaixo). 

Vale a pena observar que os controles gerenciados atualmente por meio do protection.office.com (centro de conformidade do & de segurança) estão em processo de migração para dois portais de administração separados: security.microsoft.com e compliance.microsoft.com. Change é a única constante!

### <a name="service-specific"></a>Específico do serviço

Conforme mencionado anteriormente, muitos clientes estão procurando obter um modelo de delegação mais granular. Um exemplo comum: "gerenciar o serviço XYZ somente para os usuários e locais de divisão X" (ou outra dimensão). A capacidade de fazer isso depende de cada serviço e não é consistente entre os serviços e os recursos. Em adição, cada serviço pode ter um modelo RBAC separado e exclusivo. Em vez de discutir tudo isso (será necessário para sempre), estou adicionando links relevantes para cada serviço. Esta não é uma lista completa, mas você começará a usar o.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness ](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **Descobertas** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Filtragem**  -  de permissão [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search ](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Limites**  -  de conformidade [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries ](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Descoberta eletrônica avançada**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 ](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Várias geografias** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Observação: este link é para a raiz da documentação. Há vários tipos de serviços com variações no modelo de administrador/delegação.
- **Plataforma**  -  de energia [https://docs.microsoft.com/power-platform/admin/admin-documentation ](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Aplicativos**  -  de energia [https://docs.microsoft.com/power-platform/admin/wp-security ](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Observação: há vários tipos com variações nos modelos de administrador/delegação.
  + **Automatização**  -  de energia [https://docs.microsoft.com/power-automate/environments-overview-admin ](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance ](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Observação: a segurança e a delegação da plataforma de dados (que o Power BI é um componente) é uma área complexa.
- **Mem/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control ](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft defender ATP**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Proteção contra ameaças da Microsoft** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Segurança do aplicativo do Microsoft Cloud** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role ](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Barreiras**  -  de informações [https://docs.microsoft.com/microsoft-365/compliance/information-barriers ](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Para o resto, a pesquisa em docs foi realmente boa! [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 


### <a name="activity-logs"></a>Logs de atividade
O Office 365 tem um [log de auditoria unificado](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). É um log muito [detalhado](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema), mas não lê muito para o nome. Ele pode não conter tudo o que você deseja ou precisa para suas necessidades de segurança e conformidade. Além disso, alguns clientes estão realmente interessados na [auditoria avançada](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit). 

Exemplos de logs do Microsoft 365 que são acessados por meio de outras APIs incluem o seguinte:
- [Azure ad](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (atividades não relacionadas ao Office 365)
- [Rastreamento de mensagens do Exchange](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace?view=exchange-ps)
- Sistemas de ameaça/UEBA discutidos acima (por exemplo, proteção de identidade do Azure AD, segurança do aplicativo do Microsoft Cloud, Microsoft defender ATP, etc.)
- [Proteção de informações da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

É importante primeiro identificar todas as fontes de log necessárias para um programa de segurança e conformidade. Observe também que diferentes logs têm limites de retenção online diferentes. 

Da perspectiva da delegação de administrador, a maioria dos logs de atividades do Microsoft 365 não tem um modelo RBAC interno. Se você tiver permissão para ver um log, poderá ver tudo nele. Um exemplo comum de um requisito do cliente é: "desejo ser capaz de consultar a atividade somente para usuários da UE" (ou outra dimensão). Para atender a esse requisito, precisamos transferir logs para outro serviço. Na nuvem da Microsoft, recomendamos transferi-la para o [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) ou para a [análise de logs](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace). 

Diagrama de alto nível:

![diagrama de alto nível do fluxo de logs](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

O diagrama acima representa recursos internos para enviar logs para o Hub de eventos e/ou o armazenamento do Azure e/ou a análise de logs do Azure. Nem todos os sistemas incluem essa opção pronta para uso. Mas há outras abordagens para enviar esses logs para o mesmo repositório. Por exemplo, confira [protegendo suas equipes com o Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

A combinação de todos os logs em um local de armazenamento inclui benefícios adicionais, como correlações entre diferentes, tempos de retenção personalizados, aumento dos dados necessários para dar suporte ao modelo RBAC, etc. Depois que os dados estiverem neste sistema de armazenamento, você poderá criar um painel do PowerBI (ou outro tipo de visualização) com um modelo RBAC apropriado.

Os logs não precisam ser direcionados para apenas um local. Também pode ser benéfico para integrar [logs do Office 365 com o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) ou um modelo RBAC personalizado no [Power bi](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide). Repositórios diferentes têm diferentes benefícios e audiências.

Vale a pena mencionar que há um sistema de análise incorporado muito avançado para segurança, ameaças, vulnerabilidades, etc. em um serviço chamado [proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide).

Muitos clientes grandes desejam transferir esses dados de log para um sistema de terceiros (por exemplo, SIEM). Há diferentes abordagens para isso, mas, no geral, o [Hub de eventos do Azure](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) e o [Graph](https://docs.microsoft.com/graph/security-integration) são bons pontos de partida.


### <a name="azure"></a>Azure 
Costumo ser perguntado se há uma maneira de separar as funções de alto privilégio entre o Azure AD, o Azure e o SaaS (ex.: administrador global do Office 365, mas não o Azure).  Não realmente.  A arquitetura de vários locatários é necessária se for necessária a separação administrativa completa, mas isso adiciona uma [complexidade](https://aka.ms/multi-tenant-user) significativa (veja acima). Todos esses serviços fazem parte do mesmo limite de segurança/identidade (examine o modelo hierárquico acima).  

É importante entender as relações entre vários serviços no mesmo locatário. Estou trabalhando com muitos clientes que estão criando soluções de negócios que abrangem o Azure, o Office 365 e a plataforma de energia (e geralmente também locais e serviços em nuvem de terceiros). Um exemplo comum: 
-   Eu quero colaborar em um conjunto de documentos/imagens/etc (Office 365)
-   enviar cada um deles por meio de um processo de aprovação (plataforma de energia)
-   Depois que todos os componentes são aprovados, reúna-os em uma API de entrega (s) unificada (Azure) do [Microsoft Graph](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) é seu melhor amigo para eles.  Não é impossível, mas é significativamente mais complexo criar uma solução que abrange [vários locatários](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

O RBAC (controle de acesso baseado em função) do Azure permite o gerenciamento de acesso refinado para o Azure. Usando o RBAC, você pode gerenciar o acesso a recursos, concedendo aos usuários as permissões mais baixas necessárias para executar seus trabalhos. Os detalhes estão fora do escopo deste documento, mas para obter mais informações sobre o RBAC, confira [o que é controle de acesso baseado em função (RBAC) no Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) O RBAC é importante, mas apenas parte das considerações de governança para o Azure. A [estrutura de adoção em nuvem](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) é um bom ponto de partida para saber mais. Eu gosto de como meu amigo, Andres Ravinet orienta os clientes passo a passo por meio de vários componentes para decidir sobre a abordagem. O modo de exibição de alto nível para vários elementos (não tão bons quanto o processo de acessar o modelo de cliente real) é algo assim:

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="visão de alto nível dos componentes do Azure para a administração delegada":::

Como você pode ver na imagem acima, muitos outros serviços devem ser considerados como parte do design (ex.: [políticas do Azure](https://docs.microsoft.com/azure/governance/policy/overview), [plantas do Azure](https://docs.microsoft.com/azure/governance/blueprints/overview), [grupos de gerenciamento](https://docs.microsoft.com/azure/governance/management-groups/), etc.)

## <a name="conclusion"></a>Conclusão
Iniciado como um pequeno resumo, concluído mais tempo do que o esperado.  Espero que você esteja pronto para se aventurar em uma visualização detalhada da criação do modelo de delegação para sua organização.  Essa conversa é muito comum com os clientes. Não há um modelo que funcione para todos. Aguardar alguns aprimoramentos planejados da engenharia da Microsoft antes de documentar os padrões comuns que vemos entre os clientes. Enquanto isso, você pode trabalhar com sua equipe de conta da Microsoft para organizar uma visita ao centro de [tecnologia da Microsoft](https://www.microsoft.com/mtc)mais próximo.  Veja você lá!


