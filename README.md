#### How-To Ansible

Clonar esse exemplo basico 
```
git clone https://github.com/ysoffner/ansible
cd ansible
```
Ter uma `chave.pem` de acesso ao EC2 e as variaveis de ambiente ja setadas (`AWS_SECRET_ACCESS_KEY` e `AWS_ACCESS_KEY_ID`)

#### Para rodar
```
ansible-playbook -i hosts main.yml
ansible-playbook -i hosts all -m ping -u ubuntu
```
#### Info
> No `hosts`.

Na conexão localhost `ansible_connection=local` (nao use ssh para conectar), `ansible_python_interpreter=python3` (use o python3 do meu interpreter), `gather_facts=false` (entrega o inspect do host)

> Main.yml

Arquivo principal, nele é passado as tarefas para serem seguidas/executadas

> Criação de roles
```
mkdir roles && cd roles
ansible-galaxy init create
```
cria os diretorios padrões
```
.
└── create
    ├── README.md
    ├── defaults
    ├── files       #Arquivos para serem enviados (dest)
    ├── handlers    #Ação após evento
    ├── meta
    ├── tasks       #Criação dos eventos
    ├── templates   #Arquivo para ser enviado, manipulando variaveis
    ├── tests       
    └── vars        #Centraliza as variaveis
```
Arquivo de exemplo: `task -> provisioning.yml`

`local_action ou module`, escolhe o modulo do ansible para ser usado

`register: `, registra toda vez que for chamado

`wait=true `, esperar subir

`insertafter`, insira o conteudo após essa string