# Pipeline-de-Criação-e-Execução-de-uma-Imagem-Docker

Vou criar um artigo detalhado sobre a criação e execução de uma imagem Docker com um pipeline. Abaixo, vou dividir o processo em módulos e fornecer exemplos de código.

### Etapa 1: Criar um diretório para o projeto
Comece criando um novo diretório para o seu projeto Docker. Você pode fazer isso no seu sistema local ou em um repositório Git.

### Etapa 2: Criar um arquivo Dockerfile
Dentro do diretório do projeto, crie um arquivo chamado `Dockerfile`. Este arquivo conterá as instruções para construir sua imagem Docker.

### Etapa 3: Escrever o Dockerfile
O `Dockerfile` deve conter as seguintes instruções:

1. **FROM**: Especifique a imagem base que será usada.
2. **ENV**: Declare variáveis de ambiente, se necessário.
3. **RUN**: Execute comandos para instalar dependências.
4. **COPY**: Copie arquivos de código-fonte para o diretório da imagem.
5. **CMD**: Defina os comandos para executar o aplicativo quando o contêiner for iniciado.

Aqui está um exemplo de um `Dockerfile` para um aplicativo Node.js:

```dockerfile
FROM node:16-alpine
WORKDIR /usr/src/app
COPY package.json .
RUN npm install
COPY . .
CMD ["node", "index.js"]
```

### Etapa 4: Construir a imagem Docker
Execute o seguinte comando para construir a imagem Docker (substitua `<nome da imagem>` pelo nome que você deseja dar à sua imagem):

```bash
docker build -t <nome da imagem> .
```

### Etapa 5: Executar o contêiner Docker
Após construir a imagem Docker, você pode executar o aplicativo em um contêiner. Use o seguinte comando para iniciar o contêiner:

```bash
docker run -it --rm <nome da imagem>
```

O contêiner será iniciado e o aplicativo será executado. Você verá a saída do aplicativo no terminal.

## Conclusão
Seguindo essas etapas, você pode criar e implantar facilmente seus aplicativos em contêineres Docker. Lembre-se de adaptar o `Dockerfile` e os comandos conforme necessário para o seu projeto específico.
