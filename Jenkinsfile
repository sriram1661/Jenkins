pipeline
{
  agent any;
  parameters
  {
    choice(name: 'VERSION', choices: ['1.0.0','1.0.1','1.0.2'], description: 'List of versions')
    booleanParam(name: 'ExecuteTest', defaultValue: true, description: '')
  }
  stages
  {
    stage("Build"){
      steps{
        echo "Building"
      }
    }
    stage("Test"){
      when{
        expression{
          params.ExecuteTest
        }
      }
      steps{
        echo "Testing"
      }
    }
    stage("Deploy"){
//       when{
//         expression{
//           BRANCH_NAME == "master"
//         }
//       }
      steps{
        echo "Deploying ${params.VERSION}"
      }
    }
  }
}
