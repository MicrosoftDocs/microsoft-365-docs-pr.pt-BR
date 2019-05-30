---
title: Solicitações de Entidades de Dados do Azure para o RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 5b546a38b5073297fb9b89a06b4302fcd9be71fb
ms.sourcegitcommit: ea1d28fc3d0b93441aaca659c843f67495c1874f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34544858"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a>Solicitações de Entidades de Dados do Azure para o RGPD

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introdução às DSRs (Solicitações de Entidades de Dados)

O RGPD (Regulamento Geral sobre a Proteção de Dados) da UE fornece direitos às pessoas (conhecidas na regulamentação como *titulares de dados*) para gerenciar os dados pessoais que foram coletados por um funcionário ou outro tipo de órgão ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos amplamente no RGPD como quaisquer dados relacionados a uma pessoa identificada ou identificável. O RGPD fornece aos titulares de dados os direitos específicos a seus dados pessoais; esses direitos incluem a obtenção de cópias desses dados pessoais, a solicitação de correções, a restrição do processamento, a exclusão ou o recebimento desses dados em formato eletrônico para que possam ser migrados para outro controlador. Uma solicitação formal de um titular de dados feita a um controlador para realizar uma ação em seus dados pessoais é chamada de *Solicitação de Titular de Dados* ou DSR.

O guia descreve como usar os produtos, serviços e ferramentas administrativas da Microsoft para ajudar os nossos clientes controladores a encontrar dados pessoais e agir em relação a eles para responder a DSRs. Especificamente, isso inclui como localizar, acessar e agir em dados pessoais que residem na nuvem da Microsoft. Veja aqui uma breve visão geral dos processos descritos neste guia:

- **Descoberta:** use ferramentas de pesquisa e descoberta para localizar com mais facilidade os dados de clientes que possam estar sujeitos a uma DSR. Assim que os documentos potencialmente dinâmicos forem coletados, você pode executar uma ou mais ações de DSR descritas nas etapas a seguir a fim de responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes de sua organização para responder a DSRs.
 - **Acesso:** recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.
- **Retificação:** faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.
- **Restrição:** restrinja o processamento de dados pessoais, removendo licenças de diversos serviços do Azure ou desativando os serviços desejados, quando possível. Você também pode remover dados da nuvem da Microsoft e mantê-los no local ou onde preferir.
- **Exclusão:** remova permanentemente os dados pessoais que residem na nuvem da Microsoft.
- **Exportação:** forneça uma cópia eletrônica (em um formato legível por máquina) dos dados pessoais para o titular dos dados.

Cada seção deste guia descreve os procedimentos técnicos que uma organização controladora de dados pode realizar para responder a uma DSR para dados pessoais na nuvem da Microsoft.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>

## <a name="terminology"></a>Terminologia

Veja a seguir as definições dos termos que são relevantes para este guia.

- **Controlador:** a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, onde tais fins e meios são determinados por lei da União ou Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou Estado-Membro.

- **Dados pessoais e titular dos dados:** quaisquer informações relacionadas a uma pessoa física identificada ou identificável (“titular dos dados”); uma pessoa física identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou por um ou mais fatores específicos à identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física.

- **Processador:** uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.

- **Dados do cliente:** todos os dados, incluindo texto, som, vídeo ou arquivos de imagem e software que são fornecidos à Microsoft, por ou em nome de um cliente, através do uso de serviço corporativo. Dados do cliente incluem (1) informações de identificação de usuários finais (por exemplo, nomes de usuário e informações de contato no Azure Active Directory) e conteúdo do cliente que um cliente carrega ou cria em serviços específicos (por exemplo, conteúdo de cliente na conta de Armazenamento do Azure, conteúdo do cliente em um Banco de Dados SQL do Azure ou imagem da máquina virtual do cliente em máquinas virtuais do Azure).

