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
tasks["task_3"] = {
  stage ("task_3"){    
    node('aws-S1') {  
        sh 'echo $NODE_NAME'
    }
  }
}

parallel tasks

