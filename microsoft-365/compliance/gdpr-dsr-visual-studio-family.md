---
title: Solicitações de Titulares de Dados da Família do Visual Studio para o GDPR e CCPA
description: Solicitações de Titulares de Dados da Família do Visual Studio para o GDPR e CCPA
keywords: Visual Studio, Visual Studio Code, Visual Studio para Mac, documentação do Visual Studio, privacidade, GDPR, CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 81dfd4b0c0724e2ab40113c1d134e0932c215c8f
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557981"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de Titulares de Dados da Família do Visual Studio para o GDPR e CCPA

O [GDPR (Regulamento Geral sobre a Proteção de Dados)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) da União Europeia fornece direitos às pessoas (conhecidas na regulamentação como _titulares de dados_) para gerenciar seus dados pessoais. Os dados pessoais são definidos amplamente no GDPR como quaisquer dados relacionados a uma pessoa identificada ou identificável. O RGPD fornece aos titulares de dados os direitos específicos a seus dados pessoais; esses direitos incluem a obtenção de cópias desses dados pessoais, a solicitação de correções, a restrição do processamento, a exclusão ou o recebimento desses dados em formato eletrônico. Uma solicitação formal de um titular de dados feita a um controlador de dados (um empregador ou outro tipo de agência ou organização que tem controle sobre os dados pessoais) para realizar uma ação nos dados pessoais desse titular de dados é chamado de _solicitação de titular de dados_ ou DSR. 

Da mesma forma, a Lei de Privacidade do Consumidor da Califórnia (CCPA), fornece direitos e obrigações de privacidade aos consumidores da Califórnia, incluindo direitos semelhantes aos Direitos do Titular dos Dados do RGDP, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais.  O CCPA também fornece certas divulgações, proteções contra discriminação ao eleger direitos de exercício e requisitos de "auto-exclusão/opção de inclusão" para determinadas transferências de dados classificados como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

