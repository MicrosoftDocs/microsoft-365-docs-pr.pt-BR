---
title: Perguntas frequentes sobre a importação de arquivos PST para o Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Perguntas frequentes para administradores sobre como usar o serviço de importação do Office 365 para importar os arquivos PST do Organizaiton para caixas de correio do Office 365. '
ms.openlocfilehash: 632b82a99f1be5d38db3fb50a4b2b4d7a6369186
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072628"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>Perguntas frequentes sobre a importação de arquivos PST para o Office 365

**Este artigo é para administradores. Deseja importar arquivos PST para sua própria caixa de correio? Confira [importar email, contatos e calendário de um arquivo. pst do Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Aqui estão algumas perguntas frequentes sobre como usar o serviço de importação do Office 365 para importar arquivos PST em massa para caixas de correio do Office 365. Para obter mais informações sobre como importar arquivos PST, consulte [visão geral da importação de arquivos pst para o Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).
  
## <a name="using-network-upload-to-import-pst-files"></a>Usando o carregamento de rede para importar arquivos PST

Para obter instruções passo a passo, consulte [usar o carregamento de rede para importar arquivos pst para o Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quais permissões são necessárias para criar trabalhos de importação no serviço de importação do Office 365?**
  
Você deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online para importar arquivos PST para caixas de correio do Office 365. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Para obter mais informações, consulte as seções "adicionar uma função a um grupo de funções" ou "criar um grupo de função" em [gerenciar grupos de função no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Além disso, para criar trabalhos de importação no centro de conformidade & segurança, um dos seguintes deve ser verdadeiro:
  
- Você precisa receber a função de destinatários de email no Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Ou
    
- Você deve ser um administrador global em sua organização do Office 365.
    
> [!TIP]
> Considere a criação de um novo grupo de função no Exchange Online destinado especificamente à importação de arquivos PST para o Office 365. Para obter o nível mínimo de privilégios necessários para importar arquivos PST, atribua as funções de importação de caixa de correio e destinatários de email ao novo grupo de funções e, em seguida, adicione membros. 
  
 **Onde o carregamento de rede está disponível?**
  
O carregamento de rede está disponível atualmente nos Estados Unidos, Canadá, Brasil, Reino Unido, França, Europa, Índia, leste asiático, Sudeste Asiático, Japão, República da Coréia e Austrália. Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
Isso também significa que, após os arquivos PST serem excluídos da área de armazenamento do Azure, eles não serão mais exibidos na lista de arquivos para um trabalho de importação concluído no centro de administração do Microsoft 365. Embora um trabalho de importação ainda possa ser listado na página **importar dados para o Office 365** , a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação mais antigos. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. No entanto, os arquivos que usam o formato de arquivo PST ANSI, como aqueles para idiomas que usam um conjunto de caracteres de dois bytes (DBCS), também podem ser importados para o Office 365. Para obter mais informações sobre a importação de arquivos PST ANSI, consulte a etapa 4 em [usar o carregamento de rede para importar arquivos pst da sua organização para o Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Após carregar arquivos PST para a área de armazenamento do Azure, por quanto tempo eles são mantidos no Azure antes de serem excluídos?**
  
Quando você usa o método de carregamento de rede para importar arquivos PST, você os carrega em um contêiner de blob do Azure chamado **ingestiondata**. Se não houver trabalhos de importação em andamento na página de **importação** no centro de conformidade & segurança), todos os arquivos pst no contêiner do **ingestiondata** no Azure serão excluídos 30 dias após o trabalho de importação mais recente ter sido criado no & de segurança Centro de conformidade. Isso também significa que você precisa criar um novo trabalho de importação no centro de conformidade de & de segurança (descrito na etapa 5 nas instruções de upload de rede) dentro de 30 dias do carregamento de arquivos PST para o Azure. 
  
Isso também significa que, após os arquivos PST serem excluídos da área de armazenamento do Azure, eles não serão mais exibidos na lista de arquivos para um trabalho de importação concluído no centro de conformidade do & de segurança. Embora um trabalho de importação ainda possa estar listado na página de **importação** no centro de conformidade com segurança &, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação mais antigos. 
  
 **Quanto tempo leva para importar um arquivo PST para uma caixa de correio?**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. Depois que os arquivos PST forem copiados para a área de armazenamento do Azure, um arquivo PST será importado para uma caixa de correio do Office 365 em uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, você poderá considerar outros métodos para migrar dados de email para o Office 365. Para obter mais informações, consulte [maneiras de migrar várias contas de email para o Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Da mesma forma, se vários arquivos PST forem importados para a mesma caixa de correio, eles serão importados simultaneamente.
  
 **Is there a message size limit when importing PST files?**
  
Sim. Se um arquivo PST contiver um item de caixa de correio maior do que 150 MB, o item será ignorado durante o processo de importação.
  
 **São propriedades de mensagens, como quando a mensagem foi enviada ou recebida, a lista de destinatários e outras propriedades, preservadas quando os arquivos PST são importados para uma caixa de correio do Office 365?**
  
Sim. Os metadados da mensagem original não são alterados durante o processo de importação.
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **Posso usar o carregamento de rede para importar arquivos PST para pastas públicas no Exchange Online?**
  
Não, não é possível importar arquivos PST para pastas públicas.
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Usando o envio de unidade para importar arquivos PST

Para obter instruções passo a passo, consulte [usar o envio de unidade para importar arquivos pst para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
 **Quais permissões são necessárias para criar trabalhos de importação no serviço de importação do Office 365?**
  
Você deve ser atribuído à função de exportação de importação de caixa de correio para importar arquivos PST para caixas de correio do Office 365. Por padrão, essa função não é atribuída a nenhum grupo de função no Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. Para obter mais informações, consulte as seções "adicionar uma função a um grupo de funções" ou "criar um grupo de função" em [gerenciar grupos de função no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Além disso, para criar trabalhos de importação no centro de conformidade & segurança, um dos seguintes deve ser verdadeiro:
  
- Você precisa receber a função de destinatários de email no Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Ou
    
- Você deve ser um administrador global em sua organização do Office 365.
    
> [!TIP]
> Considere a criação de um novo grupo de função no Exchange Online destinado especificamente à importação de arquivos PST para o Office 365. Para obter o nível mínimo de privilégios necessários para importar arquivos PST, atribua as funções de importação de caixa de correio e destinatários de email ao novo grupo de funções e, em seguida, adicione membros. 
  
 **Onde está disponível o envio da unidade?**
  
O envio de unidades está disponível atualmente nos Estados Unidos, Canadá, Brasil, Reino Unido, Europa, Índia, leste asiático, Sudeste Asiático, Japão, República da Coréia e Austrália. Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
O envio de unidades para importar arquivos PST para o Office 365 está disponível por meio de um Microsoft Enterprise Agreement (EA). O envio de unidades não está disponível por meio de um contrato de produtos e serviços da Microsoft (MPSA).
  
 **Qual é o preço para usar o envio de unidade para importar arquivos PST para o Office 365?**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Para obter informações sobre como encontrar um parceiro, consulte [encontre seu parceiro ou revendedor do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **What kind of hard drives are supported for drive shipping?**
  
Somente discos rígidos internos de estado sólido (SSDs) de 2,5 polegadas ou 2,5 ou 3,5 polegadas SATA II/III são suportados para uso com o serviço de importação do Office 365. You can use hard drives up to 10 TB. Para trabalhos de importação, somente o primeiro volume de dados no disco rígido será processado. The data volume must be formatted with NTFS. Ao copiar dados para uma unidade de disco rígido, você pode anexá-los diretamente usando um conector SATA de 2,5 polegadas ou 2,5 ou 3,5 polegada SATA II/III ou pode anexá-lo externamente usando um adaptador de USB 2,5 de ou/2,5 ou/ou/ou/ou SATA II de 4 pol
  
> [!IMPORTANT]
> Discos rígidos externos que acompanham um adaptador USB interno não são compatíveis com o serviço de importação do Office 365. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Após o meu disco rígido chegar ao Data Center da Microsoft, quanto tempo demora para carregar meus arquivos PST para o Azure?**
  
Depois que o disco rígido for recebido no centro de dados da Microsoft, levará entre 7 e 10 dias úteis para carregar os arquivos PST para a área de armazenamento do Microsoft Azure para sua organização. Os arquivos PST serão carregados para um contêiner de blob do Azure chamado **ingestiondata**. 
  
 **Quanto tempo leva para importar um arquivo PST para uma caixa de correio?**
  
Depois que os arquivos PST são carregados para a área de armazenamento do Azure, o Office 365 analisa os dados nos arquivos PST (de uma maneira segura e segura) para identificar a idade dos itens e os diferentes tipos de mensagem incluídos nos arquivos PST. Quando esta análise estiver concluída, você terá a opção de importar todos os dados dos arquivos PST ou definir filtros para que controlem quais dados são importados. Depois de iniciar o trabalho de importação, um arquivo PST é importado para uma caixa de correio do Office 365 em uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, você poderá considerar outros métodos para importar dados de email para o Office 365. Para obter mais informações, consulte [maneiras de migrar várias contas de email para o Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Da mesma forma, se vários arquivos PST forem importados para a mesma caixa de correio, eles serão importados simultaneamente.
  
 **Depois que a Microsoft carregar meus arquivos PST para o Azure, quanto tempo eles serão mantidos no Azure antes de serem excluídos?**
  
Todos os arquivos PST no local de armazenamento do Azure para sua organização (no contêiner de blob chamado **ingestiondata** ) são excluídos 30 dias após o trabalho de importação mais recente ter sido criado na página **importar** no centro de conformidade e segurança &. 
  
Isso também significa que, após os arquivos PST serem excluídos da área de armazenamento do Azure, eles não serão mais exibidos na lista de arquivos para um trabalho de importação concluído no centro de conformidade do & de segurança. Embora um trabalho de importação ainda possa estar listado na página de **importação** no centro de conformidade com segurança &, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação mais antigos. 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. No entanto, os arquivos que usam o formato de arquivo PST ANSI, como aqueles para idiomas que usam um conjunto de caracteres de dois bytes (DBCS), também podem ser importados para o Office 365. Para obter mais informações sobre a importação de arquivos PST ANSI, consulte a etapa 3 em [usar o envio de unidade para importar arquivos pst para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
Sim. Se um arquivo PST contiver um item de caixa de correio maior do que 150 MB, o item será ignorado durante o processo de importação.
  
 **São propriedades de mensagens, como quando a mensagem foi enviada ou recebida, a lista de destinatários e outras propriedades, preservadas quando os arquivos PST são importados para uma caixa de correio do Office 365?**
  
Sim. Os metadados da mensagem original não são alterados durante o processo de importação
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **Posso usar o envio de unidade para importar arquivos PST para pastas públicas no Exchange Online?**
  
Não, não é possível importar arquivos PST para pastas públicas.
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **A Microsoft pode destruir meu disco rígido em vez de enviá-lo novamente?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Quais serviços de Courier são compatíveis com a entrega de retorno?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **Quais são os custos de envio de devolução?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **Posso usar um serviço de envio do Courier personalizado, como o envio personalizado do FedEx, para entregar meu disco rígido à Microsoft?**
  
Sim.
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
