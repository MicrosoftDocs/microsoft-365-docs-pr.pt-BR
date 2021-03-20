---
title: Planejar sua configuração do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Saiba mais sobre os requisitos e considerações para fazer a mudança para o Microsoft 365 para empresas.
ms.openlocfilehash: 7ec1fae211ec42afd510ee431a3ea7e17e2fd16b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914061"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planejar sua configuração do Microsoft 365 para empresas

Este artigo é para pessoas que assinaram um plano do Microsoft 365 para empresas.
  
Antes de mover sua organização para o Microsoft 365, há requisitos que você precisa atender, informações que você precisa ter em mãos e decisões que você precisa tomar.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informações para ter em mãos antes de executar o assistente de instalação

Quando você estiver pronto para executar o assistente de instalação e mover seu domínio para o Microsoft 365, aqui estão as informações que você precisará ter em mãos:
  
- Lista de pessoas que você deseja adicionar ao Microsoft 365. Mesmo que você já as tenha adicionado ao Microsoft 365, se estiver atualizando suas informações de domínio, você precisará inserir seus nomes aqui.

- Como você notificará seus funcionários sobre sua ID de usuário e senha para que eles possam entrar. Você vai ligar para eles e passar as informações? Ou vai enviá-las para seus endereços de email pessoais? Eles não terão acesso ao email, portanto, você não pode usá-lo.

- Se você tiver um nome de domínio para sua organização (como **contoso.com)** e planeja usar o email da Microsoft, precisará saber onde seu domínio está registrado e ter informações de login.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>O que acontece quando você executar o assistente de configuração do Microsoft 365

O assistente de instalação orienta você a instalar os aplicativos do Microsoft 365 em seu computador, adicionar e verificar seu domínio, adicionar usuários e atribuir licenças a eles e conectar seu domínio.

> [!NOTE]
> Se você precisar atribuir funções de administrador no [Microsoft 365](../add-users/assign-admin-roles.md) para empresas aos usuários que você adiciona ao assistente, poderá fazer isso posteriormente na página **Usuários.** 
  
