# TXON-task-3

HTML code:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo App</title>
    <link rel="stylesheet" href="style4.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg==" crossorigin="anonymous" referrerpolicy="no-referrer" />

</head>
<body>
    <div class="container">
        <div id="newtask">
            <input type="text" id="taskinfo" placeholder="Task to do ...">
            <button id="add">Add</button>
        </div>
        <div id="tasklist"></div>
    </div>

    <script src="script.js"></script>


    
</body>
</html>


CSS code:
index.html

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
}

body{
    display: flex;
    height: 100vh;
    justify-content: center;
    align-items: center;
    background-color: #7C4DFF;
}
.container{
    width: 40%;
    min-width: 350px;
    background-color: white;
    max-height: 100%;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0,0,0,0.5);
}

#newtask{
    position: relative;
    padding: 30px 20px;
    display: flex;
    justify-content: space-between;
}

#taskinfo{
    width: 75%;
    height: 35px;
    border: 2px solid #d1d3d8;
    border-radius: 6px;
    color: #111115;
    font-weight: 400;
    padding-left: 5px;
}
#taskinfo:focus{
    outline: none;
    border-color: #0d75ec;
}

#add{
    width: 20%;
    height: 35px;
    border-radius:5px;
    font-weight: 500;
    background-color: #7C4DFF;
    border: none;
    color: white;
    cursor: pointer;
    outline: none;
    border: none;
}
#tasklist{
    margin-bottom: 9px;
    padding: 10px 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
}

.task{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #c5e1e6;
    height: 45px;
    margin-bottom: 9px;
    padding: 5px 10px;
    cursor: pointer;
    width: 100%;
    border-radius: 5px;
    border: 1px solid #939697;
}
.del{
    color:#d11a2a;
    border: none;
    background: none;
    cursor: pointer;
    outline: none;
   
}


javascript:
let todoele = document.getElementById("taskinfo")
let tasklist = document.getElementById("tasklist")

document.getElementById("add").onclick =function(){
    if(todoele.value.length==0){
        alert("Enter a task details")
    }
    else{
        tasklist.innerHTML = tasklist.innerHTML+`    
        <div class="task"> 
            <span id="work">${todoele.value}</span>
            <button class="del"><i class="fa fa-trash"></i></button>
        </div>`  
        let alltasks = document.querySelectorAll('.del')
        for(i=0;i<alltasks.length;i++){
                alltasks[i].onclick = function(){
                    console.log(this)
                    console.log(this.parentNode)
                this.parentNode.remove()
            }
        }
        todoele.value=""
    }
}
