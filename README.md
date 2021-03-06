## SPA Chat app (web app) that works on desktop/mobile UI

Desktop UI<br/>
<img src="https://github.com/lechatthecat/JavaChatSpa/blob/master/chat_picture.png" width="50%"><br/>
Mobile UI<br/>
<img src="https://github.com/lechatthecat/JavaChatSpa/blob/master/mobile_chat.png" width="50%">

There is "sign in" in the app.
This app is using only Vue.js. jQuery is NOT included.

non-login users cannot comment in boards and cannot create boards.
login users can comment and create boards from the bottom of side menu.

## Cloning the project

```
$ git clone https://github.com/lechatthecat/JavaChatSpa.git
$ cd JavaChatSpa
```

## Prepare the DB

At first, install postgresql, do the initial setup and login into it.

Create a database "chatboard" with a user "chatadmin".

```
postgres=# CREATE DATABASE chatboard;
postgres=# CREATE USER chatadmin WITH PASSWORD 'chatadmin';
postgres=# \q
```

Then run the script:

```
$ psql -U chatadmin -d chatboard -a -f ./src\main\resources\sql\tables.sql -h localhost
```

Then set your gmail address to enable email verication functionality in application.properties.

```
spring.mail.username = ###### Gmail address that can be used for sending email verification ######
spring.mail.password = ###### Gmail address's app password that can be used for sending email verification ######
```

Now install npm packages.

```
$ npm install
$ npm run watch
(or "$ npm run build" or "$ npm run production")
(Use "$ npm run production" for production.)
```

And complete other necessary information in the application.properties.
Now the app should work. If you are using vscode, press on F5 in vscode after wring launch.json as follows:

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "java",
            "name": "Debug (Launch)-JavachatApplication<javachat>",
            "request": "launch",
            "mainClass": "com.javachat.JavachatApplication",
            "projectName": "javachat"
        }
    ]
}
```
