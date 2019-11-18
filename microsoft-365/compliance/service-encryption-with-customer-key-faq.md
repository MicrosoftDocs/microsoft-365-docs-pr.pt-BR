---
title: Criptografia de serviço com chave do cliente para perguntas frequentes do Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: Além da linha de base, a criptografia no nível do volume habilitada por meio do BitLocker e do protocolo DKM, o Office 365 oferece uma camada adicional de criptografia no nível do aplicativo para conteúdo do cliente no Office 365, incluindo dados do Exchange Online, Skype for Business, SharePoint Online e OneDrive for Business. Isso é chamado de criptografia de serviço.
ms.openlocfilehash: 0dbc3839d5dfda98460db70de667e2f469bc1291
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38684892"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>Criptografia de serviço com chave do cliente para perguntas frequentes do Office 365

Além da linha de base, a criptografia no nível do volume habilitada por meio do BitLocker e do protocolo DKM, o Office 365 oferece uma camada adicional de criptografia no nível do aplicativo para conteúdo do cliente no Office 365, incluindo dados do Exchange Online, Skype for Business, SharePoint Online e OneDrive for Business. Isso é chamado de criptografia de serviço.
  
A chave do cliente é criada na criptografia de serviço e permite que você forneça e controle as chaves usadas para criptografar seus dados em repouso no Office 365, conforme descrito nos [termos dos serviços online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx). A chave do cliente ajuda você a cumprir as obrigações de conformidade, pois você controla as chaves de criptografia que o Office 365 usa para descriptografar dados.
  
Para fornecer comentários sobre a chave do cliente, incluindo a documentação, envie suas ideias, sugestões e perspectivas para o customerkeyfeedback@microsoft.com.
  
## <a name="what-is-service-encryption-with-customer-key"></a>O que é a criptografia de serviço com a chave do cliente?

A chave do cliente aprimora a capacidade de sua organização atender às exigências de requisitos de conformidade que especificam a principal organização com o provedor de serviços de nuvem. Com a chave do cliente, você fornece e controla as chaves de criptografia dos seus dados do Office 365 em repouso no nível do aplicativo. Como resultado, você pode exercer controle e revogar as chaves da sua organização, caso decida sair do serviço. Ao revogar as chaves, os dados são ilegíveis para o serviço. A revogação de chave é a primeira etapa no caminho em relação à exclusão de dados.

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>Quais dados 365 do Office em repouso são cobertos pela chave do cliente?
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

O conteúdo do site do SharePoint Online e os arquivos armazenados nesse site e os arquivos carregados no OneDrive for Business são cobertos. O conteúdo da caixa de correio do Exchange Online (corpo de email, entradas de calendário e conteúdo de anexos de email) é abordado. Conversas de texto do Skype for Business são abordadas, mas gravações de transmissão de reunião do Skype e carregamentos de conteúdo de reunião do Skype não são cobertos. A transmissão de reunião do Skype e os carregamentos de conteúdo de reunião do Skype são criptografados junto com todos os outros conteúdos no Office 365, mas atualmente não oferecemos controle de cliente sobre as chaves de criptografia.
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>Qual é a diferença entre a chave do cliente e a traga sua chave (BYOK) com a proteção de informações do Azure para o Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Ambas as opções permitem que você forneça e controle suas próprias chaves de criptografia; no entanto, a criptografia de serviço com a chave do cliente criptografa seus dados em repouso, residindo nos servidores do Office 365 em repouso, enquanto o BYOK com proteção de informações do Azure para o Exchange Online criptografa seus dados em trânsito e fornece persistente online e offline proteção para mensagens de email e anexos para o Office 365. A chave do cliente e o BYOK com a proteção de informações do Azure para Exchange Online são complementares e se você optar por usar chaves gerenciadas por serviços da Microsoft ou suas próprias chaves, a criptografia de dados em repouso e em trânsito pode fornecer proteção adicional contra ataques mal-intencionados.
  
