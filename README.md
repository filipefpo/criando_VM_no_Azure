# Máquinas Virtuais no Microsoft Azure

Este repositório contém documentação, tutoriais e recursos para criação e gerenciamento de máquinas virtuais no Microsoft Azure. O material foi desenvolvido como parte do desafio da DIO e serve como referência para estudos e implementações futuras.

## Índice

- [Visão Geral](#visão-geral)
- [Pré-requisitos](#pré-requisitos)
- [Criando uma Máquina Virtual](#criando-uma-máquina-virtual)
- [Configurações Importantes](#configurações-importantes)
- [Conectando à VM](#conectando-à-vm)
- [Instalando um Servidor Web](#instalando-um-servidor-web)
- [Melhores Práticas](#melhores-práticas)
- [Recursos Adicionais](#recursos-adicionais)
- [Licença](#licença)

## Visão Geral

As máquinas virtuais (VMs) do Azure permitem criar recursos de computação dedicados em minutos, que podem ser usados como uma área de trabalho física ou um computador servidor. Este repositório documenta o processo de criação, configuração e gerenciamento de VMs Windows e Linux no Azure, utilizando tanto o portal web quanto ferramentas de linha de comando.

## Pré-requisitos

- Uma conta do Azure (você pode criar uma conta gratuita se ainda não tiver)
- Navegador web moderno para acessar o Portal do Azure
- Cliente SSH (para VMs Linux) ou cliente RDP (para VMs Windows)
- Conhecimentos básicos de redes

## Criando uma Máquina Virtual

### Máquina Virtual Windows

1. Entre no [portal do Azure](https://portal.azure.com)
2. Digite "máquinas virtuais" na pesquisa
3. Em "Serviços", selecione "Máquinas virtuais"
4. Na página "Máquinas virtuais", clique em "Criar" e selecione "Máquina virtual do Azure"
5. Configure os "Detalhes da instância":
   - Insira um nome para a VM (exemplo: "myWindowsVM")
   - Selecione a imagem "Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2"
   - Deixe os outros valores como padrão
6. Configure a "Conta de administrador":
   - Forneça um nome de usuário (exemplo: "azureuser")
   - Defina uma senha segura (mínimo 12 caracteres com requisitos de complexidade)
7. Em "Regras de porta de entrada", escolha "Permitir portas selecionadas" e selecione "RDP (3389)" e "HTTP (80)"
8. Revise as configurações e clique em "Examinar + criar"
9. Após a validação, clique em "Criar"
10. Aguarde a conclusão da implantação e clique em "Ir para o recurso"

## Configurações Importantes

### Tamanho da VM

O tamanho da VM determina os recursos de computação, memória e armazenamento disponíveis. Escolha conforme a carga de trabalho planejada:
- VMs de propósito geral: série D, balanceamento entre CPU e memória
- VMs otimizadas para computação: série F, maior proporção de CPU por memória
- VMs otimizadas para memória: série E, maior proporção de memória por CPU

### Rede Virtual

Ao criar uma VM, você pode:
- Criar uma nova rede virtual ou usar uma existente
- Configurar sub-redes
- Definir grupos de segurança de rede para controlar o tráfego

### Armazenamento

- **Discos do Sistema Operacional**: Onde o sistema operacional está instalado
- **Discos de Dados**: Armazenamento adicional para aplicativos e dados
- **Tipos de Disco**: 
  - HDD Standard: mais econômico, menor desempenho
  - SSD Standard: bom equilíbrio entre custo e desempenho
  - SSD Premium: alto desempenho para cargas de trabalho críticas

## Conectando à VM

### Conexão a VMs Windows

1. No portal do Azure, navegue até a VM e clique em "Conectar"
2. Baixe o arquivo RDP
3. Abra o arquivo RDP e conecte-se usando as credenciais definidas na criação

## Melhores Práticas

- **Segurança**:
  - Mantenha as VMs atualizadas com as últimas atualizações de segurança
  - Use grupos de segurança de rede para limitar o acesso
  - Implemente uma solução de backup para suas VMs

- **Otimização de Custos**:
  - Desligue VMs quando não estiverem em uso
  - Use o dimensionamento correto para suas VMs
  - Considere Instâncias Reservadas para cargas de trabalho contínuas

- **Monitoramento**:
  - Configure alertas para uso excessivo de recursos
  - Monitore a disponibilidade e o desempenho

- **Automação**:
  - Considere usar o GitHub Actions para automatizar implantações de VMs
  - Use modelos ARM ou Bicep para implantações consistentes

## Recursos Adicionais

- [Documentação oficial do Azure Virtual Machines](https://learn.microsoft.com/pt-br/azure/virtual-machines/)
- [Práticas recomendadas para máquinas virtuais do Azure](https://learn.microsoft.com/pt-br/azure/virtual-machines/maintenance-best-practices)
- [Repositório de exemplos Azure/AzureVM](https://github.com/Azure/AzureVM)
- [Tutorial: Implantar aplicativos do GitHub no Azure](https://learn.microsoft.com/pt-br/azure/developer/github/deploy-to-azure)

