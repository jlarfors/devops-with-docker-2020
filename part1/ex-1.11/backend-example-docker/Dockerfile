FROM node:10.20

COPY . .

RUN npm install

EXPOSE 8000

ENV FRONT_URL=http://localhost:5000

ENTRYPOINT ["npm"]
CMD ["start"]
