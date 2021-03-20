---
title: Saiba mais sobre a chave disponibilidade da Chave de Cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Saiba mais sobre a chave de disponibilidade usada para recuperar chaves de cliente perdidas.
ms.openlocfilehash: bbad6ace0880c142a497bcac3469c579f13c7881
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907735"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Saiba mais sobre a chave disponibilidade da Chave de Cliente

A chave de disponibilidade é uma chave raiz gerada e provisionada automaticamente quando você cria uma política de criptografia de dados. O Microsoft 365 armazena e protege a chave de disponibilidade. A chave de disponibilidade é funcionalmente como as duas chaves raiz que você fornece para criptografia de serviço com a Chave do Cliente. A chave de disponibilidade quebra as teclas uma camada inferior na hierarquia de chaves. Ao contrário das chaves fornecidas e gerenciadas no Azure Key Vault, você não pode acessar diretamente a chave de disponibilidade. Os serviços automatizados do Microsoft 365 gerenciam a chave de disponibilidade programaticamente. Esses serviços iniciam operações automatizadas que nunca envolvem acesso direto à chave de disponibilidade.

O principal objetivo da chave de disponibilidade é fornecer capacidade de recuperação da perda não antecipada de chaves raiz que você gerencia. A perda pode ser um resultado de má gestão ou ação mal-intencionada. Se você perder o controle de suas chaves raiz, entre em contato com o Suporte da Microsoft e a Microsoft o ajudará no processo de recuperação usando a chave de disponibilidade. Você usará a chave de disponibilidade para migrar para uma nova Política de Criptografia de Dados com novas chaves raiz que você provisionar.

O armazenamento e o controle da chave de disponibilidade são deliberadamente diferentes das chaves do Azure Key Vault por três motivos:

- A chave de disponibilidade fornece uma recuperação, recurso de "quebra de vidro" se o controle sobre ambas as chaves do Azure Key Vault for perdido.
- A separação de controles lógicos e locais de armazenamento seguro fornece defesa detalhada e protege contra a perda de todas as chaves e seus dados de um único ataque ou ponto de falha.
- A chave de disponibilidade fornece um recurso de alta disponibilidade se os serviços do Microsoft 365 não puderem alcançar chaves hospedadas no Azure Key Vault devido a erros transitórios. Essa regra só se aplica à criptografia de serviço do Exchange Online e do Skype for Business. Os arquivos do SharePoint Online, do OneDrive for Business e do Teams nunca usam a chave de disponibilidade, a menos que você instrua explicitamente a Microsoft a iniciar o processo de recuperação.

Compartilhar a responsabilidade de proteger seus dados, usando uma variedade de proteções e processos para gerenciamento de chaves, em última análise reduz o risco de todas as chaves (e, portanto, seus dados) serem permanentemente perdidas ou destruídas. A Microsoft fornece autoridade exclusiva sobre a desabilitação ou destruição da chave de disponibilidade ao sair do serviço. Por design, ninguém na Microsoft tem acesso à chave de disponibilidade: ela só é acessível pelo código de serviço do Microsoft 365.

