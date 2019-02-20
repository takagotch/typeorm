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


