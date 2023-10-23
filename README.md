### Arquitetura do processo ###

![bpmn drawio](https://github.com/0verthrive/RPA-sprint4/assets/88634211/3c06ed46-1a9a-4f25-8d41-5b070392fef5)
<h5>link da <a href="https://drive.google.com/file/d/1VxhUarVtKE4FL0OZcOqo2JWgKra9oQpo/view?usp=sharing">imagem</a></h5>

### Dispatcher ###

* O dispatcher da nossa arquitetura foi o responsável por capturar os emails de acordo com a filtragem necessária e enviar para o Orchestrator, criando assim uma fila.

### REFramework ###
**Robotic Enterprise Framework**

1. **INITIALIZE PROCESS**
 + ./Framework/*InitiAllSettings* - carga das configurações dos dados do arquivo Config.xlsx e dos assets
 + ./Framework/*GetAppCredential* - Recupera as credenciais do Orchestrator assets

2. **GET TRANSACTION DATA**
 + ./Framework/*GetTransactionData* - transações de busca do Orchestrator queue definido no Config

3. **PROCESS TRANSACTION**
 + *Process* - Processa as transações e invoca a ação do workflow de automação
 + ./Framework/*SetTransactionStatus* - Atualiza o status no orchestrator pra bem "Successful" 

4. **END PROCESS**
 + ./Framework/*CloseAllApplications* - Gera os logs de saída e fecha as aplicações abertas pelo processo

