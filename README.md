# Análise Prática de Tráfego e Conexões de Rede (TCP/UDP)

## 1. Objetivo do Projeto
O objetivo deste projeto é demonstrar a capacidade de analisar fluxos de dados, identificar o comportamento de protocolos da camada de transporte (TCP) e decifrar comunicações ativas em um sistema operacional de forma analítica.

---

## 2. Conceitos Técnicos Aplicados
* **Protocolo TCP:** Focado em confiabilidade e integridade, operando através de conexões estabelecidas após o handshake de 3 vias (3-way handshake).
* **IP e Portas:** Utilização do endereço lógico local para mapear a comunicação com serviços específicos hospedados na internet através de portas conhecidas e temporárias.
* **Estados de Conexão:** Monitoramento de conexões ativas (`ESTABLISHED`) na tabela de roteamento local.

---

## 3. Coleta de Dados e Análise Forense (Mundo Real)

Para validar a teoria na prática, executei um mapeamento de conexões TCP ativas na minha máquina através do terminal. Abaixo estão as linhas coletadas e a análise técnica de cada fluxo:

```text
TCP    192.168.xx.x:49726     52.86.188.17x:443      ESTABLISHED
TCP    192.168.xx.x:51192     44.214.226.4x:443      ESTABLISHED
TCP    192.168.xx.x:51364     34.158.255.6x:4070     ESTABLISHED

Decodificação Técnico-Analítica dos Fluxos:
Tráfego Web Seguro (Porta 443 - HTTPS):

Nas duas primeiras linhas, meu IP privado local (192.168.xx.x) estabeleceu uma conexão estável (ESTABLISHED) com servidores externos na nuvem (Amazon AWS).

A comunicação ocorre via porta de destino 443, o que garante que os dados trafegados estão criptografados de ponta a ponta.

Identificação de Aplicação Específica (Porta 4070):

Na terceira linha, a porta de destino identificada foi a 4070.

Em análise de infraestrutura, essa porta é utilizada nativamente pela aplicação de desktop do Spotify para streaming de dados. O IP de destino (34.158.255.62) aponta diretamente para os servidores do Google Cloud que hospedam a distribuição de mídia da plataforma.

4. Conclusão
A segurança defensiva (Blue Team) começa pelo entendimento do tráfego legítimo. Ao dominar a leitura de tabelas de conexões e fluxos de rede, torna-se possível identificar desvios de comportamento, portas abusadas por malwares ou conexões suspeitas estabelecidas sem autorização no ambiente corporativo.
