FROM node:20-alpine
# Create non-root user
RUN addgroup -S app && adduser -S app -G app
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN chown -R app:app /app
USER app
EXPOSE 3000
CMD ["node", "index.js"]
