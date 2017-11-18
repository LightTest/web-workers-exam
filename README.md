# web-workers-exam
WebWorkers - Examples of usage

Simple Example of WebWorker.

Files:

webworker file --> worker.js
normal javascript file script --> script.js

================

In a script you create new worker:

       var myWorker = new Worker("worker.js");
  
 Next Send a Message (whatever you want):
  
       myWorker.postMessage(message);
       
 A function to receive a message from a worker:
 
   data from a worker are shown in a console and and on the Website
   
      myWorker.onmessage = function(e) {
      
            console.dir(e.data);
            document.getElementById("transfer").innerHTML = e.data;      
      
      }
      
      
 In a worker script you need to create a function for receiving data:
 
        onmessage = function(e) {

          console.log('Message received');
           console.log(e.data);

           postMessage('Transfer Completed');


        }
 
  where you give all data received from a script to a console and of course you sending something back to the script using:
  
         postMessage('Transfer Completed');
       
