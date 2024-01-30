const fs =require('fs').promises;
const express = require("express");
const app = express();
const port = 4000;
const path=require('path')


//creating new folder
fs.mkdir('./newfile',(err)=>{
    if (err) throw err
    console.log('New directory created')
    
})

//creating new text file
/* const {format}=require('date-fns')
    console.log(format(new Date(),'dd-MM-yyyy\tHH:mm:ss')) */
const datetime= `date and time:${Date()}`
      fs.writeFile(path.join(__dirname,'newfile','date-time.txt'),datetime, (err)=>{
        if (err) throw err
    console.log('New text file created')
    }
    )
    app.get('/newfile', function (req, res) {
        res.send(datetime)
      })
      
      app.listen(4000)
   
    
//uncaught error
process.on('uncaughtException',err=>{
    console.error(`There was an uncaught error: ${err}`)
})



