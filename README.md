# Nodejs-Application

1.Install Node.js & NPM (if running locally in EC2/VM before Dockerizing)
yum install -y nodejs
yum install -y npm
==============================
Check versions:
node -v
npm -v
================================
2. Create Application Directory
mkdir apps
cd apps
======================================
Initialize Node Project
npm init -y
==============================================
Install Dependencies
npm install express --save
npm install --save-dev mocha
==============================================
Create index.js file
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
=============================================
Update package.json

Edit scripts section:

{
  "name": "apps",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "mocha",
    "build": "echo 'Running Build Script...'"
  },
  "dependencies": {
    "express": "^5.1.0"
  },
  "devDependencies": {
    "mocha": "^11.7.2"
  }
}
==================================================
Create Test Directory
mkdir test
cd test
touch mytest.test.js
===================================

Add a sample Mocha test in test/mytest.test.js
const assert = require('assert');

describe('Sample Test', function() {
  it('should return true', function() {
    assert.strictEqual(true, true);
  });
});

8. Run Tests & Build
npm test
npm run build

9. Run Application
npm start


Visit 👉 http://localhost:3000

==================================================================================================================================================================================
=================================================================================================================================================================================
nodejs application deploy in docker 

insatall nodejs 
 - yum install -y nodejs
install npm 
 - yum install npm 
check the version 
 - npm version 
Build the node js application 
create the directort app
 - mkdir apps
 -cd apps
inizalite the npm 
 - npm init 
  then press the enter 
install nodejs dependences 
- npm install express --save
create index.js file 
vi index.js and write sapmle code 
=============================================
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

=============================================================
run the file 
 - node index.js   
install mocha frame work 
 - npm install --save-dev mocha

go to package.json
vi package.json

{
  "name": "apps",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "mocha",       // edit this line 
    "build": "echo 'Running Build Script'"   // edit this line 
  },
  "author": "",
  "license": "ISC",
  "description": "",
  "dependencies": {
    "express": "^5.1.0"
  },
  "devDependencies": {
    "mocha": "^11.7.2"
  }
}

let check the npm 
 - npm test
we dont have a test directory so we create a test directory 
 - mkdir test 
 - cd test 
inside create file touch mytest.test.js
cd ..
npm test
npm run build
