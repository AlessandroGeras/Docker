# Docker
### Repositório para estudos sobre Docker
  <br />
  
# 1. Instalação
## Instalação do Docker por script

<pre id="tmp" style="display: none">Download script https://docs.docker.com/engine/install/ubuntu/ <br>curl -fsSL https://get.docker.com -o get-docker.sh<br><br>Executar script<br>sh ./get-docker.sh <br><br>Verificar versão<br>docker version <br><br>Verificar se o serviço está rodando<br>systemctl status docker</pre><br>

# 2. Imagens
## Download imagens do Docker
<pre id="tmp" style="display: none">docker pull nomedaimagem<br>Ex:docker pull hello-world<br><br>Download imagem com versão específica<br>Ex:docker pull postgres:9.6 </pre>

## Listar imagens disponíveis
<pre id="tmp" style="display: none">docker images</pre>

## Listar containers em execução
<pre id="tmp" style="display: none">docker ps<br><br>docker ps -a (containers que não estão em execução)</pre>

## Executar container a partir de uma imagem
<pre id="tmp" style="display: none">docker run nomedaimagem (roda a última versão)<br><br>docker run nomedaimagem:9 (roda a versão 9 especificamente)<br><br>docker run -d nomedaimagem (detached mode - rodar o container em background, podendo fechar o terminal sem terminar o serviço)</pre>

## Entrar em um container diretamente para executar comandos
<pre id="tmp" style="display: none">docker run -it nomedaimagem (obs:entra no container e ao sair dele seu serviço terminará)</pre>

## Não entrar em um container diretamente mas permitir comandos para interagir nele
<pre id="tmp" style="display: none">docker run -dit nomedaimagem (obs: detached mode - não entrará no container mas deixará que ele receba comandos de execução)<br><br>Criar container com nome específico<br>Ex:docker run -dit -name nomecontainerespecífico nomedaimagem (podemos criar várias instâncias do mesmo container)<br><br>docker exec -it IDcontainer comandoaserexecutado<br>Ex:docker exec -it 12345 /bin/bash (exemplo para entrar no container)</pre>

## Comandos gerais
<pre id="tmp" style="display: none">docker start IDcontainer<br><br>docker stop IDcontainer<br><br>docker restart IDcontainer<br><br>docker rm IDcontainer (remove container)<br><br>docker rmi nomedaimagem (remove imagem)</pre>

## Copiar arquivos
<pre id="tmp" style="display: none">docker cp nomedoarquivoorigem.ext IDcontainer:/nomediretório (VM->container)<br><br>docker cp IDcontainer:/nomediretório/nomedoarquivoorigem.ext nomedoarquivodestino.ext (container->VM)</pre>

<br>

# 3. Acesso remoto as VM´s com Docker
## Fazer acesso Linux -> Linux usando SSH

<pre id="tmp" style="display: none">Usar SSH com usuário e IP<br><br>Ex: ssh alessandro@10.0.0.10</pre>
A senha será pedida depois. <br><br>

  ## Fazer acesso remoto Windows -> Linux usando Putty
**Observações:** <br>

* Não esquecer que as máquinas devem estar na mesma faixa de IP - Recomendado que a placa de rede da máquina virtual esteja no modo bridge para compartilhar as configurações da placa física.
<pre id="tmp" style="display: none">Verificar IP<br><br>Windows: IPCONFIG <br>Linux: IP A</pre>

* Verificar se a máquina a receber o acesso remoto está com o serviço de conexão OPENSSH ativo ou a conexão remota será recusada.
<pre id="tmp" style="display: none">Instalar o serviço de conexão OPENSSH <br><br>apt-get install openssh-server</pre>

Ao botar o IP e a porta padrão, a máquina que receber o acesso remoto pedirá autorização para permitir o acesso remoto.<br><br>

## Configurar VM na AWS (EC2)
  
1. Criar instância (Nome da VM e distribuição).
2. Criar chave de acesso para conexão remota (Nome da chave, criptografia RSA e formato PEM para conexão OPENSSH).
3. Permitir tráfego SSH para a conexão remota.
4. Executar a instância para concluir.<br><br>

## Fazer acesso remoto - Windows -> AWS usando Putty

1. Usar o PuttyGen para converter a chave de acesso com formato PEM para formato PPK para conexão com o Putty.
2. Clicar em salvar chave privada.
3. No Putty clicar em connection -> auth e carregar a nova chave.<br><br>

## Fazer acesso Linux -> AWS usando SSH

<pre id="tmp" style="display: none">Usar SSH com chave de acesso, usuário e IP<br><br>Ex: ssh -t nomedachave.pem ubuntu@10.0.0.10</pre><br><br>
