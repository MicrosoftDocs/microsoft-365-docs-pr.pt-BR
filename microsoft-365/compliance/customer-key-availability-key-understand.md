---
title: Saiba mais sobre a chave de disponibilidade da chave de cliente do Office 365
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
description: Saiba mais sobre a chave de disponibilidade usada para recuperar as chaves de cliente perdidas do Office 365.
ms.openlocfilehash: cb5284f46245db1d00506ab0e178244aac53a21f
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604168"
---
# <a name="learn-about-the-availability-key-for-office-365-customer-key"></a>Saiba mais sobre a chave de disponibilidade da chave de cliente do Office 365

A chave de disponibilidade é uma chave raiz gerada automaticamente e provisionada quando você cria uma política de criptografia de dados. O Office 365 armazena e protege a chave de disponibilidade. A chave de disponibilidade é funcionalmente parecida com as duas chaves raiz que você fornece para a criptografia de serviço com a chave do cliente. A chave de disponibilidade quebra as chaves uma camada abaixo na hierarquia de chaves. Diferentemente das chaves que você fornece e gerencia no Azure Key Vault, não é possível acessar diretamente a chave de disponibilidade. Os serviços automatizados do Office 365 gerenciam a chave de disponibilidade de maneira programática. Esses serviços iniciam operações automatizadas que nunca envolvem acesso direto à chave de disponibilidade.

O objetivo principal da chave de disponibilidade é fornecer capacidade de recuperação da perda não antecipada de chaves raiz que você gerencia. A perda pode ser um resultado de mal gerenciamento ou ação mal-intencionada. Se você perder o controle das chaves raiz, entre em contato com o suporte da Microsoft e a Microsoft ajudará você durante o processo de recuperação usando a chave de disponibilidade. Você usará a chave de disponibilidade para migrar para uma nova política de criptografia de dados com novas chaves raiz que provisionar.

O armazenamento e o controle da chave de disponibilidade são deliberadamente diferentes das chaves do Azure Key Vault por três motivos:

- A chave de disponibilidade fornece uma capacidade de recuperação, "quebra-vidro", se o controle das chaves do Azure Key Vault for perdido.
- A separação de controles lógicos e locais de armazenamento seguro oferece proteção em camadas e protege contra a perda de todas as chaves e seus dados, de um único ataque ou ponto de falha.
- A chave de disponibilidade fornece um recurso de alta disponibilidade se os serviços do Office 365 não conseguem acessar chaves hospedadas no Azure Key Vault devido a erros transitórios. Esta regra só se aplica à criptografia de serviço do Exchange Online e do Skype for Business. Os arquivos do SharePoint Online, do OneDrive for Business e do teams nunca usam a chave de disponibilidade, a menos que você instrua o Microsoft a iniciar o processo de recuperação.

Compartilhar a responsabilidade de proteger seus dados, usando uma variedade de proteções e processos para o gerenciamento de chaves, reduz o risco que todas as chaves (e, portanto, seus dados) serão permanentemente perdidas ou destruídas. A Microsoft fornecerá autoridade única sobre a desativação ou destruição da chave de disponibilidade quando você deixar o serviço. Por design, ninguém da Microsoft tem acesso à chave de disponibilidade: ele só é acessível pelo código de serviço do Office 365.

Consulte a [central de confiabilidade da Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) para obter mais informações sobre como proteger as chaves.
  
## <a name="availability-key-uses"></a>Chave de disponibilidade usa

A chave de disponibilidade fornece capacidade de recuperação para cenários nos quais um inmalefactor externo ou inadvertidamente rouba o controle de seu cofre de chave, ou quando o gerenciamento inadequado inadvertido resulta em perda de chaves raiz. Esse recurso de recuperação se aplica a todos os serviços do Office 365 compatíveis com a chave do cliente. Os serviços individuais usam a chave de disponibilidade de forma diferente. O Office 365 só usa a chave de disponibilidade das maneiras descritas abaixo.

### <a name="exchange-online-and-skype-for-business-uses"></a>O Exchange Online e o Skype for Business usam

Além do recurso de recuperação, o Exchange Online e o Skype for Business usam a chave de disponibilidade para garantir a disponibilidade de dados durante problemas temporários ou intermitentes, relacionados ao serviço de acesso a chaves raiz. Quando o serviço não consegue acessar uma das chaves do cliente no Azure Key Vault devido a erros transitórios, o serviço usa automaticamente a chave de disponibilidade. O serviço nunca vai diretamente para a chave de disponibilidade.

