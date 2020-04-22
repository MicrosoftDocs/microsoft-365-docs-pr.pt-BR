---
title: Criptografia de dados no OneDrive for Business e no SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Entenda os elementos básicos de segurança da criptografia de dados no OneDrive for Business e no SharePoint Online.
ms.openlocfilehash: e882bf3bf633c821fe50246316b5b1065cfa4693
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633336"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Criptografia de dados no OneDrive for Business e no SharePoint Online

Entenda os elementos básicos de segurança da criptografia de dados no OneDrive for Business e no SharePoint Online.
  
## <a name="overview"></a>Visão geral

O Microsoft 365 é um ambiente altamente seguro que oferece proteção abrangente em várias camadas: segurança física do Data Center, segurança da rede, segurança do acesso, segurança do aplicativo e segurança dos dados. Este artigo aborda especificamente o lado da criptografia em repouso e em trânsito da segurança de dados para OneDrive for Business e SharePoint Online.
  
Para obter uma descrição da segurança da Microsoft 365 como um todo, consulte o [White paper sobre segurança](https://go.microsoft.com/fwlink/p/?LinkId=270895).
  
Assista ao vídeo a seguir para ver como funciona a criptografia de dados.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Criptografia de dados em trânsito

No OneDrive for Business e no SharePoint Online, há dois cenários em que os dados entram e saem dos data centers.
  
- **Comunicação do cliente com o servidor** A comunicação com o OneDrive for Business pela Internet usa conexões SSL/TLS. Todas as conexões SSL são estabelecidas por meio de chaves de 2.048 bits.

- **Movimentação de dados entre data centers** O principal motivo para a movimentação de dados entre data centers se deve à replicação geográfica para habilitar a recuperação de desastres. Por exemplo, os logs de transação e os deltas de armazenamento de blobs do SQL Server passam por esse pipe. Embora esses dados já sejam transmitidos por meio de uma rede privada, eles estarão ainda mais protegidos com a melhor criptografia do mercado. 

## <a name="encryption-of-data-at-rest"></a>Criptografia de dados em repouso

A criptografia em repouso inclui dois componentes: Criptografia BitLocker no nível do disco e criptografia por arquivo de conteúdo do cliente.
  
A criptografia BitLocker está implantada para o serviço do OneDrive for Business e do SharePoint Online. A criptografia por arquivo também está no OneDrive for Business e no SharePoint Online no Microsoft 365 multilocatário e novos ambientes dedicados criados na tecnologia de vários locatários.
  
Enquanto o BitLocker criptografa todos os dados no disco, a criptografia por arquivo vai ainda mais longe e inclui uma chave de criptografia exclusiva para cada arquivo. Além disso, as atualizações de cada arquivo são criptografadas com uma chave de criptografia própria. Antes de armazená-las, as chaves do conteúdo criptografado são armazenadas em um local físico separado do conteúdo. Todas as etapas dessa criptografia usam a criptografia AES com chaves de 256 bits e estão em conformidade com o padrão FIPS 140-2. O conteúdo criptografado é distribuído para vários contêineres no data center, e cada contêiner tem credenciais exclusivas. Essas credenciais são armazenadas em um local físico separado do conteúdo e das chaves de conteúdo.
  
Para obter informações adicionais sobre a conformidade com o FIPS 140-2, confira conformidade com o [fips 140-2](https://go.microsoft.com/fwlink/?LinkId=517625).
  
A criptografia em repouso no nível do arquivo aproveita o armazenamento de blobs para proporcionar o crescimento do armazenamento praticamente ilimitado e viabilizar uma proteção sem precedentes. Todo o conteúdo do cliente no OneDrive for Business e no SharePoint Online será migrado para o armazenamento de blobs. Veja como esses dados são protegidos:
  
1. todo o conteúdo é criptografado, possivelmente com várias chaves, e distribuído pelo data center. Cada arquivo que será armazenado é dividido em uma ou mais partes, dependendo do respectivo tamanho. Em seguida, cada parte é criptografada por meio de uma chave própria exclusiva. As atualizações são tratadas da mesma maneira: o conjunto de alterações ou deltas enviados por um usuário é dividido em partes ,e cada uma delas é criptografada com uma chave própria.

2. Todas as partes (arquivos, partes de arquivos e deltas de atualização) são armazenadas em blobs na nossa BLOB Store. Além disso, elas são distribuídas aleatoriamente em vários contêineres de blob.

3. O "mapa" usado para remontar o arquivo com os respectivos componentes fica armazenado no banco de dados de conteúdo.

4. Cada contêiner de blob tem credenciais próprias e exclusivas por tipo de acesso: leitura, gravação, enumeração e exclusão. Cada conjunto de credenciais é mantido no Repositório de Chaves seguro e atualizado regularmente.

Ou seja, há três tipos diferentes de armazenamento envolvidos na criptografia por arquivo em repouso, cada um deles com uma função distinta:
  
- o conteúdo é armazenado como blobs criptografados na BLOB Store. A chave de cada parte do conteúdo é criptografada e armazenada separadamente no banco de dados de conteúdo. O conteúdo em si não inclui nenhuma pista sobre como descriptografá-lo.

- O banco de dados de conteúdo é um banco de dados do SQL Server. Ele contém o mapa necessário para localizar e remontar todos os blobs de conteúdo armazenados na BLOB store, bem como as chaves necessárias para descriptografá-los.

Todos os três componentes de armazenamento (a BLOB store, o banco de dados de conteúdo e o repositório de chaves) são fisicamente separados. As informações contidas nesses componentes por si só não são utilizáveis. Eles fornecem um nível de segurança inigualável. Sem acesso aos três componentes, é impossível recuperar as chaves das partes, descriptografar as chaves para torná-las utilizáveis, associar as chaves às respectivas partes, descriptografar qualquer parte ou reconstruir um documento com as partes integrantes.
