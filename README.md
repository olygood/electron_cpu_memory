# program for % cpu visualization  
## start program  
## clone repository  
## npm install  
## npm start  


##application cpu  
npm install electron -g  
npm install create-electron-app -g

create-electron-app cpu-app  
il va créer dans votre dossier un dossier/cpu-app  
avec node_modules / src/ package.json/ index.html/index.css/index.js  

###problème de base  
>quand j'utilis var os 	= require('os-utils');
 
 os.cpuUsage(function(v){
    console.log('cpu usage (%) ' + v*100)
  })
  cela indique le % cpu dans la console du programme 
  mais pas dans celle du navigateur
  ###résolution il faut  
  ipc qui est un multi affichage processus multiple
vu que le navigateur est sur un autre processus et que le index.js et lui aussi sur un autre
il faut ipc pour render le processus sur le navigateur
avec :  
 mainWindow.webContents.send('cpu', v*100);
 puis l'activer dans const createWindow =(){
       webPreferences:{
      nodeIntegration: true
    }
 }
 puis faire un <scipt></scrip> dans le html  
 
