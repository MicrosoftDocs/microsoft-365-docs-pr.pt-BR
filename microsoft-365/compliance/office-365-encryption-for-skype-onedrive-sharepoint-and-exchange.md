---
title: Criptografia do Office 365 para Skype, OneDrive, SharePoint e Exchange
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumo: uma descrição da criptografia para o Skype, o OneDrive, o SharePoint e o Exchange Online.'
ms.openlocfilehash: 55141f671e6cb3d7ea837bfcf9701e37a18fb7ba
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073464"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Criptografia do Office 365 para o Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online

O Office 365 é um ambiente altamente seguro, que fornece proteção ampla em várias camadas: segurança física de data center, segurança de rede, segurança de acesso, segurança de aplicativo e segurança de dados.

## <a name="skype-for-business"></a>Skype for Business

Os dados do cliente do Skype for Business podem ser armazenados em repouso no formato de arquivos ou apresentações carregados pelos participantes da reunião. O servidor de Webconferência criptografa os dados do cliente usando o AES com uma chave de 256 bits. Os dados do cliente criptografados são armazenados em um compartilhamento de arquivos. Cada parte dos dados do cliente é criptografada usando uma chave de 256 bits gerada aleatoriamente diferente. Quando uma parte dos dados do cliente é compartilhada em uma conferência, o servidor de Webconferência instrui os clientes de conferência a baixarem os dados criptografados do cliente via HTTPS. Ele envia a chave correspondente aos clientes para que os dados do cliente possam ser descriptografados. O servidor de Webconferência também autentica clientes de conferência antes de permitir que os clientes acessem os dados do cliente de conferência. Ao ingressar em uma conferência da Web, cada cliente de conferência estabelece uma caixa de diálogo SIP com o componente de foco de conferência em execução dentro do servidor front-end pelo TLS primeiro. O foco da conferência passa para o cliente da conferência um cookie de autenticação gerado pelo servidor de Webconferência. Em seguida, o cliente de conferência se conecta ao servidor de Webconferência que apresenta o cookie de autenticação a ser autenticado pelo servidor.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

Todos os arquivos do cliente no SharePoint Online são protegidos por chaves exclusivas por arquivo que são sempre exclusivas para um único locatário. As chaves são criadas e gerenciadas pelo serviço do SharePoint Online, ou quando a chave do cliente é usada, criada e gerenciada por clientes. Quando um arquivo é carregado, a criptografia é executada pelo SharePoint Online dentro do contexto da solicitação de upload, antes de ser enviada para o armazenamento do Azure. Quando um arquivo é baixado, o SharePoint Online recupera os dados do cliente criptografados do armazenamento do Azure com base no identificador de documento exclusivo e descriptografa os dados do cliente antes de enviá-los ao usuário. O armazenamento do Azure não tem capacidade de descriptografar ou mesmo identificar ou compreender os dados do cliente. A criptografia e a descriptografia acontecem nos mesmos sistemas que impõem o isolamento do locatário, que são o Active Directory do Azure e o SharePoint Online.

