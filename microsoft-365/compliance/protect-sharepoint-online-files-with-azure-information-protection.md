---
title: Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumo: aplique a Proteção de Informações do Azure para proteger arquivos em um site de equipe altamente confidencial do SharePoint Online.'
ms.openlocfilehash: 6302ee8163525502550017f62fe4350645af59b3
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "39630871"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a>Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure

 **Resumo:** aplique a Proteção de Informações do Azure para proteger arquivos em um site de equipe altamente confidencial do SharePoint Online.
  
Use as etapas neste artigo para configurar a Proteção de Informações do Azure para fornecer as permissões para arquivos e a criptografia. Esses arquivos podem ser adicionados a uma biblioteca do SharePoint configurada para proteção altamente confidencial. Em alternativa, você pode abrir um arquivo diretamente do site e usar o cliente da Proteção de Informações do Azure para adicionar criptografia. A proteção de criptografia e permissões acompanha um arquivo mesmo quando ele é baixado do site. 

Essas etapas são parte de uma solução maior de configuração da proteção altamente confidencial para sites do SharePoint e os arquivos dentro desses sites. Para saber mais, confira [Sites e arquivos seguros do SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection). 

Usar a Proteção de Informações do Azure para arquivos no SharePoint Online não é recomendável para todos os clientes, mas é uma opção para os clientes que precisam deste nível de proteção para um subconjunto de arquivos.

Algumas observações importantes sobre esta solução:
- Quando a criptografia da Proteção de Informações do Azure é aplicada aos arquivos armazenados no Office 365, o serviço não pode processar o conteúdo desses arquivos. Coautoria, descoberta eletrônica, pesquisa, Delve e outros recursos de colaboração não funcionam. Políticas DLP só funcionam com metadados (incluindo rótulos do Office 365), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).

- Esta solução exige que um usuário selecione um rótulo que se aplica à proteção da Proteção de Informações do Azure. Se precisar de criptografia automática e da capacidade do SharePoint de indexar e examinar os arquivos, considere usar o Gerenciamento de Direitos de Informação (IRM) no SharePoint Online. Quando você configura uma biblioteca do SharePoint para o IRM, os arquivos são criptografados automaticamente quando são baixados para edição. O IRM do SharePoint inclui limitações que podem influenciar a sua decisão. Para saber mais, confira [Configurar o Gerenciamento de Direitos de Informação (IRM) no Centro de administração do SharePoint](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Configuração de administrador
Primeiro, use as instruções em [Ativar o Azure RMS com o centro de administração do Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) para sua assinatura do Office 365.
  
Em seguida, configure a Proteção de Informações do Azure com uma nova política com escopo e um sub-rótulo para proteção e permissões do seu site de equipe altamente confidencial do SharePoint Online.
  
1. Acesse o centro de administração com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Em uma guia separada do navegador, vá para o Portal do Azure ([https://portal.azure.com](https://portal.azure.com)).
    
3. Se esta é a primeira vez que você configura a Proteção de Informações do Azure, confira estas [instruções](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).

4. No painel de lista, clique em **Todos os serviços**, digite **informações** e clique em **Proteção de Informações do Azure**.

5. Clique em **Rótulos**.
    
6. Clique com o botão direito do mouse no rótulo **Altamente Confidencial** e clique em **Adicionar um sub-rótulo**.
    
7. Digite um nome para o sub-rótulo em **Nome** e uma descrição do sub-rótulo em **Descrição**.
    
8. Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.
    
9. Na seção **Proteção**, clique em **Azure (chave de nuvem)**.
    
10. Na folha **Proteção**, em **Configurações de proteção**, clique em **Adicionar permissões**.
    
11. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em ** Procurar no diretório**.
    
12. No painel **Usuários e Grupos do AAD**, selecione o grupo de acesso de membros do site para seu site de equipe altamente confidencial do SharePoint Online e clique em **Selecionar**.
    
13. Em **Escolher permissões a partir de valores predefinidos ou definir valores personalizados**, clique em **Personalizar** e, em seguida, clique nas caixas de seleção **Exibir Direitos**, **Editar Conteúdo**, **Salvar**, **Responder** e **Responder a Todos**.
    
14. Clique em **OK** duas vezes.
    
15. Na folha **Sub-rótulo**, clique em **Salvar** e em **OK**.

16. Na folha **Proteção de Informações do Azure**, clique em **Políticas > + Adicionar uma nova política**.
    
17. Digite um nome para a nova política no **Nome da política** e uma descrição em **Descrição**.
    
18. Clique em **Selecionar quais usuários ou grupos obtêm esta política > Usuário/ Grupos**, e selecione o grupo de acesso dos membros do site para o site da equipe do SharePoint Online altamente confidencial.
    
19. Clique em **Selecionar > OK**.

20. Clique em **Adicionar ou remover rótulos**. No painel **Política: adicionar ou remover rótulos**, clique no nome de seu novo sub-rótulo e, em seguida, clique em **OK**.   

21. Clique em **Salvar** e em **OK**.
 
## <a name="client-setup"></a>Configuração do cliente
Agora você está pronto para começar a criar documentos e protegê-los com a Proteção de Informações do Azure e seu novo rótulo.
  
Você deve [Instalar o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em seu dispositivo ou computador baseado no Windows. Você pode criar scripts e automatizar a instalação, ou os usuários podem instalar o cliente manualmente. Confira os seguintes recursos:
  
- [O lado do cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [Instalando o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [Página de download para a instalação manual](https://www.microsoft.com/download/details.aspx?id=53018)
    
Depois de instalado, os usuários executam e entram em um aplicativo do Office (como o Microsoft Word) com suas contas do Office 365. A nova barra **Proteção de Informações** permite aos usuários selecionar um novo rótulo. Certifique-se de que os usuários saibam o site da equipe do SharePoint Online e qual rótulo devem usar para proteger os arquivos altamente confidenciais.
  
> [!NOTE]
> Se houver vários sites de equipe do SharePoint Online altamente confidenciais, crie várias políticas de escopo de Proteção de Informações do Azure com sub-rótulos com as configurações acima, com as permissões para cada sub-rótulo definidas para o grupo de acesso de membros do site, de um site específico de equipe do SharePoint Online. 
  
## <a name="adding-permissions-for-external-users"></a>Adicionar permissões para usuários externos
Há duas maneiras para conceder aos usuários externos o acesso aos arquivos protegidos com a Proteção de Informações do Azure. Em ambos os casos, os usuários externos devem ter uma conta do Azure AD. Se os usuários externos não forem membros de uma organização que usa o Azure AD, eles poderão obter uma conta do Azure AD como um indivíduo usando essa página de entrada: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Adicione usuários externos a um grupo do Azure AD usado para configurar a proteção de um rótulo. Você precisará primeiro adicionar a conta como um usuário B2B no seu diretório. Pode levar algumas horas para o [cache de associação de grupo pelo Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection).  
 - Adicione usuários externos diretamente à proteção de rótulo. Você pode adicionar todos os usuários de uma organização (por exemplo, Fabrikam.com), um grupo do Azure AD (como um grupo de finanças dentro de uma organização) ou um usuário. Por exemplo, você pode adicionar uma equipe externa de reguladores á proteção de um rótulo.

## <a name="see-also"></a>Confira também

[Proteger arquivos e sites do SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