Para saber mais sobre o RGPD, confira a [Seção RGPD do portal de Confiança do Serviço](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

## <a name="products-covered-by-this-guide"></a>Produtos cobertos por este guia

Este guia explica como usar as ferramentas da Microsoft para exportar ou excluir dados pessoais coletados durante o uso de sessão autenticada (conectada) do Visual Studio e do Visual Studio para Mac e extensões da Microsoft para eles e para o Visual Studio Code. Este guia também aborda como fazer solicitações do titular dos dados para dados pessoais coletados ao usar a Comunidade de Desenvolvedores do Visual Studio, NuGet.org e o site do ASP.NET. Esses produtos podem permitir o uso de ferramentas e extensões que não são da Microsoft e a Microsoft não é um processador ou controlador de dados para essas ferramentas e extensões. Os usuários devem contatar a ferramenta ou o provedor de extensão para compreender os dados pessoais e políticas de coleta dessas ferramentas e extensões.

## <a name="additional-privacy-information"></a>Informações adicionais sobre privacidade

Os Termos de Licença de Software da Microsoft que acompanha os produtos, a [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?LinkId=660726) e os [Compromissos de RGPD da Microsoft](https://docs.microsoft.com/legal/gdpr) descrevem nossas práticas de processamento de dados.

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Visual Studio para Mac e Visual Studio Code

### <a name="personal-data-we-collect"></a>Dados pessoais que coletamos

Na condição de processadora de dados de acordo com o RGPD, a Microsoft coleta dados de que precisamos de usuários para fornecer experiências para e aprimorar o Visual Studio e o Visual Studio para Mac e as extensões da Microsoft para eles e o Visual Studio Code. Há duas categorias de dados: logs gerados pelo sistema e dados de clientes. Os dados de clientes incluem dados interativos e transacionais identificáveis do usuário de que esses produtos precisam para executar o serviço que oferecem. Por exemplo, para fornecer aos usuários experiências personalizadas, como configurações de roaming, precisamos coletar informações de conta do usuário e dados de configurações. Os logs gerados pelo sistema são dados de diagnóstico que são usados para ajudar a identificar e solucionar problemas e aprimorar nossos produtos e serviços, e que também podem conter informações identificáveis sobre usuários finais, como nome de usuário. Os logs gerados pelo sistema são mantidos por não mais que 18 meses. Por exemplo, os logs gerados pelo sistema são agregados para cada dia do uso do produto e incluem a data de uso, o produto usado (por exemplo, "Visual Studio 2017"), a ação que você realizou (por exemplo, "vs/core/packagecostsummary/solutionload") e o número de vezes que a ação foi realizada, como mostra este exemplo:

```Log
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

Para saber mais, confira [Logs gerados pelo sistema coletados pelo Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).

Somente os dados pessoais que estão associados a identidades autenticadas podem ser oferecidos por um DSR. Portanto, por exemplo, como o Visual Studio Code não dá suporte à entrada, os logs gerados pelo sistema a partir dele não estão associados a uma identidade autenticada e não podem ser oferecidos. No entanto, algumas extensões da Microsoft para o Visual Studio Code podem fornecer dados autenticados e estes dados podem ser oferecidos por um DSR. Para saber mais, confira [RGPD e Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). Em geral, não armazenamos dados para o Visual Studio 2013 e versões anteriores; no entanto, determinadas extensões componentes podem fornecer dados associados a identidades autenticadas e podem ser oferecidos por um DSR conforme descrito abaixo.

### <a name="how-users-can-control-personal-data"></a>Como os usuários podem controlar dados pessoais

O Visual Studio 2015 e posterior, o Visual Studio para Mac e o Visual Studio Code fornecem os meios a seguir para seus usuários pararem a coleta de dados e para você como controlador exportar ou excluir dados que já foram coletados.

#### <a name="in-app-settings"></a>Configurações no aplicativo

Os usuários podem controlar as configurações de privacidade para esses produtos. Para saber mais, confira o seguinte

- [Como gerenciar as configurações de privacidade no Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).
- [Como gerenciar as configurações de privacidade no Visual Studio para Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).
- [Como desabilitar o relatório de telemetria no Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

#### <a name="exporting-or-deleting-data"></a>Exportando ou excluindo dados

Os controladores podem gerenciar os dados dos clientes e os logs gerados pelo sistema coletados de seus titulares de dados por um dos dois métodos, dependendo de como o seu produto da Família do Visual Studio ou extensões da Microsoft foram registrados. Em alguns casos, os dois métodos devem ser usados. Os dois métodos permitem que os controladores baixem uma cópia do seu histórico de atividades gerenciado por esse método. O fechamento de uma conta MSA ou AAD exclui os dados de clientes associados ao Visual Studio e cria o anonimato de dados de identificação pessoal nos logs gerados pelo sistema referentes a esses produtos. Os logs gerados pelo sistema em anonimato são mantidos por não mais que 18 meses.

- Os usuários que registraram um produto da Família do Visual Studio usando uma conta com o apoio de um locatário do Azure — por exemplo, conta AAD ou conta MSA associada a uma assinatura do Azure — pode seguir as instruções em [Solicitações de Titulares de Dados do Azure para o RGPD](gdpr-dsr-azure.md).
- Os usuários que registraram um produto da Família do Visual Studio sem uma conta com o apoio de um locatário do Azure — por exemplo, muitas contas usando uma Conta da Microsoft (MSA) — podem usar o [Centro de Respostas de Privacidade da Microsoft baseado na Web](https://aka.ms/userprivacysite) disponível por meio de sua conta da Microsoft para exibir, controlar e excluir dados de atividades vinculados a sua conta da Microsoft em vários serviços Microsoft. Neste cenário, o usuário é um controlador dos seus próprios dados pessoais.

> [!NOTE]
> Quando um titular de conta MSA exclui sua conta, todos os seus dados de identificação pessoal referentes a esses produtos são excluídos, seja a conta apoiada por um locatário do Azure ou não e os logs gerados pelo sistema são definidos de maneira anônima.

Para o Visual Studio 2013, os dados que coletamos são definidos de maneira anônima. Para o Visual Studio 2012 e as versões anteriores, excluímos imediatamente os dados ao recebê-los. Em ambos os casos, não há nada para ver, exportar ou excluir mais tarde.

## <a name="visual-studio-developer-community"></a>Comunidade de Desenvolvedores do Visual Studio

Oferecemos suporte às solicitações do [RGPD (Regulamento Geral sobre a Proteção de Dados)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) por meio do site da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com). Você pode exibir, exportar ou excluir os dados de seus comentários.

### <a name="personal-data-we-collect"></a>Dados pessoais que coletamos

A Microsoft coleta dados para nos ajudar a reproduzir e solucionar problemas que você relata com produtos da Família do Visual Studio. Esses dados incluem dados pessoais e comentários público. Os dados pessoais incluem:

- Suas informações de perfil da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com);
- Preferências e notificações;
- Os anexos e os logs gerados pelo sistema que você forneceu ao [relatar um problema no Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) ou pela [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com);
- Seus votos.

Os comentários públicos incluem: problemas relatados, comentários e soluções.

### <a name="how-users-can-control-personal-data"></a>Como os usuários podem controlar dados pessoais

#### <a name="view"></a>Exibir

Para exibir os dados relacionados a comentários, siga estas etapas:

1. Entre na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).  No canto superior direito, clique em seu perfil e selecione **Perfil e Preferências**.
2. Clique em qualquer uma das guias **Perfil**, **Notificações**, **Atividade** e **Anexos** para exibir os dados enviados para os sistemas de comentários.
   1. **Perfil** refere-se a seu perfil na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com), incluindo nome de usuário, endereço de email, sobre etc.
   2. **Notificações é como você controla as notificações por email que recebe.
   3. **Atividade** oferecerá os itens de comentários que estão ativos em (lançado, comentado etc.) e as atividades realizadas.
   4. **Anexos** é uma lista de histórico de seus anexos em um formato como `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.

#### <a name="export"></a>Exportar

Você pode exportar seus dados de comentários como parte da DSR. Criaremos um ou mais arquivos .zip que incluem:

- Suas informações de perfil da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com);
- Configurações de preferências e notificações;
- Os anexos que você forneceu ao [relatar um problema no Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) ou pela [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).

> [!NOTE]
> Excluiremos do seu arquivo os seguintes comentários públicos que você forneceu: comentários, soluções, problemas relatados.

Para iniciar uma exportação, siga estas etapas:

1. Entre na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).  No canto superior direito, clique em seu perfil e selecione **Perfil e Preferências**.
2. Clique na guia **Privacidade**, clique em **Criar um arquivo morto** para solicitar a exportação de seus dados.
3. O **Status do Arquivo Morto** será atualizado para mostrar que estamos preparando os dados. O tempo antes de os dados estarem disponíveis depende da quantidade de dados que precisamos exportar.
4. Quando os dados estiverem prontos, enviaremos um email.
5. Clique em **Baixar Arquivo Morto** no email ou acesse a guia Privacidade para baixar os dados.

