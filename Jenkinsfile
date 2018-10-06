def tasks = [:]

tasks["task_1"] = {
  stage ("task_1"){    
    node('LOCAL-S1') {  
        sh 'echo $NODE_NAME'
    }
  }
}
tasks["task_2"] = {
  stage ("task_2"){    
    node('LOCAL-S2') {  
        sh 'echo $NODE_NAME'
    }
  }
}

pipeline {
  stages {
    parallel tasks
  }
}

