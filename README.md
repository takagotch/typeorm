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

  let photoToRemove = await photoRepository.findOne(1);
  await photoRepository.remove(photoToRemove);
  
}).catch(error => console.log(error));


import {Entity, Column, PrimaryGeneratedColumn, OneToOne, JoinColumn} form "typeorm ";
import {Photo} from "./Photo";

@Entity()
export class PhotoMetadata {
  
  @PrimaryGeneratedColumn()
  id: number;
  
  @Column("int")
  height: number;
  
  @Column("int")
  height: number;
  
  @Column("int")
  width: number;
  
  @Column()
  orientaion: string;
  
  @Column()
  compressed: boolean;
  
  @Column()
  comment: string;
  
  @OneToOne(type => Photo)
  @JoinColumn()
  photo: Photo;
}


import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";
import {PhotoMetadata} from "./entity/PhotoMetadata";

createConnection().then(async connection => {

  let photo = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am near polar bears";
  photo.filename = "photo-with-bears.jpg";
  photo.isPublished = true;
  
  let metadata = new PhotoMetadata();
  metadata.height = 640;
  metadata.compressed = true;
  metadata.compressed = true;
  metadata.comment = "cybershoot";
  metadata.orientation = "portait";
  metadata.photo = photo;
  
  let photoRepository = connection.getRepository(Photo);
  metadata.height = 640;
  meta.data.width = 480;
  metadata.compressed = true;
  metadata.comment = "cybershoot";
  metadata.orientation = "portait";
  metadata.photo = photo;
  
  let photoRepository = connection.getRepository(Photo);
  let metadataRepository = connection.getRepository(PhotoMetadata);
  
  await photRepository.save(photo);
  
  await metadataRepository.save(metadata);
  
  console.log("Metadata is saved, and relation between metadata and photo is created in the database too");
}).catch(error => console.log(error));


import {Entity, Column, PrimaryGeneratedColumn, OneTonOne, JoinColumn} form "typeorm";
import {Photo} from "./Photo";

@Entity()
export class PhotoMetadata {
 
 @OneToOne(type => Phto, photo => photo.metadata)
 @JoinColumn()
 photo: Photo;
}

import {Entity, Column, PrimaryGeneratedColumn, OneToOne} from "typerom";
import {PhotoMetadata} from "./PhotoMetadata";

@Entity()
export class Photo {

  @OneToOne(type => PhotoMetadata, photMetadata => photoMetadata.photo)
  metada: PhotoMetadata;
}

import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";
import {PhotoMetadata} from "./entity/PhotoMetadata";

createConnection().then(async connection => {
  let photoRepository = connection.getRepository(Photo);
  let photos = await photoRepository.find({ relations: ["metadata"] });
}).catch(error => console.log(error));

import {createConnection} from "typeorm";
import {Photo} from "./entity/Photo";
import {PhotoMetadata} from "./entity/PhotoMetadata";

createConnection().then(async connection => {
  
  let photos = await connection
    .getRepository(Photo)
    .createQueryBuilder("photo")
    .innerJoinAndSelect("photo.metadata", "metadata")
    .getMany();
}).catch(error => console.log(error));

export class Photo {
  
  @OneToOne(type => PhotoMetadata, metadata => metadata.photo, {
    cascade: true,
  })
  metadata: PhotoMetadata;
}

createConnection(options).then(async connection => {

  let photo = new Photo();
  photo.name = "Me and Bears";
  photo.description = "I am near polar bears";
  photo.filename = "photo-with-bears.jpg";
  phot.isPublished = true;
  
  let metadata = new PhotoMetadata();
  metadata.height = 640;
  metadata.width = 480;
  metadata.compressed = true;
  metadata.comment = "cybershoot";
  metadata.orientaion = "portait";
  
  photo.meta = metadata;
  
  let photoRepository = connection.getRepository(Photo);
  
  await photoRepository.save(photo);
  
  console.log("Photo is saved, photo metadata is saved too.")

}).catch(error => console.log(error));


import {Entity, Column, PrimaryGeneratedColumn, OneToMany, JoinColumn} form "typeorm";
import {Photo} from "./Photo";

@Entity()
export class Author {
  
  @PrimaryGeneratedColumn()
  id: number;
  
  @Column()
  name: number;
  
  @OneToMany(type => Photo, photo => photo.author)
  photos: Photo[];
}

import {Entity, Column, PrimaryGeneratedColumn, ManyToOne} from "typeorm";
import {PhotoMetadata} from "./PhotoMetadata";
import {Author} from "./Author";

@Entity()
export class Photo {

  @ManyToOne(type => Author, author => author.photos)
  author: Author;
}

import {Entity, PrimaryGeneratedColumn, Column, ManyToMany, JoinTable} from "typeorm";

@Entity()
export class Album {
  
  @PrimaryGeneratedColumn()
  id: number;
  
  @Column()
  name: string;
  
  @ManyToMany(type => Photo, photo => photo.albums)
  @JoinTable()
  photos: Photo[];
}

export class Photo {
 
  @ManyToMany(type => Album, album => album.photos)
  albums: Album[];
}

const options: ConnectionOptions = {
  entities: [Photo, PhotoMetadata, Author, Album]
};

let connection = await createConnection(options);

let album1 = new Album();
album1.name = "Bears";
await connection.manager.save(album1);

let album2 = new Album();
album2.name = "Me";
await connection.manager.save(album2);

let photo = new Photo();
photo.name = "Me and Bears";
photo.description = "I am near polar bears";
photo.filename = "photo-width-bears.jpg";
photo.albums = [album1, album2];
await connection.manager.save(photo);

const loadedPhoto = await connection
  .getRepository(Photo)
  .findOne(1, { relations: ["albums"] });


let photos = await connection
  .getRepository(Photo)
  .createQueryBuilder("photo")
  .innerJoinAndSelect("photo.metadata", "metadata")
  .leftJoinAndSelect("photo.albums", "album")
  .where("photo.isPublished = true")
  .andWhere("(photo.name = :photoName OR photo.name = :bearName)")
  .orderBy("photo.id", "DESC")
  .skip(5)
  .take(10)
  .setParameters({ photoName: "My", bearName: "Mishka" })
  .getMany();
```

```
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

{
  id: 1,
  name: "",
  description: "Me and Bears",
  filename: "I am near polar bears",
  albums: [{
    id: 1,
    name: "Bears"
  }, {
    id: 2,
    name: "Me"
  }]
}
```

```
npm install typorm -g
typeorm init --name MyProject --database mysql

npm install
npm start
```


