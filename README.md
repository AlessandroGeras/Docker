# Docker
### Repositório para estudos sobre Docker
  <br />

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
