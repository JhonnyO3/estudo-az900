# estudo-az900
Neste Repositorio, concentra-se as principais informações relevantes que podem cair na certificação Azure Az900 
# Azure Knowledge Base

Este repositório contém informações e notas sobre o uso do Microsoft Azure, Azure CLI, e outros conceitos relacionados à nuvem.

### Sobre o Azure
A utilização do Azure exige uma Assinatura do Azure. Uma assinatura do Azure é vinculada a uma conta do Azure, que é uma identidade no Microsoft Entra ID 

## Azure CLI

O Azure CLI oferece suporte para comandos em PowerShell e Bash. Nem todos os recursos dependem de regiões, e existem recursos globais. Certifique-se de considerar custos ao duplicar serviços e transferir dados entre zonas de disponibilidade.

### Regiões no Azure
- Nem todos os recursos dependem de regioes, existem alguns recursos globais.
- pode haver um custo para duplicar seus serviços e transferir dados entre zonas de disponibilidade.
- Serviços em zonas: você fixa o recurso a uma zona específica (por exemplo, VMs, discos gerenciados, endereços IP).
- Serviços com redundância de zona: a plataforma replica automaticamente entre zonas (por exemplo, armazenamento com redundância de zona, Banco de Dados SQL).
- Serviços não regionais: os serviços estão sempre disponíveis em geografias do Azure e são resilientes a interrupções em toda a zona, bem como a interrupções em toda a região.
  
### Regiões Soberanas
- Regiões soberanas são instâncias do Azure isoladas da instância principal do Azure. Talvez seja necessário usar uma região soberana para fins legais ou de conformidade.
O Azure possui regiões soberanas, como US DoD Central, US Gov – Virgínia, US Gov Iowa, Leste da China, Norte da China, etc.

### Grupos de Gerenciamento
- Todas as assinaturas em um grupo de gerenciamento herdam automaticamente as condições aplicadas ao grupo de gerenciamento, da mesma forma que os grupos de recursos herdam configurações de assinaturas e recursos herdados de grupos de recursos.
- Grupos de gerenciamento podem ser aninhados.
- Grupos de gerenciamento podem ser aninhados.
- 10.000 grupos de gerenciamento podem ter suporte em um único diretório.
- Uma árvore do grupo de gerenciamento pode dar suporte a até seis níveis de profundidade
- Cada grupo de gerenciamento e assinatura podem dar suporte a somente um pai.
- Em quantos grupos de recursos um recurso pode estar ao mesmo tempo? 1
- Políticas e RBAC podem ser vinculados aos grupos de gerenciamento para facilitar o controle de acesso.

### Redes Virtuais
- ##Possiveis metodos de conexão entre o Azure e a rede local:
  - As conexões de rede virtual privada ponto a site são de um computador fora da organização de volta para a rede corporativa. Nesse caso, o computador cliente inicia uma conexão VPN criptografada para se conectar à rede virtual do Azure.
  - Redes virtuais privadas site a site vinculam seu dispositivo VPN ou gateway de VPN local ao Gateway de VPN do Azure em uma rede virtual. Na verdade, os dispositivos no Azure podem aparecer como estando na rede local. A conexão é criptografada e funciona pela Internet.
  - O Azure ExpressRoute fornece uma conectividade privada dedicada para o Azure que não passa pela Internet. O ExpressRoute é útil para ambientes em que você precisa de maior largura de banda e níveis de segurança ainda mais altos.

- Conexões VPN, ExpressRoute e emparelhamento de redes virtuais são essenciais para a conectividade.
- Métodos como site a site, ponto a site e ExpressRoute oferecem diferentes níveis de segurança e largura de banda.

### Rotear tráfego de rede:
- tabelas de rotas permitem definir regras sobre como o tráfego deve ser direcionado.
- O BGP (Border Gateway Protocol) funciona com Gateways de VPN do Azure, Servidor de Rota do Azure ou Azure ExpressRoute para propagar as rotas BGP locais para redes virtuais do Azure.

