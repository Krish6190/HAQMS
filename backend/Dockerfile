FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Install deps (including dev deps for Prisma during build/runtime)
COPY package*.json ./
RUN npm install --no-audit --no-fund

# Copy source
COPY prisma ./prisma
COPY src ./src
COPY .env ./
COPY prisma/schema.prisma ./prisma/schema.prisma
COPY run.sh ./run.sh

RUN chmod +x /usr/src/app/run.sh

EXPOSE 5000

CMD ["./run.sh"]
