---
title: Sincronização de hash de senha para ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Resumo: configurar e demonstrar a sincronização de hash de senha e a entrada para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487453"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronização de hash de senha para ambiente de teste do Microsoft 365

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na floresta local dos Serviços de domínio Active Directory (AD DS) local com o conjunto de contas no locatário do Azure AD da assinatura do Microsoft 365. 

Este artigo descreve como você pode adicionar a sincronização de hash de senha ao seu ambiente de teste do Microsoft 365, que resulta nesta configuração:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Configurar esse ambiente de teste envolve três fases:
- [Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2 – Criar e registrar o domínio testlab](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3 – Instalar o Azure AD Connect na APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365

Siga as instruções em [configuração da base corporativa simulada para o Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). A configuração resultante tem a seguinte aparência:
  
![A configuração base corporativa simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma rede virtual do Azure. DC1 é um controlador de domínio para o testlab. <*seu nome de domínio público*> domínio do AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2 – Criar e registrar o domínio testlab

Nesta fase, adicione um domínio DNS público e, em seguida, adicione-o à sua assinatura.

Primeiro, trabalhe com seu provedor de registro de DNS público para criar um novo nome de domínio DNS público com base no seu nome de domínio atual e, em seguida, adicione-o à sua assinatura. É recomendável usar o nome **testlab. <*seu domínio* > público**. Por exemplo, se o seu nome de domínio público for ** <span>contoso</span>. com**, adicione o nome de domínio público: ** <span>testlab</span>. contoso.com**.
  
Em seguida, adicione o **testlab. <seu domínio de *domínio* > público** à sua assinatura de avaliação ou pagamento do Microsoft 365 através do processo de registro de domínio. Isso consiste em adicionar outros registros DNS ao **testlab. <*seu domínio de domínio* > público** . Para obter mais informações, consulte [Adicionar um domínio ao Microsoft 365](../admin/setup/add-domain.md).

A configuração resultante tem a seguinte aparência:
  
![O registro do seu nome de domínio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuração consiste em:

- Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab. <*seu nome de domínio público*> registrado.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.

Observe como o testlab. <*seu nome de domínio público*> agora é:

- Compatível com registros DNS públicos.
- Registrado nas assinaturas do Microsoft 365.
- O domínio AD DS na sua intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3 – Instalar o Azure AD Connect na APP1

Nesta fase, instale e configure a ferramenta Azure AD Connect na APP1 e verifique se ela funciona.
  
Primeiro, instale e configure o Azure AD Connect no APP1.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.
    
2. Na área de trabalho da APP1, abra um prompt de comando do Windows PowerShell em nível de administrador e execute esses comandos para desativar a Segurança avançada do Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Na barra de tarefas, selecione **Internet Explorer** e vá para [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Na página do Microsoft Azure Active Directory Connect, selecione **Download**e, em seguida, selecione **executar**.
    
5. Na página **Bem-vindo ao Azure ad Connect** , selecione **concordo**e selecione **continuar**.
    
6. Na página **configurações expressas** , selecione **usar configurações expressas**.
    
7. Na página **conectar ao Azure ad** , insira o nome da conta de administrador global em **nome de usuário,** digite a senha em **senha**e selecione **Avançar**.
    
8. Na página **conectar-se ao AD DS** , **digite TESTLAB \\ Usuário1** em **nome de usuário,** digite a senha em **senha**e, em seguida, selecione **Avançar**.
    
9. Na página **pronto para configurar** , selecione **instalar**.
    
10. Na página **configuração concluída** , selecione **sair**.
    
11. No Internet Explorer, vá para o centro de administração do Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. No painel de navegação esquerdo, selecione **usuários > usuários ativos**.
    
    Observe a conta denominada **Usuario1**. Essa conta fica no domínio TESTLAB do AD DS e é uma prova de que a sincronização de diretórios funcionou.
    
13. Selecione a conta **Usuário1** e, em seguida, selecione **licenças e aplicativos**.
    
14. Em **licenças de produto**, selecione seu local (se necessário), desabilite a licença do **Office 365 E5** e habilite a licença do **Microsoft 365 E5** . 

15. Selecione **salvar** na parte inferior da página e selecione **fechar**.
    
Em seguida, teste a capacidade de entrar em sua assinatura com o **user1@testlab. <*o* > ** nome de domínio da conta user1:

1. Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando for solicitado um nome de usuário e uma senha, especifique **user1@testlab. <*seu nome* > de domínio** e a senha do Usuário1. Você deve conseguir entrar como Usuario1.
 
Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global. Portanto, o ícone **Administrador** não estará disponível como opção. 

A configuração resultante tem a seguinte aparência:

![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuração consiste em: 
  
- Microsoft 365 E5 ou Office 365 E5 assinaturas de avaliação ou pagas com o domínio DNS TESTLAB. <*seu nome de domínio*> registrado.
- Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio AD DS do TESTLAB para o locatário do Azure AD da sua assinatura do Microsoft 365.
- A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
