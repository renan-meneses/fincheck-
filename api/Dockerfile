# Use uma imagem base do Node.js
FROM node:18-alpine

# Configura o diretório de trabalho dentro do contêiner
WORKDIR /usr/src/app

# Define variáveis de ambiente
ENV DATABASE_URL="postgresql://postgres:postgres@localhost:5432/db?schema=public" \
    JWT_SECRET="fincheckapi" \
    RESET_PASSWORD_JWT_SECRET="resetpasswordfincheckapi" \
    FRONTEND_URL="http://localhost:5173" \
    EMAIL_USER="email@example.com" \
    EMAIL_PASSWORD="emailexamplepassword"

# Copia os arquivos de dependências (package.json e package-lock.json ou yarn.lock)
COPY package*.json ./

# Instala as dependências
RUN npm install --force 
# Run npm audit fix

# Copia o restante do código para o contêiner
COPY . ./

# Gera os arquivos do Prisma
# RUN npx prisma migrate dev

# Expõe a porta usada pela aplicação NestJS
EXPOSE 3000

# Define o comando para iniciar a aplicação
CMD ["npm", "run", "start:dev"]
