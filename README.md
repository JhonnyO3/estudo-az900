# estudo-az900
Neste Repositorio, concentra-se as principais informações relevantes que podem cair na certificação Azure Az900 
# Azure Knowledge Base

Este repositório contém informações e notas sobre o uso do Microsoft Azure, Azure CLI, e outros conceitos relacionados à nuvem.

## Azure CLI

O Azure CLI oferece suporte para comandos em PowerShell e Bash. Nem todos os recursos dependem de regiões, e existem recursos globais. Certifique-se de considerar custos ao duplicar serviços e transferir dados entre zonas de disponibilidade.

### Regiões Soberanas
O Azure possui regiões soberanas, como US DoD Central, US Gov – Virgínia, US Gov Iowa, Leste da China, Norte da China, etc.

### Grupos de Gerenciamento
- Grupos de gerenciamento podem ser aninhados.
- Políticas e RBAC podem ser vinculados aos grupos de gerenciamento para facilitar o controle de acesso.

### Redes Virtuais
- Conexões VPN, ExpressRoute e emparelhamento de redes virtuais são essenciais para a conectividade.
- Métodos como site a site, ponto a site e ExpressRoute oferecem diferentes níveis de segurança e largura de banda.

### Rotear e Filtrar Tráfego de Rede
- Tabelas de rotas e Grupos de Segurança de Rede são cruciais.
- BGP é usado para propagar rotas.
  
### Redundância de Armazenamento
- Tipos como LRS, ZRS, GRS e GZRS oferecem diferentes níveis de redundância.
- Filas e Tabelas do Azure são essenciais para gerenciamento de mensagens e armazenamento estruturado.

### Migrações para Azure
- Serviço de Migrações para Azure facilita a transição de ambientes locais para a nuvem.
- Ferramentas como Azure Data Box e AzCopy ajudam na transferência eficiente de dados.

## Microsoft Entra ID
- Microsoft Entra ID é usado por administradores, desenvolvedores, usuários e assinantes de serviços online.
- Microsoft Entra Connect sincroniza identidades entre o Active Directory local e o Microsoft Entra ID.

### Controle de Acesso Baseado em Função (RBAC) do Azure
- O RBAC é aplicado hierarquicamente a diferentes escopos.
- A segurança do aplicativo não é tratada pelo RBAC.

## Confiança Zero
- Modelo de Confiança Zero requer autenticação para todos os dispositivos, mudando a abordagem tradicional de segurança de redes corporativas.

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para adicionar informações ou correções.

