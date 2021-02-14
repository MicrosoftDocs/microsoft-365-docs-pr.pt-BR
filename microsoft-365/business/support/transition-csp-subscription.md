---
title: Fazer a transição de uma assinatura de CSP do Microsoft 365 Business
description: Descubra como você pode fazer a transição de uma assinatura de CSP do Microsoft 365 Business da visualização para a disponibilidade geral (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
- AdminSurgePortfolio
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, transição de assinatura de CSP
ms.date: 11/01/2017
ms.openlocfilehash: 5fc532b4a59d8e94068e7e1bae99bf8edac75abb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403421"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Fazer a transição de uma assinatura de CSP do Microsoft 365 Business

Se você tiver uma assinatura CSP do Microsoft 365 Business Preview, siga este guia para descobrir como poderá fazer a transição da sua assinatura de versão prévia existente para o Microsoft 365 Business GA (disponibilidade geral).

**Como fazer a transição de uma assinatura da versão prévia para GA**

1. Acesse o <a href="https://partnercenter.microsoft.com" target="_blank">Partner Center</a>.
2. No painel, selecione **Clientes** e então encontre e selecione o nome da empresa.

    As assinaturas da empresa serão listadas.

    ![Assinaturas do cliente no Partner Center](../../media/pc_customer_subscriptions_1.png)
    
3. Na página **Assinaturas da** empresa, selecione **Adicionar assinatura.**
4. Na página **Nova assinatura,** selecione **Small business** e, em seguida, selecione **Microsoft 365 Business** na lista.
5. Adicione o número de licenças e então selecione **Próximo: Revisão** para revisar a assinatura e então escolha **Enviar**.

    ![Examine a nova assinatura do Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    As **Assinaturas baseadas em licença** mostrarão **Microsoft 365 Business Preview** e **Microsoft 365 Business**. Você suspenderá a assinatura de visualização em seguida.

6. Selecione **Microsoft 365 Business Preview**.
7. Na página **Microsoft 365 Business Preview,** selecione **Suspensa** para suspender a assinatura de visualização.

    ![Suspender a assinatura do Microsoft 365 Business Preview](../../media/pc_customer_m365bpreview_suspend.png)

8. Selecione **Enviar** para confirmar.

    Na página **Assinaturas,** confirme se o status do **Microsoft 365 Business Preview** é suspenso. 

    ![Confirmar se o status da assinatura de versão prévia é suspensa](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Opcionalmente, você também pode validar o contrato de licença. Para fazer isso, execute estas etapas:
    1. Selecione **Usuários e licenças** da página **Assinaturas** da empresa.
    2. Na página **Usuários e licenças,** selecione um usuário.
    3. Na página do usuário, verifique a **seção Atribuir licenças** e confirme se ela mostra **o Microsoft 365 Business.**

        ![Confirmar se a licença do Microsoft 365 Business foi atribuída ao usuário](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Impacto nos clientes e usuários durante e após a transição

Não há impacto nos clientes e usuários durante a transição e pós-transição.

## <a name="impact-to-customers-who-dont-transition"></a>Impacto nos clientes que não fizerem a transição

A tabela a seguir resume o impacto nos clientes que não fizerem a transição de uma assinatura do Microsoft 365 Business Preview para uma assinatura do Microsoft 365 Business.

|       | T-0 até T+30     | T+30 até T+60 | T+60 até T+120 | Além de T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Estado** | No período de carência | Expirada      | Desabilitada      | Desprovisionada |
| **Impactos no serviço**                                                        |
| **Portal de administração do Microsoft 365 Business** | Não há impacto na funcionalidade | Não há impacto na funcionalidade | Pode adicionar/excluir usuários, comprar assinaturas.</br> Não é possível atribuir/revogar licenças. | A assinatura do cliente e todos os dados são excluídos. O administrador pode gerenciar outras assinaturas pagas. |
| **Aplicativos do Office**                         | Nenhum impacto no usuário final | Nenhum impacto no usuário final | O Office entra no modo de funcionalidade reduzida.</br> Os usuários podem exibir apenas os arquivos. | O Office entra no modo de funcionalidade reduzida.</br> Os usuários podem exibir apenas os arquivos. |
| **Serviços de nuvem (SharePoint Online, Exchange Online, Skype, Teams e muito mais)** | Nenhum impacto no usuário final | Nenhum impacto no usuário final | Os usuários finais e os administradores não têm acesso aos dados na nuvem. | A assinatura do cliente e todos os dados são excluídos. |
| **Componentes do EM+S** | Não há impacto no administrador</br> Nenhum impacto no usuário final | Não há impacto no administrador</br> Nenhum impacto no usuário final | A funcionalidade não é mais imposta.</br> Consulte [Impactos no dispositivo móvel após a expiração da assinatura](#mobile-device-impacts-upon-subscription-expiration) e [Impactos no computador com Windows 10 após a expiração da assinatura](#windows-10-pc-impacts-upon-subscription-expiration) para obter mais informações. | A funcionalidade não é mais imposta.</br> Consulte [Impactos no dispositivo móvel após a expiração da assinatura](#mobile-device-impacts-upon-subscription-expiration) e [Impactos no computador com Windows 10 após a expiração da assinatura](#windows-10-pc-impacts-upon-subscription-expiration) para obter mais informações. |
| **Windows 10 Business** | Não há impacto no administrador</br> Nenhum impacto no usuário final | Não há impacto no administrador</br> Nenhum impacto no usuário final | A funcionalidade não é mais imposta.</br> Consulte [Impactos no dispositivo móvel após a expiração da assinatura](#mobile-device-impacts-upon-subscription-expiration) e [Impactos no computador com Windows 10 após a expiração da assinatura](#windows-10-pc-impacts-upon-subscription-expiration) para obter mais informações. | A funcionalidade não é mais imposta.</br> Consulte [Impactos no dispositivo móvel após a expiração da assinatura](#mobile-device-impacts-upon-subscription-expiration) e [Impactos no computador com Windows 10 após a expiração da assinatura](#windows-10-pc-impacts-upon-subscription-expiration) para obter mais informações. |
| **Logon do Azure AD em um computador com o Windows 10** | Não há impacto no administrador</br> Nenhum impacto no usuário final | Não há impacto no administrador</br> Nenhum impacto no usuário final | Não há impacto no administrador</br> Nenhum impacto no usuário final | Depois que o locatário é excluído, um usuário pode entrar apenas com credenciais locais. Recrie a imagem do dispositivo se não houver nenhuma credencial local. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Impactos no dispositivo móvel após a expiração da assinatura

A tabela a seguir resume o impacto nas políticas de gerenciamento de aplicativos em dispositivos móveis.

|                            | Experiência totalmente licenciada                      | T+60 dias após a expiração          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Excluir arquivos de trabalho de um dispositivo inativo** | Os arquivos de trabalho são removidos após o número de dias selecionado | Os arquivos de trabalho permanecem em dispositivos pessoais do usuário |
| **Force os usuários a salvar todos os arquivos de trabalho no OneDrive for Business** | Os arquivos de trabalho só podem ser salvos no OneDrive for Business | Os arquivos de trabalho podem ser salvos em qualquer lugar |
| **Criptografar arquivos de trabalho** | Os arquivos de trabalho são criptografados | Os arquivos de trabalho não são mais criptografados.</br> As políticas de segurança são removidas e os dados do Office em apps são removidos. |
| **Exigir PIN ou impressão digital para acessar os aplicativos do Office** | Acesso restrito a apps | Não há restrição de acesso no nível do aplicativo |
| **Redefinir o PIN quando o logon falhar** | Acesso restrito a apps | Não há restrição de acesso no nível do aplicativo |
| **Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos** | É necessário entrar | Não é necessário entrar |
| **Negar o acesso a arquivos de trabalho em dispositivos com jailbreak ou desbloqueados por rooting** | Os arquivos de trabalho não podem ser acessados em dispositivos com jailbroken/rooted | Os arquivos de trabalho podem ser acessados em dispositivos com jailbreak ou desbloqueados por rooting |
| **Permitir que os usuários copiem conteúdo de aplicativos do Office para aplicativos pessoais** | Copiar/colar restrito aos aplicativos disponíveis como parte da assinatura do Microsoft 365 | Copiar/colar disponível para todos os apps |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Impactos no computador com Windows 10 após a expiração da assinatura

A tabela a seguir resume o impacto nas políticas de configuração de dispositivos Windows 10.

|                            | Experiência totalmente licenciada                      | T+60 dias após a expiração          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ajudar a proteger os computadores contra ameaças usando o Windows Defender** | Ativar/desativar está fora do controle do usuário | O usuário pode ativar/desativar o Windows Defender no computador com Windows 10 |
| **Ajudar a proteger os computadores contra ameaças baseadas na Web no Microsoft Edge** | Proteção do computador no Microsoft Edge | O usuário pode ativar/desativar a proteção do computador no Microsoft Edge |
| **Desativar a tela do dispositivo quando ocioso** | O administrador define a política de intervalo de tempo limite da tela | O tempo limite da tela pode ser configurado pelo usuário final |
| **Permitir que os usuários baixem apps da Microsoft Store** | O administrador define se um usuário pode baixar apps da Microsoft Store | O usuário podem baixar apps da Microsoft Store em qualquer ocasião |
| **Permitir que usuários acessem a Cortana** | O administrador define a política de acesso de usuário para a Cortana | Dispositivos de usuário para ativar/desativar a Cortana |
| **Permitir que os usuários recebam dicas e anúncios da Microsoft** | O administrador define a política sobre o usuário receber dicas e anúncios da Microsoft | O usuário pode ativar/desativar dicas e anúncios da Microsoft |
| **Permitir que os usuários copiem conteúdo de aplicativos do Office para aplicativos pessoais** | O administrador define a política para manter os dispositivos Windows 10 atualizados | Os usuários podem decidir quando atualizar o Windows |
