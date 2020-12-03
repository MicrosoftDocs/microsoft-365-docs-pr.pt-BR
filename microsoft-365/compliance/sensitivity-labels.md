---
title: Saiba mais sobre rótulos de confidencialidade
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Use rótulos de sensibilidade da estrutura Microsoft Information Protection para classificar e proteger conteúdo sensível com criptografia e marcas d'água.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 62f9cd4eb2056843cae9d68de5803afd422f8560
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527600"
---
# <a name="learn-about-sensitivity-labels"></a>Saiba mais sobre rótulos de confidencialidade

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Para realizar o trabalho, as pessoas da sua organização colaboram com outras pessoas dentro e fora da organização. Isso significa que o conteúdo não fica mais atrás de um firewall, ele pode circular em qualquer lugar, em dispositivos, aplicativos e serviços. E quando estiver em roaming, você quer fazê-lo de uma maneira segura e protegida que atenda às políticas de negócios e conformidade da sua organização.

Os rótulos de sensibilidade da estrutura da Proteção de Informações da Microsoft permitem classificar e proteger os dados da sua organização, garantindo que a produtividade do usuário e sua capacidade de colaborar não sejam prejudicadas.

Exemplo mostrando os rótulos de confidencialidade disponíveis no Excel, na guia **Página Inicial** na faixa de opções. Neste exemplo, o rótulo aplicado exibe na barra de status:

![Rótulo de confidencialidade na faixa de opções e barra de status do Excel](../media/Sensitivity-label-in-Excel.png)

Para aplicar rótulos de confidencialidade, os usuários devem ter entrado com sua conta Microsoft 365 do trabalho ou da escola.

> [!NOTE]
> Para locatários do governo dos Estados Unidos (GCC, GCC-H e DoD) rótulos de confidencialidade possuem suporte somente quando o cliente de rotulagem unificada e digitalização da Proteção de Informações do Microsoft Azure está instalado. 
> 
> Para obter mais informações, confira [Descrição do Serviço Governamental Premium de Proteção de Informações do Microsoft Azure](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).

Você pode usar rótulos de confidencialidade para:
  
- **Impor configurações de proteção, como criptografia ou marcas d'água no conteúdo rotulado.** Por exemplo, os usuários podem aplicar um rótulo confidencial a um documento ou email, e esse rótulo pode criptografar o conteúdo e aplicar uma marca d'água confidencial.

- **Proteja o conteúdo nos aplicativos do Office em diferentes plataformas e dispositivos.** Para obter uma lista de aplicativos com suporte, confira [Uso de rótulos de confidencialidade nos aplicativos do Office](sensitivity-labels-office-apps.md).

- **Proteger o conteúdo em aplicativos e serviços de terceiros** usando o Microsoft Cloud App Security. Com o Cloud App Security, você pode detectar, classificar, rotular e proteger o conteúdo em serviços e aplicativos de terceiros, como SalesForce, Box ou Dropbox, mesmo que o aplicativo ou serviço de terceiros não leia nem ofereça suporte a rótulos de confidencialidade.

- **Proteja contêineres** que incluem o Teams, grupos do Microsoft 365 e sites do Microsoft Office SharePoint Online. Por exemplo, defina as configurações de privacidade, acesso de usuário externo e compartilhamento externo e acesso de dispositivos não gerenciados.

- **Estender os rótulos de confidencialidade a aplicativos e serviços de terceiros.** Usando o SDK de Proteção de informações da Microsoft, os aplicativos e os serviços de terceiros podem ler os rótulos de confidencialidade e aplicar as configurações de proteção.

- **Classificar conteúdo sem usar nenhuma configuração de proteção.** Você também pode simplesmente atribuir uma classificação ao conteúdo (como uma etiqueta) que se mantém e se desloca com o conteúdo conforme ele é usado e compartilhado. Você pode usar essa classificação para gerar relatórios de uso e ver dados de atividade para seu conteúdo confidencial. Com base nessas informações, você pode optar por aplicar as configurações de proteção mais tarde.

Em todos esses casos, os rótulos de confidencialidade no Microsoft 365 podem ajudá-o a executar as ações diretamente no conteúdo certo. Com os rótulos de confidencialidade, você pode classificar dados em toda a organização e impor configurações de proteção com base nessa classificação.

