---
title: Solicitações de Entidades de Dados do Intune para o RGPD
description: Guia sobre como usar produtos, serviços e ferramentas administrativas da Microsoft para ajudar nossos clientes controladores a encontrarem e tomarem medidas em relação a dados pessoais para responder às solicitações de DSR.
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
author: dougeby
manager: angrobe
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 4e6afa2b9003a2cf2b41691f50688b21e3bf0ea1
ms.sourcegitcommit: dc5c297ee7bca212b8a902daebe4907254c4315f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34589797"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>Solicitações de Entidades de Dados do Intune para o RGPD

O [GDPR (Regulamento Geral sobre a Proteção de Dados)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)da União Europeia concede o direito às pessoas (conhecidas na regulamentação como *entidades de dados *) de gerenciar os dados pessoais coletados por um empregador ou outro tipo de agência ou organização (conhecidos como*controladores de dados* ou apenas *controladores*). Os dados pessoais são definidos em linhas gerais no GDPR como todos os dados relacionados a uma pessoa física identificada ou identificável. O GDPR fornece às entidades de dados direitos específicos a seus dados pessoais. Esses direitos incluem obter cópias, solicitar alterações, restringir o processamento, excluir ou receber os dados em um formato eletrônico para que eles possam ser passados para outro controlador. Uma solicitação formal feita por uma entidade de dados a um controlador para executar uma ação em seus dados pessoais é chamada neste documento de *Solicitação de Direitos da Entidade de Dados * ou DSR.

O guia descreve como usar os produtos, serviços e ferramentas administrativas da Microsoft para ajudar os nossos clientes controladores a encontrar dados pessoais e agir em relação a eles para responder a DSRs. Especificamente, isso inclui como localizar, acessar e agir em dados pessoais que residem na nuvem da Microsoft. Veja aqui uma breve visão geral dos processos descritos neste guia:

- **Descobrir** – use ferramentas de pesquisa e descoberta para localizar dados pessoais que possam ser a entidade de uma solicitação DSR. Após a coleta dos documentos que atendem à solicitação, você pode executar uma ou mais das ações de DSR a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização para responder às solicitações DSR.
- **Acesso:** recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.
- **Retificação:** faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.
- **Restringir:** restrinja o processamento de dados pessoais, removendo licenças para vários serviços do Azure ou desativando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e retê-los localmente ou em outro lugar.
- **Exclusão:** remova permanentemente os dados pessoais que residem na nuvem da Microsoft.
- **Exportação:** forneça uma cópia eletrônica (em um formato legível por máquina) dos dados pessoais para o titular dos dados.

Cada seção deste guia descreve os procedimentos técnicos que uma organização controladora de dados pode realizar para responder a uma DSR para dados pessoais na nuvem da Microsoft.

#### <a name="terminology"></a>Terminologia

Veja a seguir as definições dos termos que são relevantes para este guia.

- **Controlador:** a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, onde tais fins e meios são determinados por lei da União ou Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou Estado-Membro.
- **Dados pessoais e titular dos dados:** quaisquer informações relacionadas a uma pessoa física identificada ou identificável (“titular dos dados”); uma pessoa física identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou por um ou mais fatores específicos à identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física.
- **Processador:** uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.
- **Dados do cliente:** Todos os dados, incluindo todos os arquivos de texto, som, vídeo ou imagem e software, fornecidos à Microsoft por um cliente, em nome de um cliente ou por meio do uso do serviço corporativo. Os dados do cliente incluem tanto (1) informações identificáveis de usuários finais (por exemplo, nomes de usuário e informações de contato no Active Directory do Azure) quanto conteúdo do cliente para o qual o cliente carrega arquivos ou que é criado em serviços específicos (por exemplo, conteúdo do cliente em uma conta de Armazenamento do Azure, conteúdo do cliente de um Banco de Dados SQL do Azure ou uma imagem de máquina virtual de cliente em Máquinas Virtuais do Azure).
- **Logs gerados pelo sistema:** logs e dados relacionados gerados pela Microsoft que ajudam a Microsoft a fornecer serviços corporativos aos usuários. Os logs gerados pelo sistema contêm principalmente dados pseudonimizados, como identificadores exclusivos — normalmente, um número gerado pelo sistema que não pode, por si só, identificar uma pessoa individual, mas é usado para fornecer os serviços corporativos aos usuários. Os logs gerados pelo sistema também podem conter informações identificáveis sobre os usuários finais, como um nome de usuário.