- **Logs gerados pelo sistema:** logs e dados relacionados gerados pela Microsoft que nos ajudam a fornecer os serviços corporativos aos usuários. Logs gerados pelo sistema contêm, principalmente, dados pseudônimos, tais como identificadores exclusivos, normalmente um número gerado pelo sistema que não pode sozinho identificar um indivíduo, mas que é usado para fornecer serviços corporativos aos usuários. Logs gerados pelo sistema também podem conter informações de identificação dos usuários finais, como nomes de usuário.

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

## <a name="how-to-use-this-guide"></a>Como usar este guia

Este guia consiste em duas partes:

**Parte 1: responder às solicitações de titulares de dados para dados de cliente**: a parte 1 deste guia descreve como acessar, corrigir, restringir, excluir e exportar dados que você tenha criado e que estejam em aplicativos. Esta seção fornece detalhes sobre como executar os DSRs no Conteúdo de clientes e também as informações de identificação de usuários finais.

**Parte 2: responder às solicitações de titulares de dados por logs gerados pelo sistema**: quando você usa os serviços corporativos da Microsoft, nós geramos informações, conhecidas como logs gerados pelo sistema, para fornecer o serviço. A parte 2 deste guia descreve como acessar, excluir e exportar tais informações para o Azure.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>Noções básicas sobre DSRs para contas de serviços da Microsoft e do Azure Active Directory

Ao considerar serviços fornecidos para clientes empresariais, a execução de DSRs sempre deve ser compreendida no contexto de um locatário específico do Azure Active Directory (AAD). As DSRs sempre são executadas em um determinado locatário do AAD. Se um usuário fizer parte de vários locatários, é importante enfatizar que uma determinada DSR é executada *apenas* no contexto do locatário específico no qual a solicitação foi recebida. É essencial entender que isso significa que a execução da DSR por um cliente corporativo **não** afeta os dados de um cliente corporativo adjacente.

O mesmo também se aplica a contas de serviço da Microsoft (MSA) no contexto dos serviços fornecidos a um cliente corporativo: a execução de uma DSR em uma conta MSA *associada a um locatário do AAD* **se refere apenas** aos dados dentro do locatário. Além disso, é importante compreender o seguinte ao lidar com a contas MSA em um locatário:

-   Se um usuário MSA criar uma assinatura do Azure, a assinatura será tratada como se fosse um locatário do AAD. Consequentemente, o escopo dessas DSRs está no locatário, como descrito acima.

-   Se for excluída uma assinatura do Azure criada por uma conta MSA, **isso não afeta** a conta MSA em si. Novamente, como mencionado acima, as DSRs em execução em assinaturas do Azure são limitadas ao escopo do locatário em si.

As DSRs em relação à própria conta MSA, **fora de um determinado locatário**, são executadas por meio do Painel de privacidade do cliente. Consulte o Guia de solicitações de titulares de dados do Windows para saber mais.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guia DSR para dados de clientes

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>Executar os DSRs em relação aos dados de cliente

A Microsoft fornece a capacidade de acessar, excluir e exportar determinados dados de clientes por meio do Portal do Azure e também diretamente, por meio de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário) para serviços específicos (também conhecidas como *experiências do produto*). Detalhes sobre essas experiências internas de produtos são descritos na documentação de referência desses respectivos serviços.

>[!Important]  
> Serviços de suporte a DSRs de produtos exigem o uso direto de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário), que descrevem as operações CRUD (criar, ler, atualizar e excluir). Consequentemente, é necessário executar as DSRs de um determinado serviço e também executar uma DSR no Portal do Azure para concluir totalmente a solicitação de um determinado titular de dados. Consulte a documentação de referência de serviços específicos para saber mais.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-1-discover"></a>Etapa 1: Descoberta

A primeira etapa ao responder a uma DSR é localizar os dados pessoais do titular da solicitação. Esta primeira etapa, localizar e revisar os dados pessoais em questão, ajuda a determinar se uma DSR atende aos requisitos de sua organização para aceitá-la ou recusá-la. Por exemplo, depois de localizar e analisar os dados pessoais em questão, pode ser que você determine que a solicitação não atende aos requisitos da sua organização porque afetaria negativamente os direitos e liberdades de terceiros.

