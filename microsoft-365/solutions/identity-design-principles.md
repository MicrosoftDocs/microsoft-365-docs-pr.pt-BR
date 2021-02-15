---
title: Planejamento de recursos corporativos do Microsoft 365 - Arquitetura de segurança
description: Saiba mais sobre as principais estratégias de design para a arquitetura do Microsoft Enterprise de Alex Shteynberg, arquiteto principal técnico da Microsoft.
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
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 00fede86da826b940026b894a4ba2a9774ae4dc2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771902"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Para identidade e além — arquitetura de um arquiteto

Neste artigo, [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), arquiteto técnico principal da Microsoft, discute as principais estratégias de design para organizações corporativas que adotam o Microsoft 365 e outros serviços de nuvem da Microsoft.

## <a name="about-the-author"></a>Sobre o autor

![Foto de Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Sou arquiteto técnico principal no Centro de Tecnologia da Microsoft de Nova [York.](https://www.microsoft.com/mtc?rtc=1) Trabalho principalmente com clientes grandes e requisitos complexos. Minhas opiniões e opiniões são baseadas nessas interações e podem não se aplicar a todas as situações. No entanto, na minha experiência, se ajudarmos os clientes com os desafios mais complexos, podemos ajudar todos os clientes.

Normalmente, trabalho com mais de 100 clientes a cada ano. Embora toda organização tenha características exclusivas, é interessante ver tendências e semelhanças. Por exemplo, uma tendência é de interesse entre setores para muitos clientes. Afinal, uma filial bancária também pode ser uma cafeteria e um centro da comunidade.

Na minha função, concentre-me em ajudar os clientes a chegarem à melhor solução técnica para abordar seu conjunto exclusivo de metas de negócios. Oficialmente, foco em Identidade, Segurança, Privacidade e Conformidade. Eu amo o fato de que eles tocam tudo o que fazemos. Isso me dá uma oportunidade de estar envolvido com a maioria dos projetos. Isso me mantém muito ocupado e aproveitando essa função.

Eu vivo na cidade de Nova York (o melhor!) e realmente curti a diversidade de sua cultura, sua alimentação e as pessoas (não o tráfego). Eu quero viagem quando puder e quero ver a maior parte do mundo em minha vida. Atualmente, estou pesquisando uma viagem para a África para saber mais sobre a vida curinga.

## <a name="guiding-principles"></a>Princípios de orientação

- **Geralmente, é melhor:** você pode fazer (quase) qualquer coisa com a tecnologia, mas isso não significa que você deva. Especialmente no espaço de segurança, muitos clientes superencontram soluções. Eu quero [este vídeo](https://www.youtube.com/watch?v=SOQgABDSYZE) da conferência stripe do Google para sublinhar esse ponto.
- **Pessoas, processos, tecnologia:** [projetar para que as pessoas](https://en.wikipedia.org/wiki/Human-centered_design) aprimoram o processo, não a tecnologia primeiro. Não há soluções "perfeitas". Precisamos equilibrar vários fatores de risco e as decisões serão diferentes para cada negócio. Muitos clientes projetam uma abordagem que seus usuários evitam posteriormente.
- **Concentre-se em "por que" primeiro e "como" mais** tarde: seja a antiga mera sete ou mais incômoda com um milhão de perguntas. Não podemos chegar na resposta certa se não sabemos as perguntas certas. Muitos clientes fazem suposições sobre como as coisas precisam funcionar em vez de definir o problema de negócios. Sempre há vários caminhos que podem ser tomados.
- **Longo prazo das práticas recomendadas anteriores:** reconheça que as práticas recomendadas estão mudando na velocidade da luz. Se você já viu o Azure AD há mais de três meses, provavelmente está desa datado. Tudo aqui está sujeito a alterações após a publicação. A opção "Melhor" hoje pode não ser o mesmo daqui a seis meses.

## <a name="baseline-concepts"></a>Conceitos de linha de base

Não ignore esta seção. Muitas vezes, vejo que preciso voltar a esses tópicos, mesmo para clientes que usam serviços de nuvem há anos.
Ai de mim, o idioma não é uma ferramenta precisa. Muitas vezes usamos a mesma palavra para significar conceitos diferentes ou palavras diferentes para significar o mesmo conceito. Geralmente, uso este diagrama abaixo para estabelecer uma terminologia de linha de base e um "modelo de hierarquia".
<br><br>

![Ilustração de locatário, assinatura, serviço e dados](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Quando você aprende a se juntar, é melhor começar no pool e não no meio do oceano. Não estou tentando ser tecnicamente preciso com este diagrama. É um modelo para discutir alguns conceitos básicos.

No diagrama:

- Locatário = uma instância do Azure AD. Ele está na "parte superior" de uma hierarquia ou nível 1 no diagrama. Podemos considerar isso como o["](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)limite " em que todo o resto ocorre ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) à parte). Todos os serviços de nuvem empresarial da Microsoft fazem parte de um desses locatários. Os serviços de consumidor são separados. "Locatário" aparece na documentação como locatário do Office 365, locatário do Azure, locatário WVD e assim por diante. Muitas vezes, essas variações causam confusão para os clientes.
- Serviços/assinaturas, Nível 2 no diagrama, pertencem a apenas um locatário. A maioria dos serviços SaaS é 1:1 e não pode se mover sem migração. O Azure é diferente, você pode [mover cobrança e/ou](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) uma [assinatura](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) para outro locatário. Há muitos clientes que precisam mover assinaturas do Azure. Isso tem várias implicações. Objetos que existem fora da assinatura não se movem (por exemplo, controle de acesso baseado em função ou RBAC do Azure e objetos do Azure AD, incluindo grupos, aplicativos, políticas e assim por diante). Além disso, alguns serviços (como o Azure Key Vault, Data Vaults e assim por diante). Não migre serviços sem uma boa necessidade comercial. Alguns scripts que podem ser úteis para migração são [compartilhados no GitHub.](https://github.com/lwajswaj/azure-tenant-migration)
- Um determinado serviço geralmente tem algum tipo de limite de "subnível" ou Nível 3 (L3). Isso é útil para entender a segregação de segurança, políticas, governança e assim por diante. Infelizmente, não há nenhum nome uniforme que eu conheça. Alguns exemplos de nomes para L3 são: Assinatura do Azure = [recurso](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instância](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [espaço de trabalho](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview); e assim por diante.
- O Nível 4 é onde residem os dados reais. Este 'plano de dados' é um tópico complexo. Alguns serviços estão usando o Azure AD para RBAC, outros não. Discutirei um pouco sobre isso quando chegarmos aos tópicos de delegação.

Alguns conceitos adicionais que eu vejo muitos clientes (e funcionários da Microsoft) estão confusos ou têm dúvidas sobre:

- Qualquer pessoa [pode criar](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) muitos locatários [sem custo.](https://azure.microsoft.com/pricing/details/active-directory/) Você não precisa de um serviço provisionado dentro dele. Eu tenho dezenas. Cada nome de locatário é exclusivo no serviço de nuvem mundial da Microsoft (em outras palavras, nenhum locatário pode ter o mesmo nome). Todos eles estão no formato de TenantName.onmicrosoft.com. Também há processos que criam locatários automaticamente[(locatários não-administrativos).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) Por exemplo, isso pode ocorrer quando um usuário se ins loco para um serviço corporativo com um domínio de email que não existe em nenhum outro locatário.
- Em um locatário gerenciado, muitos [domínios DNS](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) podem ser registrados nele. Isso não altera o nome do locatário original. Atualmente, não há uma maneira fácil de renomear um locatário (além da migração). Embora o nome do locatário tecnicamente não seja crítico atualmente, alguns podem achar que isso é uma limitação.
- Você deve reservar um nome de locatário para sua organização mesmo se ainda não estiver planejando implantar serviços. Caso contrário, alguém poderá tirar isso de você e não há um processo simples para reamentá-lo (mesmo problema que nomes DNS). Eu vejo isso com muita frequência dos clientes. O nome do seu locatário também deve ser um tópico de debate.
- Se você possui namespaces DNS, você deve adicionar todos eles aos seus locatários. Caso contrário, é possível criar [um locatário não gerenciado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) com esse nome, o que causa interrupções para [torná-lo gerenciado.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- O namespace DNS (como contoso.com) pode pertencer a apenas um locatário. Isso tem implicações para vários cenários (por exemplo, compartilhamento de um domínio de email durante uma fusão ou aquisição e assim por diante). Há uma maneira de registrar um sub dns (como div.contoso.com) em um locatário diferente, mas isso deve ser evitado. Ao registrar um nome de domínio de nível superior, todos os sub-domínios são assumidos como pertencendo ao mesmo locatário. Em cenários multilocatárias (veja abaixo), normalmente recomendaria usar outro nome de domínio de nível superior (como contoso.ch ou ch-contoso.com).
- Quem deve "possuir" um locatário? Frequentemente vejo clientes que não sabem quem é o proprietário atual do locatário. Esse é um sinalizador vermelho grande. Ligue para o suporte da Microsoft assim que possível. Assim como problemático é quando um proprietário de serviço (geralmente um administrador do Exchange) é designado para gerenciar um locatário. O locatário conterá todos os serviços que você pode querer no futuro. O proprietário do locatário deve ser um grupo que pode tomar a decisão de habilitar todos os serviços de nuvem em uma organização. Outro problema é quando um grupo de proprietários de locatários é solicitado a gerenciar todos os serviços. Isso não é dimensionar para grandes organizações.
- Não há um conceito de sub/super locatário. Por algum motivo, essa situação continua se repetindo. Isso também se aplica [aos locatários do Azure AD B2C.](https://docs.microsoft.com/azure/active-directory-b2c/) Eu sei muitas vezes: "Meu ambiente B2C está em meu locatário XYZ" ou "Como faço para mover meu locatário do Azure para meu locatário do Office 365?"
- Este documento se concentra principalmente na nuvem comercial mundial, pois é isso que a maioria dos clientes está usando. Às vezes, é útil saber sobre [nuvens soberanas.](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud) Nuvens soberanas têm implicações adicionais para discutir quais estão fora do escopo desta discussão.

## <a name="baseline-identity-topics"></a>Tópicos de identidade de linha de base

Há muita documentação sobre a plataforma de identidade da Microsoft – Azure Active Directory (Azure AD). Para aqueles que estão apenas começando, isso geralmente parece sobrecarrega. Mesmo depois de aprender sobre isso, acompanhar a inovação e a mudança constantes pode ser um desafio. Nas minhas interações com o cliente, muitas vezes me vejo servindo como "tradutor" entre metas de negócios e abordagens "Boas, Melhores, Melhores" para lidar com essas "anotações" humanas para esses tópicos. Raramente há uma resposta perfeita e a decisão "correta" é um equilíbrio de vários fatores de risco. Veja a seguir algumas das perguntas comuns e áreas de confusão que eu tende a discutir com os clientes.

### <a name="provisioning"></a>Provisionamento

O Azure AD não resolve a falta de governança em seu mundo de identidade! [A governança de](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) identidade deve ser um elemento essencial, independentemente de qualquer decisão de nuvem. Os requisitos de governança mudam ao longo do tempo, e é por isso que ele é um programa e não uma ferramenta.

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. algo mais (de terceiros ou personalizado)? Salve a si mesmo com muita cabeça agora e no futuro e vá com o Azure AD Connect. Há todos os tipos de inteligentes nesta ferramenta para lidar com as configurações do cliente e inovações contínuas.

Alguns casos de borda que podem levar a uma arquitetura mais complexa:

- Tenho várias florestas do AD sem conectividade de rede entre elas. Há uma nova opção chamada [Provisionamento de Nuvem.](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Não tenho o Active Directory nem quero instalá-lo. O Azure AD Connect pode ser configurada para [sincronização do LDAP](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (o parceiro pode ser necessário).
- Preciso provisionar os mesmos objetos para vários locatários. Isso não é tecnicamente suportado, mas depende da definição de "mesmo".

Devo personalizar regras de sincronização padrão[(objetos de filtro,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [atributos de](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)alteração, ID de [logon](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)alternativo e assim por diante)? Evite! Uma plataforma de identidade só é tão valiosa quanto os serviços que a usam. Embora você possa fazer todos os tipos de configurações de noz, para responder a essa pergunta, é necessário ver o impacto nos aplicativos. Se você filtrar objetos habilitados para email, a GAL para serviços online ficará incompleta; se o aplicativo depende de atributos específicos, filtre-os terá um impacto imprevisível; e assim por diante. Não é uma decisão de equipe de identidade.

XYZ SaaS dá suporte ao provisionamento Just-in-Time (JIT), por que você está exigindo que eu sincronizar? Veja acima. Muitos aplicativos precisam de informações de "perfil" para a funcionalidade. Você não poderá ter uma GAL se todos os objetos habilitados para email não estão disponíveis. O mesmo se aplica ao [provisionamento do usuário](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) em aplicativos integrados ao Azure AD.

### <a name="authentication"></a>Autenticação

[Sincronização de hash de](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) senha (PHS) versus autenticação de passagem (PTA) versus [](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) [federação](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Normalmente, há um [grande debate em torno](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) da federação. Geralmente, mais simples é melhor e, portanto, use o PHS, a menos que você tenha um bom motivo para não usá-lo. Também é possível configurar diferentes métodos de autenticação para domínios DNS diferentes no mesmo locatário. 

Alguns clientes habilitam federação + PHS principalmente para:

- Uma opção para [voltar](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (para recuperação de desastre) se o serviço de federação não estiver disponível.
- Recursos adicionais (por ex.: [Azure AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) e serviços de segurança (por ex.: [credenciais vazadas)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- Suporte para serviços no Azure que não entendem a autenticação federada (por exemplo, Arquivos [do Azure).](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)

Geralmente, passo os clientes pelo fluxo de autenticação do cliente para esclarecer alguns conceitos errados. O resultado se parece com a imagem abaixo, que não é tão bom quanto o processo interativo de chegar lá.

![Exemplo de conversa do quadro de diálogo](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Esse tipo de desenho do quadro de branco ilustra onde as políticas de segurança são aplicadas dentro do fluxo de uma solicitação de autenticação. Neste exemplo, as políticas impostas por meio do AD FS (Serviço de Federação do Active Directory) são aplicadas à primeira solicitação de serviço, mas não às solicitações de serviço subsequentes. Isso é pelo menos um motivo para mover os controles de segurança para a nuvem o máximo possível.

Estamos esperando o sósia de [logom](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) único (SSO) pelo tempo que eu puder lembrar. Alguns clientes acredita que podem conseguir isso escolhendo o provedor de federação (STS) "correto". O Azure AD pode ajudar significativamente a habilitar os recursos [de SSO,](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) mas nenhum STS é um problema. Há muitos métodos de autenticação "herdáveis" que ainda são usados para aplicativos críticos. Estender o Azure AD com [soluções de parceiros](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) pode resolver muitos desses cenários. O SSO é uma estratégia e uma jornada. Você não pode chegar lá sem se mover em direção [aos padrões para aplicativos.](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types) Relacionada a este tópico é uma jornada para a [autenticação](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) sem senha, que também não tem uma resposta incrível.

[A autenticação multifatória](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) é essencial hoje[(aqui para](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) obter mais). Adicione a ele [a análise do comportamento do](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) usuário e você tem uma solução que impede ataques cibernéticos mais comuns. Até mesmo os serviços de consumidor estão mudando para exigir a MFA. No entanto, ainda me reúne com muitos clientes que não querem mudar para abordagens [de autenticação](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) moderna. O maior argumento que eu ouvir é que ele afetará os usuários e aplicativos herdados. Às vezes, um bom passo pode ajudar os clientes a seguir em frente - Alterações [anunciadas pelo](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)Exchange Online. Muitos relatórios do Azure [AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) agora estão disponíveis para ajudar os clientes nessa transição.

### <a name="authorization"></a>Autorização

Por [Wikipédia](https://en.wikipedia.org/wiki/Authorization), "para autorizar" é definir uma política de acesso. Muitas pessoas o olharão como a capacidade de definir controles de acesso a um objeto (arquivo, serviço e assim por diante). No mundo atual das ameaças cibernéticas, esse conceito está evoluindo rapidamente para uma política dinâmica que pode reagir a vários vetores de ameaças e ajustar rapidamente os controles de acesso em resposta a eles. Por exemplo, se eu acessar minha conta bancária de um local incomum, obterão etapas de confirmação adicionais. Para abordar isso, precisamos considerar não apenas a própria política, mas o ecossistema de detecção de ameaças e metodologias de correlação de sinal.

O mecanismo de política do Azure AD é implementado usando [políticas de Acesso Condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Esse sistema depende das informações de uma variedade de outros sistemas de detecção de ameaças para tomar decisões dinâmicas. Uma exibição simples seria algo como a ilustração a seguir:

![Mecanismo de política no Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Combinar todos esses sinais em conjunto permite políticas dinâmicas como estas:

- Se uma ameaça for detectada em seu dispositivo, o acesso aos dados será reduzido à Web apenas sem a capacidade de download.
- Se você estiver baixando um volume de dados excepcionalmente alto, tudo o que você baixar será criptografado e restrito.
- Se você acessar um serviço de um dispositivo não autorizado, você será bloqueado contra dados altamente confidenciais, mas poderá acessar dados não restritos sem a capacidade de copiá-lo para outro local.

Se você concordar com essa definição expandida de autorização, precisará implementar soluções adicionais. As soluções implementadas dependerão da dinâmica que você deseja que a política seja e das ameaças que você deseja priorizar. Alguns exemplos desses sistemas são:

- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [O que é o Microsoft Defender para Identidade?](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Obter o Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Proteção de Informações da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/)

Obviamente, além do Azure AD, vários serviços e aplicativos têm seus próprios modelos de autorização específicos. Alguns deles são discutidos posteriormente na seção de delegação.

### <a name="audit"></a>Auditoria

O Azure AD tem recursos detalhados [de auditoria e relatórios.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) No entanto, essa geralmente não é a única fonte de informações necessárias para tomar decisões de segurança. Veja mais discussão sobre isso na seção de delegação.

## <a name="theres-no-exchange"></a>Não há Nenhum Exchange

Não fazer Isso! Isso não significa que o Exchange está sendo preterido (ou o SharePoint e assim por diante). Ele ainda é um serviço principal. O que quero dizer é que, por algum tempo, os provedores de tecnologia têm feito a transição de experiências do usuário (UX) para abranger componentes de vários serviços. No Microsoft 365, um exemplo simples é " anexos modernos " onde[anexos](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)de email são armazenados no SharePoint Online ou no OneDrive for Business.

![Anexar um arquivo a um email](../media/solutions-architecture-center/modern-attachments.png)

Ao olhar para o cliente do Outlook, você pode ver muitos serviços que estão "conectados" como parte dessa experiência, não apenas o Exchange. Isso inclui o Azure AD, a Pesquisa da Microsoft, os Aplicativos, o Perfil, a conformidade e os grupos do Office 365. 

![Interface do Outlook com os callouts](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Leia sobre [o Microsoft Fluid Framework para](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) visualização de recursos futuros. Na visualização agora, posso ler e responder a conversas do Teams diretamente no Outlook. Na verdade, o [cliente do Teams](https://products.office.com/microsoft-teams/download-app) é um dos exemplos mais proeminentes dessa estratégia. 

Em geral, está se tornando mais difícil desenhar uma linha clara entre o Office 365 e outros serviços nas nuvens da Microsoft. Vejo isso como um ótimo benefício para os clientes, pois eles podem se beneficiar da inovação total em tudo o que fazemos, mesmo que eles usem um componente. Muito legal e tem implicações abrangentes para muitos clientes.

Hoje, vejo que muitos grupos de CLIENTES de IT estão estruturados em torno de "produtos". É lógico para um mundo local, pois você precisa de um especialista para cada produto específico. No entanto, estou totalmente feliz por não ter que depurar um banco de dados do Active Directory ou do Exchange novamente, pois esses serviços foram movidos para a nuvem. A automação (que é o tipo de nuvem) remove determinados trabalhos manuais repetitivos (veja o que aconteceu com as armas). No entanto, eles foram substituídos por requisitos mais complexos para entender a interação entre serviços, impacto, necessidades comerciais e assim por diante. Se você estiver disposto a [aprender,](https://docs.microsoft.com/learn/)há ótimas oportunidades habilitadas pela transformação na nuvem. Antes de entrar na tecnologia, converso frequentemente com os clientes sobre como gerenciar mudanças em habilidades de IT e estruturas de equipe.

Para todos os fãs e desenvolvedores do SharePoint, pare de perguntar "Como posso fazer XYZ no SharePoint online?" Use [o Power Automate](https://docs.microsoft.com/power-automate/) (ou o Flow) para o fluxo de trabalho, é uma plataforma muito mais poderosa. Use [o Azure Bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) para criar uma melhor UX para sua lista de itens de 500 K. Comece a [usar o Microsoft Graph](https://developer.microsoft.com/graph/) em vez do CSOM. [O Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) inclui o SharePoint, mas também um mundo mais. Há muitos outros exemplos que posso listar. Há uma grande e incrível quantidade por aí. Abra a porta e [comece a explorar.](https://docs.microsoft.com)

O outro impacto comum está na área de conformidade. Essa abordagem entre serviços parece confundir completamente muitas políticas de conformidade. Vejo organizações com o estado "Preciso fazer o diário de todas as comunicações de email para um sistema de Descoberta Eletrônica". O que isso realmente significa quando o email não é mais apenas um email, mas uma janela para outros serviços? O Office 365 tem uma abordagem abrangente de [conformidade,](https://docs.microsoft.com/microsoft-365/compliance/)mas mudar pessoas e processos geralmente é muito mais difícil do que a tecnologia.

Há muitas outras pessoas e implicações de processo. Na minha opinião, esta é uma área crítica e sub-discutida. Talvez mais em outro artigo.

## <a name="tenant-structure-options"></a>Opções de estrutura do locatário

### <a name="single-tenant-vs-multi-tenant"></a>Locatário único versus multi-locatário

Em geral, a maioria dos clientes deve ter apenas um locatário de produção. Há muitas razões pelas quais vários locatários são desafiadores (dê a ele uma pesquisa do [Bing)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)ou leia [este whitepaper](https://aka.ms/multi-tenant-user). Ao mesmo tempo, muitos clientes corporativos com quem trabalho têm outro locatário (pequeno) para aprendizado, teste e experimentação de IT. O acesso entre locatários do Azure fica mais fácil com o [Azure Tenant.](https://azure.microsoft.com/services/azure-lighthouse/) O Office 365 e muitos outros serviços SaaS têm limites para cenários entre locatários. Há muito a considerar em cenários [B2B do Azure AD.](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)

Muitos clientes terminam com vários locatários de produção após uma fusão e aquisição (M&A) e querem consolidar. Hoje isso não é simples e exigiria o Microsoft Consulting Services (MCS) ou um parceiro mais software de terceiros. Há trabalho contínuo de engenharia para lidar com vários cenários com clientes multi-locatários no futuro.

Alguns clientes optam por ir com mais de um locatário. Essa decisão deve ser muito cuidadosa e quase sempre orientada por motivos comerciais! Alguns exemplos incluem o seguinte:

- Uma estrutura empresarial de tipo de holding em que a colaboração fácil entre entidades diferentes não é necessária e há fortes necessidades administrativas e outras de isolamento.
- Após uma aquisição, uma decisão comercial é tomada para manter duas entidades separadas.
- Simulação do ambiente de um cliente que não altera o ambiente de produção do cliente. 
- Desenvolvimento de software para clientes.

Nesses cenários de vários locatários, os clientes geralmente querem manter algumas configurações iguais entre locatários ou relatar alterações e desvios de configuração. Isso geralmente significa mudar de alterações manuais para configuração como código. O suporte da Microsoft Premier oferece um workshop para esses tipos de requisitos com base neste IP público: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Para [multi-geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) ou não multi-geo, essa é a pergunta. Com o Office 365 Multi-Geo, você pode provisionar e armazenar dados em repouso nas localizações geográficas escolhidas para atender aos requisitos de [residência de](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) dados. Há muitos conceitos errados sobre essa funcionalidade. Lembre-se do seguinte:

- Ele não oferece benefícios de desempenho. Isso pode tornar o desempenho pior se o [design de rede](https://aka.ms/office365networking) não estiver correto. Obter dispositivos "próximos" à rede Da Microsoft, não necessariamente para seus dados.
- Não é uma solução para conformidade [com o RGPD.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) O RGPD não se concentra na soberania de dados ou locais de armazenamento. Há outras estruturas de conformidade para isso.
- Ele não resolve a delegação da administração (veja abaixo) ou as [barreiras de informações.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)
- Não é o mesmo que vários locatários e requer fluxos [de trabalho de provisionamento de usuário](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) adicionais.
- Ele não move [seu locatário](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) (seu Azure AD) para outra geografia. 

## <a name="delegation-of-administration"></a>Delegação de administração

Na maioria das grandes organizações, a separação de funções e controle de acesso baseado em função (RBAC) é uma realidade necessária. Vou pedir muita atenção com antecedência. Isso não é tão simples quanto alguns clientes querem que seja. Os requisitos de cliente, jurídico, de conformidade e outros são diferentes e, às vezes, conflitantes em todo o mundo. Simplicidade e flexibilidade geralmente estão em lados opostos uns dos outros. Não me deixe mal, podemos fazer um trabalho melhor. Houve (e haverá) melhorias significativas ao longo do tempo. Visite o Centro [de Tecnologia da Microsoft](https://www.microsoft.com/mtc) local para trabalhar com o modelo que atende às suas necessidades de negócios sem ler os documentos 379230! Aqui, me concentrarei no que você deve pensar e não no motivo disso. Abaixo estão cinco áreas diferentes para planejar e algumas das perguntas comuns que eu tenho encontrado.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD e centros de administração do Microsoft 365

Há uma lista longa e crescente de [funções integrados.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Cada função consiste em uma lista de permissões de função agrupadas para permitir que ações específicas sejam executadas. Você pode ver essas permissões na guia "Descrição" dentro de cada função. Como alternativa, você pode ver uma versão mais acessível para humanos no Centro de Administração do Microsoft 365. As definições para funções integrados não podem ser modificadas. Geralmente, os agrupa em três categorias:

- **Administrador global:** essa função "toda poderosa" deve ser [altamente protegida](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) como faria em outros sistemas. As recomendações típicas incluem: nenhuma atribuição permanente e uso do Azure AD Privileged Identity Management (PIM); autenticação forte; e assim por diante. Interessantemente, essa função não dá acesso a tudo por padrão. Normalmente, vejo confusão sobre o acesso à conformidade e o acesso ao Azure, discutidos posteriormente. No entanto, essa função sempre pode atribuir acesso a outros serviços no locatário. 
- **Administradores de serviços específicos:** alguns serviços (Exchange, SharePoint, Power BI e assim por diante) consomem funções de administração de alto nível do Azure AD. Isso não é consistente em todos os serviços e há mais funções específicas do serviço discutidas posteriormente.
- **Funcional:** há uma lista longa (e crescente) de funções voltadas para operações específicas (convidado convidado e assim por diante). Periodicamente, mais delas são adicionadas com base nas necessidades do cliente.

Não é possível delegar tudo (embora a lacuna está diminuindo), o que significa que a função de administrador global precisaria ser usada às vezes. A configuração como código e a automação devem ser consideradas em vez da associação de pessoas dessa função.

**Observação:** o Centro de administração do Microsoft 365 tem uma interface mais amigável, mas tem um subconjunto de recursos em comparação com a experiência de administrador do Azure AD. Os dois portais usam as mesmas funções do Azure AD, portanto, as alterações estão ocorrendo no mesmo local. Dica: se você quiser uma interface do usuário de administrador focada no gerenciamento de identidade sem toda a desorganização do Azure, [https://aad.portal.azure.com](https://aad.portal.azure.com) use. 

O que há no nome? Não faça suposições a partir do nome da função. O idioma não é uma ferramenta muito precisa. O objetivo deve ser definir operações que precisam ser delegadas antes de ver quais funções são necessárias. Adicionar alguém à função "Leitor de Segurança" não faz com que ela veja configurações de segurança em tudo.

A capacidade de criar [funções personalizadas](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) é uma pergunta comum. Isso é limitado no Azure AD hoje (veja abaixo), mas aumentará seus recursos ao longo do tempo. Eu as vejo como aplicáveis às funções no Azure AD e talvez não estendo "abaixo" o modelo de hierarquia (discutido acima). Sempre que lido com "personalizado", tendem a voltar para minha entidade de "simples é melhor".

Outra pergunta comum é a capacidade de criar um escopo de funções para um subconjunto de um diretório. Um exemplo é algo como "Administrador de Helpdesk para usuários apenas na UE". [As Unidades](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) Administrativas (AU) destinam-se a resolver isso. Como acima, eu as vejo como aplicáveis a funções no Azure AD e talvez não se estebelecem "para baixo". Obviamente, determinadas funções não fazem sentido para o escopo (administradores globais, administradores de serviço e assim por diante).

Hoje, todas essas funções exigem associação direta (ou atribuição dinâmica se você usar o [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)). Isso significa que os clientes devem gerenciá-los diretamente no Azure AD e eles não podem ser baseados em uma associação de grupo de segurança. Não faço parte da criação de scripts para gerenciá-los, pois seria necessário executar com direitos elevados. Geralmente, recomendamos a integração da API com sistemas de processo como o ServiceNow ou o uso de ferramentas de governança de parceiros, como o Saviynt. Há trabalho de engenharia para resolver isso ao longo do tempo.

Eu [mencionava o PIM do Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) algumas vezes. Há uma solução do GERENCIAMENTO [](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) de Acesso Privilegiado (PAM) correspondente do Microsoft Identity Manager (MIM) para controles locais. Talvez você também queira ver as Estações de Trabalho [com](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) Acesso Privilegiado (PAWs) e a Governança de Identidade do [Azure AD.](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) Há várias ferramentas de terceiros também, que podem habilitar a elevação de função just-in-time, just-enough e dinâmica. Isso geralmente faz parte de uma discussão maior para proteger um ambiente. 

Às vezes, os cenários chamam a adição de um usuário externo a uma função (consulte a seção multilocatária acima). Isso funciona muito bem. [O Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) é outro tópico grande e divertido para ajudar os clientes, talvez em outro artigo.

### <a name="security-and-compliance-center-scc"></a>Centro de Conformidade e Segurança (SCC)

As permissões no Centro de Conformidade e Segurança do [Office 365 &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) são um conjunto de "grupos de funções", que são separados e distintos das funções do Azure AD. Isso pode ser confuso porque alguns desses grupos de função têm o mesmo nome que as funções do Azure AD (por exemplo, Leitor de Segurança), mas podem ter associações diferentes. Eu prefira o uso de funções do Azure AD. Cada grupo de função consiste em uma ou mais "funções" (veja o que quero dizer com reutilização da mesma palavra?) e tem membros do Azure AD, que são objetos habilitados para email. Além disso, você pode criar um grupo de funções com o mesmo nome de uma função, que pode ou não conter essa função (evitar essa confusão).

Em um sentido, essas são uma evolução do modelo de grupos de função do Exchange. No entanto, o Exchange Online tem sua própria interface [de gerenciamento de grupo de](https://docs.microsoft.com/exchange/permissions-exo) funções. Alguns grupos de função no Exchange Online são bloqueados e gerenciados no Azure AD ou no Centro de Conformidade do & de Segurança, mas outros podem ter nomes iguais ou semelhantes e são gerenciados no Exchange Online (adicionando a confusão). Recomendamos que você evite usar a interface do usuário do Exchange Online, a menos que precise de escopos para o gerenciamento do Exchange.

Você não pode criar funções personalizadas. As funções são definidas pelos serviços criados pela Microsoft e aumentarão à medida que novos serviços são introduzidos. Isso é semelhante em conceito a [funções definidas por aplicativos](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) no Azure AD. Quando novos serviços são habilitados, geralmente novos grupos de função precisam ser criados para conceder ou delegar acesso a eles (por exemplo, gerenciamento de riscos [insider](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

Esses grupos de função também exigem associação direta e não podem conter grupos do Azure AD. Infelizmente, atualmente esses grupos de função não são suportados pelo Azure AD PIM. Como as funções do Azure AD, eu tendem a recomendar o gerenciamento dessas funções por meio de APIs ou de um produto de governança de parceiro, como o Saviynt, ou outros.

As funções do Centro de Conformidade & segurança abrangem o Microsoft 365 e você não pode escopo esses grupos de função para um subconjunto do ambiente (como você pode com unidades administrativas no Azure AD). Muitos clientes perguntem como eles podem subdelegar. Por exemplo, "crie uma política de DLP apenas para usuários da UE". Hoje, se você tiver direitos & para uma função específica no Centro de Conformidade e Segurança, terá direitos sobre tudo o que estiver coberto por essa função no locatário. No entanto, muitas políticas têm recursos para direcionar um subconjunto do ambiente (por exemplo, "disponibilizar esses rótulos apenas para esses usuários"). [](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) A governança e a comunicação adequadas são um componente essencial para evitar conflitos. Alguns clientes optam por implementar uma abordagem de "configuração como código" para lidar com subdelegação no Centro de Conformidade e Segurança & Segurança. Alguns serviços específicos suportam subdelegação (veja abaixo).

Vale a pena notar que os controles atualmente gerenciados por meio do & Security & Compliance Center (protection.office.com) estão em processo de migração para dois portais de administração separados: security.microsoft.com e compliance.microsoft.com. A alteração é a única constante!

### <a name="service-specific"></a>Específico do serviço

Conforme indicado anteriormente, muitos clientes estão tentando obter um modelo de delegação mais granular. Um exemplo comum: "Gerenciar o serviço XYZ apenas para usuários e locais da Divisão X" (ou alguma outra dimensão). A capacidade de fazer isso depende de cada serviço e não é consistente entre serviços e recursos. Além disso, cada serviço pode ter um modelo RBAC separado e exclusivo. Em vez de discutir tudo isso (levará uma vida para sempre), estou adicionando links relevantes para cada serviço. Esta não é uma lista completa, mas você vai começar.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **Descoberta eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Filtragem de Permissões**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Limites de conformidade**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Descoberta Descoberta Avançada**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Observação: este link é para a raiz da documentação. Há vários tipos de serviços com variações no modelo de administrador/delegação.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Observação: há vários tipos com variações nos modelos de administrador/delegação.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Observação: a segurança e a delegação da plataforma de dados (que o Power BI é um componente) é uma área complexa.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender para Ponto de Extremidade**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Barreiras de informações**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Para o restante, a pesquisa em Documentos tem sido muito boa em todos os tempos- [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 

### <a name="activity-logs"></a>Logs de Atividades

O Office 365 tem um [log de auditoria unificado.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) É um log [muito detalhado,](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)mas não leia muito no nome. Ele pode não conter tudo o que você deseja ou precisa para suas necessidades de segurança e conformidade. Além disso, alguns clientes estão realmente interessados em [Auditoria Avançada.](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)

Exemplos de logs do Microsoft 365 que são acessados por meio de outras APIs incluem o seguinte:

- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (atividades não relacionadas ao Office 365)
- [Controle de Mensagens do Exchange](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- Sistemas de Ameaças/UEBA discutidos acima (por exemplo, Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender para Ponto de Extremidade e assim por diante)
- [Proteção de informações da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

É importante identificar primeiro todas as fontes de log necessárias para um programa de segurança e conformidade. Observe também que logs diferentes têm limites de retenção online diferentes. 

Da perspectiva da delegação de administrador, a maioria dos logs de atividades do Microsoft 365 não tem um modelo RBAC integrado. Se você tiver permissão para ver um log, poderá ver tudo nele. Um exemplo comum de um requisito de cliente é: "Quero poder consultar a atividade apenas para usuários da UE" (ou alguma outra dimensão). Para atingir esse requisito, precisamos transferir logs para outro serviço. Na nuvem da Microsoft, recomendamos transferi-lo para o [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) ou o [Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 

Diagrama de alto nível:

![diagrama de fontes de log para um programa de segurança e conformidade](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

O diagrama acima representa recursos integrados para enviar logs para o Hub de Eventos e/ou Armazenamento do Azure e/ou a Análise de Log do Azure. Nem todos os sistemas incluem isso pronto para uso. Mas há outras abordagens para enviar esses logs para o mesmo repositório. Por exemplo, confira [Proteger o Teams com o Azure Sentinel.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

Combinar todos os logs em um local de armazenamento inclui benefícios adicionais, como correlações cruzadas, tempos de retenção personalizados, aumento dos dados necessários para dar suporte ao modelo RBAC e assim por diante. Quando os dados estão nesse sistema de armazenamento, você pode criar um painel do Power BI (ou outro tipo de visualização) com um modelo RBAC apropriado.

Os logs não têm que ser direcionados apenas para um local. Também pode ser vantajoso integrar logs do [Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) com o Microsoft Cloud App Security ou um modelo RBAC personalizado no [Power BI.](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide) Repositórios diferentes têm diferentes benefícios e audiências.

Vale a pena mencionar que há um sistema de análise muito rico e integrado para segurança, ameaças, vulnerabilidades e assim por diante em um serviço chamado [Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)

Muitos clientes grandes querem transferir esses dados de log para um sistema de terceiros (por exemplo, SIEM). Há diferentes abordagens para isso, mas o Hub de Eventos do [Azure](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) e o [Graph](https://docs.microsoft.com/graph/security-integration) em geral são bons pontos de partida.

### <a name="azure"></a>Azure

Muitas vezes, sou perguntado se há uma maneira de separar funções de alto privilégio entre o Azure AD, o Azure e o SaaS (ex.: Administrador Global do Office 365, mas não o Azure).  Na verdade, não.  A arquitetura multilocatária será necessária se a separação administrativa completa for necessária, mas isso adiciona complexidade [significativa](https://aka.ms/multi-tenant-user) (veja acima). Todos esses serviços fazem parte do mesmo limite de segurança/identidade (veja o modelo de hierarquia acima).  

É importante entender as relações entre vários serviços no mesmo locatário. Estou trabalhando com muitos clientes que estão criando soluções de negócios que abrangem o Azure, o Office 365 e a Plataforma Power (e geralmente também serviços de nuvem locais e de terceiros). Um exemplo comum:

1. Quero colaborar em um conjunto de documentos/imagens/etc (Office 365)
2. Enviar cada um deles por meio de um processo de aprovação (Power Platform)
3.  Depois que todos os componentes são aprovados, monte-os em uma API do [Microsoft Graph](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) do Azure (produtos unificados) é seu melhor amigo para eles.  Não é impossível, mas é significativamente mais complexo projetar uma solução que abrange [vários locatários.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

O Azure Role-Based Access Control (RBAC) permite o gerenciamento de acesso fino para o Azure. Usando o RBAC, você pode gerenciar o acesso aos recursos, concedendo aos usuários a menor permissão necessária para executar seus trabalhos. Os detalhes estão fora do escopo deste documento, mas para obter mais informações sobre o RBAC, consulte O que é controle de acesso baseado em função [(RBAC) no Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) O RBAC é importante, mas apenas parte das considerações de governança para o Azure. [A Estrutura de Adoção](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) da Nuvem é um ótimo ponto de partida para saber mais. Eu quero saber como meu amigo, Andres Ltdnet, orienta os clientes passo a passo, embora vários componentes decidam sobre a abordagem. A exibição de alto nível para vários elementos (não tão boa quanto o processo para chegar ao modelo de cliente real) é algo parecido com isto:

![Visão de alto nível dos componentes do Azure para administração delegada](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Como você pode ver na imagem acima, muitos outros serviços devem ser considerados como parte do design (por ex.: Políticas do [Azure,](https://docs.microsoft.com/azure/governance/policy/overview)Blueprints do [Azure,](https://docs.microsoft.com/azure/governance/blueprints/overview)Grupos de Gerenciamento [e](https://docs.microsoft.com/azure/governance/management-groups/)assim por diante).

## <a name="conclusion"></a>Conclusão

Iniciado como um resumo curto, terminou por mais tempo do que eu esperava.  Agora, esperamos que você esteja pronto para se preparar para criar um modelo de delegação para sua organização.  Essa conversa é muito comum com os clientes. Não há um modelo que funcione para todos. Aguardando algumas melhorias planejadas da engenharia da Microsoft antes de documentar padrões comuns que vemos entre os clientes. In the meantime, you can work with your Microsoft account team to arrange a visit to the nearest [Microsoft Technology Center](https://www.microsoft.com/mtc).  Até lá!
