# CustomerManagementServer

Generate Crud Restful Web Service and Angular JS Client in minitues using Sails.JS and https://github.com/jlmonteagudo/generator-angular-crud

a [Sails](http://sailsjs.org) application

1.) Sails Server

    sudo brew install node
    npm -g install sails

    sails new CustomerManagementServer
    cd CustomerManagementServer/
    npm install lodash --save

    update config/models to enable the following parameter: migrate: 'alter'
    update config/cors to set allRoutes: true and origin: '*'

    sails generate api Customer

    update Properties of Customer Model

      module.exports = {

        attributes: {
          name: "string",
          address: "string",
          state: "string",
          country: "string"
        }
      };

    Start Server
    276  sails lift

    http://localhost:1337/customer

2.) AngularJS

    cd CustomerManagementServer/
    mkdir CustomerManagementClient
    cd CustomerManagementClient/

    sudo npm install -g generator-angular-crud
    sudo npm install -g yo
    sudo install -g bower

    sudo yo angular-crud
    sudo npm install
    sudo yo angular-crud:feature Customer
      Add new properties to the angular-formly array properties in src/client/app/feature-name/services/feature-name.form.client.service.js
      Add new columns for the new properties in the HTML table in src/client/app/feature-name/views/list.html

    gulp serve-dev
    http://localhost:3000/



