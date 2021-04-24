# Run Distributed MinIO on Docker Compose
1. Prerequisites
Familiarity with [Docker Compose](https://docs.docker.com/compose/overview/).
Docker installed on your machine. Download the relevant installer from [here](https://www.docker.com/community-edition#/download).
## environment
```env
 MINIO_ROOT_USER: minio
 MINIO_ROOT_PASSWORD: minio123
```
## Init on port 9000
```bash
_>npm run up
```
#### OR
```bash
_>docker-compose build && docker-compose up -d
```

## Remove
```bash
_>npm run down
```
#### OR
```bash
_> docker-compose down
```
## Start
```bash
_>npm run start
```
#### OR
```bash
_>docker-compose start
```
## Stop
```bash
_>npm run stop
```
#### OR
```bash
_>docker-compose stop
```

## Restart
```bash
_>npm run restart
```
#### OR
```bash
_>docker-compose restart
```
## Example
```js
import { Module } from '@nestjs/common';
import { NestMinioClientController } from './nest-minio-client.controller';
import { NestMinioModule } from '../nest-minio.module';

@Module({
  controllers: [NestMinioClientController],
  imports: [
    NestMinioModule.register({
      endPoint: 'play.min.io',
      bucket: 'sajadweb',
      port: 9000,
      useSSL: true,
      accessKey: 'Q3AM3UQ867SPQQA43P2F',
      secretKey: 'zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG',
    }),
  ],
})
export class NestMinioClientModule {}

});
```
## Author
Sajjad Mohhamadi Nejad < daram3118@gmail.com >