### Filtrar tráfego de rede:
- Grupos de segurança de rede são recursos do Azure que podem conter várias regras de segurança de entrada e saída. Você pode definir essas regras para permitir ou bloquear tráfego com base em fatores como endereço IP de origem e de destino, porta e protocolo.
- Soluções de virtualização de rede são VMs especializadas que podem ser comparadas a um dispositivo de rede protegida. Uma solução de virtualização de rede realiza uma função de rede específica, como execução de um firewall ou otimização de WAN (rede de longa distância).

### Conectar redes virtuais
- Você pode vincular redes virtuais usando o emparelhamento dessas redes. O emparelhamento permite que duas redes virtuais se conectem diretamente entre si.
- O emparelhamento permite que os recursos em cada rede virtual se comuniquem entre si. Essas redes virtuais podem estar em regiões separadas, o que permite criar uma rede global interconectada por meio do Azure.
 
### Gateways VPN
- Conecte datacenters locais a redes virtuais por meio de uma conexão site a site.
- Conecte dispositivos individuais a redes virtuais por meio de uma conexão ponto a site.
- Conecte redes virtuais a outras redes virtuais por meio de uma conexão rede a rede.

### Azure ExpressRoute
- O ExpressRoute dá suporte a quatro modelos que podem ser usados para conectar a rede local à Microsoft Cloud:
- Colocação do CloudExchange
- Conexão Ethernet ponto a ponto
- Conexão qualquer para qualquer
- Direto de sites do ExpressRoute

### Redundância na região primária
- Os dados em uma conta de Armazenamento do Azure são sempre replicados três vezes na região primária. 
- LRS (armazenamento com redundância local) e ZRS (armazenamento com redundância de zona).

- LRS replica seus dados três vezes em um único data center na região primária. O LRS oferece pelo menos 11 noves de durabilidade (99,999999999%) dos objetos em um determinado ano.
- O LRS é a opção de redundância de menor custo e oferece a menor durabilidade em comparação com outras opções

### Armazenamento com redundância de zona
- o ZRS (armazenamento com redundância de zona) replica os dados do Armazenamento do Azure de maneira síncrona em três zonas de disponibilidade do Azure na região primária. O ZRS oferece durabilidade para objetos de dados do Armazenamento do Azure de, pelo menos, 12 noves (99,9999999999%) em um dado ano.



### Redundância em uma região secundária
- O Armazenamento do Azure oferece duas opções para copiar seus dados em uma região secundária: GRS (armazenamento com redundância geográfica) e GZRS (armazenamento com redundância de zona geográfica)
- Por padrão, os dados na região secundária não ficam disponíveis para acesso de leitura ou gravação, a menos que haja um failover na região secundária. 


### Armazenamento com redundância geográfica
- O GRS copia seus dados de maneira síncrona três vezes em um único local físico na região primária usando LRS. Em seguida, ele copia os dados de maneira assíncrona em um único local físico na região secundária (o par da região) 
- O GRS oferece durabilidade para objetos de dados do Armazenamento do Azure de, pelo menos, 16 noves (99,99999999999999%) em um dado ano.

### Armazenamento com redundância de zona geográfica

- O GZRS combina a alta disponibilidade fornecida pela redundância entre zonas de disponibilidade com a proteção contra interrupções regionais fornecidas pela replicação geográfica. Os dados em uma conta de armazenamento GZRS são copiados entre três zonas de disponibilidade do Azure na região primária (semelhante ao ZRS) e são replicados em uma região geográfica secundária usando LRS para proteção contra desastres regionais. A Microsoft recomenda o uso do GZRS para aplicativos que exigem consistência, durabilidade e disponibilidade máximas, excelente desempenho e resiliência para recuperação de desastres

- Filas do Azure: um armazenamento de mensagens para um sistema de mensagens confiável entre componentes do aplicativo.
O Armazenamento de Filas do Azure é um serviço usado para armazenar grandes quantidades de mensagens. Após o armazenamento, você pode acessar as mensagens em qualquer lugar do mundo por meio de chamadas autenticadas usando HTTP ou HTTPS