Sistemas automatizados no Exchange Online e no Skype for Business podem usar a chave de disponibilidade durante erros transitórios para dar suporte a serviços de back-end automatizados, como antivírus, e-Discovery, prevenção de perda de dados, movimentações de caixa de correio e indexação de dados.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>Os arquivos do SharePoint Online, do OneDrive for Business e do teams usam

Para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade nunca é usada fora do recurso de recuperação, e os clientes devem instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação. As operações de serviço automatizadas dependem exclusivamente das chaves do cliente no Azure Key Vault. Para obter informações detalhadas sobre como a hierarquia de chaves funciona para esses serviços, consulte [How SharePoint Online, onedrive for Business e Teams files use the Availability Key](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Segurança da chave de disponibilidade

A Microsoft compartilha a responsabilidade da proteção de dados com você instanciar a chave de disponibilidade e realizar medidas abrangentes para protegê-la. A Microsoft não expõe o controle direto da chave de disponibilidade para os clientes. Por exemplo, você só pode rolar (girar) as chaves que você possui no Azure Key Vault. Para obter mais informações, consulte [rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Repositórios de segredo de chave de disponibilidade

A Microsoft protege as chaves de disponibilidade em repositórios de segredo internos, controlados pelo Access, como o Azure Key Vault voltado para o cliente. Implementamos os controles de acesso para evitar que os administradores da Microsoft acessem diretamente os segredos contidos em. As operações de repositório secreto, incluindo rotação e exclusão de chaves, ocorrem por meio de comandos automatizados que nunca envolvem acesso direto à chave de disponibilidade. As operações de gerenciamento de repositório secreto são limitadas a engenheiros específicos e exigem escalonamento de privilégios por meio de uma ferramenta interna, lockbox. A elevação de privilégio requer a aprovação do gerente e a justificativa antes de ser concedida. O Lockbox garante que o acesso seja vinculado à revogação do acesso automático após o tempo limite de expiração ou engenharia.

As chaves de disponibilidade **do Exchange Online e do Skype for Business** são armazenadas em um repositório de segredo do Active Directory do Exchange Online. As chaves de disponibilidade são armazenadas com segurança dentro de contêineres específicos do locatário dentro do controlador de domínio do Active Directory. Esse local de armazenamento seguro é separado e isolado do repositório secreto de arquivos do SharePoint Online, do OneDrive for Business e do teams.

As chaves de disponibilidade de **arquivos do SharePoint Online, do onedrive for Business e do teams** são armazenadas em um repositório de segredo interno gerenciado pela equipe de serviço. Esse serviço de armazenamento de segredos seguro tem servidores front-end com pontos de extremidade de aplicativo e um banco de dados SQL como back-end. As chaves de disponibilidade são armazenadas no banco de dados SQL e são quebradas (criptografadas) por chaves de criptografia de repositório secreto que usam uma combinação de AES-256 e HMAC para criptografar a chave de disponibilidade em repouso. As chaves de criptografia de repositório secreto são armazenadas em um componente isolado de forma lógica do mesmo banco de dados SQL e são criptografadas com as chaves RSA-2048 contidas em certificados gerenciados pela autoridade de certificação (CA) da Microsoft. Esses certificados são armazenados nos servidores front-end de repositório secreto que executam operações no banco de dados.

### <a name="defense-in-depth"></a>Proteção em camadas

A Microsoft emprega uma estratégia de proteção em camadas para impedir que os atores mal-intencionados afetem a confidencialidade, integridade ou disponibilidade dos dados do cliente armazenados na nuvem da Microsoft. Os controles preventivos e de detecção específicos são implementados para proteger o repositório secreto e a chave de disponibilidade como parte da estratégia de segurança abrangente.

O Office 365 foi criado para evitar o uso indevido da chave de disponibilidade. A camada de aplicativo é o único método pelo qual as teclas, incluindo a chave de disponibilidade, podem ser usadas para criptografar e descriptografar dados. Somente o código do serviço do Office 365 tem a capacidade de interpretar e percorrer a hierarquia da chave para atividades de criptografia e descriptografia. O isolamento lógico existe entre os locais de armazenamento das chaves do cliente, as chaves de disponibilidade, outras chaves hierárquicas e dados do cliente. Esse isolamento reduz o risco de exposição dos dados no caso de um ou mais locais serem comprometidos. Cada camada na hierarquia criou recursos de detecção de invasão 24x7 para proteger dados e segredos armazenados.

Os controles de acesso são implementados para impedir o acesso não autorizado a sistemas internos, incluindo repositórios de segredo de chave de disponibilidade. Os engenheiros da Microsoft não têm acesso direto aos repositórios secretos de chave de disponibilidade. Para obter detalhes adicionais sobre controles de acesso, examine os [controles de acesso administrativo no Office 365](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Os controles técnicos impedem que o pessoal da Microsoft faça logon em contas de serviço com privilégios elevados, o que pode ser usado por invasores para representar os serviços do Office 365. Por exemplo, esses controles impedem o logon interativo.

O log de segurança e os controles de monitoramento são uma outra proteção de defesa profunda implementada que reduz o risco para os serviços da Microsoft e seus dados. As Teams Service da Microsoft implantaram soluções de monitoramento ativo que geram alertas e logs de auditoria. Todas as equipes de serviço carregam seus logs em um repositório central no qual os logs são agregados e processados. Ferramentas internas examinam automaticamente os registros para confirmar que os serviços estão funcionando em um estado ideal, resiliente e seguro. Atividade incomum está sinalizada para análise adicional.

Qualquer evento de log que indica uma possível violação da política de segurança da Microsoft é imediatamente levado à atenção do Microsoft Security Teams. A segurança do Office 365 configurou alertas para detectar o acesso às lojas de segredo de chave de disponibilidade. Os alertas também são gerados se o pessoal da Microsoft tentar fazer logon interativo nas contas de serviço, o que é proibido e protegido pelos controles de acesso. A segurança do Office 365 também detecta e alerta após desvios do serviço do Office 365 de operações normais da linha de base. Malefactors tentativa de uso indevido de serviços do Office 365 acionaria alertas resultando na remoção do infrator do ambiente de nuvem da Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Usar a chave de disponibilidade para recuperar da perda de chave

Se você perder o controle de suas chaves de cliente, a chave de disponibilidade fornecerá a capacidade de recuperar e criptografar novamente os dados.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedimento de recuperação do Exchange Online e do Skype for Business

Se você perder o controle de suas chaves de cliente, a chave de disponibilidade fornecerá a capacidade de recuperar seus dados e trazer seus recursos do Office 365 afetados novamente online. A chave de disponibilidade continua a proteger seus dados durante a recuperação. Em um nível alto, para recuperar totalmente da perda de teclas, você precisará criar um novo DEP e mover recursos impactados para a nova política.

Para criptografar seus dados com novas chaves de cliente, crie novas chaves no Azure Key Vault, crie uma nova DEP usando as novas chaves de cliente e, em seguida, atribua a nova DEP às caixas de correio atualmente criptografadas com a DEP anterior para a qual as chaves foram perdidas ou comprometidas.

Esse processo de re-criptografia pode levar até 72 horas. Essa é a duração padrão quando você altera uma DEP.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Procedimento de recuperação para os arquivos do SharePoint Online, do OneDrive for Business e do teams

Para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade nunca é usada fora do recurso de recuperação. Você deve instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação. Para iniciar o processo de recuperação, entre em contato com a Microsoft para ativar a chave de disponibilidade. Depois de ativado, a chave de disponibilidade é usada automaticamente para descriptografar seus dados, permitindo que você criptografe os dados com uma DEP recém-criada associada a novas chaves de cliente.  

Essa operação é proporcional ao número de sites em sua organização. Após ligar para a Microsoft para usar a chave de disponibilidade, você deve estar totalmente online em cerca de quatro horas.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Como o Exchange Online e o Skype for Business usam a chave de disponibilidade

Quando você cria uma DEP com chave de cliente, o Office 365 gera uma chave de política de criptografia de dados (chave DEP) associada a essa DEP. O serviço criptografa a chave DEP três vezes: uma vez por cada chave do cliente e uma vez com a chave de disponibilidade. Somente as versões criptografadas da chave DEP são armazenadas, e uma chave DEP só pode ser descriptografada com as chaves do cliente ou a chave de disponibilidade. A chave DEP é usada para criptografar chaves de caixa de correio, que criptografam caixas de correio individuais.
  
O Office 365 segue esse processo para descriptografar e fornecer dados quando os clientes estão usando o serviço:
  
1. Descriptografar a chave DEP usando a chave do cliente.

2. Use a chave da DEP descriptografada para descriptografar uma chave de caixa de correio.

3. Use a chave de caixa de correio descriptografada para descriptografar a caixa de correio, permitindo que você acesse os dados dentro da caixa de correio.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Como os arquivos do SharePoint Online, do OneDrive for Business e do teams usam a chave de disponibilidade

A arquitetura e a implementação do SharePoint Online e do OneDrive for Business para a chave de disponibilidade e a chave do cliente são diferentes do Exchange Online e do Skype for Business.
  
Quando uma organização é movida para chaves gerenciadas pelo cliente, o Office 365 cria uma chave intermediária específica do locatário (TIK). O Office 365 criptografa o TIK duas vezes, uma vez com cada uma das chaves do cliente e armazena as duas versões criptografadas do TIK. Somente as versões criptografadas do TIK são armazenadas, e um TIK só pode ser descriptografado com as chaves do cliente. O TIK é usado para criptografar chaves de site, que são usadas para criptografar chaves de BLOB (também chamadas chaves de bloco de arquivo). Dependendo do tamanho do arquivo, o serviço pode dividir um arquivo em vários blocos de arquivo com uma chave exclusiva. Os BLOBs (partes de arquivo) propriamente ditos são criptografados com as chaves de BLOB e armazenados no serviço de armazenamento de blob do Microsoft Azure.
  
O Office 365 segue esse processo para descriptografar e fornecer arquivos de cliente quando os clientes estão usando o serviço:

1. Descriptografar o TIK usando a chave do cliente.

2. Use o TIK descriptografado para descriptografar uma chave de site.

3. Use a chave do site descriptografado para descriptografar uma chave blob.

4. Use a chave do blob descriptografado para descriptografar o blob.

O Office 365 descriptografa um TIK emitindo duas solicitações de descriptografia para o Azure Key Vault com um ligeiro deslocamento. O primeiro a concluir fornece o resultado, cancelando a outra solicitação.
  
Caso você perca o acesso às suas chaves de cliente, o Office 365 também criptografa o TIK com uma chave de disponibilidade e o armazena junto com o TIKs criptografado com cada chave de cliente. O TIK criptografado com a chave de disponibilidade é usado somente quando o cliente chama a Microsoft para inscrever o caminho de recuperação quando perdeu o acesso às suas chaves, de forma mal-intencionada ou acidental.
  
Por motivos de disponibilidade e escala, os TIKs descriptografados são armazenados em cache em um cache de memória limitado por tempo. Duas horas antes de um cache do TIK ser definido como expirar, o Office 365 tenta descriptografar cada TIK. Descriptografar o TIKs estende o tempo de vida do cache. Se a descriptografia do TIK falhar por um período significativo, o Office 365 gerará um alerta para notificar a engenharia antes da expiração do cache. Somente se o cliente chamar a Microsoft, o Office 365 iniciará a operação de recuperação, que envolve a descriptografia do TIK com a chave de disponibilidade armazenada no repositório secreto da Microsoft e a integração do locatário novamente usando o TIK descriptografado e um novo conjunto de chaves do Azure Key Vault fornecidas pelo cliente.
  
A partir de hoje, a chave do cliente está envolvida na cadeia de criptografia e descriptografia dos dados de arquivo do SharePoint Online armazenadas no repositório de blob do Azure, mas não no SharePoint Online itens de lista ou metadados armazenados no banco de dados SQL. O Office 365 não usa a chave de disponibilidade para o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e arquivos do teams diferentes do caso descrito acima, que é iniciado pelo cliente. O acesso humano aos dados do cliente é protegido por Lockbox de cliente.

## <a name="availability-key-triggers"></a>Gatilhos de chave de disponibilidade

O Office 365 aciona a chave de disponibilidade somente em circunstâncias específicas. Essas circunstâncias diferem pelo serviço.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Gatilhos para o Exchange Online e o Skype for Business
  
1. O Office 365 lê a DEP à qual a caixa de correio é atribuída para determinar o local das duas chaves do cliente no Azure Key Vault.

2. O Office 365 escolhe aleatoriamente uma das duas chaves de cliente da DEP e envia uma solicitação para o Azure Key Vault para desencapsular a chave DEP usando a chave do cliente.

3. Se a solicitação para desencapsular a chave DEP usando a chave do cliente falhar, o Office 365 enviará uma segunda solicitação para o Azure Key Vault, desta vez instruindo-o a usar a chave alternativa (segundo) do cliente.

4. Se a segunda solicitação para desencapsular a chave DEP usando a chave do cliente falhar, o Office 365 examinará os resultados das duas solicitações.

    - Se o exame determinar que as solicitações falharam retornando um erro do sistema:

       - O Office 365 dispara a chave de disponibilidade para descriptografar a chave DEP.

       - O Office 365 usa a chave DEP para descriptografar a chave da caixa de correio e concluir a solicitação do usuário. 

       - Nesse caso, o Azure Key Vault não consegue responder ou não pode ser acessado devido a um erro transitório.

    - Se o exame determinar que as solicitações não retornaram acesso NEGAdo:

       - Isso significa que ações deliberadas, inadvertidas ou mal-intencionadas foram tomadas para renderizar as chaves do cliente indisponíveis (por exemplo, durante o processo de limpeza de dados como parte de deixar o serviço).

       - Nesse caso, a chave de disponibilidade será usada apenas para as ações do sistema e não para as ações do usuário, a solicitação do usuário falhará e o usuário receberá uma mensagem de erro.

>[!IMPORTANT]
>O código de serviço do Office 365 sempre tem um token de logon válido para o raciocínio dos dados do cliente para fornecer os serviços de nuvem de valor agregado. Portanto, até que a chave de disponibilidade tenha sido excluída, ela pode ser usada como fallback para ações iniciadas por, ou internas, do Exchange Online e do Skype for Business, como a criação de índice de pesquisa ou a movimentação de caixas de correio. Isso se aplica a erros transitórios e solicitações NEGAdas de acesso ao Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Gatilhos para os arquivos do SharePoint Online, do OneDrive for Business e do teams

Para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade nunca é usada fora do recurso de recuperação, e os clientes devem instruir explicitamente a Microsoft a iniciar o uso da chave de disponibilidade durante um cenário de recuperação.

## <a name="audit-logs-and-the-availability-key"></a>Logs de auditoria e a chave de disponibilidade

Sistemas automatizados no Office 365 processam todos os dados à medida que ele flui pelo sistema para fornecer serviços de nuvem, por exemplo, antivírus, e-Discovery, prevenção de perda de dados e indexação de dados. O Office 365 não gera logs visíveis ao cliente para esta atividade. Além disso, a equipe da Microsoft não acessa seus dados como parte dessas operações normais do sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Log de chave de disponibilidade do Exchange Online e do Skype for Business

Quando o Exchange Online e o Skype for Business acessam a chave de disponibilidade para fornecer serviço, o Office 365 publica os logs visíveis ao cliente que podem ser acessados no centro de segurança e conformidade. Um registro de log de auditoria para a operação de chave de disponibilidade é gerado cada vez que o serviço usa a chave de disponibilidade. Um novo tipo de registro chamado "criptografia de serviço de chave do cliente" com o tipo de atividade "fallback para chave de disponibilidade" permite que os administradores filtrem os resultados da pesquisa de [log de auditoria unificada](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para exibir registros chave de disponibilidade

Registros de log incluem atributos como data, hora, atividade, ID da organização e ID da política de criptografia de dados. O registro está disponível como parte dos logs de auditoria unificada do Office 365 e é acessível na guia pesquisa de log de auditoria do centro de conformidade e segurança do Office 365.

![Pesquisa de log de auditoria por eventos principais de disponibilidade](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Registros de chave de disponibilidade do Exchange Online e do Skype for Business use o [esquema comum](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) da atividade de gerenciamento do Office 365 com parâmetros personalizados adicionados: ID da política, ID da versão da chave de escopo e ID da solicitação.

![Parâmetros personalizados de chave de disponibilidade](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Log de chave de disponibilidade de arquivos do SharePoint Online, do OneDrive for Business e do teams

O log de chave de disponibilidade ainda não está disponível para esses serviços. Para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, a chave de disponibilidade é ativada pela Microsoft, quando instruída por você, para fins de recuperação. Como resultado, você já sabe todos os eventos nos quais a chave de disponibilidade é usada para esses serviços.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Chave de disponibilidade na hierarquia de chave do cliente
  
O Office 365 usa a chave de disponibilidade para quebrar a camada de chaves abaixo na hierarquia de teclas estabelecida para a criptografia de serviço de chave do cliente. Há diferentes hierarquias de teclas entre os serviços. Os algoritmos de chave também diferem entre chaves de disponibilidade e outras chaves na hierarquia de cada serviço aplicável. Os algoritmos de chave de disponibilidade usados pelos diferentes serviços são os seguintes:

- As chaves de disponibilidade do Exchange Online e do Skype for Business usam AES-256.

- As chaves de disponibilidade de arquivos do SharePoint Online, do OneDrive for Business e do teams usam o RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o Exchange Online e o Skype for Business

![Codificações de criptografia para a chave do cliente do Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Codificações de criptografia usadas para criptografar chaves para o SharePoint Online e o OneDrive for Business

![Codificações de criptografia para a chave do cliente do SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com a chave do cliente para o Office 365](customer-key-overview.md)

- [Configurar a chave do cliente para o Office 365](customer-key-set-up.md)

- [Gerenciar a chave do cliente para o Office 365](customer-key-manage.md)

- [Rolar ou girar uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)
