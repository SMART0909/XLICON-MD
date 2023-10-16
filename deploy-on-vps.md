## Deploy on VPS or PC.
- You need to Install git,ffmpeg,curl,nodejs,yarn with pm2 
   1. Install git ffmpeg curl 
      ```
       sudo apt -y 2349015767177
       sudo apt -y install git ffmpeg curl
      ```
   2. Install nodejs 
      ```
      sudo apt -y remove nodejs
      curl -fsSl https://deb.nodesource.com/setup_lts.x | sudo bash - && sudo apt -y install nodejs
      ```
 
   3. Install yarn
      ```
      curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 
      echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
      sudo apt -y update && sudo apt -y install yarn
      ```

   4. Install pm2
      ```
      sudo yarn global add pm2
      ```

   5. Clone Repo and install required packages
      ```
      git clone https://github.com/salmanytofficial/XLICON-MD
      cd XLICON-MD
      yarn install --network-concurrency 1
      ```

   6. Create an env file for ENV. 
      ```
      touch config.env
      nano config.env
      ```
      copy paste lines below.

      ```
      OWNER_NUMBER="2349015767177"
      MONGODB_URI="mongodb+srv://*************"
      SESSION_ID = "XLICON-MD;;;eyJub2lzZUtleSI6eyJwcml2YXRlIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoia0lpOUJzdEVrZm1kd1Q4R2F3QlI5QVMxRXdKRXNySkR0NUNlQkM5UlFsaz0ifSwicHVibGljIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiNVdrMjdiSDN2SDZWNXVkcVNnWkhlOVZEZG0zVDd4NHA3SlE0VHMxci9EVT0ifX0sInNpZ25lZElkZW50aXR5S2V5Ijp7InByaXZhdGUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJvQ0FSZmF3NGR5YlRWS1lsUVhWK1ZSejVucTNxS1ExaGFnSVFtbWprVUc0PSJ9LCJwdWJsaWMiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJQRnhTYTduWGEyRWdyNk53WkdueGlTbjh2cGhuR2dyRmxqU2FadDB1SXpRPSJ9fSwic2lnbmVkUHJlS2V5Ijp7ImtleVBhaXIiOnsicHJpdmF0ZSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6ImVJd3FDQkw1S0J6TUg1eEtZeng3SFg2dzRPNWlxWm9kMUsxZVJzUUN5VTA9In0sInB1YmxpYyI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6Ilg0U21kZFBPTlJZVDM5V0pLeU0wdG83MUlKRFZqNGNWcHkvYU94ZzVTR2c9In19LCJzaWduYXR1cmUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJGMXdSYkNrSytjRWNGanlWaGlXYnFsdmswOVVMdzdDOG1mbnBZNjE4RnBDbVVhdlZSYXdPUlNOeUk2TDRzRy84alZxNFJsckp1OGh2Nkt0eUxVT3VEdz09In0sImtleUlkIjoxfSwicmVnaXN0cmF0aW9uSWQiOjEyMSwiYWR2U2VjcmV0S2V5IjoiM052Y0oybnhCMzdzVzNSTE91cDdiYTdCOWtrY0ZORmlwQlk4dHNCbW1XOD0iLCJwcm9jZXNzZWRIaXN0b3J5TWVzc2FnZXMiOltdLCJuZXh0UHJlS2V5SWQiOjMxLCJmaXJzdFVudXBsb2FkZWRQcmVLZXlJZCI6MzEsImFjY291bnRTeW5jQ291bnRlciI6MCwiYWNjb3VudFNldHRpbmdzIjp7InVuYXJjaGl2ZUNoYXRzIjpmYWxzZX0sImRldmljZUlkIjoiVFlUajFrSVpRLTZBX3lFSlA2VzhVUSIsInBob25lSWQiOiIxYmNmZDRjMS1iYjgwLTQ0N2EtOTFkOC1lMGNlMGI1MWZkMjIiLCJpZGVudGl0eUlkIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoid000L0ZnVHpnOTJMWVROamVuVmlnakxoU2xVPSJ9LCJyZWdpc3RlcmVkIjpmYWxzZSwiYmFja3VwVG9rZW4iOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJuVTc0SFVTUlBCWkJmdThyOG9nZ084b2h5OEU9In0sInJlZ2lzdHJhdGlvbiI6e30sImFjY291bnQiOnsiZGV0YWlscyI6IkNMYlovdUFFRUxqZ3Rxa0dHQUU9IiwiYWNjb3VudFNpZ25hdHVyZUtleSI6IjhmN1UvQkFvRjNqQlFNcjlqbjFNWlhNRkhsYi8rSmo1MldHbVAyK1hxR0k9IiwiYWNjb3VudFNpZ25hdHVyZSI6IjVQS0Z1T1J1R2xWUVNMMUc1eklqVGRpclE2R0RGeU5EN1NlRzlhdFJmL29ZUGpnOEJRWG1KMUFjN2lUOFNYNUYzUU85YmxUWHQrakVoZVAwY2E3a0NnPT0iLCJkZXZpY2VTaWduYXR1cmUiOiJkc3p2QVU5eWtUTTBiZEFiakZwTkkweDZhRTE3eDNTb2MwbXlWbVdzZkxwRXppNFlCZ2MveFR4T0xiMUxmWVdQUE5nWmM3bUpreTlYZUtYSWpzSnFCUT09In0sIm1lIjp7ImlkIjoiMjM0OTAxNTc2NzE3NzoyQHMud2hhdHNhcHAubmV0In0sInNpZ25hbElkZW50aXRpZXMiOlt7ImlkZW50aWZpZXIiOnsibmFtZSI6IjIzNDkwMTU3NjcxNzc6MkBzLndoYXRzYXBwLm5ldCIsImRldmljZUlkIjowfSwiaWRlbnRpZmllcktleSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IkJmSCsxUHdRS0JkNHdVREsvWTU5VEdWekJSNVcvL2lZK2RsaHBqOXZsNmhpIn19XSwicGxhdGZvcm0iOiJhbmRyb2lkIiwibGFzdEFjY291bnRTeW5jVGltZXN0YW1wIjoxNjk3NDkzMDUyfQ=="
      THUMB_IMAGE = "https://telegra.ph/file/8f6f537cc4103b48f3783.jpg"
      port = 5000
      email = "xxxxxxxxxxxxx@gmail.com"
      global_url = "www.instagram.com/itz_shaikho/_"
      OWNER_NAME = "SMART"
      AUTO_REACTION = false
      FAKE_COUNTRY_CODE = 354
      READ_MESSAGE = false
      PREFIX = .
      WARN_COUNT = 3
      DISABLE_PM = false
      ANTI_BAD_WORD = "fuck"
      LEVEL_UP_MESSAGE= true
      WELCOME_MESSAGE =  "*Hi,* @user \n*Welcome in* @gname \n*Member count* : @count th* *∆kindly introduce yourself with a Pic/vid in Viewonce"
      THEME= GOJO
      WORKTYPE = private
      PACK_INFO = "XLICON MD;WA BOT"
      ANTILINK_VALUES = "chat.whatsapp.com"
      
      ```
      ctrl + o and ctrl + x, To save and exit

   7. start and stop bot

      To start bot ``` npm start ```,
      To stop bot ``` npm stop ```
