# 💻 HEROKU COMMANDS 

### 1. STOP A RUNNING DYNO
- Maintenance mode doesn not shut your dyno , it only stops traffic acces to you dyno.

    `heroku ps:stop <dynotype-web/worker> -a <app_name> `

---

### 2. SCALE YOUR DYNO
- You could mention worker dyno or web dyno type or both when using this command. Here i used both.

    `heroku ps:scale web=0 worker=1 -a <app_name> ` 
 
 ---
 
 ### 3. SSH INTO YOUR RUNNING DYNO.
    
    `heroku ps:exec --dyno=web.2 -a <app_name>`
 
 - Use the `--status` flag to check the status of the Exec connection.
 
    `heroku ps:exec --status <app_name>`
 
 ---
 
 ### 4. PORT FORWARDING
    
    `heroku ps:forward 9090 -a <app_name>`
 
 ---
 
 ### 5. Remote debugging
 - For Node.js, you must add the --inspect=9090 to the node command that starts your app. For example, your Procfile might look like this:
    
    `web: node --inspect=9090 index.js`
 
 - After you change your Procfile and redeploy your app, you can start port forwarding with the Heroku Exec client:
   
    `heroku ps:forward 9090 -a <app_name>`
 
 ---
 
 ### 6. INSTALL A BUILDPACK FROM THE TERMINAL
 -  Here we're installing the puppeteer buildpack which I tested using Nodejs.
    
    `heroku buildpacks:add jontewks/puppeteer -a <app_name>`

---
