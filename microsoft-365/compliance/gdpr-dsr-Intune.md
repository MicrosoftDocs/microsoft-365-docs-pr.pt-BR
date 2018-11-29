---
title: Solicitações de Entidades de Dados do Intune para o RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
author: dougeby
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
ms.collection: GDPR
ms.openlocfilehash: eeb50954f849b0c110a88cc7d768844847d99255
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865312"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>Solicitações de Entidades de Dados do Intune para o RGPD
O RGPD (Regulamento Geral sobre a Proteção de Dados) da UE fornece direitos às pessoas (conhecidas na regulamentação como *titulares de dados*) para gerenciar os dados pessoais que foram coletados por um funcionário ou outro tipo de órgão ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos amplamente no RGPD como quaisquer dados relacionados a uma pessoa identificada ou identificável. O RGPD fornece aos titulares de dados os direitos específicos a seus dados pessoais; esses direitos incluem a obtenção de cópias desses dados pessoais, a solicitação de correções, a restrição do processamento, a exclusão ou o recebimento desses dados em formato eletrônico para que possam ser migrados para outro controlador. Uma solicitação formal de um titular de dados feita a um controlador para realizar uma ação em seus dados pessoais é chamada de *Solicitação de Titular de Dados* ou DSR.

O guia descreve como usar os produtos, serviços e ferramentas administrativas da Microsoft para ajudar os nossos clientes controladores a encontrar dados pessoais e agir em relação a eles para responder a DSRs. Especificamente, isso inclui como localizar, acessar e agir em dados pessoais que residem na nuvem da Microsoft. Veja aqui uma breve visão geral dos processos descritos neste guia:

1.  ***Descobrir***: use as ferramentas de pesquisa e descoberta para encontrar com mais facilidade os dados de clientes que possam estar sujeitos a uma DSR. Assim que os documentos potencialmente responsivos forem coletados, você pode executar uma ou mais ações de DSR descritas nas etapas a seguir a fim de responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes de sua organização para responder a DSRs.

2.  ***Acessar***: recupere os dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.

3.  ***Retificar***: faça alterações ou implemente outras ações solicitadas nos dados pessoais, quando aplicável.

4.  ***Restringir***: restrinja o processamento dos dados pessoais, seja removendo as licenças de vários serviços do Azure ou desativando os serviços desejados, quando possível. Você também pode remover dados da nuvem da Microsoft e mantê-los no local ou onde preferir.

5.  ***Excluir***: remova permanentemente os dados pessoais que residem na nuvem da Microsoft.

6.  ***Exportar***: forneça uma cópia eletrônica (em um formato legível por máquina) dos dados pessoais para o titular dos dados.

Cada seção deste guia descreve os procedimentos técnicos que uma organização controladora de dados pode realizar para responder a uma DSR para dados pessoais na nuvem da Microsoft.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>Terminologia

Veja a seguir as definições dos termos que são relevantes para este guia.

-   *Controlador*: a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, em que tais fins e meios são determinados por lei da União ou do Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou do Estado-Membro.

-   *Dados pessoais* e *titular dos dados*: quaisquer informações relacionadas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou por um ou mais fatores específicos à identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física.

-   *Processador*: uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.

-   *Dados do cliente*: todos os dados, incluindo qualquer arquivo de texto, som, vídeo ou imagem, e software fornecidos à Microsoft por um cliente ou em seu nome através do uso de serviço corporativo. Dados do cliente incluem (1) informações de identificação de usuários finais (por exemplo, nomes de usuário e informações de contato no Azure Active Directory) e conteúdo do cliente que um cliente carrega ou cria em serviços específicos (por exemplo, conteúdo de cliente na conta do Armazenamento do Azure, conteúdo do cliente em um Banco de Dados SQL do Azure ou imagem da máquina virtual do cliente em máquinas virtuais do Azure).

-   *Logs gerados pelo sistema*: logs e dados relacionados gerados pela Microsoft que nos ajudam a fornecer os serviços empresariais aos usuários. Logs gerados pelo sistema contêm principalmente dados pseudônimos, tais como identificadores exclusivos, normalmente um número gerado pelo sistema que não pode sozinho identificar um indivíduo, mas que é usado para fornecer serviços empresariais aos usuários. Logs gerados pelo sistema também podem conter informações de identificação dos usuários finais, como nomes de usuário.  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>Como usar este guia

