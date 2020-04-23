---
title: Planejar a configuração do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Saiba o que você precisa fazer para configurar seu Microsoft 365 para empresas.
ms.openlocfilehash: d02e1aaf03449bd976b8db549274002b3ebb6ed6
ms.sourcegitcommit: b458277f0a9937555bc6c5b3fb2a41613f7cc9a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "43794024"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planejar a configuração do Microsoft 365 para empresas

Este artigo é para pessoas que assinaram um plano do Microsoft 365 para empresas.
  
Há algumas coisas que você precisa decidir e informações que precisa ter à mão, antes de mover sua organização para o Microsoft 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informações que devem estar disponíveis antes de executar o assistente de configuração

Quando você estiver pronto para executar o assistente de configuração e mover seu domínio para a Microsoft 365, aqui estão as informações que você precisa ter à mão:
  
- Lista de pessoas que você deseja adicionar ao Microsoft 365. Mesmo que você já as tenha adicionado ao Microsoft 365, se estiver atualizando as informações do seu domínio, precisará inserir seus nomes aqui.

- Como você irá notificar seus funcionários sobre sua ID de usuário e senha para que eles possam entrar. Você vai ligar para eles e passar as informações? Ou vai enviá-las para seus endereços de email pessoais? Eles não terão acesso ao email, portanto, você não poderá usá-lo.

- Se você tiver um nome de domínio para sua organização (como contoso.com) **e** planeja usar o email da Microsoft, precisará saber onde seu domínio está registrado e ter informações de logon.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>O que acontece quando você executa o assistente de instalação do Microsoft 365

O assistente de instalação orienta você durante a instalação dos aplicativos do Microsoft 365 em seu computador, adição e verificação de seu domínio, adição de usuários e atribuição de licenças a eles e conexão do seu domínio.

> [!NOTE]
> Se você precisar [atribuir funções de administrador no Microsoft 365 for Business](../add-users/assign-admin-roles.md) aos usuários que você adicionar no assistente, poderá fazer isso mais tarde na página **usuários** . 
  
