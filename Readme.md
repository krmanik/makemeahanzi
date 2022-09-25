# Install and run the makemeahanzi tool

1. Install meteor (on Ubuntu)
   ```
   sudo apt install nodejs
   npm install -g meteor
   ```
   Or
   ```
   curl https://install.meteor.com/ | sh
   ```
   
   For other system view [www.meteor.com](https://www.meteor.com/developers/install)

2. Install and run `mongodb` service, (`mongodump` / `mongorestore` required for the projects)
   - https://www.mongodb.com/docs/database-tools/installation/installation/
   - https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/

3. Running meteor will give errors `error: certificate has expired`, so run meteor with `NODE_TLS_REJECT_UNAUTHORIZED=0` flag
   ```
   export NODE_TLS_REJECT_UNAUTHORIZED=0; meteor run
   ```
4. Now open localhost in browser to use the app
   ```
   http://localhost:3000
   ```
5. Open dev tools and run following to reload the database from the backup in the repository.
   ```
   Meteor.call('restore');
   ```
6. Use `A` and `D` keys step back and forth between characters, while `shift-A` and `shift-D` step back and forth between incomplete characters. The `W` and `S` keys step up and down between different `stages`.

7. Save the generated strokes order
   ```
   Meteor.call('export');
   // Check the Meteor logs and wait for dictionary.txt and graphics.txt to be ready
   Meteor.call('exportSVGs');
   // Check the Meteor logs and wait for .svgs to be ready
   ```
8. On Windows, WSL can be used.