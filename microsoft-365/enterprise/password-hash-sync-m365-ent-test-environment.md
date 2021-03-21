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
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921499"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronização de hash de senha para ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e office 365 Enterprise.*

Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na floresta local dos Serviços de domínio Active Directory (AD DS) local com o conjunto de contas no locatário do Azure AD da assinatura do Microsoft 365. 

Este artigo descreve como você pode adicionar a sincronização de hash de senha ao seu ambiente de teste do Microsoft 365, o que resulta nessa configuração:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
A configuração desse ambiente de teste envolve três fases:
- [Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2 – Criar e registrar o domínio testlab](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3 – Instalar o Azure AD Connect na APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365

Siga as instruções na [configuração de base corporativa simulada para o Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Sua configuração resultante tem esta aparência:
  
![A configuração base corporativa simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em:
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma rede virtual do Azure. DC1 é um controlador de domínio para testlab.<*seu nome* de domínio público> domínio do AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2 – Criar e registrar o domínio testlab

Nesta fase, adicione um domínio DNS público e adicione-o à sua assinatura.

Primeiro, trabalhe com seu provedor de registro DNS público para criar um novo nome de domínio DNS público baseado no seu nome de domínio atual e, em seguida, adicione-o à sua assinatura. Recomendamos usar o nome **testlab.<*seu domínio público* >**. Por exemplo, se seu nome de domínio público for **<span>contoso</span>.com**, adicione o nome de domínio público: **<span>testlab</span>.contoso.com**.
  
Em seguida, adicione **o  > testlab.<** seu domínio público à sua avaliação do Microsoft 365 ou assinatura paga passando pelo processo de registro de domínio. Isso consiste em adicionar registros DNS adicionais ao **testlab.<*domínio* >** público. Para obter mais informações, [consulte Adicionar um domínio ao Microsoft 365](../admin/setup/add-domain.md).

Sua configuração resultante tem esta aparência:
  
![O registro do seu nome de domínio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuração consiste em:

- Uma avaliação do Microsoft 365 E5 ou assinatura paga com o domínio DNS testlab.<seu nome *de domínio* público> registrado.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.

Observe como o testlab.<*nome de domínio* público> agora:

- Compatível com registros DNS públicos.
- Registrado nas assinaturas do Microsoft 365.
- O domínio AD DS na sua intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3 – Instalar o Azure AD Connect na APP1

Nesta fase, instale e configure a ferramenta do Azure AD Connect no APP1 e verifique se ela funciona.
  
Primeiro, instale e configure o Azure AD Connect no APP1.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.
    
2. Na área de trabalho da APP1, abra um prompt de comando do Windows PowerShell em nível de administrador e execute esses comandos para desativar a Segurança avançada do Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Na barra de tarefas, selecione **Internet Explorer** e vá para [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. Na página Conexão do Microsoft Azure Active Directory, selecione **Baixar** e, em seguida, selecione **Executar**.
    
5. Na página **Bem-vindo ao Azure AD Connect,** selecione **Eu concordo** e selecione **Continuar**.
    
6. Na página **Configurações expressas,** selecione **Usar configurações expressas**.
    
7. Na página **Conectar-se ao Azure AD,** insira o nome da sua conta de administrador global em Nome de **Usuário,** insira sua senha em **Senha** e selecione **Próximo**.
    
8. Na página **Conectar-se ao AD DS,** insira **TESTLAB \\ User1** em Nome de **Usuário,** insira sua senha em **Senha** e selecione **Próximo**.
    
9. Na página **Pronto para configurar,** selecione **Instalar**.
    
10. Na página **Configuração completa,** selecione **Sair**.
    
11. No Internet Explorer, vá para o centro de administração do Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. No painel de navegação esquerdo, selecione **Usuários > usuários ativos**.
    
    Observe a conta denominada **Usuario1**. Essa conta fica no domínio TESTLAB do AD DS e é uma prova de que a sincronização de diretórios funcionou.
    
13. Selecione a **conta User1** e selecione **Licenças e aplicativos**.
    
14. Em **Licenças de produto,** selecione seu local (se necessário), desabilite a licença do **Office 365 E5** e habilita a licença do **Microsoft 365 E5.** 

15. Selecione **Salvar** na parte inferior da página e selecione **Fechar**.
    
Em seguida, teste a capacidade de entrar na sua assinatura com o **user1@testlab.< >** nome de usuário do nome de domínio da conta User1:

1. Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando solicitado a um nome de usuário e senha, especifique **user1@testlab.<*seu* >** nome de domínio e a senha User1. Você deve conseguir entrar como Usuario1.
 
Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global. Portanto, o ícone **Administrador** não estará disponível como opção. 

Sua configuração resultante tem esta aparência:

![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuração consiste em: 
  
- Avaliação do Microsoft 365 E5 ou Office 365 E5 ou assinaturas pagas com o domínio DNS TESTLAB.<seu nome *de* domínio> registrado.
- Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio testlab AD DS com o locatário do Azure AD da sua assinatura do Microsoft 365.
- A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)