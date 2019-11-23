---
title: Sincronização de hash de senha para ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configurar e demonstrar a sincronização de hash de senha e a entrada para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: ef08fcf59602d7812875015971d00a34526576d6
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202452"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronização de hash de senha para ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste do Microsoft 365 Enterprise e do Office 365 Enterprise.*

Muitas organizações usam o Azure Ad Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na própria floresta do Active Directory Domain Services (AD DS) com o conjunto de contas no locatário do Azure AD de sua assinatura do Microsoft 365 ou do Office 365. Este artigo descreve como adicionar a sincronização de hash de senha a seu ambiente de teste do Microsoft 365, resultando na seguinte configuração:
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Há duas fases para configurar esse ambiente de teste:
  
1. Crie o ambiente de teste corporativo simulado do Microsoft 365.
2. Instale e configure o Azure AD Connect na APP1.
    
> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365

Siga as instruções da [configuração base corporativa simulada do Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Aqui está a configuração resultante.
  
![A configuração base corporativa simulada](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuração consiste em: 
  
- Assinatura de avaliação ou assinatura paga do Microsoft 365 E5 ou Office 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste em máquinas virtuais do DC1, APP1 e CLIENT1 em uma rede virtual do Azure. O DC1 é um controlador de domínio para o testlab.\<seu nome de domínio público> domínio do AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2 – Criar e registrar o domínio testlab

Nesta fase, você adiciona um domínio DNS público e o adiciona-o à assinatura.

Primeiro, trabalhe com um provedor de registro DNS público para criar um nome de domínio DNS público com base em um nome de domínio atual e adicioná-lo à sua assinatura. Recomendamos usar o nome **testlab.**\<domínio público>. Por exemplo, se o nome de domínio público for **<span>contoso</span>.com**, adicione o nome de domínio público **<span>testlab</span>.contoso.com**.
  
Em seguida, adicione o domínio **testlab.**\<domínio público> da sua assinatura de avaliação ou paga do Microsoft 365 ou Office 365 por meio do processo de registro de domínio. Isso consiste em adicionar outros registros DNS ao **testlab.**\<seu domínio público> domínio. Para saber mais, confira [Adicionar um domínio ao Office 365.](https://docs.microsoft.com/office365/admin/setup/add-domain) 

Esta é a configuração resultante.
  
![O registro do seu nome de domínio testlab](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuração consiste em:

- Assinaturas pagas ou de avaliação do Microsoft 365 E5 ou do Office 365 E5 com o domínio DNS testlab.\<seu nome de domínio público> registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.

Veja como o testlab.\<seu nome de domínio público> está agora:

- Compatível com registros DNS públicos.
- Registrado nas assinaturas do Microsoft 365 ou do Office 365.
- O domínio AD DS na sua intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3 – Instalar o Azure AD Connect na APP1

Nesta fase, instale e configure a ferramenta Azure AD Connect na APP1 e verifique se ela funciona.
  
Primeiro, instale e configure o Azure AD Connect na APP1.

1. No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.
    
2. Na área de trabalho da APP1, abra um prompt de comando do nível de administrador do Windows PowerShell e execute estes comandos:
    
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
    
Em seguida, teste a capacidade de entrar na sua assinatura com a conta <strong>usuario1@testlab.</strong>\<nome de domínio> nome de usuário da conta Usuário1.

1. No APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.

2. Quando solicitado a fornecer o nome de usuário e a senha, especifique <strong>usuario1@testlab.</strong>\<seu nome de domínio público> e a senha de Usuário1. Você deve entrar como Usuário1. 
 
Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global. Portanto, o ícone **Administrador** não estará disponível como opção. 

Esta é a configuração resultante.

![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuração consiste em: 
  
- Assinaturas pagas ou de avaliação do Microsoft 365 E5 ou do Office 365 E5 com o domínio DNS TESTLAB.\<seu nome de domínio>registrado.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure Ad Connect é executado periodicamente no APP1 para sincronizar o domínio TESTLAB do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 ou Office 365.
- A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.

## <a name="next-step"></a>Próxima etapa

Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