Depois de encontrar os dados, você pode executar uma ação específica que atenda à solicitação feita pelo titular dos dados.

<span id="_Toc511384807" class="anchor"><span id="_Toc511163878" class="anchor"><span id="_Toc511136235" class="anchor"><span id="_Toc511125168" class="anchor"><span id="_Toc511120755" class="anchor"><span id="_Toc511122662" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

O [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) é um serviço da Microsoft para gerenciamento de identidades e diretórios com vários locatários baseados na nuvem. Você pode localizar informações de identificação de usuários finais, como perfis de usuários de clientes e funcionários, e informações de trabalho de usuários, que contenham dados pessoais do ambiente do [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) usando o [portal do Azure](https://portal.azure.com/).

Isso é especialmente útil se você quiser localizar ou alterar dados pessoais de um usuário específico. Também é possível adicionar ou alterar informações de trabalho e de perfil de usuário. Você deve entrar com uma conta de administrador global do diretório.

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>Como localizar ou exibir informações de trabalho e de perfil de um usuário?

1. Entre no [portal do Azure](https://portal.azure.com/) com uma conta de administrador global do diretório.

1. Selecione **Todos os serviços**, digite **Usuários e grupos** na caixa de texto e pressione **Enter**.

     ![Selecionar Todos os serviços](media/azure-dsr_image3.png)

3. Na folha **Usuários e grupos**, selecione **Usuários**.

     ![Selecionar usuários](media/azure-dsr_image9.png)

4.  Na folha **Usuários e grupos - Usuários**, selecione um usuário na lista e, em seguida, na folha do usuário selecionado, selecione **Perfil** para exibir as informações de perfil do usuário que possam conter dados pessoais.

    ![Selecionar perfil](media/azure-dsr_image5.png)

5. Se for necessário, é possível adicionar ou alterar informações de perfil do usuário e depois, na barra de comando, selecionar **Salvar**.

<!-- steps 6 and 7 not in original 
6. On the blade for the selected user, select **Work Info** to view user work information that may contain personal data.

     ![Select work info](media/azure-dsr_image11.png)

7. If you need to add or change user work information, you can do so, and then, in the command bar, select **Save.**

end of text to isolate -->

<span id="_Toc511384808" class="anchor"><span id="_Toc511163879" class="anchor"><span id="_Toc511136236" class="anchor"><span id="_Toc511125169" class="anchor"><span id="_Toc511120756" class="anchor"><span id="_Toc511122663" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Access" class="anchor"><span id="_Toc508792512" class="anchor"><span id="_Ref511119401" class="anchor"><span id="_Toc511122664" class="anchor"><span id="_Toc511120757" class="anchor"><span id="_Toc511125170" class="anchor"><span id="_Toc511136237" class="anchor"><span id="_Toc511163880" class="anchor"><span id="_Toc511384809" class="anchor"><span id="_Hlk503968195" class="anchor"></span></span></span></span></span></span></span></span></span></span>

### <a name="step-2-access"></a>Etapa 2: Acesso

Depois de encontrar dados pessoais potencialmente responsivos a uma DSR, cabe a você e a sua organização decidir quais dados fornecer ao titular dos dados. Por exemplo, você pode fornecer a ele uma cópia do documento original, uma versão adequadamente redigida ou uma captura de tela das partes que você considerou apropriado compartilhar. Para cada uma dessas respostas a uma solicitação de acesso, você terá que recuperar uma cópia do documento ou outro item que contenha os dados responsivos.

Ao fornecer uma cópia ao titular dos dados, talvez você tenha que remover ou redigir informações pessoais sobre outros titulares de dados e quaisquer informações confidenciais.

<span id="_Using_Content_Search_1" class="anchor"></span>A seguir explicamos como obter uma cópia dos dados em resposta a uma solicitação de acesso a DSR.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>A Microsoft oferece um portal e experiências de produtos, proporcionando ao administrador de locatários do cliente corporativo a capacidade de gerenciar solicitações de acesso a DSR. As solicitações de acesso a DSR permitem acessar dados pessoais do usuário, incluindo: (a) informações de identificação sobre um usuário final e (b) logs gerados pelo sistema.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-3-rectify"></a>Etapa 3: Retificação

Se um titular dos dados pediu para corrigir os dados pessoais que residem nos dados da sua organização, você e sua organização precisam determinar se é apropriado aceitar a solicitação. A correção dos dados pode incluir a execução de ações como editar, redigir ou remover dados pessoais de um documento ou de outro tipo de item. A maneira mais apropriada para fazer isso com dados do Suporte da Microsoft e do Microsoft FastTrack é fornecida abaixo.

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

Clientes corporativos têm a capacidade de gerenciar solicitações de retificação de DSR, incluindo recursos de edição limitados por natureza de um determinado serviço da Microsoft. Como processador de dados, a Microsoft não oferece a capacidade de corrigir logs gerados pelo sistema, pois refletem atividades concretas e constituem um registro do histórico de eventos em serviços da Microsoft. Em relação ao Azure Active Directory, os recursos de edição limitados existem para retificar as informações de identificação sobre usuários finais, como descrito abaixo.

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory: retificar/corrigir dados pessoais incorretos ou incompletos

Você pode corrigir, atualizar ou excluir informações de identificação sobre usuários finais, como perfis de usuário de funcionários e clientes, e informações de trabalho de usuário que contêm dados pessoais, como nome do usuário, título de trabalho, endereço ou número de telefone no seu ambiente [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) usando a [portal do Azure](https://portal.azure.com/). Você deve entrar com uma conta de administrador global do diretório.

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>Como corrigir ou atualizar o perfil de usuário e as informações de trabalho no Azure Active Directory?

1.  Entre no [portal do Azure](https://portal.azure.com/) com uma conta de administrador global do diretório.

2.  Selecione **Todos os serviços**, digite **Usuários e grupos** na caixa de texto e pressione **Enter**.

    ![Selecionar Todos os serviços](media/azure-dsr_image3.png)

3.  Na folha **Usuários e grupos**, selecione **Usuários**.
         
    ![Selecionar usuários](media/azure-dsr_image9.png)

4.  Na folha **Usuários e grupos - Usuários**, selecione um usuário na lista e, em seguida, na folha do usuário selecionado, selecione **Perfil** para exibir as informações de perfil do usuário que precisam ser corrigidas ou atualizadas.

    ![Selecionar perfil](media/azure-dsr_image5.png)

5.  Corrija ou atualize as informações e, em seguida, na barra de comando, selecione **Salvar**.

6.  Na folha do usuário selecionado, selecione **Informações de trabalho** para exibir informações de trabalho de usuários que precisam ser corrigidas ou atualizadas.

    ![Selecionar informações de trabalho](media/azure-dsr_image4.png)

7.  Corrija ou atualize as informações de trabalho de usuário e, em seguida, na barra de comando, selecione **Salvar**.

<span id="_Toc511384814" class="anchor"><span id="_Toc511163885" class="anchor"><span id="_Toc511136242" class="anchor"><span id="_Toc511125175" class="anchor"><span id="_Toc511120762" class="anchor"><span id="_Toc511122669" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Gain_access_to" class="anchor"><span id="_Toc508792521" class="anchor"><span id="_Toc511122670" class="anchor"><span id="_Toc511120763" class="anchor"><span id="_Toc511125176" class="anchor"><span id="_Toc511136243" class="anchor"><span id="_Toc511163886" class="anchor"><span id="_Toc511384815" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-4-restrict"></a>Etapa 4: Restrição

<span id="_Delete" class="anchor"></span>Os titulares de dados podem solicitar que você restrinja o processamento dos dados pessoais. Fornecemos o Portal do Azure e APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário). Essas experiências proporcionam ao administrador de locatários do cliente corporativo a capacidade de gerenciar tais DSRs por meio de uma combinação de exportação e exclusão de dados. Um cliente pode (1) exportar uma cópia eletrônica de dados pessoais do usuário, incluindo (a) conta(s), (b) logs gerados pelo sistema e (c) logs associados, seguidos de (2) exclusão da conta e dos dados associados que residem em sistemas da Microsoft.

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>

### <a name="step-5-delete"></a>Etapa 5: Exclusão

O “direito de apagar” através da remoção de dados pessoais dos Dados de Clientes de uma organização é uma proteção fundamental do RGPD. A remoção de dados pessoais inclui a remoção de todos os dados pessoais e logs gerados pelo sistema, exceto as informações de logs de auditoria. Quando um usuário é **excluído temporariamente** (veja os detalhes abaixo), a conta é desativada por 30 dias. Se nenhuma ação for realizada durante este período de 30 dias, o usuário é **excluído permanentemente** (novamente, veja os detalhes abaixo). Em uma **exclusão permanente**, a conta do usuário, dados pessoais e logs gerados pelos sistemas são eliminados após mais 30 dias adicionais. Se um administrador de locatário emitir imediatamente uma **exclusão permanente**, a conta de usuário, os dados pessoais e os logs gerados pelo sistema são eliminados dentro de 30 dias da data de emissão.

> [!Important]
> Você deve ser um administrador de locatários para excluir um usuário do locatário.

<span id="_Toc511384817" class="anchor"><span id="_Toc511163888" class="anchor"><span id="_Toc511136245" class="anchor"><span id="_Toc511125178" class="anchor"><span id="_Toc511120765" class="anchor"><span id="_Toc511122672" class="anchor"><span id="_Ref511119801" class="anchor"></span></span></span></span></span></span></span>

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>Excluir um usuário e os dados associados no portal do Azure

Após receber uma solicitação de exclusão de um titular de dados, você pode usar o portal do Azure para excluir um usuário e as informações pessoais associadas, assim como logs gerados pelo sistema.

Excluir dados significa também excluir o usuário do locatário. Inicialmente os usuários são excluídos temporariamente, o que significa que a conta pode ser recuperada por um administrador de locatário em até 30 dias após ser marcada para exclusão temporária. Após 30 dias, a conta será automática e permanentemente excluída do locatário. Antes desses 30 dias, você pode excluir manualmente na Lixeira o usuário excluído temporariamente.

Veja a seguir o processo detalhado para excluir usuários de locatários.

1.  Acesse o portal do Azure e localize o usuário.

2.  Exclua o usuário. Ao excluir o usuário inicialmente, a conta do usuário é enviada para a Lixeira. **Neste ponto, o usuário é excluído temporariamente, ou seja, a conta é desabilitada, mas não eliminada do Azure Active Directory.**

3.  Acesse a lista de usuários excluídos recentemente e exclua permanentemente o usuário. **Agora o usuário é excluído permanentemente (também conhecido como exclusão irreversível), o que significa que a conta foi eliminada do Azure Active Directory**

###### <a name="to-delete-a-user-from-an-azure-tenant"></a>Para excluir um usuário de um locatário do Azure

1.  Abra o portal do Azure, selecione a folha **Azure Active Directory** e selecione **Usuários**.

    A folha **Usuários - Todos os usuários** é exibida.

    ![Localizar usuário](media/azure-dsr_image8.png)

2.  Marque a caixa ao lado do usuário que você deseja excluir, selecione **Excluir usuário**e selecione **Sim** na caixa que confirma se você deseja excluir o usuário.

    ![Gerenciamento de usuários](media/azure-dsr_image9.png)

3.  Na caixa suspensa **Mostrar**, selecione **Usuários excluídos recentemente**.

    ![Exibir perfil de usuário](media/azure-dsr_image10.png)

4.  Selecione o mesmo usuário novamente, escolha **Excluir permanentemente**e selecione **Sim** na caixa que pergunta se você tem certeza.

>[!Important]  
>Lembre-se que, ao clicar em **Sim**, você exclui permanente e irrevogavelmente o usuário, todos os dados associados e os logs gerados pelo sistema. Se você fizer isso por engano, será necessário adicioná-lo manualmente ao locatário. Os dados associados e os logs gerados pelo sistema não podem ser recuperados.

   ![Exibir informações comerciais do usuário](media/azure-dsr_image11.png)

<span id="_Export" class="anchor"><span id="_Step_6:_Export" class="anchor"><span id="_Toc511116629" class="anchor"><span id="_Toc511122673" class="anchor"><span id="_Toc511120766" class="anchor"><span id="_Toc511125179" class="anchor"><span id="_Toc511136246" class="anchor"><span id="_Toc511163889" class="anchor"><span id="_Toc508792534" class="anchor"></span></span></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Toc511384819" class="anchor"><span id="_Toc511163890" class="anchor"><span id="_Toc511136247" class="anchor"><span id="_Toc511125180" class="anchor"><span id="_Toc511120767" class="anchor"><span id="_Toc511122674" class="anchor"></span></span></span></span></span></span>
## <a name="step-6-export"></a>Etapa 6: Exportação

<span id="_Power_BI_2" class="anchor"></span> O “direito de portabilidade de dados” permite que o titular de dados solicite uma cópia dos seus dados pessoais em formato eletrônico (que é um “formato estruturado, comumente usado, interoperável e legível por máquina”) que pode ser transmitido para outro controlador de dados. O Azure dá suporte a isso ao habilitar a sua organização a exportar dados no formato nativo JSON para o contêiner de armazenamento especificado do Azure.

>[Importante]: você deve ser administrador de locatários para exportar dados de usuário do locatário.

<span id="_Toc511384820" class="anchor"><span id="_Toc511163891" class="anchor"><span id="_Toc511136248" class="anchor"><span id="_Toc511125181" class="anchor"><span id="_Toc511120768" class="anchor"><span id="_Toc511122675" class="anchor"><span id="_Ref511119875" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Em relação aos dados do cliente, a Microsoft oferece um portal e experiências internas do produto que proporcionam ao administrador de locatários do cliente corporativo a capacidade de gerenciar solicitações de exportação de informações de identificação de um usuário final.

<span id="_Toc511384821" class="anchor"><span id="_Toc511163892" class="anchor"></span></span>
### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>

## <a name="part-2-system-generated-logs"></a>Parte 2: Logs gerados pelo sistema

A Microsoft também proporciona a capacidade de acessar, excluir e exportar determinados logs gerados pelo sistema associados à utilização do Azure por um usuário.

>[!Important]
> Não há suporte para a capacidade de restringir ou corrigir dados nos logs gerados pelo sistema. Logs gerados pelo sistema constituem ações concretas realizadas na nuvem da Microsoft e dados de diagnóstico. A modificação de tais dados comprometeria o registro histórico de ações e aumentaria os riscos de segurança e fraude.

<span id="_Toc511384823" class="anchor"><span id="_Toc511163894" class="anchor"><span id="_Toc511136252" class="anchor"><span id="_Toc511125185" class="anchor"><span id="_Toc511120772" class="anchor"><span id="_Toc511122679" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-system-generated-logs"></a>Executar as DSRs em logs gerados pelo sistema

A Microsoft fornece a capacidade de acessar, excluir e exportar determinados logs gerados pelo sistema por meio do Portal do Azure e, também, diretamente por meio de interfaces de programação ou interfaces de usuário para serviços específicos. Os detalhes são descritos na documentação de referência desses respectivos serviços.

>[!Important]  
> Serviços de suporte a DSRs de produtos exigem o uso direto de APIs (interfaces de programação de aplicativos) preexistentes ou IUs (interfaces de usuário). Consequentemente, **é necessário executar as DSRs e também executar uma DSR no Portal do Azure para concluir totalmente a solicitação de um determinado titular de dados. Consulte a documentação de referência de serviços específicos para saber mais.**

<span id="_Toc511384824" class="anchor"><span id="_Toc511163895" class="anchor"><span id="_Toc511136253" class="anchor"><span id="_Toc511125186" class="anchor"><span id="_Toc511120773" class="anchor"><span id="_Toc511122680" class="anchor"><span id="_Ref511119063" class="anchor"><span id="_Toc508792552" class="anchor"><span id="_Toc509825622" class="anchor"></span></span></span></span></span></span></span></span></span>

### <a name="step-1-access"></a>Etapa 1: Acessar 

O administrador de locatário é a única pessoa em sua organização que tem acesso aos logs geradas pelo sistema associados ao uso do Azure por um usuário específico. Dados recuperados para uma solicitação de acesso são fornecidos em um formato legível por máquina em arquivos que permitem ao usuário saber com quais serviços os dados estão associados. Como mencionado acima, os dados recuperados não incluem dados que possam comprometer a segurança do serviço.

<span id="_Toc511384825" class="anchor"><span id="_Toc511163896" class="anchor"><span id="_Toc511136254" class="anchor"><span id="_Toc511125187" class="anchor"><span id="_Toc511120774" class="anchor"><span id="_Toc511122681" class="anchor"><span id="_Toc511119129" class="anchor"></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

A Microsoft oferece um portal e experiências de produto, proporcionando ao administrador de locatários do cliente corporativo a capacidade de gerenciar solicitações de acesso. As solicitações de acesso permitem o acesso a dados pessoais do usuário, incluindo: (a) informações de identificação sobre um usuário final e (b) logs gerados pelo sistema. O processo é idêntico ao descrito na seção da Parte 1, Etapa 2: Acesso, do Azure Active Directory.

<span id="_Toc511384826" class="anchor"><span id="_Toc511163897" class="anchor"><span id="_Toc511136255" class="anchor"><span id="_Toc511125188" class="anchor"><span id="_Toc511120775" class="anchor"><span id="_Toc511122682" class="anchor"><span id="_Toc511119130" class="anchor"></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Toc511384827" class="anchor"><span id="_Toc511163898" class="anchor"><span id="_Toc511136256" class="anchor"><span id="_Toc511125189" class="anchor"><span id="_Toc511120776" class="anchor"><span id="_Toc511122683" class="anchor"><span id="_Toc508792553" class="anchor"><span id="_Toc509825623" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-2-delete"></a>Etapa 2: Excluir

O administrador de locatário é a única pessoa em sua organização que pode executar uma solicitação de exclusão de DSR de um determinado usuário em um locatário do Azure.

<span id="_Toc511384828" class="anchor"><span id="_Toc511163899" class="anchor"><span id="_Toc511136257" class="anchor"><span id="_Toc511125190" class="anchor"><span id="_Toc511120777" class="anchor"><span id="_Toc511122684" class="anchor"><span id="_Toc511119563" class="anchor"></span></span></span></span></span></span></span>
#### <a name="azure-active-directory"></a>Azure Active Directory

A Microsoft oferece um portal e experiências de produto, proporcionando ao administrador de locatários do cliente corporativo a capacidade de gerenciar solicitações de exclusão de DSR, que seguem o mesmo processo descrito em Excluir um usuário e dados associados na seção do portal do Azure da Parte 1, Etapa 5: Excluir.

<span id="_Toc511384829" class="anchor"><span id="_Toc511163900" class="anchor"><span id="_Toc511136258" class="anchor"><span id="_Toc511125191" class="anchor"><span id="_Toc511120778" class="anchor"><span id="_Toc511122685" class="anchor"><span id="_Toc511119564" class="anchor"></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

<span id="_Toc511384830" class="anchor"><span id="_Toc511163901" class="anchor"><span id="_Toc511136259" class="anchor"><span id="_Toc511125192" class="anchor"><span id="_Toc511120779" class="anchor"><span id="_Toc511122686" class="anchor"><span id="_Toc508792554" class="anchor"><span id="_Toc509825624" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-3-export"></a>Etapa 3: Exportação

O administrador de locatários é a única pessoa em sua organização que tem acesso aos logs gerados pelo sistema associados ao uso do Azure por um usuário específico. Dados recuperados para uma solicitação de exportação são fornecidos em um formato legível por máquina em arquivos que permitem ao usuário saber com quais serviços os dados estão associados. Como mencionado acima, dados recuperados não incluem dados que possam comprometer a segurança ou estabilidade do serviço.

<span id="_Toc511384831" class="anchor"><span id="_Toc511163902" class="anchor"></span></span>

#### <a name="export-system-generated-logs-using-the-azure-portal"></a>Exportar logs gerados pelo sistema usando o portal do Azure

Após receber uma solicitação de exportação de um titular de dados, você pode usar o portal do Azure para exportar os logs gerados pelo sistema associados a um determinado usuário.

Veja a seguir o processo detalhado para exportar os dados de seu locatário.

1. Acesse o portal do Azure e crie uma solicitação de exportação em nome do usuário.
2. Exporte os dados e envie o arquivo para o usuário.

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a>Para exportar informações de um usuário de um locatário do Azure

1. Abra o portal do Azure, selecione **Todos os serviços**, digite *Política* para filtrar e selecione **Política**.

     ![Filtro Todos os serviços ](media/azure-dsr_image12.png)

2. Na folha **Política**, selecione **Privacidade do usuário**, selecione **Gerenciar Solicitações de Usuário**e selecione **Adicionar solicitação de exportação**.

    ![Adicionar solicitação de exportação ](media/azure-dsr_image13.png)

3. Preencha a **Solicitação de exportação de dados**:

    ![Nova solicitação de exportação de dados](media/azure-dsr_image14.png)

- **Usuário.** Digite o endereço de email do usuário do Azure Active Directory que solicitou a exportação.

- **Assinatura.** Selecione a conta que você usa para relatar o uso de recursos e cobrar pelos serviços. Esse também é o local de sua conta de armazenamento do Azure.

- **Conta de armazenamento.** Selecione a localização de seu Armazenamento do Azure (Blob). Para saber mais, confira o artigo [Introdução ao Armazenamento do Microsoft Azure — armazenamento de Blob](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).

- **Contêiner.** Crie um novo contêiner (ou selecione um existente) como o local de armazenamento para os dados de privacidade exportados do usuário.

4. Selecione **Criar**.

A solicitação de exportação entra no status **Pendente**. Você pode exibir o status do relatório na folha **Privacidade do usuário — Visão Geral**.

>[!Important]  
>Como dados pessoais podem vir de vários sistemas, é possível que o processo de exportação possa demorar até um mês.

<span id="_Toc511384832" class="anchor"><span id="_Toc511163903" class="anchor"></span></span>

#### <a name="service-specific-interfaces"></a>Interfaces específicas de serviços

A Microsoft oferece a capacidade de descobrir os dados dos clientes diretamente por APIs (interfaces de programação de aplicativos) preexistentes ou por IUs (interfaces de usuário) para serviços específicos. Os detalhes são descritos na documentação de referência dos respectivos serviços e descrevem as operações aplicáveis de CRUD (criar, ler, atualizar e excluir).

### <a name="notify-about-exporting-or-deleting-issues"></a>Notificar problemas de exportação ou exclusão
Se você tiver problemas ao exportar ou excluir dados do Portal do Azure, acesse a folha **Ajuda + Suporte** do portal do Azure e envie um novo tíquete na folha **Gerenciamento de Assinaturas > Outra Solicitação de Segurança e Conformidade > Privacidade e Solicitações de RGPD**.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)