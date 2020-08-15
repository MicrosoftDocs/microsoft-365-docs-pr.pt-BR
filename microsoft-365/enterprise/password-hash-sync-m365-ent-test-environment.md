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
ms.openlocfilehash: 2930d147e2ae3277b0af4d2aa81a602c73128439
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686543"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronização de hash de senha para ambiente de teste do Microsoft 365

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na floresta local dos Serviços de domínio Active Directory (AD DS) local com o conjunto de contas no locatário do Azure AD da assinatura do Microsoft 365. Este artigo descreve como adicionar a sincronização de hash de senha a seu ambiente de teste do Microsoft 365, resultando na seguinte configuração:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Há duas fases para configurar esse ambiente de teste:
  
1. Crie o ambiente de teste corporativo simulado do Microsoft 365.
2. Instale e configure o Azure AD Connect na APP1.
    
> [!TIP]
> Vá para a [pilha do guia do laboratório de teste do microsoft 365 for Enterprise](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para um mapa Visual para todos os artigos da pilha do guia do laboratório de teste da Microsoft 365 para empresas.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365

Siga as instruções da [configuração base corporativa simulada do Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Aqui está a configuração resultante.
  
![A configuração base corporativa simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste em máquinas virtuais do DC1, APP1 e CLIENT1 em uma rede virtual do Azure. DC1 é um controlador de domínio para o testlab.\<your public domain name> Domínio do AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2 – Criar e registrar o domínio testlab

Nesta fase, você adiciona um domínio DNS público e o adiciona-o à assinatura.

Primeiro, trabalhe com seu provedor de registro DNS público para criar um novo nome de domínio DNS público com base no seu nome de domínio atual e adicioná-lo à sua assinatura. Recomendamos o uso do nome **testlab.**\<your public domain>. Por exemplo, seu nome de domínio público for**<span>contoso</span>.com**, e adicione o nome de domínio público **<span>testlab</span>.contoso.com**.
  
Em seguida, adicione **testlab.**\<your public domain> domínio à sua assinatura de avaliação ou pagamento da Microsoft 365 através do processo de registro de domínio. Isso consiste em adicionar registros DNS adicionais ao **testlab.**\<your public domain> domínio. Para obter mais informações, consulte [Adicionar um domínio ao Microsoft 365](../admin/setup/add-domain.md). 

Esta é a configuração resultante.
  
![O registro do seu nome de domínio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuração consiste em:

- Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab.\<your public domain name> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.

Observe como o testlab.\<your public domain name> agora é:

- Compatível com registros DNS públicos.
- Registrado nas assinaturas do Microsoft 365.
- O domínio AD DS na sua intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3 – Instalar o Azure AD Connect na APP1

Nesta fase, instale e configure a ferramenta Azure AD Connect na APP1 e verifique se ela funciona.
  
Primeiro, instale e configure o Azure AD Connect na APP1.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.
    
2. Na área de trabalho da APP1, abra um prompt de comando do Windows PowerShell em nível de administrador e execute esses comandos para desativar a Segurança avançada do Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. Na barra de tarefas, clique em **Internet Explorer** e acesse [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. Na página do Microsoft Azure Active Directory Connect, clique em **Baixar** e, em seguida, clique em **Executar**.
    
5. Na página **Bem-vindo ao Azure AD Connect**, clique em **Concordo** e, em seguida, **Continuar**.
    
6. Na página **Configurações Expressas**, clique em **Usar configurações expressas**.
    
7. Na página **Conectar-se ao Azure AD**, digite o nome de sua conta de administrador global em **Nome de usuário**, digite a sua senha em **Senha** e clique em **Avançar**.
    
8. Na página **Conectar-se ao AD DS**, digite **TestLab\\Usuário1** no campo **Nome de usuário**, digite a senha no campo **Senha** e clique em **Avançar**.
    
9. Na página **Pronto para configurar**, clique em **Instalar**.
    
10. Na página **Configuração concluída**, clique em **Sair**.
    
11. No Internet Explorer, vá para o centro de administração do Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. Na navegação à esquerda, clique em **Usuários > Usuários ativos**.
    
    Observe a conta denominada **Usuario1**. Essa conta fica no domínio TESTLAB do AD DS e é uma prova de que a sincronização de diretórios funcionou.
    
13. Clique na conta **Usuário1** e, em seguida, clique em **Licenças e aplicativos**.
    
14. Em **Licenças de produto**, selecione sua localização (se necessário), desabilite a licença do **Office 365 E5** e habilite a licença do **Microsoft 365 E5**. 

15. Clique em **Salvar**, no final da página, e clique em **Fechar**.
    
Em seguida, você testa a capacidade de entrar na sua assinatura com o <strong>user1@testlab.</strong>\<your domain name> nome de usuário da conta User1.

1. Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando for pedido um nome de usuário e senha, especifique <strong>user1@testlab.</strong>\<your domain name> e a senha do User1. Você deve conseguir entrar como Usuario1. 
 
Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global. Portanto, o ícone **Administrador** não estará disponível como opção. 

Esta é a configuração resultante.

![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuração consiste em: 
  
- Avaliação de Microsoft 365 E5 ou Office 365 E5 ou assinaturas pagas com o domínio DNS TESTLAB.\<your domain name> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD das suas assinaturas do Microsoft 365 periodicamente.
- A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)


