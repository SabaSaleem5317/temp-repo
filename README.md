# Cynable Project Setup
## 1. Folder Structure  
   - Create following folder structure and add a .env fil in each folder:  
     &nbsp;&nbsp;Cynable/  
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cynable-fe  
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cynable-be  
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cynable-infra  
   - Add a .env file in each folder (ask someone for .env file content)

## 2. Configuration
   - Get your local IP address by running following command:  
      &nbsp;&nbsp;&nbsp;`ifconfig -s e0`  
   - Update your .env files:
     - In cynable-infra .env file -> set `HOSTNAME` to your IP
     - In cynable-be .env file -> set `AUTH_SERVER_URL` and `CYNABLE_URL` to your IP

## 3. Start Infrastructure  
   -  Run docker compose inside infra folder:  
      &nbsp;&nbsp;&nbsp; `docker compose up -d`

## 4. Backend Setup  
   - Navigate to BE folder and run following commands:  
     - Install dependencies `pnpm install`
     - Run db migrations `pnpm migration:run`
     - Seed data  
       &nbsp;&nbsp;&nbsp;`pnpm script ./src/scripts/populate-locations`  
       &nbsp;&nbsp;&nbsp;`pnpm script ./src/scripts/user-role-permission-script.ts`
     - Start the server `pnpm start:dev`  

## 5. Update user table  
   - Update the keycloak_id column in user table with the actual Keycloak user ID.

     


Access both frontend and backend using your IP. You'are all set!

     
    
    
   
