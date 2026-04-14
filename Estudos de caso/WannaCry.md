
# Estudo de caso: Ataque cibernético Global WannaCry (2017)

## Contexto

O WannaCry é um dos **ransomwares** (um malware que **criptografa os arquivos do computador** em troca de um **resgate financeiro**) mais danosos da história da cibersegurança. No dia **12 de maio de 2017**, milhares de sistemas ao redor do mundo foram contaminados. Hospitais, escolas, fábricas e diversas outras empresas perderam acesso aos seus sistemas. Em questão de horas, **150 países** estavam sob ataque do mesmo vírus.


## Ambiente afetado

O ransomware afetou **ambientes Windows desatualizados**, aproveitando-se de uma **vulnerabilidade no protocolo SMB (TCP 445)**, conectando-se a outros computadores na rede e depois executando o malware, gerando assim uma **reação em cadeia**, afetando cada vez mais sistemas.


## Vetor de ataque

O vírus se aproveita de uma vulnerabilidade chamada **EternalBlue**, uma vulnerabilidade alegadamente desenvolvida **há anos** antes do ocorrido pela NSA. Eles deixaram essa vulnerabilidade guardada, sem reportar para a Microsoft, para poderem utilizá-la como uma **“chave-mestra”** para qualquer ambiente Windows que quisessem acessar.

Porém, em **agosto de 2016**, o grupo The Shadow Brokers alegou ter hackeado o Equation Group, um grupo de hackers sofisticado associado à NSA. Em **abril de 2017**, esse mesmo grupo vazou uma série de **malwares e ferramentas de hacking**, entre elas o EternalBlue.


## Cadeia do ataque

Depois de se **conectar ao alvo**, era utilizada outra ferramenta chamada **DoublePulsar** (um **backdoor** também vazado pelos The Shadow Brokers) para garantir uma **porta de acesso persistente** e segura com **permissão elevada**. Uma vez instalado, permite que o invasor execute comandos de mais alto nível, como **exec**, possibilitando a execução de outros malwares.

Por último, o malware era executado: **todos os arquivos do computador eram criptografados**, e uma mensagem escrita **"Ooops, your files have been encrypted!"**, com uma **contagem regressiva**, informava que todos os arquivos seriam **excluídos** caso não fosse pago o valor de **US$ 300,00**. A mensagem foi traduzida para **200 línguas**, ampliando seu alcance global.


## Impacto

O ataque durou por volta de **7 horas**, infectou mais de **230.000 computadores** em **150 países**, e os prejuízos podem chegar a cerca de **US$ 4.000.000.000**.


## Resposta e recuperação

A Microsoft já **havia corrigido a vulnerabilidade antes do ataque**. Em **março de 2017**, a empresa lançou uma **atualização de segurança**, corrigindo a falha para diversas versões do Windows, inclusive sistemas fora de suporte, como **Windows XP** e **Windows Server 2003**.

Mesmo assim, o ataque ocorreu porque **muitos sistemas não estavam atualizados** e porque ambientes industriais frequentemente utilizam **sistemas legados**.

Quem ajudou a conter o problema foi o pesquisador de segurança Marcus Hutchins, que, durante a engenharia reversa do malware, identificou um comportamento incomum: o programa tentava se conectar a um **domínio específico**.

Ao registrar esse domínio, ele percebeu que milhares de **máquinas** começaram a se conectar **ao seu servidor** no mesmo instante. Assim que as **máquinas** se conectavam, elas paravam de proliferar o **vírus**, reduzindo significativamente a propagação do ataque.

Isso acontecia porque o malware possuía um comportamento em que, ao conseguir se conectar a esse domínio, sua execução era interrompida. Esse mecanismo ficou conhecido como **“kill switch”**.


## Lições aprendidas

Situações como essa mostram a importância de manter sistemas **sempre atualizados**. Após esse ataque, as empresas passaram a exigir maior rigor nas **políticas de atualização**.

Além disso, fica evidente que os dados, mesmo quando armazenados localmente, **nunca estão 100% seguros**, reforçando a importância de **backups** e **redundância de sistemas**.