Várias cargas de trabalho no Office 365 armazenar dados no SharePoint Online, incluindo o Microsoft Teams, que armazena todos os arquivos no SharePoint Online e o OneDrive for Business, que usa o SharePoint Online para seu armazenamento. Todos os dados do cliente armazenados no SharePoint Online são criptografados (com uma ou mais chaves AES de 256 bits) e distribuídos no datacenter da seguinte maneira. (Cada etapa deste processo de criptografia é o FIPS 140-2 nível 2 validado. Para obter informações adicionais sobre conformidade com o FIPS 140-2, confira [conformidade com fips 140-2](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).

- Cada arquivo é dividido em uma ou mais partes, dependendo do tamanho do arquivo. Cada parte é criptografada usando sua própria chave exclusiva de 256 bits do AES.
- Quando um arquivo é atualizado, a atualização é manipulada da mesma forma que a alteração é dividida em uma ou mais partes, e cada parte é criptografada com uma chave exclusiva separada.
- Esses blocos – arquivos, partes de arquivos e deltas de atualização – são armazenados como BLOBs no armazenamento do Azure que são distribuídos aleatoriamente em várias contas de armazenamento do Azure.
- O conjunto de chaves de criptografia para esses blocos de dados do cliente é criptografado.

    - As chaves usadas para criptografar os BLOBs são armazenadas no banco de dados de conteúdo do SharePoint Online.
    - O banco de dados de conteúdo é protegido por controles de acesso ao banco de dados e criptografia em repouso. A criptografia é realizada usando a [criptografia de dados transparente](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) (TDE) no banco de dados [SQL do Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). (O banco de dados SQL do Azure é um serviço de banco de dados relacional de uso geral no Microsoft Azure que oferece suporte a estruturas como dados relacionais, JSON, Spatial e XML.) Esses segredos estão no nível de serviço do SharePoint Online, e não no nível do locatário. Esses segredos (às vezes chamados de chaves mestras) são armazenados em um repositório seguro separado chamado de armazenamento de chave. O TDE fornece segurança em repouso para o banco de dados ativo e os backups e logs de transações.
    - Quando os clientes fornecem a chave opcional, a chave do cliente é armazenada no Azure Key Vault, e o serviço usa a chave para criptografar uma chave de locatário, que é usada para criptografar uma chave de site, que é usada para criptografar as chaves de nível de arquivo. Essencialmente, uma nova hierarquia de chave é introduzida quando o cliente fornece uma chave.
- O mapa usado para remontar o arquivo é armazenado no banco de dados de conteúdo juntamente com as chaves criptografadas, separadamente da chave mestra necessária para descriptografá-las.
- Cada conta de armazenamento do Azure tem suas próprias credenciais exclusivas por tipo de acesso (ler, gravar, enumerar e excluir). Cada conjunto de credenciais é mantido no Repositório de Chaves seguro e atualizado regularmente. Conforme descrito acima, há três tipos diferentes de repositórios, cada um com uma função distinta:
    - Os dados do cliente são armazenados como BLOBs criptografados no armazenamento do Azure. A chave para cada parte dos dados do cliente é criptografada e armazenada separadamente no banco de dados de conteúdo. Os dados do cliente propriamente ditos não têm idéia de como ele pode ser descriptografado.
    - O banco de dados de conteúdo é um banco de dados do SQL Server. Ele mantém o mapa necessário para localizar e remontar os blobs de dados do cliente mantidos no armazenamento do Azure, bem como as chaves necessárias para criptografar esses BLOBs. No entanto, o conjunto de chaves é criptografado (conforme explicado acima) e mantido em um repositório de chaves separado.
    - O repositório de chave é fisicamente separado do banco de dados de conteúdo e do Azure Storage. Ele contém as credenciais de cada contêiner de armazenamento do Azure e a chave mestra para o conjunto de chaves criptografadas mantidas no banco de dados de conteúdo.

Cada um desses três componentes de armazenamento – o repositório de blob do Azure, o banco de dados de conteúdo e o armazenamento de chaves – é fisicamente separado. As informações contidas nesses componentes por si só não são utilizáveis. Sem acesso a todos os três, é impossível recuperar as chaves para os fragmentos, descriptografar as teclas para torná-las utilizáveis, associar as chaves com seus blocos correspondentes, descriptografar cada parte ou reconstruir um documento de seus blocos constituintes.

Os certificados do BitLocker, que protegem os volumes de disco físico em máquinas no datacenter, são armazenados em um repositório seguro (o repositório secreto do SharePoint Online) que é protegido pela chave do farm.

As chaves TDE que protegem as chaves por blob são armazenadas em dois locais:

- O repositório seguro, que abriga os certificados do BitLocker e é protegido pela chave do farm; e
- Em um repositório seguro gerenciado pelo banco de dados SQL do Azure.

As credenciais usadas para acessar os contêineres de armazenamento do Azure também são mantidas no repositório de segredo do SharePoint Online e delegadas a cada farm do SharePoint Online, conforme necessário. Essas credenciais são assinaturas de SAS de armazenamento do Azure, com credenciais separadas usadas para ler ou gravar dados, e com a política aplicada para que expire automaticamente a cada 60 dias. Credenciais diferentes são usadas para ler ou gravar dados (não ambos) e os farms do SharePoint Online não recebem permissões para enumerar.

> [!NOTE]
> Para clientes do governo dos EUA do Office 365, os blobs de dados são armazenados no armazenamento do governo dos EUA do Azure. Além disso, o acesso às chaves do SharePoint Online no Office 365 governo dos EUA limita-se à equipe do Office 365 que foi especificamente filtrada. A equipe de operações do governo dos EUA do Azure não tem acesso ao repositório de chaves do SharePoint Online usado para criptografar blobs de dados.

Para obter mais informações sobre a criptografia de dados no SharePoint Online e no OneDrive for Business, consulte [criptografia de dados no onedrive for Business e no SharePoint Online](https://technet.microsoft.com/en-us/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Listar itens no SharePoint Online

Itens de lista são partes menores de dados do cliente que são criados ad-hoc ou que podem residir mais dinamicamente dentro de um site, como linhas em uma lista criada pelo usuário, postagens individuais em um blog do SharePoint Online ou entradas dentro de uma página wiki do SharePoint Online. Os itens de lista são armazenados no banco de dados de conteúdo (banco de dados SQL do Azure) e protegidos com o TDE.

## <a name="encryption-of-data-in-transit"></a>Criptografia de dados em trânsito

No OneDrive for Business e no SharePoint Online, há dois cenários em que os dados entram e saem dos data centers.

- A **comunicação do cliente com a comunicação do servidor com o** onedrive for Business pela Internet usa conexões SSL/TLS. Todas as conexões SSL são estabelecidas por meio de chaves de 2.048 bits.
- **Movimentação de dados entre data centers** -o principal motivo para mover dados entre data centers é para replicação geográfica para permitir a recuperação de desastres. Por exemplo, os logs de transação e os deltas de armazenamento de blobs do SQL Server passam por esse pipe. Embora esses dados já sejam transmitidos por meio de uma rede privada, eles estarão ainda mais protegidos com a melhor criptografia do mercado.

## <a name="exchange-online"></a>Exchange Online

O Exchange Online usa o BitLocker para todos os dados de caixa de correio, e a configuração do BitLocker é descrita no [BitLocker para criptografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md). A criptografia de nível de serviço criptografa todos os dados de caixa de correio no nível da caixa de correio. 

Além da criptografia de serviço, o Office 365 oferece suporte à chave do cliente, que é criada na parte superior da criptografia de serviço. A chave do cliente é uma opção de chave gerenciada pela Microsoft para a criptografia de serviço do Exchange Online que também está no mapa da Microsoft. Esse método de criptografia fornece maior proteção não é proporcionada pelo BitLocker, pois fornece separação de administradores de servidor e chaves criptográficas necessárias para a descriptografia de dados, e como a criptografia é aplicada diretamente aos dados (em contraste com o BitLocker, que aplica criptografia no volume do disco lógico, todos os dados do cliente copiados de um servidor do Exchange permanecem criptografados.

O escopo para a criptografia de serviço do Exchange Online é dados do cliente armazenados em repouso no Exchange Online. (O Skype for Business armazena quase todo o conteúdo gerado pelo usuário dentro da caixa de correio do Exchange Online do usuário e, portanto, herda o recurso de criptografia de serviço do Exchange Online.)