#### <a name="how-to-use-this-guide"></a>Como usar este guia

Este guia consiste em duas partes:

- **Parte 1: Respondendo a Solicitações de Entidade de Dados para Dados do Cliente:** a Parte 1 deste guia discute como acessar, retificar, restringir, excluir e exportar dados de aplicativos nos quais você criou dados. Esta seção detalha como executar o DSRs no conteúdo do cliente e também as informações identificáveis dos usuários finais.
- **Parte 2: Respondendo a Solicitações de Entidades de Dados para Logs Gerados pelo Sistema:** quando você usa os serviços corporativos da Microsoft, a Microsoft gera algumas informações, conhecidas como Logs Gerados pelo Sistema, para fornecer o serviço.  A Parte 2 deste guia discute como acessar, excluir e exportar essas informações para o Azure.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Noções básicas sobre DSRs para Azure Active Directory e Microsoft Intune

Ao considerar serviços fornecidos para clientes empresariais, a execução de DSRs sempre deve ser compreendida no contexto de um locatário específico do Azure Active Directory (AAD). As DSRs sempre são executadas em um determinado locatário do AAD. Se um usuário fizer parte de vários locatários, é importante enfatizar que uma determinada DSR é executada *apenas* no contexto do locatário específico no qual a solicitação foi recebida. É essencial entender que isso significa que a execução da DSR por um cliente corporativo **não** afeta os dados de um cliente corporativo adjacente.

O mesmo também se aplica ao Microsoft Intune fornecido a um cliente corporativo: execução de um DSR em uma conta do Intune *associada a um locatário do AAD* **se refere apenas** aos dados dentro do locatário. Além disso, é importante compreender o seguinte ao lidar com a contas do Intune em um locatário:

- Se um usuário do Intune criar uma assinatura do Azure, a assinatura será tratada como se fosse um locatário do AAD. Consequentemente, o escopo dessas DSRs está no locatário, como descrito acima.
- Se for excluída uma assinatura do Azure criada por uma conta do Intune, **isso não afetará** a conta do Intune em si. Novamente, como mencionado acima, os DSRs em execução em assinaturas do Azure são limitadas ao escopo do locatário em si.

Os DSRs em relação à própria conta do Intune, **fora de um determinado locatário**, são executados por meio do Painel de Privacidade do Cliente. Consulte o Guia de Solicitações de Titulares de Dados do Windows para saber mais.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guia DSR para dados de clientes

### <a name="executing-dsrs-against-customer-data"></a>Executar os DSRs em relação aos dados de cliente

A Microsoft fornece a capacidade de acessar, excluir e exportar determinados dados de clientes por meio do Portal do Azure e também diretamente, por meio de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário) para serviços específicos (também conhecidas como *experiências do produto*). Detalhes sobre essas experiências internas de produtos são descritos na documentação de referência desses respectivos serviços.

>[!IMPORTANT]  
>Serviços de suporte a DSRs de produtos exigem o uso direto de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário), que descrevem as operações CRUD (criar, ler, atualizar e excluir). Consequentemente, é necessário executar as DSRs de um determinado serviço e também executar uma DSR no Portal do Azure para concluir totalmente a solicitação de um determinado titular de dados. Consulte a documentação de referência de serviços específicos para saber mais.

### <a name="step-1-discover"></a>Etapa 1: Descoberta

A primeira etapa para responder a uma DSR é localizar os dados pessoais do titular da solicitação. Esta primeira etapa, ou seja, localizar e analisar os dados pessoais em questão, ajuda a determinar se a DSR atende aos requisitos da sua organização para aceitá-la ou recusá-la. Por exemplo, depois de localizar e analisar os dados pessoais em questão, pode ser que você determine que a solicitação não atende aos requisitos da sua organização porque afetaria negativamente os direitos e liberdades de terceiros.

Depois de encontrar os dados, você pode executar uma ação específica que atenda à solicitação feita pelo titular dos dados. Para obter detalhes, confira o seguinte:

