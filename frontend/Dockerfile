# Use uma imagem base do Node.js
FROM node:18-alpine

# Defina o diretório de trabalho no container
WORKDIR /app

# Copie os arquivos de configuração do projeto para o diretório de trabalho
COPY package*.json ./

# Instale as dependências do projeto
RUN npm install --force 
# Run npm audit fix --force 

# Copie todo o código do projeto para o diretório de trabalho
COPY . .

# Exponha a porta em que o servidor de desenvolvimento será executado
EXPOSE 3000

# Comando para iniciar o servidor de desenvolvimento
CMD ["npm", "dev"]