> [!NOTE]
> - Nós não enviaremos email se você tiver escolhido não receber notificações na guia Notificações.
> - Se você solicitar Exportar novamente, removeremos seu arquivo morto antigo e criaremos um novo.

#### <a name="delete"></a>Excluir

A exclusão removerá as seguintes informações sobre você da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com):

- Informações de perfil;
- Configurações de preferências e notificações;
- Os anexos que você forneceu ao [relatar um problema no Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) ou pela [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).
- Seus votos

> [!NOTE]
> Nós não os excluiremos, mas definiremos como anônimas as seguintes informações públicas: seus comentários, suas soluções, os problemas reportados por você.
>
> [!IMPORTANT]
> O processo de exclusão de uma conta AAD ou MSA aciona o processo de exclusão para a [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).

Para iniciar uma exclusão, siga estas etapas:

1. Entre na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com).  No canto superior direito, clique em seu perfil e selecione **Perfil e Preferências**.
2. Clique na guia **Privacidade**, clique em **Excluir seus dados e conta** para iniciar a exclusão de dados.
3. A página de confirmação será exibida.
4. Digite "excluir" na caixa e clique em **Excluir minha conta**.

Depois de clicar em **Excluir minha conta:**

- Nós desconectaremos você.
- Excluiremos sua conta da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com), seus dados pessoais e anexos.
- Definiremos como anônimos seus comentários públicos. Seus comentários públicos permanecerão disponíveis na Comunidade de Desenvolvedores e serão indicados como relatados por um usuário anônimo.
- Nós não mandaremos email depois de excluirmos sua conta, porque você não existirá mais no sistema.
- Se você relatar um problema novo ou fazer logon na [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com), será identificado como um novo usuário.
- Se você excluir a conta da [Comunidade de Desenvolvedores](https://developercommunity.visualstudio.com), nós não a excluiremos de outros serviços Microsoft.

## <a name="xamarin-forums"></a>Fóruns do Xamarin

### <a name="personal-data-we-collect"></a>Dados pessoais que Coletamos

Por meio da comunidade dos usuários dos [Fóruns do Xamarin](https://forums.xamarin.com/), a Microsoft coleta dados que você fornece para nos ajudar a reproduzir e solucionar problemas que você possa ter com os produtos e serviços da Microsoft. Esses dados incluem dados pessoais e comentários públicos. Os dados pessoais que coletamos são dados da conta do usuário (por exemplo, nomes de usuário e endereços de email associados aos Fóruns do Xamarin) e os comentários públicos que coletamos incluem bugs, problemas, comentários e soluções que você fornece através dos Fóruns do Xamarin.

### <a name="how-you-can-control-your-data"></a>Como você pode controlar seus dados

#### <a name="xamarin-forums"></a>Fóruns do Xamarin

##### <a name="view"></a>Exibir

Os usuários com contas ativas dos Fóruns do Xamarin podem exibir seus dados pessoais e comentários públicos (por exemplo, todos os threads postados e postagens) de sua página de conta dos Fóruns do Xamarin. Os usuários também podem editar seus dados pessoais por meio da página de sua conta.

##### <a name="export"></a>Exportar

Os Fóruns do Xamarin estão hospedados por terceiros, Vanilla Forums. Para solicitar a exportação de seus dados públicos, os usuários devem contatar forums@xamarin.com (monitorado pela equipe do Xamarin). Trabalharemos diretamente com a Vanilla Forums para processar esta solicitação.

##### <a name="delete"></a>Delete

Os Fóruns do Xamarin são hospedados por terceiros, Vanilla Forums. Para solicitar a exclusão de seus dados públicos e pessoais, os usuários devem contatar forums@xamarin.com (monitorado pela equipe do Xamarin). Depois disso, atenderemos manualmente à solicitação de exclusão dos dados pessoais do usuário.

> [!NOTE]
> Bugzilla para Xamarin não aceita mais novas questões. Os ex-titulares de contas do Xamarin Bugzilla podem visualizar um arquivo com todos os bugs relatados e todos os comentários adicionados aos bugs em: [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/). Para solicitar a exclusão de dados pessoais contidos no arquivo, os usuários podem arquivar e emitir em [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose). Os comentários públicos (por exemplo, bugs, problemas, comentários e soluções) que os usuários postaram no Xamarin Bugzilla não serão excluídos após o recebimento de uma solicitação de exclusão. Em vez disso, os comentários públicos são desativados pela remoção do nome e endereço de email associados a todos os comentários públicos criados pelo usuário que enviou a solicitação de exclusão.

## <a name="nuget"></a>NuGet

Para saber mais sobre DSR para NuGet.org, confira [Solicitações de dados do usuário do NuGet](https://docs.microsoft.com/nuget/policies/data-requests).

## <a name="aspnet"></a>ASP.NET

Para ter informações sobre DSR para o site do ASP.NET, consulte [o site do ASP.NET e o processamento de solicitação do titular de dados do RGPD](https://www.asp.net/gdpr).

## <a name="iisnet"></a>IIS.NET

Para ter informações sobre DSR para o site do IIS.NET, consulte [o site do IIS.NET e o processamento de solicitação do titular de dados do RGPD](https://www.iis.net/gdpr).

## <a name="other-visual-studio-family-services"></a>Outros serviços da Família do Visual Studio

### <a name="surveymonkey"></a>SurveyMonkey

Ocasionalmente, nós convidamos clientes para enviar comentários sobre esses produtos por meio do SurveyMonkey. Esses dados são excluídos em até 28 dias. Ao fornecer atendimento a solicitações de titular de dados para esses produtos, se tivermos respostas de pesquisas autenticadas, nós as incluiremos nas solicitações de exportação e exclusão de titulares de dados.

## <a name="learn-more"></a>Saiba mais

- [Compromissos da Microsoft sobre o RGPD para com os clientes dos nossos produtos de software empresarial disponibilizados de maneira geral](https://docs.microsoft.com/legal/gdpr)
- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [Portal de Confiança do Serviço](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Painel de Privacidade da Microsoft](https://account.microsoft.com/privacy)
- [Centro de Resposta Privacidade da Microsoft](https://aka.ms/userprivacysite)
- [Solicitações de Entidades de Dados do Azure para o RGPD](gdpr-dsr-azure.md)
