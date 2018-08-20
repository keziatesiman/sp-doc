# ANTD Dashboard

### Author
* Zuiidea [http://antd-admin.zuiidea.com](http://antd-admin.zuiidea.com)
* Modified by Kezia Irene


## Setup and Installation

First of, you have to make sure that you have installed nodejs to your computer. After that, you can download the code to your computer then run these code in your bash: 

* `npm install` - Install dependencies for server.
* `npm run client-install` - Install dependencies for client.
* `npm run dev` - Run the client & server with concurrently.
* `npm run server` - Run the Express server only.
* `npm run client` - Run the React client only.
* Server runs on http://localhost:1339 and client on http://localhost:8000


## Project Directory
``` 
├── server.js               # server side / back end
└── / client /              # client side / front end
    ├── / dist /            # project output directory 
    ├── / mock /            # data mock 
    ├── / public /          # public documents, compile-time copy to the dist directory 
    ├── / src /             # project source directory 
    │ ├── / components /    # UI UI components and associated methods 
    │ ├── / Layouts /       # global components 
    │ │ └── app.js        # page inlet 
    │ │ └── The index.js      # entry file 
    │ ├── / Models /        # data model 
    │ ├── / pages /         # page components 
    │ │ └── document.ejs # HTML template 
    │ ├── / Services /      # data interface
    ├── │ / Themes /        # Item Style 
    │ │ ├── default.less # global style 
    │ │ └── vars.less     # Global Style Variables 
    │ ├── / utils /         # utility function 
    │ │ ├── config. JS     # project General configuration 
    │ │ ├── menu.js       # menu and bread crumbs configuration 
    │ │ ├── the config.js     # project General configuration 
    │ │ ├── request.js    # asynchronous request function (Axios) 
    │ │ └─ theme.js ─      # project needs to be used in the js style variable 
    ├── package.json      # project information 
    ├── .eslintrc         # Eslint configuration 
    └── .umirc.js         # umi configuration
    .umirc.mock.js └──    # mock configuration 
    └── .theme.config.js # theme less build configuration
```    

## Instance

A request from the client to the server response and rendering process

The overall layout file of the front-end page is client/src/pages. Then using axios module [https://github.com/axios/axios](https://github.com/axios/axios) to connect to the back-end in server.js. The back-end server is connected to database 
```bash
    var connection = mysql.createConnection({
    //properties...
    host: 'localhost',
    user: 'root',
    password: '',
    database: 'sampleDB',
    multipleStatements: true
    });
```

The database now is using localhost, you can change the directory by changing the host. 