Se você não concluir o assistente de instalação, poderá concluir as tarefas de configuração a qualquer momento da**configuração**do [Centro](https://go.microsoft.com/fwlink/p/?linkid=2024339) > de administração. Aqui você pode migrar emails e contatos de outro serviço de email, alterar o domínio de sua conta de administrador, gerenciar suas informações de cobrança, adicionar ou remover usuários, redefinir senhas e realizar outras funções de negócios. Para obter mais informações sobre as diferenças entre o assistente de instalação e a página de **configuração** , confira [diferenças entre o assistente de instalação do Microsoft 365 e a página de configuração](o365-setup-wizard-and-setup-page.md).

Se você tiver algum problema, fale conosco. [Estamos aqui para ajudar!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Quando não usar o Assistente de configuração: Sincronização do Active Directory e ambientes híbridos

Há alguns cenários que incluem a migração de dados ou de usuários de ambientes locais ou a configuração de um sistema híbrido que inclui a sincronização de diretórios. Se você estiver em qualquer uma das duas categorias, siga as instruções nestes artigos:
  
- Para configurar a sincronização de diretório com o Active Directory local, confira [Configurar a sincronização de diretórios para o Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)e para entender os diferentes modelos de identidade no Microsoft 365, leia [Understanding Microsoft 365 Identity e Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Para configurar uma implantação híbrida do Exchange, o conjunto completo de instruções que orientam você por todas as diferentes maneiras de configurar um híbrido do Exchange (incluindo a configuração de registros DNS) pode ser encontrado aqui: [Assistente de Implantação do Exchange Server](https://aka.ms/exdeploy)

- Para configurar uma implantação híbrida do SharePoint, especialmente os recursos de site e pesquisa híbridos, confira [Pesquisa Híbrida no SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Mover para o Microsoft 365 tudo de uma só vez ou em estágios

- **Você deseja mover sua organização para a Microsoft 365 todos de uma só vez?** Em caso afirmativo, planeje mover seu domínio para o Microsoft 365 imediatamente. Inicie executando o assistente de instalação do Microsoft 365; ele solicitará que você configure seu domínio.

- **Você deseja mudar para a Microsoft 365 gradativamente?** Se você quiser mudar para o Microsoft 365 em estágios, pule a execução do assistente de instalação do Microsoft 365 e considere a adoção dos recursos do Microsoft 365 na seguinte ordem:

    1. [Adicione seus funcionários ao Microsoft 365](../add-users/add-users.md) para que eles possam baixar e instalar os aplicativos do Office.

    2. [Baixe e instale os aplicativos do Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) para usar o Word, o Excel e o PowerPoint no seu computador e em seus dispositivos.

    3. [Configurar o Microsoft Teams](#plan-for-teams) para usar em suas reuniões.

    4. [Mova o conteúdo para o Microsoft 365 Cloud Storage](set-up-file-storage-and-sharing.md) (onedrive ou sites de equipe do SharePoint).

    5. Quando estiver pronto, no centro de [Administração](https://go.microsoft.com/fwlink/p/?linkid=2024339), selecione **configuração** no painel de navegação esquerdo e use a página de **configuração** para [mover seu domínio e email](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Verificar se seus dispositivos atendem aos requisitos do sistema

Cada pessoa em sua organização pode instalar o pacote de aplicativos do Office 2016 (Word, Excel, PowerPoint e assim por diante) em até cinco PCs e Macs. Veja os requisitos de sistema operacional e de computador para instalar os [pacotes do Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para empresas.
  
Os aplicativos móveis podem ser instalados em dispositivos iOS, Android e Windows. Você pode encontrar informações sobre o suporte a dispositivos móveis e a navegadores em [Requisitos do sistema do Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planejar para o email

Se você estiver planejando migrar de um serviço de email existente para o Microsoft 365, geralmente leva dois dias para fazer a opção.
  
### <a name="plan-for-email-downtime"></a>Planejar o tempo de inatividade de email
  
Se você for usar o Microsoft 365 para o seu email:
  
- Para mover seu endereço de email comercial (como *rob\@contoso.com*) de outro serviço de email para o Microsoft 365, você precisa direcionar seu email para que ele seja entregue em sua nova caixa de correio do Microsoft 365. Para fazer isso, selecione **migrar os dados dos seus usuários** na página de **configuração** , onde orientamos você pelas atualizações que você precisa fazer no seu host de domínio, passo a passo.

- Depois de atualizar o host do seu domínio, as alterações normalmente entrarão em vigor em apenas uma ou duas horas. Mas esteja ciente de que às vezes pode levar até 72 horas para que as alterações sejam atualizadas na Internet.

- Como você pode ter tempo de inatividade de email, recomendamos que você planeje mudar para o email da Microsoft durante uma noite ou em um fim de semana quando receber menos emails.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planejar mover o email , os contatos e o calendário existentes
  
Se você for usar o Microsoft 365 para sua conta de email, poderá trazer seus emails, contatos e calendário existentes com você. A página de **configuração** ajuda você a migrar seus emails e contatos existentes para a maioria dos cenários. Também temos guias passo a passo para migrar uma ou várias caixas de correio.
  
|**Quantas caixas de correio?**|**Recomendação**|
|:-----|:-----|
|Apenas algumas  <br/> |Se não quiser usar a página de **configuração** para migrar as caixas de correio, você poderá permitir que os proprietários da caixa de correio migrem seus próprios emails e contatos. Confira [migrar emails e contatos para a Microsoft 365 para empresas](migrate-email-and-contacts-admin.md).  <br/> |
|Várias  <br/> |Se você estiver migrando do Gmail, consulte [Migrate G Suite Mailboxes to Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Se você estiver migrando de outro provedor de email, incluindo o Exchange, consulte [maneiras de migrar várias contas de email para o Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planejar o armazenamento de arquivos e a migração

O Microsoft 365 fornece armazenamento em nuvem para indivíduos, organizações pequenas e empresas. Para obter orientação sobre o que armazenar onde, confira [onde você pode armazenar documentos no Microsoft 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **Você pode mover centenas de arquivos** para o [onedrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) ou um [site de equipe do SharePoint](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). É possível carregar 100 arquivos de uma só vez. Evite carregar arquivos com mais de 2 GB, que é o tamanho máximo de arquivos por padrão.
  
- **Se você quiser mover vários milhares de arquivos** para o armazenamento da Microsoft 365, revise os [limites do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Recomendamos que você use uma ferramenta de migração ou contrate um [parceiro](https://go.microsoft.com/fwlink/?linkid=391089) para ajudá-lo com a migração. Para obter informações sobre como migrar um grande número de arquivos, confira [Guia do usuário sobre migração do SharePoint Online e do OneDrive](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planejar o Teams

Você pode usar o Microsoft Teams para fazer chamadas para outras pessoas em sua organização que estão na sua assinatura. Por exemplo, se sua organização tiver 10 pessoas, você poderá ligar e enviar mensagens instantâneas usando o Teams sem qualquer configuração especial. Para obter mais informações, consulte [introdução ao Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizações maiores ou se você estiver começando no Skype for Business, no local ou em implantações híbridas, consulte [como implantar o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planejar a integração com o Active Directory ou com outro software

- **Você deseja integrar ao seu Active Directory local?** Você pode integrar seu Active Directory local ao Microsoft 365 usando o Azure Active Directory Connect. Para obter instruções, consulte [set up Directory Synchronization for Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Você deseja integrar o Microsoft 365 com software feito por outras empresas?** Se você precisar integrar o Microsoft 365 com outro software em sua organização, recomendamos que você considere [contratar um parceiro](https://go.microsoft.com/fwlink/?linkid=391089) para ajudá-lo com sua implantação.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Você deseja que alguém o ajude a configurar o Microsoft 365?

- **Se você tiver menos de 50 funcionários:**

  - **Peça ajuda, e entraremos em contato com você**. Depois de comprar o Microsoft 365, você pode acessar o centro de administração (não é necessário executar o programa de instalação para acessá-lo). Na parte inferior do centro de administração, selecione **precisa de ajuda?** Descreva seu problema, e entraremos em contato com você. 
  - **Ligue [para o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md) com suas dúvidas**. Estamos aqui para ajudar! 
  - **Considere a possibilidade de contratar um [parceiro da Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Se você está curto no tempo ou tem requisitos avançados (como mover milhares de arquivos para o armazenamento em nuvem da Microsoft 365 ou integrar com outro software), um parceiro experiente pode ser uma grande ajuda. 

- **Se você tiver mais de 50 funcionários**, o [Centro de Integração do Microsoft FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) está disponível para ajudá-lo com a sua implantação. 