Se você não concluir o assistente de instalação, poderá concluir as tarefas de instalação a qualquer momento a partir da Instalação [do Centro de](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **administração.** A partir daqui, você pode migrar emails e contatos de outro serviço de email, alterar o domínio da sua conta de administrador, gerenciar suas informações de cobrança, adicionar ou remover usuários, redefinir senhas e fazer outras funções comerciais. Para obter mais informações sobre as  diferenças entre o assistente de instalação e a página de Instalação, consulte Diferenças entre o assistente de configuração do [Microsoft 365](o365-setup-wizard-and-setup-page.md)e a página De instalação .

Se você tiver algum problema, fale conosco. [Estamos aqui para ajudar!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Quando não usar o Assistente de configuração: Sincronização do Active Directory e ambientes híbridos

Há alguns cenários que incluem migrar dados ou usuários de ambientes locais ou configurar um sistema híbrido que inclui a sincronização de diretórios. Se você estiver em uma das categorias, siga as instruções nestes artigos:
  
- Para configurar a sincronização de diretórios com o Active Directory local, consulte Configurar a sincronização de diretórios para [o Microsoft 365](../../enterprise/set-up-directory-synchronization.md)e para entender os diferentes modelos de identidade no Microsoft 365, leia Noções básicas sobre a identidade do Microsoft 365 e o [Azure Active Directory.](../../enterprise/about-microsoft-365-identity.md)

- Para configurar uma implantação híbrida do Exchange, o conjunto completo de instruções que orientam você por todas as diferentes maneiras de configurar um híbrido do Exchange (incluindo a configuração de registros DNS) pode ser encontrado aqui: [Assistente de Implantação do Exchange Server](/exchange/exchange-deployment-assistant)

- Para configurar uma implantação híbrida do SharePoint, especialmente os recursos de site e pesquisa híbridos, confira [Pesquisa Híbrida no SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Mover para o Microsoft 365 de uma só vez ou em estágios

- **Deseja mover sua organização para o Microsoft 365 de uma só vez?** Em caso afirmado, planeje mover seu domínio para o Microsoft 365 imediatamente. Inicie executando o assistente de configuração do Microsoft 365; ele solicitará que você configurar seu domínio.

- **Deseja mudar para o Microsoft 365 gradualmente?** Se você quiser mudar para o Microsoft 365 em estágios, ignore a execução do assistente de configuração do Microsoft 365 e considere adotar recursos do Microsoft 365 na seguinte ordem:

    1. [Adicione seus funcionários ao Microsoft 365](../add-users/add-users.md) para que eles possam baixar e instalar os aplicativos do Office.

    2. [Baixe e instale os aplicativos do Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para usar o Word, o Excel e o PowerPoint no seu computador e em seus dispositivos.

    3. [Configurar o Microsoft Teams para](#plan-for-teams) usar em suas reuniões.

    4. [Mova seu conteúdo para o armazenamento em nuvem do Microsoft 365](set-up-file-storage-and-sharing.md) (sites de equipe do OneDrive ou do SharePoint).

    5. Quando estiver pronto, no centro de  [administração,](https://go.microsoft.com/fwlink/p/?linkid=2024339)selecione Configurar no painel  de navegação esquerdo e use a página Instalação para mover seu [domínio e email.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Verificar se seus dispositivos atendem aos requisitos do sistema

Cada pessoa em sua organização pode instalar o pacote de aplicativos do Office 2016 (Word, Excel, PowerPoint e assim por diante) em até cinco computadores e Macs. Veja os requisitos de sistema operacional e de computador para instalar os [pacotes do Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para empresas.
  
Aplicativos móveis podem ser instalados em dispositivos iOS, Android e Windows. Você pode encontrar informações sobre o suporte a dispositivos móveis e a navegadores em [Requisitos do sistema do Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planejar para o email

Se você estiver planejando mudar de um serviço de email existente para o Microsoft 365, geralmente leva dois dias para fazer a troca.
  
### <a name="plan-for-email-downtime"></a>Planejar o tempo de inatividade de email
  
Se você vai usar o Microsoft 365 para seu email:
  
- Para mover seu endereço de email comercial (como roubar *\@ contoso.com*) de outro serviço de email para o Microsoft 365, você precisa direcionar seu email para ser entregue à sua nova caixa de correio do Microsoft 365. Você faz isso **selecionando Migrar** os  dados de seus usuários na página Instalação, onde o orientamos pelas atualizações que você precisa fazer no host de domínio, passo a passo.

- Depois de atualizar o host do seu domínio, as alterações normalmente entrarão em vigor em apenas uma ou duas horas. Mas esteja ciente de que às vezes pode levar até 72 horas para que as alterações sejam atualizadas na Internet.

- Como você pode ter tempo de inatividade de email, recomendamos que você planeje mudar para o email da Microsoft durante uma noite ou fim de semana quando receber menos emails.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planejar mover o email , os contatos e o calendário existentes
  
Se você vai usar o Microsoft 365 para sua conta de email, pode levar seus emails, contatos e calendário existentes com você. A **página Instalação** ajuda você a mover seus emails e contatos existentes para a maioria dos cenários. Também temos guias passo a passo para migrar uma ou várias caixas de correio.
  
|**Quantas caixas de correio?**|**Recomendação**|
|:-----|:-----|
|Apenas algumas  <br/> |Se você não quiser usar  a página De instalação para migrar as caixas de correio, poderá permitir que os proprietários da caixa de correio migrem seus próprios emails e contatos. Consulte [Migrar emails e contatos para o Microsoft 365 para empresas.](migrate-email-and-contacts-admin.md)  <br/> |
|Várias  <br/> |Se você estiver migrando do Gmail, consulte [Migrate G Suite mailboxes to Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Se você estiver migrando de outro provedor de email, incluindo o Exchange, consulte Maneiras de migrar várias contas de [email para o Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planejar o armazenamento de arquivos e a migração

O Microsoft 365 fornece armazenamento em nuvem para indivíduos, pequenas organizações e empresas. Para obter orientações sobre o que armazenar onde, consulte [Onde você pode armazenar documentos no Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Você pode mover centenas de arquivos para** o [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) ou para um [site de equipe do SharePoint.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) É possível carregar 100 arquivos de uma só vez. Evite carregar arquivos com mais de 2 GB, que é o tamanho máximo de arquivos por padrão.
  
- **Se você quiser mover vários milhares de arquivos** para o armazenamento do Microsoft 365, revise os Limites do [SharePoint Online.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) Recomendamos que você use uma ferramenta de migração ou contrate um [parceiro](https://go.microsoft.com/fwlink/?linkid=391089) para ajudá-lo com a migração. Para obter informações sobre como migrar um grande número de arquivos, confira [Guia do usuário sobre migração do SharePoint Online e do OneDrive](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Planejar o Teams

Você pode usar o Microsoft Teams para fazer chamadas para outras pessoas em sua organização que estão em sua assinatura. Por exemplo, se sua organização tiver 10 pessoas, você poderá chamar e fazer um IM entre si usando o Teams sem qualquer configuração especial. Para obter mais informações, [consulte Get started with Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizações maiores ou se você estiver começando do Skype for Business, implantações locais ou híbridas, consulte [How to roll out Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planejar a integração com o Active Directory ou com outro software

- **Você deseja integrar ao seu Active Directory local?** Você pode integrar seu Active Directory local com o Microsoft 365 usando o Azure Active Directory Connect. Para obter instruções, consulte [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md).
  
- **Deseja integrar o Microsoft 365 com softwares feitos por outras empresas?** Se você precisar integrar o Microsoft 365 com outros [](https://go.microsoft.com/fwlink/?linkid=391089) softwares em sua organização, recomendamos que você considere contratar um parceiro para ajudá-lo com sua implantação.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Você deseja que alguém ajude você a configurar o Microsoft 365?

- **Se você tiver menos de 50 funcionários:**

  - **Peça ajuda, e entraremos em contato com você**. Depois de comprar o Microsoft 365, você pode acessar o centro de administração (não é necessário executar a instalação para chegar a ele). Na parte inferior do centro de administração, selecione **Precisa de ajuda?** Descreva seu problema, e entraremos em contato com você. 
  - **Chame [o Microsoft 365 for Business Support](../contact-support-for-business-products.md) com suas perguntas.** Estamos aqui para ajudar! 
  - **Considere a possibilidade de contratar um [parceiro da Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Se você tiver pouco tempo ou tiver requisitos avançados (como mover milhares de arquivos para o armazenamento em nuvem do Microsoft 365 ou se integrar a outros softwares), um parceiro experiente pode ser uma grande ajuda. 

- **Se você tiver mais de 50 funcionários**, o [Centro de Integração do Microsoft FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) está disponível para ajudá-lo com a sua implantação.