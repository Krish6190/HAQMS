FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Install deps (including dev deps for Prisma during build/runtime)
COPY backend/package*.json ./
RUN npm install --no-audit --no-fund

# Copy source
COPY backend/prisma ./prisma
COPY backend/src ./src
COPY backend/run.sh ./run.sh

RUN chmod +x /usr/src/app/run.sh

EXPOSE 5000

CMD ["./run.sh"]
