
## passo 1 gerar o build
./mvnw package && java -jar target/validarCpf.jar
mvnw.cmd package && java -jar target/validarCpf.jar

## Documentação jar Dockerfile java
https://spring.io/guides/gs/spring-boot-docker/

## passo 2 - gerar o build do Dockerfile
docker build -t pdalston/validador-cpf-turma-devops -f Dockerfile .

## passo 3 - gerar e startar a imagem
docker run -d -p 8081:8080 --name validador-cpf-turma-devops pdalston/validador-cpf-turma-devops

## o primeiro é porta de saída que acessamos o docker
## o segundo é a porta que roda a aplicação dentro do docker
8081:8080 

## Para parar o seriviço rodar
docker stop validador-cpf-turma-devops

## Para startar o seriviço rodar
docker start validador-cpf-turma-devops

## Para remover o seriviço rodar
docker rm validador-cpf-turma-devops

## login
docker login

### Criar a tag apontando para o repositório do docker hub ###
docker tag pdalston/validador-cpf-turma-devops hub.docker.com/r/pdalston/validador-cpf-turma-devops

## Fazer o push da imagem para a docker hub ###
docker push pdalston/validador-cpf-turma-devops
"# validador-cpf-java" 