- Tabelas do Azure: opção de tabela NoSQL para dados estruturados e não relacionais..
O Armazenamento de Tabelas do Microsoft Azure armazena grandes quantidades de dados estruturados. As tabelas do Azure são um repositório de dados NoSQL que aceita chamadas autenticadas de dentro e de fora da nuvem do Azure. 



### Migrações para Azure

- O Migrações para Azure é um serviço que ajuda você a migrar de um ambiente local para a nuvem. O Migrações para Azure funciona como um hub para ajudar você a gerenciar a avaliação e a migração do datacenter local para o Azure. Elas fornecem o seguinte:
- Plataforma de migração unificada: 
- Variedade de ferramentas:
- Avaliação e migração

### Azure Data Box

- O Azure Data Box é um serviço de migração física que ajuda a transferir grandes quantidades de dados de maneira rápida, barata e confiável. A transferência de dados segura é acelerada com o envio de um dispositivo de armazenamento Data Box proprietário que tem uma capacidade máxima de armazenamento utilizável de 80 terabytes. O Data Box é transportado entre o datacenter por meio de uma empresa regional. Uma caixa robusta protege o Data Box contra danos durante o transporte.


### AzCopy

- O AzCopy é um utilitário de linha de comando que você pode usar para copiar blobs ou arquivos de/para uma conta de armazenamento. Com o AzCopy, você pode carregar arquivos, baixar arquivos, copiar arquivos entre contas de armazenamento e até mesmo sincronizar arquivos.

### Microsoft Entra ID
- Microsoft Entra ID é a solução de gerenciamento de identidade e acesso baseada em nuvem da Microsoft

### Quem usa o Microsoft Entra ID?

- Administradores de TI. Os administradores podem usar o Microsoft Entra ID para controlar o acesso a aplicativos e recursos com base nas necessidades das respectivas empresas.
- Desenvolvedores de aplicativos. Os desenvolvedores podem usar o Microsoft Entra ID para fornecer uma abordagem baseada em padrões ao adicionar funcionalidades aos aplicativos que compilam, como, por exemplo, adicionar a funcionalidade de SSO a um aplicativo ou habilitar um aplicativo para trabalhar com as credenciais existentes de um usuário.
- Usuários. Os usuários podem gerenciar as respectivas identidades e executar ações de manutenção, como redefinição de senha por autoatendimento.
- Assinantes do serviço online. Os assinantes do Microsoft 365, Microsoft Office 365, Azure e Microsoft Dynamics CRM Online já estão usando o Microsoft Entra ID para se autenticar em suas contas.


métodos de conexão entre o Microsoft Entra ID e seu AD local é o uso do Microsoft Entra Connect. O Microsoft Entra Connect sincroniza as identidades do usuário entre o Active Directory local e o Microsoft Entra ID. 


### O que é Microsoft Entra Domain Services?

- O Microsoft Entra Domain Services é um serviço que fornece serviços de domínio gerenciado, como ingresso no domínio, política de grupo, protocolo de acesso leve a diretórios (LDAP) e autenticação Kerberos/NTLM.

- No entanto, o gerenciamento desse nível de permissões para uma equipe inteira se tornaria tedioso. Em vez de definir os requisitos de acesso detalhados para cada indivíduo e atualizar os requisitos de acesso quando outros recursos forem criados ou novas pessoas entrarem na equipe, o Azure permite controlar o acesso por meio do RBAC do Azure (controle de acesso baseado em função do Azure).

- O Azure fornece funções internas que descrevem regras de acesso comuns para os recursos de nuvem. Você também pode definir suas funções. Cada função tem um conjunto associado de permissões de acesso relacionadas a essa função. Quando você atribui indivíduos ou grupos a uma ou mais funções, eles recebem todas as permissões de acesso relacionadas.


### Como o controle de acesso baseado em função é aplicado aos recursos?

- O controle de acesso baseado em função é aplicado a um escopo, que é um recurso ou um conjunto de recursos ao qual esse acesso se aplica.]

- Os escopos incluem:
  - Um grupo de gerenciamento (uma coleção de várias assinaturas).
  - Uma assinatura única.
  - Um grupo de recursos.

