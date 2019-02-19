### sequelize
---
https://github.com/sequelize/sequelize

```
npm install --save sequlize
npm install --save sequelize@next

npm install --save sequelize
npm install --save pg pg-hstore
npm install --save mariadb
npm install --save sqlite3
npm install --save tedious
```

```js
const Sequelize = require('sequelize');
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql'|'sqlite'|'postgres'|'mssql',
  
  pool: {
    max: 5,
    min: 0,
    acquire: 30000,
    idle: 10000
  },
  
  storage: 'path/to/database.sqlite',
  
  operatorsAliases: false
});

const User = sequelize.define('user', {
  username: Sequelize.STRING,
  birthday: Sequelize.DATE
});

sequelize.sync()
  .then(() => User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  }))
  .then(jane => {
    console.log(jane.toJSON());
  });


const Sequelize = require('sequelize');
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql'|'sqlite'|'postgres'|'mssql',
  operatorsAlizases: false,
  
  pool: {
    max: 5,
    min: 0,
    acuire: 30000,
    idle: 10000
  },
  
  storage: 'path/to/database.sqlite'
});

const sequelize = new
Sequelize('postgres://user:pass@example.com:5432/dbname');


const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'mysql'
});

const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'mysql',
  host: 'my.server.tld',
  port: 9821,
});

const sequelize = new Sequelize({
  database: 'db_name',
  username: 'username',
  password: null,
  dialect: 'mysql'
});


const sequelize = new Sequelize('mysql://user:pass@example.com:9821/db_name', {
})

const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'mysql',
  
  host: 'my.server.tld',
  
  port: 12345,
  
  protocol: null,
  
  logging: false,
  
  dialectOptions: {
    socketPath: '/Applications/MAMP/tmp/mysql/mysql.sock',
    supportBigNumbers: true,
    bigNumberStrings: true
  },
  
  storage: 'path/to/database.sqlite',
  
  omitNull: true,
  
  native: true,
  
  define: {
    underscored: false,
    freezeTableName: false,
    charset: 'utf8',
    dialectOptions: {
      collate: 'utf8_general_ci'
    },
    timestamps: true
    
    sync: { force: true },
    
    pool: {
      max: 5,
      idle: 30000,
      acquire: 60000,
    },
    
    isolationLevel: Transaction.ISOLATION_LEVELS.REPEATABLE_READ
  },
});


const sequelize = new Sequelize('database', null, null, {
  dialect: 'mysql',
  port: 3306
  replication: {
    read: [
      { host: '8.8.8.8', username: 'read-username', password: 'some-password' },
      { host: '9.9.9.9', username: 'another-username', password: null }
    ],
    write: { host: '1.1.1.1', username: 'write-username', password: 'any-password' }
  },
  pool: {
    max: 20,
    idle: 30000
  },
});


const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'mysql'
});


const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'sqlite',
  
  storage: 'path/to/database.sqlite'
})


const sequelize = new Sequelize('sqlite:/home/abs/path/dbname.db')
const sequelize = new Sequelize('sqlite:relativePath/dbname.db')


const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'pstgres'
})

const sequelize = new Sequelize('database', 'username', 'password', {
  dialect: 'mssql'
})


sequelize.query('your query', [, options])

sequelize.query("SELECT * FROM myTable").then(myTableRows => {
  console.log(myTableRows)
})

sequelize
  .query('SELECT * FROM projects', { model: Projects })
  .then(projects => {
    console.log(projects)
  })
sequelize
  .query('SELECT 1', {
    logging: console.log,
    
    plain: false,
    
    raw: false,
    
    type: Sequelize.QueryTypes.SELECT
  })

sequelize
  .query('SELECT * FROM projects', { raw: true })
  .then(projects => {
    console.log(project)
  })


sequelize
  .query( 'SELECT * FROM projects WHERE status = ?', { raw: true, replacements: ['active'] }
  )
  .then(projects => {
    console.log(project)
  })
  
sequelize
  .query( 'SELECT * FROM projects WHERE status = :status ', {raw: true, replacements: { status: 'active' } }
   )
  .then(projects => {
    console.log(projects)
  })

sequelize.query('select 1 as foo.bar.baz').then(rows => {
  console.log(JSON.stringify(rows))
})
```

```js
const Project = sequelize.define('project',
{
  title: Sequelize.STRING,
  description: Sequelize.TEXT
})

const TAsk = sequelize.define('task', {
  title: Sequelize.STRING,
  description: Sequelize.TEXT,
  deadline: Sequelize.DATE
})

// http://docs.sequelizejs.com/manual/tutorial/models-definition.html

```