O BYOK com proteção de informações do Azure para o Exchange Online é oferecido nos recursos de criptografia de mensagem do Office 365.
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>A criptografia de mensagem do Office 365 e a traga sua própria chave com a proteção de informações do Azure alteram a abordagem da Microsoft para solicitações de dados de terceiros, como intimações?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Não. A criptografia de mensagem do Office 365 e a opção para fornecer e controlar suas próprias chaves de criptografia com a BYOK (traga sua própria chave) para a proteção de informações do Azure não foram projetadas para responder às intimações de aplicação de leis. A criptografia de mensagem do Office 365 com o BYOK para o AIP foi projetada para clientes voltados à conformidade que precisam atender às obrigações de conformidade internas ou externas. A Microsoft leva muito seriamente as solicitações de terceiros para os dados dos clientes. Como um provedor de serviços de nuvem, sempre defendemos a privacidade dos dados do cliente. No evento, obtemos uma intimação, tentamos sempre redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [proteção dos dados do cliente a partir do rastreamento governamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos periodicamente informações detalhadas sobre a solicitação que recebemos [aqui](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data).
  
Consulte a [central de confiabilidade da Microsoft](https://www.microsoft.com/trustcenter/default.aspx) sobre solicitações de dados de terceiros e "divulgação de dados do cliente" nos [termos dos serviços online (OST) ](https://www.microsoft.com/Licensing/product-licensing/products.aspx)para obter mais informações.
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>A criptografia de serviço com a chave do cliente altera a abordagem da Microsoft para solicitações de dados de terceiros, como intimações?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Não. A chave do cliente não foi projetada para responder às intimações de imposição de leis. Ele foi projetado para clientes regulamentados para atender às obrigações de conformidade internas ou externas. A Microsoft leva muito seriamente as solicitações de terceiros para os dados dos clientes. Como um provedor de serviços de nuvem, sempre defendemos a privacidade dos dados do cliente. No evento, obtemos uma intimação, tentamos sempre redirecionar o terceiro para o cliente para obter as informações. (Leia o blog de Brad Smith: [proteção dos dados do cliente a partir do rastreamento governamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos periodicamente informações detalhadas sobre a solicitação que recebemos [aqui](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data).
  
Consulte a [central de confiabilidade da Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) sobre solicitações de dados de terceiros e "divulgação de dados do cliente" nos [termos dos serviços online (OST)](https://www.microsoft.com/Licensing/product-licensing/products.aspx) para obter mais informações. 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>O suporte ao FastTrack está disponível para a implementação da chave do cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Não. O FastTrack é usado apenas para coletar informações de configuração de locatários e serviços necessárias para registrar-se na chave do cliente. As ofertas de chave do cliente são publicadas via FastTrack para que os clientes e parceiros enviem essas informações necessárias usando o mesmo método e para facilitar o arquivamento de dados que os clientes fornecem na oferta.
  
Se você precisar de suporte adicional além da documentação, entre em contato com a MCS (serviços de consultoria da Microsoft), PFE (Engenharia de campo Premier) ou um parceiro da Microsoft para obter assistência.
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>Se minhas chaves forem destruídas, como posso recuperar?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

A chave de disponibilidade fornece a capacidade de se recuperar da perda não prevista de chaves raiz que você gerencia. Se você perder suas chaves raiz, entre em contato com o suporte da Microsoft e a Microsoft ajudará você durante o processo de habilitação da chave de disponibilidade. Você usará a chave de disponibilidade para migrar para uma nova política de criptografia de dados com novas chaves configuradas por você. 
  
## <a name="what-is-the-availability-key"></a>O que é a chave de disponibilidade?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

A chave de disponibilidade é uma chave raiz que é configurada quando você cria uma política de criptografia de dados. A chave de disponibilidade é armazenada e protegida no Office 365 e é funcionalmente parecida com as duas chaves raiz fornecidas por você para uso com a chave de serviço com o cliente. Diferentemente das chaves que você fornece e gerencia no Azure Key Vault, não é possível acessar diretamente a chave de disponibilidade. O armazenamento e o controle da chave de disponibilidade são deliberadamente diferentes das chaves do Azure Key Vault por três motivos: primeiro, a chave de disponibilidade fornece uma capacidade de alta disponibilidade no caso de os serviços do Office 365 não serem capazes de alcançar chaves hospedadas na chave do Azure Compartimentaliza em segundo lugar, a chave de disponibilidade fornece uma capacidade de "ruptura" no caso de as chaves do Azure Key Vault serem perdidas; e terceiro, a separação de controles lógicos fornece proteção em camadas e protege contra a perda de todas as chaves de um único ataque ou ponto de falha. Compartilhar a responsabilidade para proteger as chaves, ao usar uma variedade de proteções e processos para o gerenciamento de chaves, reduz o risco de que todas as chaves (e, portanto, seus dados) sejam perdidas ou destruídas. A Microsoft fornece autoridade única sobre a destruição da chave de disponibilidade. Por design, ninguém da Microsoft tem acesso à chave de disponibilidade-ela é acessível apenas pelo código de serviço do Office 365.
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>Quantas políticas de criptografia de dados (DEPs) posso criar?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for Business:** Você pode criar até 50 DEPs. 
  
 **SharePoint Online e onedrive for Business:** Uma DEP aplica-se aos dados em um local geográfico, também chamado de uma geografia. Se você usar o recurso multigeográfico do Office 365, poderá criar uma DEP por Geo. Se você não estiver usando o multigeográfico, você pode criar um DEP.
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>Posso atribuir uma política de criptografia de dados antes de migrar uma caixa de correio para a nuvem?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Sim. Você pode usar o cmdlet do Windows PowerShell Set-MailUser para atribuir uma DEP (política de criptografia de dados) ao usuário antes de migrar a caixa de correio para o Office 365. Ao fazer isso, o conteúdo da caixa de correio será criptografado usando a DEP atribuída à medida que o conteúdo for migrado. Isso pode ser mais eficiente do que a atribuição de uma DEP após a caixa de correio já ter sido migrada e, em seguida, aguardar a criptografia ocorrer, o que pode levar horas ou possivelmente dias. 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>Como verifico se a chave de criptografia com o cliente está ativada e o Office 365 terminou a criptografia com a chave do cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for Business:** Você pode [se conectar ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) e, em seguida, usar o cmdlet **[Get-MailboxStatistics]** para cada caixa de correio que você deseja verificar. Na saída do cmdlet Get-MailboxStatistics, a propriedade _IsEncrypted_ retornará um valor **true** se a caixa de correio for criptografada e um valor **false** se não for. Se a caixa de correio estiver criptografada, o valor retornado para a propriedade _DataEncryptionPolicyID_ será o GUID da DEP com a qual a caixa de correio será criptografada. Para obter mais informações sobre a execução deste cmdlet, consulte [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx) e using PowerShell with Exchange Online. 
  
Se as caixas de correio não são criptografadas após esperar 72 horas a partir do momento em que você atribuiu a DEP, inicie uma movimentação de caixa de correio. Para fazer isso, [Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) e use o cmdlet New-MoveRequest e forneça o alias da caixa de correio da seguinte maneira: 
  
```powershell
New-MoveRequest <alias>
```

 **SharePoint Online e onedrive for Business:** Você pode [se conectar ao PowerShell do SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx)e usar o cmdlet **[Get-SPODataEncryptionPolicy]** para verificar o status do seu locatário. A propriedade * * _State_* * retornará um valor **registrado** se a criptografia de chave do cliente estiver habilitada e todos os arquivos em todos os sites tiverem sido criptografados. Se a criptografia ainda estiver em andamento, este cmdlet fornecerá informações sobre a porcentagem de sites concluído. 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>Se eu quiser mudar para um conjunto diferente de chaves, quanto tempo demora para o novo conjunto de chaves proteger meus dados?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for Business:** Pode levar até 72 horas para proteger uma caixa de correio de acordo com uma nova DEP (política de criptografia de dados), desde o momento em que a nova DEP é atribuída à caixa de correio. 
  
 **SharePoint Online e onedrive for Business:** Pode levar até quatro horas para criptografar novamente o locatário inteiro depois que uma nova chave é atribuída. 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>Meus dados existentes são armazenados sem criptografia a qualquer momento enquanto são descriptografados ou criptografados com a chave do cliente?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Não. Seus dados são sempre criptografados em repouso no serviço do Office 365 com o BitLocker e o DKM. Para obter mais informações, consulte as informações sobre segurança, privacidade e conformidade do Office 365 ", e [como o Exchange Online protege seus segredos de email](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376).
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>Se não quiser mais usar as chaves de criptografia gerenciadas pelo cliente, posso alternar para chaves gerenciadas pela Microsoft?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for Business:** Ainda não. Isso será suportado uma vez que a criptografia de serviço no Office 365 com chaves gerenciadas pela Microsoft seja distribuída de forma ampla. Esperamos revertê-lo no serviço depois de lançar a criptografia de serviço com a chave do cliente. 
  
 **SharePoint Online e onedrive for Business:** Sim. Você pode optar por reverter o uso de teclas gerenciadas pela Microsoft separadamente para cada Geografia (se você usar o recurso multigeográfico) ou para todos os seus dados se ele estiver em uma única geografia. 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>Se eu perder minhas chaves, quanto tempo demora para recuperar a disponibilidade do serviço usando a chave de recuperação?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online e Skype for Business:** Depois que você ligar para usar a chave de disponibilidade, as caixas de correio poderão ser acessadas em minutos. 
  
 **SharePoint Online e onedrive for Business:** Essa operação é proporcional ao número de sites que você tem. Após ligar para a Microsoft para usar a chave de disponibilidade, você estará totalmente online em cerca de quatro horas. 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>Como a chave de disponibilidade é usada com o Exchange Online?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Há três maneiras de a chave de disponibilidade ser usada com o Exchange Online:
  
- Disponibilidade do serviço-no caso em que as chaves do Azure Key Vault não estão acessíveis.
    
- Ações iniciadas pelo código de serviço do Office 365, como a criação de índice de pesquisa ou movimentação de caixa de correio.
    
- Recuperar da perda de chave, como a perda das chaves do Azure Key Vault associadas a uma única DEP.
    
 **O uso da chave de disponibilidade para disponibilidade de serviço nas chaves do Azure Key Vault não estão acessíveis.**
  
O Office 365 usa a chave de disponibilidade para disponibilidade de serviço e recuperação de um estado de chave do cliente não íntegro para o Exchange Online. Há uma hierarquia de chaves usadas pela chave do cliente. Essa hierarquia é ilustrada na figura a seguir.
  
![Um gráfico mostra a hierarquia das chaves na chave do cliente](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Se as chaves do Azure Key Vault de uma única diretiva de criptografia de dados (DEP) não estiverem disponíveis, o Office 365 poderá usar a chave de disponibilidade para mudar para uma nova DEP. O Office 365 determina se deve ser usada a chave de disponibilidade para disponibilidade de serviço de maneira diferente, dependendo se uma atividade iniciada pelo usuário, por exemplo, quando um usuário baixa emails para o cliente do Outlook ou uma atividade iniciada pelo sistema, como indexação conteúdo da caixa de correio ou para pesquisas de descoberta eletrônica, disparou o processo.
  
O Office 365 segue esse processo em resposta às ações iniciadas pelo usuário para determinar se deve usar a chave de disponibilidade para caixas de correio do usuário:
  
1. O Office 365 lê a DEP à qual a caixa de correio é atribuída para determinar o local das duas chaves do cliente no Azure Key Vault.
    
2. O Office 365 escolhe aleatoriamente uma das duas chaves de cliente da DEP e envia uma solicitação para o Azure Key Vault para desencapsular a chave DEP usando a chave do cliente.
    
3. Se a solicitação para desencapsular a chave DEP usando a chave do cliente falhar e retornar um erro, o Office 365 enviará uma segunda solicitação ao Azure Key Vault, desta vez instruindo-o a usar a chave alternativa (segundo) do cliente.
    
4. Se a segunda solicitação para desencapsular a chave DEP usando a chave do cliente falhar e retornar um erro, o Office 365 examinará os resultados das duas solicitações:
    
  - Se o exame determinar que os erros não refletem uma ação explícita por uma identidade de cliente, o Office 365 usa a chave de disponibilidade para descriptografar a chave DEP. A chave DEP é usada para descriptografar a chave da caixa de correio e concluir a solicitação do usuário.
    
    Nesse caso, o Azure Key Vault não pode responder ou inacessível por qualquer motivo. O Office 365 não tem como determinar se o cliente revogou intencionalmente o acesso às chaves.
    
  - Se o exame indicar que a ação deliberada foi tomada para renderizar as chaves do cliente indisponíveis, a chave de disponibilidade não será usada, a solicitação do usuário falhará e o usuário receberá uma mensagem de erro, como falha de logon.
    
    Quando isso acontece, o cliente está ciente de que o serviço é afetado e a condição da chave do cliente não é íntegra. Por exemplo, se um cliente está usando uma única DEP para todas as caixas de correio na organização, o cliente pode experimentar uma falha abrangente, onde os usuários não podem acessar suas caixas de correio. Isso garante que, quando as duas chaves do cliente não estiverem saudáveis, o cliente tenha consciência da necessidade de corrigir a situação e restaurar o serviço para um estado íntegro.
    
 **Usando a chave de disponibilidade para ações iniciadas pelo código de serviço do Office 365.**
  
O código de serviço do Office 365 sempre tem um token de logon válido e não pode ser bloqueado. Portanto, até que a chave de disponibilidade tenha sido excluída, ela pode ser usada para ações iniciadas por ou do código de serviço interno do Office 365, como a criação de índice de pesquisa ou a movimentação de caixas de correio.
  
 **Usando a chave de disponibilidade para recuperar da perda de chave.**
  
Você pode usar a chave de disponibilidade para se recuperar da perda das chaves do Azure Key Vault que estão associadas à mesma DEP, conforme descrito na resposta à entrada de perguntas frequentes "se minhas chaves forem destruídas, como posso recuperar?".
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>Como a chave de disponibilidade é usada com o SharePoint Online e o OneDrive for Business?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

A arquitetura e a implementação do SharePoint Online e do OneDrive for Business para a chave de disponibilidade e a chave do cliente são diferentes do Exchange Online e do Skype for Business.
  
Quando um cliente se move para chaves gerenciadas pelo cliente, o Office 365 cria uma chave intermediária específica do locatário (TIK). O Office 365 criptografa o TIK duas vezes, uma vez com cada uma das chaves do cliente e armazena as duas versões criptografadas do TIK. Somente as versões criptografadas do TIK são armazenadas, e um TIK só pode ser descriptografado com as chaves do cliente. O TIK é usado para criptografar chaves de site, que são usadas para criptografar chaves de BLOB. Os BLOBs em si são criptografados e armazenados no serviço de armazenamento de blob do Microsoft Azure.
  
O Office 365 segue esse processo para acessar um blob que tem dados de arquivo de cliente:
  
1. Descriptografar o TIK usando a chave do cliente.
    
2. Use o TIK descriptografado para descriptografar uma chave de site.
    
3. Use a chave do site descriptografado para descriptografar uma chave blob.
    
4. Use a chave do blob descriptografado para descriptografar o blob.
    
Ao descriptografar um TIK, o Office 365 emite duas solicitações de descriptografia ao Azure Key Vault com um ligeiro deslocamento. O primeiro a concluir fornece o resultado, cancelando a outra solicitação.
  
Caso o cliente perca o acesso às chaves do cliente, o Office 365 também criptografa o TIK com uma chave de disponibilidade e o armazena junto com o TIKs criptografado com cada chave do cliente. O TIK criptografado com a chave de disponibilidade é usado somente quando o cliente chama a Microsoft para inscrever o caminho de recuperação quando perdeu o acesso às suas chaves, de forma mal-intencionada ou acidental.
  
Por motivos de disponibilidade e escala, os TIKs descriptografados são armazenados em cache em um cache de memória limitado por tempo. Duas horas antes de um cache do TIK ser definido como expirar, o Office 365 tenta descriptografar cada TIK. Descriptografar o TIKs estende o tempo de vida do cache. Se a descriptografia do TIK falhar por um período significativo, o Office 365 gerará um alerta para notificar a engenharia antes da expiração do cache. Somente se o cliente chamar a Microsoft, o Office 365 iniciará a operação de recuperação, que envolve a descriptografia do TIK com a chave de disponibilidade armazenada no repositório secreto da Microsoft e a integração do locatário novamente usando o TIK descriptografado e um novo conjunto de chaves do Azure Key Vault fornecidas pelo cliente.
  
A partir de hoje, a chave do cliente está envolvida na cadeia de criptografia e descriptografia dos dados de arquivo do SharePoint Online armazenadas no repositório de blob do Azure, mas não no SharePoint Online itens de lista ou metadados armazenados no banco de dados SQL. O Office 365 não usa a chave de disponibilidade para o SharePoint Online ou o OneDrive for Business diferente do caso descrito acima, que é iniciado pelo cliente. O acesso humano aos dados do cliente é protegido por Lockbox de cliente.
  
## <a name="how-is-customer-key-licensed"></a>Como a chave do cliente é licenciada?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

A chave do cliente é oferecida no pacote corporativo do Office 365, "E5" e a SKU de conformidade avançada. Além disso, os clientes também devem adquirir a licença apropriada para usar o Azure Key Vault.
  
Cada usuário que se beneficia da chave do cliente deve ser licenciado se eles quiserem ser cobertos pela chave do cliente.
  
Para o SharePoint Online, o administrador do Office 365 que configura a chave do cliente também precisa ser licenciado para executar as etapas de configuração. Além disso, os usuários que estão se beneficiando do recurso precisam ser licenciados: isso inclui o proprietário do site e todos os usuários que acessam arquivos em um ou mais sites que são criptografados usando a chave do cliente. Os usuários externos não precisam ser licenciados para acessar arquivos em um ou mais sites que são criptografados usando a chave do cliente.
  
Para o Exchange Online, as caixas de correio de "usuário" e as caixas de correio "usuário de email" devem ser licenciadas. Todos os outros, como caixas de correio compartilhadas, não precisam ter uma licença para a chave do cliente. Para verificar se a caixa de correio do Exchange Online está devidamente licenciada, execute o seguinte cmdlet:
  
```powershell
(Get-Mailbox <alias >).PersistedCapabilities
```

Se a cadeia de caracteres BPOS_S_EquivioAnalytics existir, a caixa de correio será devidamente licenciada. Caso contrário, você deve aplicar a licença adequada para usar o recurso de chave do cliente para esta caixa de correio.
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>É possível habilitar a chave do cliente para uma assinatura de avaliação?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Não. Por definição, as assinaturas de avaliação têm um tempo de vida limitado. Chaves de criptografia hospedadas em assinaturas de avaliação podem ser perdidas no final da vida útil da avaliação. Como a Microsoft não pode e não impede que os clientes coloquem dados importantes do cliente em assinaturas de avaliação, o uso da chave do cliente com assinaturas de avaliação é proibido.
  
## <a name="how-much-will-using-customer-key-cost"></a>Quanto o custo da chave do cliente será usado?
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Além do licenciamento necessário para a chave do cliente, os clientes incorrerão em um custo para o uso do cofre de chaves. Os [detalhes de preços do Azure Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) descrevem o modelo de custo e ajudarão na estimativa. Não há uma maneira de prever o custo exato que qualquer cliente se incorrerá porque os padrões de uso variam. A experiência mostrou que o custo é muito baixo e geralmente está dentro do intervalo de $0.02 a $0.05 por usuário, mais o custo de chaves com suporte a HSM. O custo também variará de acordo com a configuração de registro em log escolhida pelo cliente e a quantidade de armazenamento do Azure usada para os logs do Azure Key Vault. 
  
## <a name="for-more-information"></a>Para obter mais informações
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

Para começar a usar a chave do cliente, consulte [controle dos dados no Office 365 usando a chave do cliente](controlling-your-data-using-customer-key.md).
  