Este guia consiste em duas partes:

**Parte 1: responder às solicitações de titulares de dados para dados de cliente**: a parte 1 deste guia descreve como acessar, corrigir, restringir, excluir e exportar dados que você tenha criado e que estejam em aplicativos. Esta seção fornece detalhes sobre como executar os DSRs no Conteúdo de clientes e também as informações de identificação de usuários finais.

**Parte 2: responder às solicitações de titulares de dados por logs gerados pelo sistema**: quando você usa os serviços corporativos da Microsoft, nós geramos informações, conhecidas como logs gerados pelo sistema, para fornecer o serviço. A parte 2 deste guia descreve como acessar, excluir e exportar tais informações para o Azure.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Noções básicas sobre DSRs para Azure Active Directory e Microsoft Intune

Ao considerar serviços fornecidos para clientes empresariais, a execução de DSRs sempre deve ser compreendida no contexto de um locatário específico do Azure Active Directory (AAD). As DSRs sempre são executadas em um determinado locatário do AAD. Se um usuário fizer parte de vários locatários, é importante enfatizar que uma determinada DSR é executada *apenas* no contexto do locatário específico no qual a solicitação foi recebida. É essencial entender que isso significa que a execução da DSR por um cliente corporativo **não** afeta os dados de um cliente corporativo adjacente.

O mesmo também se aplica ao Microsoft Intune fornecido a um cliente corporativo: execução de um DSR em uma conta do Intune *associada a um locatário do AAD* **se refere apenas** aos dados dentro do locatário. Além disso, é importante compreender o seguinte ao lidar com a contas do Intune em um locatário:

-   Se um usuário do Intune criar uma assinatura do Azure, a assinatura será tratada como se fosse um locatário do AAD. Consequentemente, o escopo dessas DSRs está no locatário, como descrito acima.

-   Se for excluída uma assinatura do Azure criada por uma conta do Intune, **isso não afetará** a conta do Intune em si. Novamente, como mencionado acima, os DSRs em execução em assinaturas do Azure são limitadas ao escopo do locatário em si.

Os DSRs em relação à própria conta do Intune, **fora de um determinado locatário**, são executados por meio do Painel de Privacidade do Cliente. Consulte o Guia de Solicitações de Titulares de Dados do Windows para saber mais.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guia DSR para dados de clientes

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>Executar os DSRs em relação aos dados de cliente

A Microsoft fornece a capacidade de acessar, excluir e exportar determinados dados de clientes por meio do Portal do Azure e também diretamente, por meio de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário) para serviços específicos (também conhecidas como *experiências do produto*). Detalhes sobre essas experiências internas de produtos são descritos na documentação de referência desses respectivos serviços.

>[!Important]  
>Serviços de suporte a DSRs de produtos exigem o uso direto de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário), que descrevem as operações CRUD (criar, ler, atualizar e excluir). Consequentemente, é necessário executar as DSRs de um determinado serviço e também executar uma DSR no Portal do Azure para concluir totalmente a solicitação de um determinado titular de dados. Consulte a documentação de referência de serviços específicos para saber mais.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>Etapa 1: Descoberta

A primeira etapa para responder a uma DSR é localizar os dados pessoais do titular da solicitação. Esta primeira etapa, ou seja, localizar e analisar os dados pessoais em questão, ajuda a determinar se a DSR atende aos requisitos da sua organização para aceitá-la ou recusá-la. Por exemplo, depois de localizar e analisar os dados pessoais em questão, pode ser que você determine que a solicitação não atende aos requisitos da sua organização porque afetaria negativamente os direitos e liberdades de terceiros.

