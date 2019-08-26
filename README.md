#### How-To Ansible

Clonar esse exemplo basico 
```
git clone https://github.com/ysoffner/ansible
cd ansible
```

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

`register: `, registra toda vez que for chamado