- [Conjunto de dados](https://docs.microsoft.com/intune/privacy-data-collect)
- [Armazenamento e processamento de dados](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Exibir dados pessoais](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Etapa 2: Acesso

Depois de encontrar dados pessoais potencialmente responsivos a uma DSR, cabe a você e a sua organização decidir quais dados fornecer ao titular dos dados. Por exemplo, você pode fornecer a ele uma cópia do documento original, uma versão adequadamente redigida ou uma captura de tela das partes que você considerou apropriado compartilhar. Para cada uma dessas respostas a uma solicitação de acesso, você terá que recuperar uma cópia do documento ou outro item que contenha os dados responsivos.

Ao oferecer uma cópia ao titular dos dados, talvez você tenha que remover ou redigir informações pessoais sobre outros titulares de dados e quaisquer informações confidenciais.

A seguir explicamos como obter uma cópia dos dados em resposta a uma solicitação de acesso a DSR.

#### <a name="azure-active-directory"></a>Azure Active Directory

A Microsoft oferece experiências de portal e produto, proporcionando ao administrador de locatário do cliente corporativo a capacidade de gerenciar solicitações de acesso de DSR. As solicitações de acesso de DSR permitem o acesso dos dados pessoais do usuário, incluindo: (a) informações identificáveis sobre um usuário final e (b) logs gerados pelo sistema.

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

O Microsoft Intune fornece a capacidade de [descobrir os Dados dos Clientes](#step-1-discover) diretamente por meio de UIs (interfaces de usuário) ou APIs (interfaces de programação de aplicativo) pré-existentes.

### <a name="step-3-rectify"></a>Etapa 3: Retificação

Se um titular dos dados pediu para corrigir os dados pessoais que residem nos dados da sua organização, você e sua organização precisam determinar se é apropriado aceitar a solicitação. A correção dos dados pode incluir a execução de ações como editar, redigir ou remover dados pessoais de um documento ou de outro tipo de item. 

Enquanto processadora de dados, a Microsoft não oferece a capacidade de corrigir logs gerados pelo sistema, pois eles refletem atividades concretas e constituem um registro do histórico de eventos dos serviços Microsoft. Com relação ao Intune, os administradores não podem atualizar informações específicas do aplicativo ou dispositivo. Se um usuário final quiser corrigir qualquer dado pessoal (como o nome do dispositivo), deverá fazer isso diretamente em seu dispositivo. Essas alterações são sincronizadas na próxima conexão com o Intune.

### <a name="step-4-restrict"></a>Etapa 4: Restrição

Os entidades de dados podem solicitar que você restrinja o processamento de seus dados pessoais. Fornecemos tanto o Portal do Azure como interfaces de programação de aplicativos (APIs) ou interfaces de usuário (UIs) pré-existentes. Essas experiências fornecem ao administrador de locatário do cliente corporativo a capacidade de gerenciar essas DSRs por meio de uma combinação de exportação e exclusão de dados. Para obter detalhes, consulte [Processando dados pessoais](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

### <a name="step-5-delete"></a>Etapa 5: Exclusão

O "direito de eliminação", com a remoção de dados pessoais dos Dados de Clientes da organização, é uma proteção importante do RGPD. A remoção de dados pessoais inclui a remoção de todos os dados pessoais e logs gerados pelo sistema, exceto informações de log de auditoria. Para saber mais, confira [Excluir dados pessoais do usuário final](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>Parte 2: Logs gerados pelo sistema

Os logs de auditoria dão aos administradores de locatário um registro de atividades que geram uma alteração no Microsoft Intune. Os Logs de Auditoria disponíveis para várias atividades de gerenciamento e normalmente criam, atualizam (editam), excluem e atribuem ações. Também é possível revisar tarefas remotas que geram eventos de auditoria. Esses logs de auditoria podem conter dados pessoais de usuários cujos dispositivos estão registrados no Intune. Os administradores não podem excluir os logs de auditoria. Para saber mais, confira [Auditoria de dados pessoais](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar problemas de exportação ou exclusão

Se você tiver problemas ao exportar ou excluir dados do Portal do Azure, acesse a folha **Ajuda + Suporte** do portal do Azure e envie um novo tíquete na folha **Gerenciamento de Assinaturas > Outra Solicitação de Segurança e Conformidade > Privacidade e Solicitações de RGPD**.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)