Depois de encontrar os dados, você pode executar uma ação específica que atenda à solicitação feita pelo titular dos dados. Para obter detalhes, confira o seguinte:
- [Conjunto de dados](https://docs.microsoft.com/intune/privacy-data-collect)
- [Armazenamento e processamento de dados](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Exibir dados pessoais](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Etapa 2: Acesso
Depois de encontrar dados pessoais potencialmente responsivos a uma DSR, cabe a você e a sua organização decidir quais dados fornecer ao titular dos dados. Por exemplo, você pode fornecer a ele uma cópia do documento original, uma versão adequadamente redigida ou uma captura de tela das partes que você considerou apropriado compartilhar. Para cada uma dessas respostas a uma solicitação de acesso, você terá que recuperar uma cópia do documento ou outro item que contenha os dados responsivos.

Ao fornecer uma cópia ao titular dos dados, talvez você tenha que remover ou redigir informações pessoais sobre outros titulares de dados e quaisquer informações confidenciais.

<span id="_Using_Content_Search_1" class="anchor"></span>A seguir explicamos como obter uma cópia dos dados em resposta a uma solicitação de acesso a DSR.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>A Microsoft oferece um portal e experiências de produtos, proporcionando ao administrador de locatários do cliente corporativo a capacidade de gerenciar solicitações de acesso a DSR. As solicitações de acesso a DSR permitem acessar dados pessoais do usuário, incluindo: (a) informações de identificação sobre um usuário final e (b) logs gerados pelo sistema.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

O Microsoft Intune fornece a capacidade de [descobrir os Dados dos Clientes](#step-1-discover) diretamente por meio de UIs (interfaces de usuário) ou APIs (interfaces de programação de aplicativo) pré-existentes.

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>Etapa 3: Retificação

Se um titular dos dados pediu para corrigir os dados pessoais que residem nos dados da sua organização, você e sua organização precisam determinar se é apropriado aceitar a solicitação. A correção dos dados pode incluir a execução de ações como editar, redigir ou remover dados pessoais de um documento ou de outro tipo de item.  

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 Enquanto processadora de dados, a Microsoft não oferece a capacidade de corrigir logs gerados pelo sistema, pois eles refletem atividades concretas e constituem um registro do histórico de eventos dos serviços Microsoft. Com relação ao Intune, os administradores não podem atualizar informações específicas do aplicativo ou dispositivo. Se um usuário final quiser corrigir qualquer dado pessoal (como o nome do dispositivo), deverá fazer isso diretamente em seu dispositivo. Essas alterações são sincronizadas na próxima conexão com o Intune.

### <a name="step-4-restrict"></a>Etapa 4: Restrição

<span id="_Delete" class="anchor"></span>Os titulares de dados podem solicitar que você restrinja o processamento dos dados pessoais. Fornecemos o Portal do Azure e APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário). Essas experiências proporcionam ao administrador de locatários do cliente corporativo a capacidade de gerenciar tais DSRs por meio de uma combinação de exportação e exclusão de dados. Para obter detalhes, confira [Processamento de dados pessoais](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>Etapa 5: Exclusão

O "direito de eliminação", com a remoção de dados pessoais dos Dados de Clientes da organização, é uma proteção importante do RGPD. A remoção de dados pessoais inclui a remoção de todos os dados pessoais e logs gerados pelo sistema, exceto informações de log de auditoria. Para saber mais, confira [Excluir dados pessoais do usuário final](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>Parte 2: Logs gerados pelo sistema
Os logs de auditoria dão aos administradores de locatário um registro de atividades que geram uma alteração no Microsoft Intune. Os Logs de Auditoria disponíveis para várias atividades de gerenciamento e normalmente criam, atualizam (editam), excluem e atribuem ações. Também é possível revisar tarefas remotas que geram eventos de auditoria. Esses logs de auditoria podem conter dados pessoais de usuários cujos dispositivos estão registrados no Intune. Os administradores não podem excluir os logs de auditoria. Para saber mais, confira [Auditoria de dados pessoais](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).


## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar problemas de exportação ou exclusão
Se você tiver problemas ao exportar ou excluir dados do Portal do Azure, acesse a folha **Ajuda + Suporte** do portal do Azure e envie um novo tíquete na folha **Gerenciamento de Assinaturas > Outra Solicitação de Segurança e Conformidade > Privacidade e Solicitações de RGPD**.

#### <a name="learn-more"></a>Saiba mais
[Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)