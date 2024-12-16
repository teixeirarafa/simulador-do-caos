FROM node:20.9.0
WORKDIR /app
COPY package*.json ./
RUN npm install
RUN apt update && apt install stress --yes
COPY . .
RUN npm run compile
#HEALTHCHECK --interval=30s --timeout=30s --start-period=30s --retries=3 CMD [ "curl", "-f", "http://localhost:3000/helth" ]	
EXPOSE 3000
CMD ["npm", "start"]