Consulte a [Central de Confiações da Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obter mais informações sobre como proteger chaves.
  
## <a name="availability-key-uses"></a>A chave de disponibilidade usa

A chave de disponibilidade fornece capacidade de recuperação para cenários em que um mal-intencionado ou mal-intencionado insider externo rouba o controle do seu cofre de chaves ou quando a má gestão inadvertida resulta em perda de chaves raiz. Esse recurso de recuperação se aplica a todos os serviços do Microsoft 365 compatíveis com a Chave do Cliente. Os serviços individuais usam a chave de disponibilidade de forma diferente. O Microsoft 365 usa apenas a chave de disponibilidade nas maneiras descritas abaixo.

### <a name="exchange-online-and-skype-for-business-uses"></a>Usos do Exchange Online e do Skype for Business

Além do recurso de recuperação, o Exchange Online e o Skype for Business usam a chave de disponibilidade para garantir a disponibilidade de dados durante problemas operacionais transitórios ou intermitentes, relacionados ao serviço que acessa chaves raiz. Quando o serviço não consegue alcançar nenhuma das chaves do cliente no Azure Key Vault devido a erros transitórios, o serviço usa automaticamente a chave de disponibilidade. O serviço NUNCA vai diretamente para a chave de disponibilidade.

Sistemas automatizados no Exchange Online e no Skype for Business podem usar a chave de disponibilidade durante erros transitórios para dar suporte a serviços de back-end automatizados, como antivírus, descoberta automática, prevenção contra perda de dados, movimentações de caixa de correio e indexação de dados.

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>Os arquivos do SharePoint Online, do OneDrive for Business e do Teams usam

Para arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade NUNCA é usada fora do recurso de recuperação e os clientes devem instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação. As operações de serviço automatizadas dependem exclusivamente das chaves do cliente no cofre de chaves do Azure. Para obter informações detalhadas sobre como a hierarquia de chaves funciona para esses serviços, consulte Como os arquivos do [SharePoint Online, do OneDrive for Business](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)e do Teams usam a chave de disponibilidade.

## <a name="availability-key-security"></a>Segurança da chave de disponibilidade

A Microsoft compartilha a responsabilidade da proteção de dados com você, instando a chave de disponibilidade e tomando medidas abrangentes para protegê-la. A Microsoft não expõe o controle direto da chave de disponibilidade aos clientes. Por exemplo, você só pode rolar (girar) as chaves que possui no Azure Key Vault. Para obter mais informações, [consulte Roll or rotate a customer key or an availability key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Armazenamentos secretos de chave de disponibilidade

A Microsoft protege as chaves de disponibilidade em armazenamentos secretos internos controlados pelo acesso, como o Azure Key Vault voltado para o cliente. Implementamos controles de acesso para impedir que os administradores da Microsoft acessem diretamente os segredos contidos. Operações do Armazenamento Secreto, incluindo rotação de teclas e exclusão, ocorrem por meio de comandos automatizados que nunca envolvem acesso direto à chave de disponibilidade. As operações de gerenciamento de armazenamento secreto são limitadas a engenheiros específicos e exigem escalonamento de privilégios por meio de uma ferramenta interna, Lockbox. O escalonamento de privilégios exige aprovação e justificativa do gerente antes de ser concedido. O lockbox garante que o acesso está vinculado ao tempo limite com revogação de acesso automático após a expiração de tempo ou o logon do engenheiro.

**As chaves de disponibilidade do Exchange Online e do Skype for Business** são armazenadas em um armazenamento secreto do Exchange Online Active Directory. As chaves de disponibilidade são armazenadas com segurança dentro de contêineres específicos do locatário no Controlador de Domínio do Active Directory. Esse local de armazenamento seguro é separado e isolado do armazenamento secreto de arquivos do SharePoint Online, do OneDrive for Business e do Teams.

As chaves de disponibilidade de arquivos do **SharePoint Online, do OneDrive for Business** e do Teams são armazenadas em um armazenamento secreto interno gerenciado pela equipe de serviço. Esse serviço de armazenamento seguro e secreto tem servidores front-end com pontos de extremidade de aplicativo e um banco de dados SQL como back-end. As chaves de disponibilidade são armazenadas no banco de dados do SQL e são empacotadas (criptografadas) por chaves de criptografia de armazenamento secreto que usam uma combinação do AES-256 e do HMAC para criptografar a chave de disponibilidade em repouso. As chaves de criptografia do armazenamento secreto são armazenadas em um componente logicamente isolado do mesmo banco de dados SQL e são ainda mais criptografadas com chaves RSA-2048 contidas em certificados gerenciados pela Autoridade de Certificação da Microsoft (CA). Esses certificados são armazenados nos servidores front-end do armazenamento secreto que executam operações no banco de dados.

### <a name="defense-in-depth"></a>Defesa em profundidade

A Microsoft emprega uma estratégia de defesa aprofundada para impedir que os atores mal-intencionados impactem a confidencialidade, a integridade ou a disponibilidade dos dados do cliente armazenados no Microsoft Cloud. Controles preventivos e detetives específicos são implementados para proteger o armazenamento secreto e a chave de disponibilidade como parte da estratégia de segurança abrangente.

O Microsoft 365 foi criado para evitar o uso indevido da chave de disponibilidade. A camada de aplicativo é o único método pelo qual as chaves, incluindo a chave de disponibilidade, podem ser usadas para criptografar e descriptografar dados. Somente o código de serviço do Microsoft 365 tem a capacidade de interpretar e percorrer a hierarquia de chaves para atividades de criptografia e descriptografia. Existe isolamento lógico entre os locais de armazenamento de Chaves do Cliente, chaves de disponibilidade, outras chaves hierárquicas e dados do cliente. Esse isolamento reduz o risco de exposição de dados caso um ou mais locais sejam comprometidos. Cada camada na hierarquia tem recursos de detecção de intrusão 24x7 para proteger dados e segredos armazenados.

Os controles de acesso são implementados para impedir o acesso não autorizado a sistemas internos, incluindo os armazenamentos secretos de chave de disponibilidade. Os engenheiros da Microsoft não têm acesso direto aos principais armazenamentos secretos de disponibilidade. Para obter detalhes adicionais sobre controles de acesso, consulte [Administrative Access Controls in Microsoft 365](/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Os controles técnicos impedem que a equipe da Microsoft entre em contas de serviço altamente privilegiadas, que podem ser usadas por invasores para representar os serviços da Microsoft. Por exemplo, esses controles impedem o logon interativo.

Os controles de registro em log e monitoramento de segurança são outra proteção de defesa em profundidade implementada que reduz o risco para os serviços da Microsoft e seus dados. As equipes de serviço da Microsoft implantaram soluções de monitoramento ativas que geram alertas e logs de auditoria. Todas as equipes de serviço carregam seus logs em um repositório central onde os logs são agregados e processados. As ferramentas internas examinam automaticamente os registros para confirmar que os serviços estão funcionando em um estado ideal, resiliente e seguro. Atividade incomum é sinalizada para revisão posterior.

Qualquer evento de log que indique uma possível violação da Política de Segurança da Microsoft é imediatamente levado à atenção das equipes de segurança da Microsoft. A segurança do Microsoft 365 configurou alertas para detectar tentativas de acesso a armazenamentos secretos de chave de disponibilidade. Os alertas também serão gerados se a equipe da Microsoft tentar fazer logon interativo para contas de serviço, o que é proibido e protegido pelos controles de acesso. A segurança do Microsoft 365 também detecta e alerta sobre desvios do serviço do Microsoft 365 das operações de linha de base normais. Malfeitores que tentam usar indevidamente os serviços do Microsoft 365 disparariam alertas que resultam no despejo do ofensor do ambiente de nuvem da Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Usar a chave de disponibilidade para se recuperar da perda de chave

Se você perder o controle das Chaves do Cliente, a chave de disponibilidade lhe oferece a capacidade de recuperar e criptografar seus dados.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimento de recuperação para Exchange Online e Skype for Business

Se você perder o controle de suas Chaves do Cliente, a chave de disponibilidade lhe dará a capacidade de recuperar seus dados e colocar seus recursos do Microsoft 365 afetados novamente online. A chave de disponibilidade continua a proteger seus dados enquanto você se recupera. Em um nível alto, para se recuperar totalmente da perda de chaves, você precisará criar um novo DEP e mover os recursos afetados para a nova política.

Para criptografar seus dados com novas Chaves do Cliente, crie novas chaves no Azure Key Vault, crie um novo DEP usando as novas Chaves do Cliente e atribua o novo DEP às caixas de correio atualmente criptografadas com o DEP anterior para o qual as chaves foram perdidas ou comprometidas.

Esse processo de recriptação pode levar até 72 horas. Essa é a duração padrão quando você altera um DEP.
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Procedimento de recuperação para arquivos do SharePoint Online, OneDrive for Business e Teams

Para arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade NUNCA é usada fora do recurso de recuperação. Você deve instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação. Para iniciar o processo de recuperação, contate a Microsoft para ativar a chave de disponibilidade. Depois de ativada, a chave de disponibilidade é usada automaticamente para descriptografar seus dados, permitindo que você criptografe os dados com um DEP recém-criado associado às novas Chaves do Cliente.  

Essa operação é proporcional ao número de sites em sua organização. Depois de chamar a Microsoft para usar a chave de disponibilidade, você deve estar totalmente online em cerca de quatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Como o Exchange Online e o Skype for Business usam a chave de disponibilidade

Quando você cria um DEP com a Chave do Cliente, o Microsoft 365 gera uma Chave de Política de Criptografia de Dados (CHAVE DEP) associada a essa DEP. O serviço criptografa a Chave DEP três vezes: uma com cada uma das chaves do cliente e uma vez com a chave de disponibilidade. Somente as versões criptografadas da Chave DEP são armazenadas e uma Chave DEP só pode ser descriptografada com as chaves do cliente ou a chave de disponibilidade. A chave DEP é usada para criptografar Chaves de Caixa de Correio, que criptografam caixas de correio individuais.
  
O Microsoft 365 segue esse processo para descriptografar e fornecer dados quando os clientes estão usando o serviço:
  
1. Descriptografar a Chave DEP usando a Chave do Cliente.

2. Use a chave DEP descriptografada para descriptografar uma Chave de Caixa de Correio.

3. Use a Chave de Caixa de Correio descriptografada para descriptografar a própria caixa de correio, permitindo que você acesse os dados dentro da caixa de correio.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Como os arquivos do SharePoint Online, do OneDrive for Business e do Teams usam a chave de disponibilidade

A arquitetura e a implementação do SharePoint Online e do OneDrive for Business para Chave do Cliente e a chave de disponibilidade são diferentes do Exchange Online e do Skype for Business.
  
Quando uma organização se move para chaves gerenciadas pelo cliente, o Microsoft 365 cria uma chave intermediária (TIK) específica da organização. O Microsoft 365 criptografa o TIK duas vezes, uma vez com cada uma das chaves do cliente, e armazena as duas versões criptografadas do TIK. Somente as versões criptografadas do TIK são armazenadas e um TIK só pode ser descriptografado com as chaves do cliente. O TIK é usado para criptografar chaves de site, que são usadas para criptografar chaves de blob (também chamadas de chaves de bloco de arquivo). Dependendo do tamanho do arquivo, o serviço pode dividir um arquivo em várias partes de arquivo cada uma com uma chave exclusiva. Os blobs (partes de arquivo) são criptografados com as chaves de blob e armazenados no serviço de armazenamento do Microsoft Azure Blob.
  
O Microsoft 365 segue esse processo para descriptografar e fornecer arquivos do cliente quando os clientes estão usando o serviço:

1. Descriptografar o TIK usando a Chave do Cliente.

2. Use o TIK descriptografado para descriptografar uma chave de site.

3. Use a chave de site descriptografada para descriptografar uma chave de blob.

4. Use a chave de blob descriptografada para descriptografar o blob.

O Microsoft 365 descriptografa um TIK em emissão de duas solicitações de descriptografia para o Azure Key Vault com um pequeno deslocamento. O primeiro a concluir fornece o resultado, cancelando a outra solicitação.
  
Caso você perca o acesso às chaves do cliente, o Microsoft 365 também criptografa o TIK com uma chave de disponibilidade e armazena isso junto com os TIKs criptografados com cada chave do cliente. O TIK criptografado com a chave de disponibilidade é usado somente quando o cliente chama a Microsoft para se inscrever no caminho de recuperação quando perder o acesso às chaves, de forma mal-intencionada ou acidental.
  
Por motivos de disponibilidade e escala, OS TIKs descriptografados são armazenados em cache em cache de memória limitado por tempo. Duas horas antes de um cache TIK ser definido para expirar, o Microsoft 365 tenta descriptografar cada TIK. Descriptografar os TIKs estende o tempo de vida do cache. Se a descriptografia TIK falhar por um período de tempo significativo, o Microsoft 365 gerará um alerta para notificar a engenharia antes da expiração do cache. Somente se o cliente chamar a Microsoft iniciará a operação de recuperação do Microsoft 365, que envolve descriptografar o TIK com a chave de disponibilidade armazenada no armazenamento secreto da Microsoft e integrando o locatário novamente usando o TIK descriptografado e um novo conjunto de chaves do Azure Key Vault fornecida pelo cliente.
  
A partir de hoje, a Chave do Cliente está envolvida na cadeia de criptografia e descriptografia dos dados de arquivo do SharePoint Online armazenados no armazenamento de blob do Azure, mas não itens de lista do SharePoint Online ou metadados armazenados no banco de dados SQL. O Microsoft 365 não usa a chave de disponibilidade para arquivos do Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams que não seja o caso descrito acima, que é iniciado pelo cliente. O acesso humano aos dados do cliente é protegido pelo Customer Lockbox.

## <a name="availability-key-triggers"></a>Gatilhos de chave de disponibilidade

O Microsoft 365 aciona a chave de disponibilidade somente em circunstâncias específicas. Essas circunstâncias diferem pelo serviço.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Gatilhos para Exchange Online e Skype for Business
  
1. O Microsoft 365 lê o DEP ao qual a caixa de correio é atribuída para determinar o local das duas Chaves do Cliente no Azure Key Vault.

2. O Microsoft 365 escolhe aleatoriamente uma das duas Chaves de Cliente do DEP e envia uma solicitação ao Azure Key Vault para desembrulhar a chave DEP usando a Chave do Cliente.

3. Se a solicitação para desembrulhar a chave DEP usando a Chave do Cliente falhar, o Microsoft 365 enviará uma segunda solicitação para o Azure Key Vault, desta vez instruindo-a a usar a Chave de Cliente alternativa (segunda).

4. Se a segunda solicitação para desembrulhar a chave DEP usando a Chave do Cliente falhar, o Microsoft 365 examinará os resultados de ambas as solicitações.

    - Se o exame determinar que as solicitações falharam ao retornar um ERRO do sistema:

       - O Microsoft 365 dispara a chave de disponibilidade para descriptografar a chave DEP.

       - O Microsoft 365 usa a chave DEP para descriptografar a chave de caixa de correio e concluir a solicitação do usuário. 

       - Nesse caso, o Azure Key Vault não consegue responder ou inacessível devido a um ERRO transitório.

    - Se o exame determinar que as solicitações falharam ao retornar o ACCESS NEGADO:

       - Isso significa que foi tomada uma ação deliberada, inadvertida ou mal-intencionada para tornar as chaves do cliente indisponíveis (por exemplo, durante o processo de limpeza de dados como parte da saída do serviço).

       - Nesse caso, a chave de disponibilidade será usada apenas para ações do sistema e não para ações do usuário, a solicitação do usuário falha e o usuário recebe uma mensagem de erro.

>[!IMPORTANT]
>O código de serviço do Microsoft 365 sempre tem um token de logon válido para raciocínio sobre os dados do cliente para fornecer serviços de nuvem de adição de valor. Portanto, até que a chave de disponibilidade seja excluída, ela pode ser usada como um fallback para ações iniciadas ou internas para o Exchange Online e o Skype for Business, como criação de índice de pesquisa ou movimentação de caixas de correio. Isso se aplica a solicitações DE ERROS transitórios e ACESSO NEGADO ao Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Gatilhos para arquivos do SharePoint Online, OneDrive for Business e Teams

Para arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade NUNCA é usada fora do recurso de recuperação e os clientes devem instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação.

## <a name="audit-logs-and-the-availability-key"></a>Logs de auditoria e a chave de disponibilidade

Sistemas automatizados no Microsoft 365 processam todos os dados à medida que ele flui pelo sistema para fornecer serviços de nuvem, por exemplo, antivírus, descoberta automática, prevenção contra perda de dados e indexação de dados. O Microsoft 365 não gera logs visíveis para o cliente para essa atividade. Além disso, a equipe da Microsoft não acessa seus dados como parte dessas operações normais do sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Log de chave de disponibilidade do Exchange Online e do Skype for Business

Quando o Exchange Online e o Skype for Business acessam a chave de disponibilidade para fornecer o serviço, o Microsoft 365 publica logs visíveis para o cliente acessíveis do Centro de Segurança e Conformidade. Um registro de log de auditoria para a operação da chave de disponibilidade é gerado sempre que o serviço usa a chave de disponibilidade. Um novo tipo de registro chamado "Criptografia de Serviço de Chave de Cliente" [](./search-the-audit-log-in-security-and-compliance.md) com o tipo de atividade "Fallback to Availability Key" permite que os administradores filtrem os resultados da pesquisa do Log de Auditoria Unificada para exibir os registros de chave de disponibilidade.

Os registros de log incluem atributos como data, hora, atividade, ID da organização e ID da política de criptografia de dados. O registro está disponível como parte dos Logs de Auditoria Unificada e pode ser acessado na guia Pesquisa de Log de Auditoria do Centro de Conformidade & Segurança.

![Pesquisa de log de auditoria para eventos de chave de disponibilidade](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Os registros de chave de disponibilidade do Exchange Online e do Skype for Business usam o [esquema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) comum atividade de gerenciamento do Office 365 com parâmetros personalizados adicionados: ID da política, ID da versão da chave de escopo e Id de solicitação.

![Parâmetros personalizados da chave de disponibilidade](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Log de chave de disponibilidade de arquivos do SharePoint Online, OneDrive for Business e Teams

O log da chave de disponibilidade ainda não está disponível para esses serviços. Para arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade só é ativada pela Microsoft, quando instruído por você, para fins de recuperação. Como resultado, você já sabe todos os eventos em que a chave de disponibilidade é usada para esses serviços.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Chave de disponibilidade na hierarquia da Chave do Cliente
  
O Microsoft 365 usa a chave de disponibilidade para quebrar a camada de chaves mais baixa na hierarquia de chaves estabelecida para a criptografia de serviço chave do cliente. Hierarquias de chaves diferentes existem entre os serviços. Os algoritmos chave também diferem entre chaves de disponibilidade e outras chaves na hierarquia de cada serviço aplicável. Os algoritmos chave de disponibilidade usados pelos diferentes serviços são os seguinte:

- As chaves de disponibilidade do Exchange Online e do Skype for Business usam o AES-256.

- As chaves de disponibilidade do SharePoint Online, do OneDrive for Business e do Teams usam o RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o Exchange Online e o Skype for Business

![Codificações de criptografia para Chave de Cliente do Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o SharePoint Online e o OneDrive for Business

![Codificações de criptografia para Chave de Cliente do SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Configurar a Chave do Cliente](customer-key-set-up.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)