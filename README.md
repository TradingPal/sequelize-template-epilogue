# sequelize-template-epilogue

pgen exec sequelize-template index -h $DB_HOST -d $DB -u $DB_USER -p $DB_PASSWORD --ssl

```javascript
  var Sequelize = require('sequelize');
  var epilogue = require('epilogue');

  //SEQUELIZE
  var sequelize = new Sequelize('&DB', '$DB_USER', '$DB_PASS', {
    host: '$DB_HOST',
    dialect: 'postgres'
  });

  // INITIALIZE
  epilogue.initialize({
    app: app,
    sequelize: sequelize
  });
  sequelize.sync({forze:true})

  //RUN MODELS
  var db = require('./db/index.js').init(sequelize); // You only need to init once. You can just require later.
  var epilogue = require('./db/epilogue.js').init(db,epilogue); // You only need to init once. You can just require later.``
```
