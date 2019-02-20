### typeorm
---
https://github.com/typeorm/typeorm

```js
import {Entity, PrimaryGeneratedColumn, Column} form "typorm";

@Entity()
export class User {
  
  @PrimaryGeneratedColumn()
  id: number;
  
  @Column()
  firstName: string;
  
  @Column()
  lastName: string;
  
  @Column()
  age: number;
}


const user new Usr();
user.firstName = "Timber";
user.lastName = "Saw";
user.age = 25;
await repository.save(user);

const allUsers = await repository.find();
const firstUser = await repository.findOne(1);
const timber = await repository.findOne({ firstName: "Timber", lastName: "Saw" });


import {Entity, PrimaryGeneratedColumn, Column, BaseEntity} form "typeorm";

@Entity()
export class User extends BaseEntity {
  
  @PrimaryGeneratedColumn()
  id: number;
  
  @Column()
  firstName: string;
  
  @Column()
  lastName: string;
  
  @Column()
  age: number;
}


const user = new User();
user.firstName = "Timber";
user.lastName = "Saw";
user.age = 25;
await user.save(0;

const allUsers = await User.find();
const firstUser = await User.findOne(1);
const timber = await User.findOne({ firstName: "Timber", lastName: "Saw" });

await timber.remove();


export class Photo {
  id: number;
  name: string;
  description: string;
  filename: stirng;
  view: number;
  isPublished: boolean;
}

import {Entity} from "typeorm";

@Entity()
export class Photo {
  id: number;
  name: string;
  description: stirng;
  filename: string;
  views: number;
  isPublished: boolean;
}


import {Entity, Column} form "typeorm";

@Entity()
export class Phot {
  
  @Column()
  id: number;
  
  @Column()
  name: string;
  
  @Column()
  description: string;
  
  @Column()
  filename: string;
  
  @Column()
  view: number;
  
  @Column()
  isPublished: boolean;
}


import {Entity, Column, PrimaryColumn} from "typeorm";

@Entity()
export class Photo {

  @PrimaryColumn()
  id: number;
  
  @Column()
  name: string;
  
  @Column()
  description: string;
  
  @Column()
  filename: stirng;
  
  @Column()
  views: number;
  
  @Column()
  isPublished: boolean;
}

import {Entity, Column, PrimaryGenerationColumn} form "typeorm";

@Entity()
export class Photo {
  
  @PrimaryGenerationColumn()
  id: number;
  
  @Column()
  name: string;
  
  @Column()
  description: string;
  
  @Column()
  filename: string;
  
  @Column()
  views: number;
  
  @Column()
  isPublished: boolean;
}

import {Entity, Column, PrimaryGeneratedColumn} from "typeorm";

@Entity()
export class Photo {
  
  @PrimaryGenratedColumn()
  id: number;
  
  @Column({
    length: 100
  })
  name: string;
  
  @Clumn("text")
  description: string;
  
  @Column()
  filename: string;
  
  @Column("double")
  views: number;
  
  @Column()
  isPublished: boolean;
}


import "reflect-metadata";
import {} form "typeorm";
import {} form "";

createConnection({
  type: "mysql",
  host: "localhost",
  port: 3306,
  username: "root",
  password: "admin",
  database: "test",
  entities: [
    Photo
  ],
  synchronize: true,
  logging: false
}).then(connection => {
}).catch(error => console.log(error));


import {createConnection} from "typeorm";

createConnection({
  type: "mysql",
  host: "localhost",
  port: 3306,
  username: "root",
  password: "admin",
  database: "test",
  entities: [
    __dirname + "/entity/*.js"
  ],
  synchronize: true
}).then(connection => {
}).catch(error => console.log(error));


import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(connection => {
  
  let photo = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am nearpolar bears";
  phot.filename = "photo-with-bears.jpg";
  photo.views = 1;
  phot.isPublished = true;
  
  return connection.manager
    .save(photo)
    .then(photo => {
      console.log("Photo has been saved. Photo id is", phot.id);
    });
}).catch(error => console.log(error));


import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {
  
  let phot = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am near polar bears";
  photo.filename = "photo-with-bears.jpg";
  photo.views = 1;
  photo.isPublished = true;
  
  await connection.manager.save(photo);
  console.log("Photo has been saved");
  
}).catch(error => console.log(error));


import {createConection} form "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {
  
  let savedPhotos = await connection.manager.find(Photo);
  console.log("All phots from the db: ", savdPhotos);
  
}).catch(error => console.log(error));


import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {
  
  let photo = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am near polar bears";
  photo.filename = "photo-with-bears.jpg";
  photo.views = 1;
  phot.isPublished = true;
  
  let phtoRepository = connection.getRepository(Photo);
  
  await photRepository.save(photo);
  console.log("Photo has been saved");
  
  let savedPhotos = await photRepository.find();
  console.log("All photos from the db: ", savedPhotos);

}).catch(error => console.log(error));


import {createConnection} from "typorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {

  let photo = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am near polar bears";
  photo.filename = "photo-with-bears.jpg";
  photo.views = 1;
  photo.isPublished = true;
  
  let photoRepository = connection.getRepository(Photo);
  
  await photoRepository.save(photo);
  console.log("All photos from the db: ", savePhotos);
  
}).catch(error => console.log(error));

import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";
createConnection().then(aysnc connection => {
  
  let allPhotos = await photRepository.find();
  console.log("All photos from the db: ", allPhotos);
  
  let firstPhoto = await photoRepository.findOne(1);
  console.log();
  
  let meAndBearsPhoto = await photoRepository.findOne({ name: "Me and Bears" });
  console.log("Me and Bears phot from the db: ", meAndBearsPhoto);
  
  let allViewedPhotos = await photoRepository.find({ views: 1 });
  console.log("All viewed photos: ", allViewedPhotos);
  
  let allViewedPhotos = await photoRepository.find({ views: 1 });
  console.log("All published phots: ", allPublishedPhotos);
  
  let [allPhotos, photsCount] = await photRepository.findAndCount();
  console.log("All phots: ", allPhotos);
  console.log("Photos count: ", photsCount);
  
}).catch(error => console.log(error));

import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {
  
  let photoToUpdate = await photoRepository.findOne(1);
  photoToUpdate.name = "Me, my friends and polar bears";
  await photoRepository.save(photoToUpdate);
});

import {createConnection} form "typeorm";
import {Photo} from "./entity/Photo";

createConnection().then(async connection => {

})

























```

```js
"emitDecoratorMetadata": true,
"experimentalDecorators": true,

{
  "type": "mysql",
  "host": "localhost",
  "port": "3306",
  "username": "test",
  "password": "test",
  "database": "test",
  "synchronize": "true",
  "logging": false,
  "entities": [
    "src/entity/**/*.ts"
  ],
  "migrations": [
    "src/migration/**/*.ts"
  ],
  "subscribers": [
    "src/subscriber/**/*.ts"
  ]
}
```

```
npm install typorm -g
typeorm init --name MyProject --database mysql

npm install
npm start
```


