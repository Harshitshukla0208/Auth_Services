# Welcome to Authentication Service

## Project Setup
- Clone the project on your local
- Execute `npm install` on the same path as of your root directory of the downloaded project
- Create a `.env` file in the root directory and add the following environment variables
    - `PORT=3001`
    - `SALT = authservicesalt`
    - `JWT_KEY = auth`
- Inside the `src/config` folder create a new file `config.json` and then add the following piece of json

```
{
  "development": {
    "username": <YOUR_DB_LOGIN_NAME>,
    "password": <YOUR_DB_PASSWORD>,
    "database": "AUTH_DB_DEV",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}

```
- Once you've added your db config as listed above, go to the src folder from your terminal and execute `npx sequelize db:create` 
and then execute  

`npx sequelize db:migrate`
```


## DB Design
  - Users
  - Roles
  - User_Roles


  
## Tables

### Users -> id, email, password, createdAt, updatedAt
### Roles -> id, role, created_at, updated_at
    Relationship -> One user has a particular set of role.
```
npx sequelize model:generate --name Users --attributes email:String,password:String
```