## <a name="what-a-sensitivity-label-is"></a>O que é um rótulo de confidencialidade

Quando você atribui um rótulo de sensibilidade a um documento ou e-mail, isso é como um carimbo aplicado ao conteúdo, qual seja:

- **Personalizável.** Você pode criar categorias para diferentes níveis de conteúdo confidencial em sua organização, como Pessoal, Público, Geral, Confidencial e Altamente Confidencial.

- **Texto não criptografado.** Como o rótulo é armazenado em texto não criptografado nos metadados do conteúdo, aplicativos e serviços de terceiros podem lê-lo e aplicar suas próprias ações de proteção, se necessário.

- **Persistente.** Depois de aplicar um rótulo de confidencialidade ao conteúdo, o rótulo é armazenado nos metadados desse email ou documento. Isso significa que o rótulo acompanha o conteúdo, incluindo as configurações de proteção, e esses dados tornam-se a base para a aplicação e imposição de políticas.

Em aplicativos do Office, um rótulo de confidencialidade simplesmente aparece como uma marca em um email ou documento.

Cada item que oferece suporte a rótulos de confidencialidade pode ter um único rótulo de confidencialidade aplicado a ele. Documentos e emails podem ter um rótulo de confidencialidade e uma [marca de retenção](retention.md#retention-labels) aplicado a eles.

> [!div class="mx-imgBorder"]
> ![Rótulo de confidencialidade aplicado a um email](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>O que rótulos de confidencialidade podem fazer

Depois que um rótulo de confidencialidade é aplicado a um email ou documento, todas as definições de proteção definidas para esse rótulo são aplicadas no conteúdo. Com um rótulo de confidencialidade, você pode:

- **Criptografar** apenas emails ou emails e documentos. Você pode escolher quais ações determinados usuários ou grupos possuem permissões para executar e a duração das permissões. Por exemplo, você pode optar por permitir que os usuários de um grupo específico de outra organização tenham permissões para revisar o conteúdo por apenas sete dias depois que o mesmo for rotulado. Como alternativa, em vez de atribuir permissões definidas pelo administrador, você pode permitir que os usuários atribuam permissões ao conteúdo quando eles aplicam o rótulo. 
    
    Para obter mais informações sobre as configurações de **Criptografia** quando você cria ou edita um rótulo de confidencialidade, consulte [Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade](encryption-sensitivity-labels.md).

- **Marque o conteúdo** quando usar aplicativos do Office, adicionando marcas d’água, cabeçalhos ou rodapés a emails ou documentos que tenham o rótulo aplicado. As marcas d’água podem ser aplicadas a documentos, mas não a emails. Exemplo de cabeçalho e marca d' água:
    
    ![Marca-d'água e cabeçalho aplicados ao documento](../media/Sensitivity-label-watermark-header.png)
    
    Precisa verificar quando as marcações de conteúdo são aplicadas? Confira [Quando os aplicativos do Office aplicam a marcação e criptografia de conteúdo](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption).
    
    Alguns, mas nem todos os aplicativos oferecem suporte a marcações dinâmicas usando variáveis. Por exemplo, insira o nome do rótulo ou o nome do documento no cabeçalho, rodapé ou marca d'água. Para saber mais, confira [marcações dinâmicas com variáveis](sensitivity-labels-office-apps.md#dynamic-markings-with-variables).
    
    Comprimentos de cadeias de caracteres: as marcas d' água estão limitadas a 255 caracteres. Os cabeçalhos e rodapés estão limitados a 1024 caracteres, exceto no Excel. O Excel tem um limite total de 255 caracteres para cabeçalhos e rodapés, mas esse limite inclui caracteres que não estão visíveis, como códigos de formatação. Se esse limite for alcançado, a cadeia de caracteres inserida não será exibida no Excel.

- **Proteja o conteúdo em contêineres, como sites e grupos**, quando você habilita a capacidade de [usar rótulos de confidencialidade no Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](sensitivity-labels-teams-groups-sites.md).
    
    Você não pode definir as configurações de proteção para grupos e sites até ativar esse recurso. Essa configuração de rótulo não resulta em documentos ou emails sendo automaticamente rotulados, mas em vez disso, as configurações de rótulo protegem o conteúdo, controlando o acesso ao contêiner onde o conteúdo pode ser armazenado. Essas configurações incluem configurações de privacidade, acesso de usuário externo e acesso de dispositivos não gerenciados.

- **Aplique o rótulo automaticamente nos aplicativos do Office ou recomende um rótulo.** Escolha quais tipos de informações confidenciais deseja rotular, e o rótulo poderá ser aplicado automaticamente ou será solicitado aos usuários que apliquem o rótulo recomendado. Caso recomende um rótulo, um texto de alerta escolhido por você será exibido. Por exemplo:
    
    ![Solicitar confirmação antes de atribuir a um rótulo necessário](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    Para obter mais informações sobre as configurações de **Rótulo automático para aplicativos do Office** quando você cria ou edita um rótulo de confidencialidade, consulte [Aplicar um rótulo de confidencialidade ao conteúdo automaticamente](apply-sensitivity-label-automatically.md).

### <a name="label-scopes"></a>Escopos de rótulo

Ao criar um rótulo de confidencialidade, você é solicitado a configurar o escopo do rótulo, que determina duas coisas:
- Quais configurações de rótulo você pode definir para esse rótulo
- Onde o rótulo ficará visível para os usuários

Esta configuração de escopo permite que você tenha rótulos de confidencialidade que são apenas para documentos e emails e não podem ser selecionados para containers. E da mesma forma, rótulos de confidencialidade que são apenas para contêineres e não podem ser selecionados para documentos e emails. Por padrão, ambos os escopos estão selecionados:

![Opções de escopo para rótulos de confidencialidade](../media/sensitivity-labels-scopes.png)

Quando você altera esse padrão e seleciona apenas um escopo, ainda vê a primeira página das configurações do outro escopo, mas não pode selecioná-los. Por exemplo, se o escopo para arquivos e emails não for selecionado, você não pode selecionar as opções na próxima página:

![Opções indisponíveis para rótulos de confidencialidade](../media/sensitivity-labels-unavailable-settings.png)

Para essas páginas que têm opções indisponíveis, selecione **Avançar** para continuar. Ou selecione **Voltar** para alterar o escopo do rótulo.

### <a name="label-priority-order-matters"></a>Prioridade de rótulo (a ordem importa)

Quando você cria seus rótulos de confidencialidade no centro de administração, eles aparecem em uma lista na guia **Confidencialidade**, na página **Rótulos**. Nessa lista, a ordem dos rótulos é importante porque reflete sua prioridade. Você quer que seu rótulo de confidencialidade mais restritivo, como o Altamente Confidencial, apareça na **parte inferior** da lista, e que seu rótulo de confidencialidade menos restritivo, como o Público, apareça na **parte superior**.

Você pode aplicar apenas um rótulo de confidencialidade a um item, como um documento, email ou container. Se você definir uma opção que exija que os usuários forneçam uma justificativa para alterar um rótulo para uma classificação inferior, a ordem desta lista identificará as classificações inferiores. No entanto, essa opção não se aplica aos sub-rótulos.

Embora a ordem dos sub-rótulos seja usada com [rotulagem automática](apply-sensitivity-label-automatically.md). Ao configurar rótulos para que sejam aplicados automaticamente ou como uma recomendação, várias correspondências podem resultar em mais de um rótulo. A ordem dos rótulos é usada para determinar qual rótulo será aplicado ou recomendado: o último rótulo de confidencialidade é selecionado e, se aplicável, o último sub-rótulo.

![Opção para criar um sub-rótulo](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Sub-rótulos (agrupamento de rótulos)

Com os sub-rótulos, você pode agrupar um ou mais rótulos abaixo de um rótulo pai que o usuário verá em um aplicativo do Office. Por exemplo, em Confidencial, sua organização pode usar várias etiquetas diferentes para tipos específicos dessa classificação. Nesse exemplo, o rótulo pai confidencial é simplesmente um rótulo de texto sem as configurações de proteção, e por ser um subrótulo, não pode ser aplicado ao conteúdo. Em vez disso, os usuários deverão escolher Confidencial para visualizar os sub-rótulos e, em seguida, eles podem escolher um sub-rótulo para aplicar o conteúdo.

Os sub-rótulos são simplesmente uma maneira de apresentar as etiquetas aos usuários em grupos lógicos. Os subrótulos não herdam nenhuma configuração do rótulo pai. Quando você publica um sub-rótulo para um usuário, esse usuário pode aplicá-lo ao conteúdo, mas não pode aplicar apenas o rótulo pai.

Não escolha um rótulo pai como rótulo padrão nem configure-o para ser aplicado automaticamente (ou recomendado). Se o fizer, o rótulo principal não será aplicado ao conteúdo.

Exemplo de como os sub-rótulos são exibidos para os usuários:

![Sub-rótulos agrupados na faixa de opções](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Editar ou excluir um rótulo de confidencialidade

Se você excluir um rótulo de confidencialidade do centro de administração, o rótulo não será removido automaticamente do conteúdo, e todas as configurações de proteção continuarão impostas ao conteúdo que tinha o rótulo aplicado.

Se você editar um rótulo de sensibilidade, a versão do rótulo que foi aplicada ao conteúdo será aplicado nesse conteúdo.

## <a name="what-label-policies-can-do"></a>O que as políticas de rótulo podem fazer

Depois de criar seus rótulos de confidencialidade, você precisa publicá-los para disponibilizá-los às pessoas e serviços em sua organização. Os rótulos de confidencialidade podem ser aplicados a documentos e emails. Diferentemente de rótulos de retenção, que são publicados em locais como todas as caixas de correio do Exchange, os rótulos de confidencialidade são publicados para usuários ou grupos. Os rótulos de confidencialidade serão exibidos nos aplicativos do Office para esses usuários e grupos.

Com uma política de rótulos, você pode:

- **Escolha quais usuários e grupos verão os rótulos.** Os rótulos podem ser publicados para qualquer usuário específico ou grupo de segurança habilitado para email, grupo de distribuição ou grupo do Microsoft 365 (que podem ter [associação dinâmica](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)) no Azure AD.

- **Aplique um rótulo padrão** a todos os novos documentos e emails criados pelos usuários e grupos incluídos na política de rótulo, e o mesmo ou diferente rótulo padrão para contêineres (se você [habilitou rótulos de confidencialidade para Microsoft Teams, grupos Microsoft 365 e sites do Microsoft Office SharePoint Online](sensitivity-labels-teams-groups-sites.md)) Os usuários sempre poderão alterar o rótulo padrão se ele não for o rótulo certo para o documento ou o e-mail. 
    
    Considere usar um rótulo padrão para definir um nível de base de configurações de proteção que você deseja aplicar a todo o seu conteúdo. No entanto, sem o treinamento do usuário e outros controles, essa configuração também pode resultar em rotulagem inexata. Geralmente, não é uma boa ideia selecionar um rótulo que aplica a criptografia como um rótulo padrão para documentos. Por exemplo, muitas organizações precisam enviar e compartilhar emails com usuários externos que podem não ter aplicativos compatíveis com a criptografia ou talvez não usem uma conta que possa ser autorizada. Para obter mais informações sobre esse cenário, consulte [Compartilhar documentos criptografados com usuários externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).

- **Exigir uma justificativa para alterar um rótulo.** Se um usuário tentar remover um rótulo ou substituí-lo por um rótulo com um número de pedido menor, você poderá pedir que o usuário forneça uma justificativa para executar essa ação. Por exemplo, um usuário abre um documento rotulado como confidencial (número de pedido 3) e substitui esse rótulo por um denominado público (número 1). Atualmente, o motivo da justificativa é usado apenas pelo [Cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2), que envia essas informações para a [Análise do Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/reports-aip).

    ![Prompt onde os usuários inserem uma justificativa](../media/Sensitivity-label-justification-required.png)

- **Exigir que os usuários apliquem um rótulo** com uma opção para email e documentos e outra para contêineres. Também conhecido como rotulagem obrigatória, essas opções garantem que um rótulo deve ser aplicado antes que os usuários possam salvar documentos e enviar emails, e criar novos grupos ou sites.
    
    Para documentos e emails, um rótulo pode ser atribuído manualmente pelo usuário, automaticamente como resultado de uma condição que você configurar, ou ser atribuído por padrão (a opção de rótulo padrão descrita acima). Um prompt de exemplo exibido no Outlook quando um usuário é solicitado a atribuir um rótulo:

    ![Prompt no Outlook pedindo ao usuário para aplicar o rótulo necessário](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > Atualmente, a rotulagem obrigatória exige o [cliente de rotulagem unificada da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app). O cliente só é executado no Windows, portanto esse recurso ainda não é compatível com Mac, iOS e Android.
    
    Para contêineres, um rótulo deve ser atribuído no momento em que o grupo ou local é criado.
    
    Considere usar essa opção para ajudar a aumentar a cobertura de rótulos. No entanto, sem treinamento do usuário, essas configurações podem resultar em rotulagem imprecisa. Além disso, a menos que você também defina um rótulo padrão correspondente, o rótulo obrigatório pode frustrar seus usuários com as solicitações frequentes. 

- **Fornecer um link de ajuda para uma página de ajuda personalizada** Se os usuários não tiverem certeza do significado dos rótulos de sensibilidade ou de como devem ser usados, você pode fornecer um URL Saiba mais que aparece na parte inferior do menu do **Rótulo de sensibilidade** nos aplicativos do Office:

    ![Link do Saiba mais no botão Confidencialidade na faixa de opções](../media/Sensitivity-label-learn-more.png)

Após ser criada uma política de rótulo que atribui novos rótulos de confidencialidade a usuários e grupos, esses rótulos estarão visíveis para os usuários em seus aplicativos do Office dentro de 30 minutos. No entanto, é preciso aguardar até 24 horas para as alterações desses rótulos.

Não há limite para o número de rótulos de confidencialidade que você pode criar e publicar, com uma exceção: se o rótulo aplicar criptografia, o máximo que pode ser criado é de 500 rótulos. No entanto, como prática recomendada para diminuir as despesas gerais do administrador e reduzir a complexidade para seus usuários, tente manter o número mínimo de rótulos. As implantações no mundo real provaram que a eficácia é visivelmente reduzida quando os usuários têm mais de cinco rótulos principais ou mais de cinco sub-rótulos por rótulo principal.

### <a name="label-policy-priority-order-matters"></a>Prioridade das políticas de rótulos (a ordem é importante)

Você disponibiliza seus rótulos de confidencialidade aos usuários ao publicá-los em uma política de rótulos de confidencialidade, que aparece em uma lista na guia **Políticas de confidencialidade** na página **Políticas de rótulos**. Assim como rótulos de confidencialidade (veja[Prioridade de rótulo (importância da ordem)](#label-priority-order-matters)), a ordem das políticas de rótulos de confidencialidade é importante porque reflete sua prioridade. A política de rótulo com prioridade mais baixa aparece na **parte superior** e a política de rótulo com a prioridade mais alta aparece na **parte inferior**.

Uma política de rótulo consiste em:

- Um conjunto de rótulos.
- O escopo da política de rótulos, que são os usuários e grupos incluídos na política.
- As configurações da política de rótulo descritas acima (rótulo padrão, justificativa, rótulo obrigatório e link de ajuda).

Você pode incluir um usuário em várias políticas de rótulos e esse usuário verá todas os rótulos de confidencialidade dessas políticas. Entretanto, um usuário só obtém as configurações de política da política de rótulo com a prioridade mais alta.

Se não estiver vendo a configuração da política de rótulos ou do rótulo esperada para um usuário ou grupo e já tiver aguardado 30 minutos, verifique a ordem das políticas de rótulos de confidencialidade. Para reordenar as políticas de rótulo, selecione uma política de rótulo de sensibilidade > escolha as reticências à direita > **Mover para baixo** ou **Mover para cima**.

![Opções de movimentação na página de políticas de rótulos de confidencialidade](../media/sensitivity-label-policy-priority.png)

Se você usa rótulos de confidencialidade e rótulos de retenção, é importante lembrar que a prioridade é importante em políticas de rótulo de confidencialidade, mas não em [rótulo de retenção](retention.md#the-principles-of-retention-or-what-takes-precedence).

## <a name="sensitivity-labels-and-azure-information-protection"></a>Rótulos de confidencialidade e Proteção de Informações do Azure

Se você tiver implantado rótulos com a Proteção de Informações do Azure, use as seções a seguir para obter diretrizes antes de começar a usar o rótulos de confidencialidade.

### <a name="azure-information-protection-labels"></a>Rótulos da Proteção de Informações do Azure

> [!NOTE]
> O gerenciamento de rótulos para os rótulos da Proteção de Informações do Azure no portal do Azure será substituído em **31 de março de 2021**. Saiba mais no [aviso de substituição](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179) oficial.

Se você estiver usando os rótulos da Proteção de Informações do Azure porque o locatário ainda não está na [plataforma de rotulagem unificada](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform), recomendamos que você evite criar novos rótulos de confidencialidade até ativar a rotulagem unificada. Neste cenário, os rótulos que você vê no portal do Azure são rótulos da Proteção de Informações do Azure, em vez de rótulos de confidencialidade. Esses rótulos podem ser usados pelo cliente da Proteção de Informações do Azure (clássico) em computadores com Windows, mas não podem ser usados por dispositivos que executam o macOS, iOS ou Android. Para resolver esse problema, [migre esses rótulos](/azure/information-protection/configure-policy-migrate-labels) para rótulos de confidencialidade. 

Os metadados aplicados por ambos os conjuntos de rótulos são compatíveis, então não é necessário rotular novamente os documentos e os emails quando a migração estiver concluída.

### <a name="azure-information-protection-clients"></a>Clientes da Proteção de Informações do Azure

Ao usar rótulos de confidencialidade nos Aplicativos do Microsoft 365 para empresas em computadores Windows, você pode optar por usar um cliente da Proteção de Informações do Azure ou usar rótulos internos do Office.

Por padrão, a rotulagem interna é desativada nesses aplicativos quando o cliente da Proteção de Informações do Azure é instalado. Para obter mais informações, incluindo como alterar esse comportamento padrão, confira [Cliente da rotulagem interna do Office e cliente da Proteção de Informações do Azure](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client).

Mesmo quando você usa rótulos internos nos aplicativos do Office, também poderá usar o cliente de rotulagem unificada da Proteção de Informações do Azure com rótulos de confidencialidade nos seguintes casos:

- Um scanner para descobrir informações confidenciais armazenadas no local e, opcionalmente, rotular o conteúdo

- Opções de clique com o botão direito do mouse no Explorador de Arquivos para que os usuários apliquem rótulos a todos os tipos de arquivo

- Um visualizador para exibir arquivos criptografados para textos, imagens ou documentos PDF

- Um módulo do PowerShell para descobrir informações confidenciais em arquivos no local, e aplicar ou remover rótulos e criptografia desses arquivos.

Se você é novo na Proteção de Informações do Azure ou se já é um cliente da Proteção de Informações do Azure que acabou de migrar seus rótulos, consulte [Escolher qual cliente de rotulagem usar para computadores Windows na documentação da Proteção de Informações do Azure](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers).

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a>Rótulos de confidencialidade e Microsoft Cloud App Security

Usando o CAS (Cloud App Security), é possível descobrir, classificar, rotular e proteger o conteúdo em serviços e aplicativos de terceiros, como SalesForce, Box ou Dropbox. 

O Cloud App Security funciona com os rótulos de confidencialidade e rótulos da Proteção de Informações do Azure:

- Se o centro de administração de etiquetas tiver um ou mais rótulos de confidencialidade [publicados](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) por pelo menos um usuário, os rótulos de confidencialidade serão usados.

- Se os centros de administração de etiquetagem não tiverem rótulos de confidencialidade publicados, os rótulos de proteção de informações do Azure serão usados.

Para obter instruções sobre como usar o Cloud App Security com esses rótulos, confira [Integração da proteção de informações do Azure](https://docs.microsoft.com/cloud-app-security/azip-integration).

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>Rótulos de confidencialidade e SDK da Proteção de informações da Microsoft

Como um rótulo de confidencialidade é armazenado como texto não criptografado nos metadados de um documento, aplicativos e serviços de terceiros podem ler e gravar nos metadados de rotulagem para complementar sua implantação de rotulagem. Além disso, os desenvolvedores de software podem usar o [SDK da Proteção de Informações da Microsoft](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk) para oferecer suporte total aos recursos de rotulagem e criptografia em várias plataformas. Para saber mais, confira o [Comunicado de Disponibilidade Geral no Blog da Comunidade Técnica](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). 

Você também pode saber mais sobre [soluções de parceiro que estão integradas à Proteção de Informações da Microsoft](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="deployment-guidance"></a>Guia de implantação

Para planejamento de implantação e orientação que inclui informações de licenciamento, permissões, estratégia de implantação e uma lista de recursos para cenários suportados e documentação do usuário final, consulte [Primeiros passos com rótulos de confidencialidade](get-started-with-sensitivity-labels.md).

