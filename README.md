# Docker
### Repositório para estudos sobre Docker
  <br />
  
  ## Fazer acesso remoto a uma máquina Windows -> Linux usando Putty
**Observações:** <br>
* Não esquecer que as máquinas devem estar na mesma faixa de IP - Recomendado que a placa de rede da máquina virtual esteja no modo bridge para compartilhar as configurações da placa física.
<pre id="tmp" style="display: none">Verificar IP<br><br>Windows: IPCONFIG <br>Linux: IP A</pre>

* Verificar se a máquina a receber o acesso remoto está com o serviço OPENSSH ativo ou a conexão remota será recusada.
<pre id="tmp" style="display: none">Instalar OPENSSH <br><br>apt-get install openssh-server</pre>

Ao botar o IP e a porta padrão, a máquina a receber o acesso remoto pedirá autorização para permitir o acesso remoto.
