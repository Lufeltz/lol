## Projeto Lavanderia On-Line Web 2

### Utilização do projeto

#### Realize o clone do projeto

```
git clone https://github.com/Lufeltz/lol.git
```
#### Antes de executar o projeto é necessário o download de algumas ferramentas

* [Git](https://www.git-scm.com/downloads)
* [Node.js](https://nodejs.org/en/download/package-manager)
* [Java 21](https://www.oracle.com/br/java/technologies/downloads/#jdk21-windows)
    * Nota: Para evitar problemas futuros, antes de instalar a versão 21 confirme se já existe uma versão do java sdk instalado no seu sistema usando: <code>java --version</code>. Em caso positivo, desinstale a versão atual e prossiga com a instalação do Java 21.
* [PostgreSQL 16.4](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)
    * Nota: foi utilizado login e senha postgres e porta 5432 para comunicação com o PostgreSQL

#### Confirmar que todos os arquivos foram instalados corretamente através do terminal
* Nota: As versões podem variar
```
git --version
git version 2.46.0.windows.1

java --version
java 21.0.4 2024-07-16 LTS
Java(TM) SE Runtime Environment (build 21.0.4+8-LTS-274)
Java HotSpot(TM) 64-Bit Server VM (build 21.0.4+8-LTS-274, mixed mode, sharing)

node --version
v20.3.1

npm --version
9.6.7

psql --version
psql (PostgreSQL) 16.4
```

#### Instalação do Angular usando o npm no terminal
```
npm install -g @angular/cli
```

```
ng version
Angular CLI: 18.2.4
Node: 20.3.1
Package Manager: npm 9.6.7
OS: win32 x64
```

#### Configuração do projeto

* Acesse o diretório do cliente recém clonado e instale todos os pacotes necessários
```
cd lol/client

npm install
```
* Execute o front end utilizando angular
```
ng serve
```
* Nota: Caso ocorra um erro dizendo a execução de scripts é proibida no sistema, abra um terminal powershell como administrador e execute o código
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
```
* Execute novamente o comando e acesse a URL http://localhost:4200/
```
ng serve
Initial chunk files | Names         |  Raw size   
main.js             | main          | 358.42 kB | 
styles.css          | styles        | 271.13 kB |
polyfills.js        | polyfills     |  86.30 kB |
scripts.js          | scripts       |  77.90 kB |

                    | Initial total | 793.75 kB

Application bundle generation complete. [6.628 seconds]

Watch mode enabled. Watching for file changes...
  ➜  Local:   http://localhost:4200/
  ➜  press h + enter to show help
```

* Agora para a configuração do server, acesse diretório server e abra outra instância do VS Code
```
cd lol/server
code .

```
* Acesse as extensões do VS Code e instale as extensões
    * Extension Pack for Java
    * Spring Boot Dashboard

* Antes de executar o projeto será necessário a criação da database lol no PostgreSQL. Para auxiliar nessa execução adicione a pasta contendo o binário do PostgreSQL ao PATH das variáveis de ambiente do seu sistema
    * [Tutorial](https://www.youtube.com/watch?v=awzSkaDoA38)

* Feito isso acesse o seu banco de dados PostgreSQL no terminal

```
psql -U postgres
Password for user postgres:

psql (16.4)
WARNING: Console code page (850) differs from Windows code page (1252)
         8-bit characters might not work correctly. See psql reference
         page "Notes for Windows users" for details.
Type "help" for help.
```

* Faça a criação da database lol
```
postgres=# CREATE DATABASE lol;
CREATE DATABASE
```

* Após esses passos faça a execução do projeto do server acessando a extensão do Spring Boot Dashboard no VS Code, vá em APPS, clique em lol e depois no botão de play. Aguarde a execução e acesse a aplicação Web em http://localhost:4200/