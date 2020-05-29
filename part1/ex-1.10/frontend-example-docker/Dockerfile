FROM node:10.20

COPY . .

RUN npm install

EXPOSE 5000

ENV API_URL=http://localhost:8000

ENTRYPOINT ["npm"]
CMD ["start"]
